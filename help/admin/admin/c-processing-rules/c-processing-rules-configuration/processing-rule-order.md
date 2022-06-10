---
description: Donde las reglas de procesamiento residen en la canalización de datos general de Analytics.
subtopic: Processing rules
title: Orden de procesamiento
feature: Processing Rules
exl-id: c7143527-017c-4550-b55e-09ea437d7c85
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '506'
ht-degree: 52%

---

# Orden de procesamiento

Para utilizar de forma eficaz las reglas de procesamiento, es esencial comprender cuándo se aplican durante la recopilación de datos.

![Orden de procesamiento](assets/analytics_processing_order.png)

Las siguientes tablas indican los datos que suelen estar disponibles antes y después de aplicar las reglas de procesamiento.

## Antes de las reglas de procesamiento

| Dimensión | Descripción |
|--- |--- |
| [Variables dinámicas](/help/implement/vars/page-vars/dynamic-variables.md) | Variables que se rellenan dinámicamente extrayendo información de encabezados HTTP u otras variables. |
| [AppMeasurement](/help/implement/home.md) | Las funciones y complementos utilizados en las bibliotecas de AppMeasurement se ejecutan en el explorador o en la aplicación cliente. |
| [Implementación de etiquetas](/help/implement/launch/overview.md) | Reglas definidas en la extensión de Adobe Analytics dentro de la recopilación de datos de Adobe Experience Platform. |
| [SDK web de Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/edge/data-collection/adobe-analytics/analytics-overview.html) | Los datos recopilados mediante el SDK web se envían a Adobe Experience Edge y, a continuación, se reenvían al grupo de informes deseado. |
| [Reglas de bots](/help/admin/admin/bot-removal/bot-rules.md) | Permite eliminar el tráfico generado por arañas de web y bots conocidos. |

## Después de las reglas de procesamiento

| Dimensión | Descripción |
|--- |--- |
| Datos agregados por VISTA | Las reglas de procesamiento se aplican antes de VISTA. |
| Número de página de visita | Las reglas de procesamiento solo tienen en cuenta los datos contenidos en la visita actual. El número de página de visita se compila después de aplicar las reglas de procesamiento. |
| La dirección URL limpia se agrega como nombre de página si no está definido | Tras aplicar las reglas de procesamiento y de VISTA, la dirección URL limpia se agrega como nombre de página si no se ha definido ninguno. Dado que esta lógica se produce después de aplicar las reglas de procesamiento, Adobe recomienda agregar una condición para comprobar si el nombre de página está vacío.  Si ejecuta la variable **[!UICONTROL Contenido del sitio]** > **[!UICONTROL Páginas]** Informe y verá valores de URL para los nombres de página; es probable que la variable del nombre de página esté en blanco.  Puede configurar una condición para comprobar si un nombre de página está vacío o para ver si el nombre de página o la dirección URL de la página contiene un valor específico. A continuación, se puede definir el nombre de página según sea necesario. |
| Reglas de procesamiento de canal de marketing | Con las reglas de procesamiento pueden prepararse los datos para su procesamiento con las [reglas de procesamiento del canal de marketing](https://experienceleague.adobe.com/docs/analytics/components/marketing-channels/c-rules.html?lang=es). |
| Búsqueda GEO | Incluye los valores de Estado del visitante y Código postal del visitante. |
| Persistencia de eVars | Las eVars incluidas en alguna visita anterior no persisten en cada visita durante el procesamiento de las reglas. Solo están disponibles las eVars definidas en la visita que se está procesando actualmente. |

## Aplicación de las reglas de procesamiento al copiar visitas usando VISTA

Si tiene una regla VISTA configurada para copiar visitas a otro grupo de informes, las visitas se envían aunque haya reglas de procesamiento definidas en el otro grupo de informes.

Si tiene reglas de procesamiento definidas en el grupo de informes original, es posible que estas reglas se apliquen o no en función de cómo configuraron la regla de VISTA los servicios de ingeniería. Para averiguarlo, puede preguntarle a su especialista en implementaciones si la regla de VISTA copia los valores “pre” o “post” en el grupo de informes original. Si se copia un valor “pre”, las reglas de procesamiento definidas en el grupo de informes original no se aplican. Si se copia el valor “post”, las reglas de procesamiento se aplican antes de que se copie la visita.

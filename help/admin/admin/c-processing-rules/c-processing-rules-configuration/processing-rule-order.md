---
description: Para utilizar de forma eficaz las reglas de procesamiento, es esencial comprender cuándo se aplican durante la recopilación de datos.
subtopic: Processing rules
title: Orden de procesamiento
topic: Admin tools
uuid: cea01d13-dfd5-40f7-8b2f-b6e2fe8354df
translation-type: tm+mt
source-git-commit: 31506d4d3fa26a3012cce2c6a8fdeb7af52c2537
workflow-type: tm+mt
source-wordcount: '505'
ht-degree: 87%

---


# Orden de procesamiento

Para utilizar de forma eficaz las reglas de procesamiento, es esencial comprender cuándo se aplican durante la recopilación de datos.

![](assets/analytics_processing_order_test.png)

Las siguientes tablas indican los datos que suelen estar disponibles antes y después de aplicar las reglas de procesamiento:

## Antes de las reglas de procesamiento

| Dimensión | Descripción |
|--- |--- |
| Búsqueda de variables dinámicas | Las variables se rellenan dinámicamente extrayendo información de los encabezados HTTP u otras variables. Por ejemplo, `s.eVar5="D=c1"` introducirá el valor de prop1 en eVar5. |
| AppMeasurement | Las funciones y los complementos utilizados en AppMeasurement se ejecutan en el explorador o en la aplicación cliente. |
| Gestión de etiquetas | Las reglas definidas en Inicio de Adobe o Administración dinámica de etiquetas se ejecutan tal como están definidas. |
| Reglas de bots | [Las reglas de bots](/help/admin/admin/bot-removal/bot-rules.md) permiten eliminar de un grupo de informes el tráfico generado por arañas de web y bots conocidos. |

## Después de las reglas de procesamiento

| Dimensión | Descripción |
|--- |--- |
| Datos agregados por VISTA | Las reglas de procesamiento se aplican antes de VISTA. |
| Número de página de visita | En general, las reglas de procesamiento solo tienen en cuenta los datos contenidos en la visita actual. El número de página de visita se compila después de aplicar las reglas de procesamiento. |
| La dirección URL limpia se agrega como nombre de página si no está definido | Tras aplicar las reglas de procesamiento y de VISTA, la dirección URL limpia se agrega como nombre de página si no se ha definido ninguno. Dado que esto ocurre después de aplicar las reglas de procesamiento, se recomienda agregar una condición para comprobar si el nombre de página está vacío.  Si ejecuta Contenido del sitio > Informe de páginas y observa los valores de https:// de los nombres de página, es probable que el nombre de página esté vacío y se esté utilizando la URL.  Puede configurar una condición para comprobar si un nombre de página está vacío, o para ver si el nombre de página o la URL de la página contiene un determinado valor. A continuación, se puede definir el nombre de página según sea necesario. |
| Reglas de procesamiento de canal de marketing | Con las reglas de procesamiento pueden prepararse los datos para su procesamiento con las [reglas de procesamiento del canal de marketing](https://docs.adobe.com/content/help/en/analytics/components/marketing-channels/c-rules.html). |
| Búsqueda GEO | Incluye los valores de Estado del visitante y Código postal del visitante. |
| Persistencia de eVars | Las eVars incluidas en alguna visita anterior no persisten en cada visita durante el procesamiento de las reglas. Solo están disponibles las eVars definidas en la visita que se está procesando actualmente. |

## Aplicación de las reglas de procesamiento al copiar visitas usando VISTA {#section_576EE8C240A24CBA979BD614E8D5338D}

Si tiene una regla de VISTA configurada para copiar visitas a otro grupo de informes, las visitas se envían a través de cualquier regla de procesamiento definida en el otro grupo de informes.

Si tiene reglas de procesamiento definidas en el grupo de informes original, pueden aplicarse o no en función de cómo configuraron la regla de VISTA los servicios de ingeniería. Para averiguarlo, puede preguntarle a su especialista en implementaciones si la regla de VISTA copia los valores “pre” o “post” en el grupo de informes original. Si se copia un valor “pre”, las reglas de procesamiento definidas en el grupo de informes original no se aplican. Si se copia el valor “post”, las reglas de procesamiento se aplican antes de que se copie la visita.

---
description: Use segmentos rápidos en Analysis Workspace.
title: Segmentos rápidos
feature: Segmentation
role: User, Admin
exl-id: 680e7772-10d3-4448-b5bf-def3bc3429d2
source-git-commit: 931e9b0bd71abd852c515cd2e7d99dc9ae423a63
workflow-type: tm+mt
source-wordcount: '887'
ht-degree: 75%

---

# Segmentos rápidos

Puede crear segmentos rápidos dentro de un proyecto para evitar la complejidad del [generador de segmentos](/help/components/segmentation/segmentation-workflow/seg-build.md) completo. Segmentos rápidos

* Aplicar como [segmentos solo de proyecto](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/segments/quick-segments.html?lang=en#what-are-project-only-segments%3F).
* Permiten hasta 3 reglas.
* No se admiten contenedores anidados ni reglas secuenciales.

Para ver una comparación de lo que pueden hacer los segmentos rápidos frente a los segmentos de lista de componentes completos, consulte [aquí](/help/analyze/analysis-workspace/components/segments/t-freeform-project-segment.md).

A continuación se muestra un vídeo introductorio de los segmentos rápidos:

>[!VIDEO](https://video.tv.adobe.com/v/341466/?quality=12&learn=on)

## Requisitos previos

Cualquiera puede crear un [!UICONTROL segmento rápido]. Sin embargo, necesita el permiso de [!UICONTROL Creación de segmentos] en [Adobe Admin Console](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/permissions/summary-tables.html?lang=es#analytics-tools) para poder guardar segmentos rápidos o abrirlos en el [!UICONTROL Generador de segmentos].

## Creación de segmentos rápidos

En una tabla improvisada, haga clic en el icono Filtrar+ del encabezado del panel:

![](assets/quick-seg1.png)

Configure el segmento rápido desde esta pizarra en blanco:

![segmento rápido en blanco](assets/qs-blank-slate.png)

| Configuración | Descripción |
| --- | --- |
| Nombre | El nombre predeterminado de un segmento es una combinación de los nombres de reglas del segmento. Puede cambiar el nombre del segmento. |
| Inclusión/exclusión | Puede incluir o excluir componentes en su definición de segmento, pero no ambas cosas. |
| Contenedor de visita/visita individual/visitante | Los segmentos rápidos incluyen solo un [contenedor de segmentos](https://experienceleague.adobe.com/docs/analytics/components/segmentation/seg-overview.html?lang=es#section_AF2A28BE92474DB386AE85743C71B2D6) que le permite incluir una dimensión, métrica o intervalo de fecha en el segmento (o excluirlo). [!UICONTROL Visitante] contiene datos globales específicos del visitante en las visitas y vistas de páginas. Un contenedor de [!UICONTROL Visita] le permite establecer reglas para desglosar los datos del visitante en función de las visitas, y un contenedor de [!UICONTROL Visita individual] le permite desglosar la información del visitante según las vistas de página individuales. El contenedor predeterminado es [!UICONTROL Visita individual]. |
| Componentes (dimensión/métrica/intervalo de fechas) | Defina hasta 3 reglas añadiendo componentes (dimensiones o métricas o intervalos de fechas) y sus valores. Existen tres formas de encontrar el componente correcto:<ul><li>Empiece a escribir y el generador de [!UICONTROL segmentos rápidos] encontrará automáticamente el componente adecuado.</li><li>Utilice la lista desplegable para buscar el componente.</li><li>Arrástrelos y suéltelos desde el carril izquierdo.</li></ul> |
| Operador | Utilice el menú desplegable para buscar operadores estándar y operadores de [!UICONTROL recuento distintos]. [Más información](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segment-reference/seg-operators.html?lang=es) |
| Signo más (+) | Añadir otra regla |
| Cualificadores AND/OR | Puede agregar calificadores AND u OR a las reglas, pero no puede combinar AND y OR en una sola definición de segmento. |
| Aplicar | Aplique este segmento al panel. Si el segmento no contiene datos, se le preguntará si desea continuar. |
| Abrir creador | Se abrirá el Generador de segmentos. Una vez guardado o aplicado el segmento en el Generador de segmentos, ya no se considera un “segmento rápido”. Forma parte de la biblioteca de segmentos de lista de componentes. |
| Cancelar | Cancele este segmento rápido: no lo aplique. |
| Intervalo de fechas | El validador utiliza el intervalo de fecha del panel para la búsqueda de datos. Sin embargo, cualquier intervalo de fechas aplicado en un segmento rápido anula el intervalo de fechas del panel en la parte superior del panel. |
| Vista previa (parte superior derecha) | Le permite previsualizar las métricas clave para comprobar si tiene un segmento válido y ver su amplitud. Representa el desglose del conjunto de datos que verá cuando aplique este segmento. Podría recibir un aviso que indique que este segmento no tiene datos. Si es el caso, puede continuar o cambiar la definición del segmento. |

Este es un ejemplo de un segmento que combina dimensiones y métricas:

![](assets/quick-seg2.png)

El segmento aparece en la parte superior. Fíjese en su barra lateral con bandas azules, a diferencia de la barra lateral azul para segmentos de nivel de componente en la biblioteca de segmentos a la izquierda.

![](assets/quick-seg5.png)

## Edición de segmentos rápidos

1. Pase el ratón sobre el segmento rápido y seleccione el icono de lápiz.
1. Edite la definición del segmento o el nombre del segmento.
1. Haga clic en [!UICONTROL Aplicar].

## Guardado de segmentos rápidos

>[!IMPORTANT]
>Una vez guardado o aplicado el segmento, ya no puede editarlo en el Generador de segmentos rápidos, solo en el Generador de segmentos normal.

1. Una vez aplicado el segmento rápido, pase el ratón sobre él y seleccione el icono de información (“i”).

   ![](assets/quick-seg6.png)

1. Haga clic en **[!UICONTROL Hacer disponible en todos los proyectos y añadir a la lista de componentes]**.
1. (Opcional) Cambie el nombre del segmento.
1. Haga clic en **[!UICONTROL Guardar]**.

Observe cómo la barra lateral del segmento cambia de azul rayado a azul más claro. Ahora también aparece en la lista de componentes del carril izquierdo.

## ¿Qué son segmentos solo de proyecto?

Los segmentos solo de proyecto son segmentos que solo se aplican al proyecto actual en el que se crearon. No estarán disponibles en otros proyectos y no se podrán compartir con otros usuarios. Están pensados para una exploración rápida de sus datos sin tener que crear ni guardar un segmento en el carril izquierdo. Los segmentos solo de proyecto se pueden crear en la zona de colocación del panel con segmentos rápidos o [segmentos ad hoc](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/segments/ad-hoc-segments.html?lang=en).

Si un segmento solo de proyecto se abre en la variable [!UICONTROL Generador de segmentos], aparece una notificación de solo proyecto. Si no marca &quot;Hacer que este segmento esté disponible.&quot; y haga clic en **[!UICONTROL APLICAR]**, el segmento sigue siendo un segmento solo de proyecto. Nota: si aplica un segmento rápido desde el Generador de segmentos, ya no se puede abrir en el [!UICONTROL Generador de segmentos rápido].

![Solo de proyecto marcado](assets/project-only-unchecked.png)

Si marca &quot;Hacer que este segmento esté disponible.&quot; y haga clic en **[!UICONTROL GUARDAR]**, el segmento está disponible en la lista de componentes del carril izquierdo para su uso en otros proyectos. También se puede compartir con otros usuarios desde el Administrador de segmentos.

![Solo de proyecto marcado](assets/project-only-checked.png)

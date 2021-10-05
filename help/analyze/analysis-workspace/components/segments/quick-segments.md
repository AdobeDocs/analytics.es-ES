---
description: Use segmentos rápidos en Analysis Workspace.
title: Segmentos rápidos
feature: Workspace Basics
role: User, Admin
source-git-commit: 3964f7e1595ccad7ee066018c2e76604e0f6d4c7
workflow-type: tm+mt
source-wordcount: '775'
ht-degree: 14%

---


# Segmentos rápidos

Puede crear segmentos rápidos dentro de un proyecto para evitar la complejidad del [generador de segmentos](/help/components/segmentation/segmentation-workflow/seg-build.md) completo. Segmentos rápidos

* Se aplican solo a los proyectos en los que se crearon (puede cambiar esto).
* Permitir hasta 3 reglas.
* No se admiten contenedores anidados ni reglas secuenciales.
* Trabaje en proyectos con varios grupos de informes.

Para ver una comparación de lo que pueden hacer los segmentos rápidos frente a los segmentos de lista de componentes completa, vaya [aquí](/help/analyze/analysis-workspace/components/segments/t-freeform-project-segment.md).

>[!IMPORTANT]
> Los segmentos rápidos están actualmente en pruebas limitadas y estarán disponibles para el público general el 21 de octubre de 2021.

## Requisitos previos

Cualquiera puede crear un [!UICONTROL segmento rápido]. Sin embargo, necesita el permiso[!UICONTROL Creación de segmentos] en [Adobe Admin Console](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/permissions/summary-tables.html?lang=en#analytics-tools) para poder guardar segmentos rápidos o abrirlos en el [!UICONTROL Generador de segmentos].

## Creación de segmentos rápidos

En una tabla improvisada, haga clic en el icono Filtrar+ del encabezado del panel:

![](assets/quick-seg1.png)

| Configuración | Descripción |
| --- | --- |
| Nombre | El nombre predeterminado de un segmento es una combinación de los nombres de reglas del segmento. Puede cambiar el nombre del segmento. |
| Incluir/excluir | Puede incluir o excluir componentes en su definición de segmento, pero no ambos. |
| Contenedor de visita/visita individual/visitante | Los segmentos rápidos incluyen un [contenedor de segmento](https://experienceleague.adobe.com/docs/analytics/components/segmentation/seg-overview.html?lang=en#section_AF2A28BE92474DB386AE85743C71B2D6) solo que le permite incluir una dimensión, métrica o intervalo de fechas en el segmento (o excluirlo de).  Visitante contiene datos globales específicos del visitante en las visitas y vistas de páginas. Un contenedor de [!UICONTROL visita] le permite establecer reglas para desglosar los datos del visitante en función de las visitas, y un contenedor de [!UICONTROL visita individual] le permite desglosar la información del visitante según las vistas de página individuales. El contenedor predeterminado es [!UICONTROL Visita]. |
| Componentes (Dimension/métrica/intervalo de fechas) | Defina hasta 3 reglas agregando componentes, dimensiones o métricas y/o intervalos de fechas y sus valores. Existen tres formas de encontrar el componente correcto:<ul><li>Empiece a escribir y el [!UICONTROL Generador de segmentos rápidos] encuentre automáticamente el componente adecuado.</li><li>Utilice la lista desplegable para buscar el componente.</li><li>Arrastre y suelte los componentes desde el carril izquierdo.</li></ul> |
| Operador | Utilice el menú desplegable para buscar operadores estándar y operadores [!UICONTROL Distinct Count]. [Más información](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segment-reference/seg-operators.html?lang=en) |
| Signo más (+) | Añadir otra regla |
| Cualificadores AND/OR | Puede agregar calificadores AND u OR a las reglas, pero no puede combinar AND y OR en una sola definición de segmento. |
| Aplicar | Aplique este segmento al panel. Si el segmento no contiene datos, se le preguntará si desea continuar. |
| Abrir creador | Abre el Generador de segmentos. Una vez guardado el segmento en el Generador de segmentos, ya no se considera un &quot;segmento rápido&quot;. Forma parte de la biblioteca de segmentos de la lista de componentes. |
| Cancelar | Cancele este segmento rápido: no lo aplique. |
| Intervalo de fechas | El validador utiliza el intervalo de fechas del panel para la búsqueda de datos. Sin embargo, cualquier intervalo de fechas aplicado en un segmento rápido anula el intervalo de fechas del panel en la parte superior del panel. |
| Vista previa (parte superior derecha) | Le permite ver si tiene un segmento válido y su amplitud. Representa el desglose del conjunto de datos que verá al aplicar este segmento. podría recibir un aviso que indique que este segmento no tiene datos. Puede continuar o cambiar la definición del segmento. |

Este es un ejemplo de un segmento que combina dimensiones y métricas:

![](assets/quick-seg2.png)

El segmento aparece en la parte superior. Fíjese en su barra lateral con bandas azules, a diferencia de la barra lateral azul para segmentos de nivel de componente en la biblioteca de segmentos a la izquierda.

![](assets/quick-seg5.png)

## Editar segmentos rápidos

1. Pase el ratón sobre el segmento rápido y seleccione el icono de lápiz.
1. Edite la definición del segmento o el nombre del segmento.
1. Haga clic en [!UICONTROL Aplicar].

## Guardar segmentos rápidos

>[!IMPORTANT]
>Una vez guardado o aplicado el segmento, ya no puede editarlo en el Generador de segmentos rápido, solo en el Generador de segmentos normal.

1. Una vez aplicado el segmento rápido, pase el ratón sobre él y seleccione el icono de información (&quot;i&quot;).

   ![](assets/quick-seg6.png)

1. Haga clic en **[!UICONTROL Poner a disposición de todos los proyectos y agregarlos a la lista de componentes]**.
1. (Opcional) Cambie el nombre del segmento.
1. Haga clic en **[!UICONTROL Guardar]**.

Observe cómo la barra lateral del segmento cambia de azul rayado a azul. Ahora aparece en la lista de componentes en el carril izquierdo.

## ¿Qué son segmentos solo de proyecto?

Los segmentos solo de proyecto son segmentos rápidos o segmentos de proyecto específicos de Workspace. Al editarlos/abrirlos en el [!UICONTROL Generador de segmentos], aparecerá el cuadro de solo proyecto. Si aplica un segmento rápido en el generador pero no marca la casilla de verificación para que esté disponible, entonces sigue siendo un segmento solo de proyecto pero ya no se puede abrir en el [!UICONTROL Generador de segmentos rápido]. Si marca la casilla y hace clic en **[!UICONTROL SAVE]**, ahora es un segmento de lista de componentes.
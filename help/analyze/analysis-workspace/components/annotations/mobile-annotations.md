---
title: Anotaciones de cuadros de resultados móviles
description: Aprenda a mostrar anotaciones en cuadros de resultados móviles.
role: User, Admin
solution: Analytics
feature: Components
exl-id: d8212ab1-d639-41b5-b28e-da580a3628b0
source-git-commit: 602f837689186f232c4c0f8baebbcf911446bc99
workflow-type: tm+mt
source-wordcount: '368'
ht-degree: 92%

---


# Compartir anotaciones en cuadros de resultados móviles

Puede mostrar anotaciones creadas en Workspace en cuadros de resultados móviles. Esto le permite compartir matices de datos contextuales y perspectivas sobre su organización y campañas directamente en proyectos de cuadros de resultados móviles, visibles en la aplicación móvil de paneles de Analytics.

## Anotaciones de superficie en cuadros de resultados móviles

Para que aparezcan anotaciones en cuadros de resultados móviles, primero cree la anotación desde proyectos de Workspace o desde el menú de componentes.

Para obtener información sobre la creación de anotaciones, consulte [Crear anotaciones](create-annotations.md). Las anotaciones están desactivadas en los cuadros de resultados móviles de forma predeterminada y deben habilitarse para cada cuadro de resultados que desee que aparezca en los cuadros de resultados móviles.

1. Activar anotaciones. Para activar las anotaciones, consulte [Activar o desactivar anotaciones](overview.md#annotations-on-off).

1. Cree una anotación y asegúrese de que se comparta con todos sus proyectos. Para crear una anotación en Workspace, consulte [Crear anotaciones](create-annotations.md).

1. Seleccione **Mostrar anotaciones** para mostrar la anotación en los cuadros de resultados móviles.

   ![](assets/show-annotations.png)

1. Confirme que la opción mostrar anotaciones esté seleccionada y vaya a **Proyecto** > **Información y configuración del proyecto**.

   ![](assets/project-info-settings.png)

## Ver anotaciones en cuadros de resultados móviles

Cuando las anotaciones están activadas, los iconos de anotación se pueden ver en el Generador de cuadros de resultados. Las anotaciones solo aparecen en los gráficos y tablas de la vista detallada. Las anotaciones no están visibles desde la vista de mosaico principal del cuadro de resultados.

![](assets/view-annotations.png)

Cuando los iconos de anotación están visibles, no se puede ver ni interactuar con las anotaciones en el lienzo del generador. Utilice el modo de vista previa para ver e interactuar con anotaciones tal y como aparecen en la aplicación ![](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Play_18_N.svg) **Vista previa**.

Los colores de anotación se seleccionan cuando la anotación se crea en el espacio de trabajo. Las anotaciones grises indicaban la presencia de más de una anotación.

## Ver anotaciones de gráfico

| Fecha | Aspecto |
| --- | --- |
| **Día único** | ![](assets/single-day-mobile-annotations.png)<br></br> |
| **Intervalo de fechas** | ![](assets/date-range.png) |
| **Anotaciones superpuestas** | ![](assets/overlapping-annotations.png)<br></br>Para ver los detalles de las anotaciones en la aplicación de paneles de Analytics, pulse un icono de anotación. <br></br>Cuando vea una anotación en un gráfico, puede deslizar hacia la izquierda y hacia la derecha para navegar por todas las anotaciones presentes en el gráfico. Cuando vea una anotación en la tabla, deslice a izquierda y derecha para navegar por todas las anotaciones asociadas con ese elemento de fila en la tabla. <br></br>![](assets/swipe-multiple-annotations.png) <br></br>En gráficos que no tienen un *eje x* basado en el tiempo, como los gráficos de barras circulares u horizontales, las anotaciones que se aplican al gráfico se pueden ver tocando el icono situado en la esquina inferior derecha.<br></br> ![](assets/charts-without-timebase.png) |

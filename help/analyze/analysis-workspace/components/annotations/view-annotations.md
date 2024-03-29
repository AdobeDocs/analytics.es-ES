---
title: Visualización de anotaciones
description: Cómo ver anotaciones en Espacio de trabajo.
role: User, Admin
feature: Annotations
exl-id: 52b179fd-d9a4-4119-a3c6-f6a36f24f8ea
source-git-commit: 20ab0e9728969c4cc11227a1255e41e3d1a1540f
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 100%

---

# Visualización de anotaciones

Las anotaciones se manifiestan de forma ligeramente diferente, en función de si abarcan un solo día o un intervalo de fechas.

## Visualización de anotaciones en gráficos de líneas o tablas

| Fecha | Aspecto |
| --- | --- |
| **Día único** | ![](assets/single-day.png)<p>Cuando pasa el ratón por encima de la anotación, puede ver sus detalles, puede editarla seleccionando el icono de la pluma o puede eliminarla:<p> ![](assets/hover.png) |
| **Intervalo de fechas** | El icono cambia y, cuando pasa el ratón por encima, aparece el intervalo de fechas.<p>![](assets/multi-day.png)<p>Cuando lo selecciona en el gráfico de líneas, aparecen los metadatos de la anotación y puede editarlos o eliminarlos:![](assets/multi-hover.png)<p>En una tabla, aparece un icono en cada fecha del intervalo de fechas.<p>![](assets/multi-day-table.png) |
| **Anotaciones superpuestas** | En los días que tengan más de una anotación vinculada a ellos, el icono será de color gris.<p>![](assets/grey.png)<p>Cuando pasa el ratón por encima del icono gris, aparecen todas las anotaciones superpuestas:<p>![](assets/overlap.png) |

{style="table-layout:auto"}

## Visualización de anotaciones en un archivo .pdf

Dado que no puede pasar el ratón sobre los iconos de un archivo .pdf, este archivo (tras la exportación) proporciona notas de explicaciones en la parte inferior de un panel. Vea el siguiente ejemplo:

![](assets/ann-pdf.png)

## Ver anotaciones con datos de tendencias

A veces, las anotaciones se muestran con datos sin tendencias, pero vinculados a una dimensión específica. En ese caso, solo aparecen en una anotación de resumen en la esquina inferior derecha. Vea el siguiente ejemplo:

![](assets/non-date.png)

El gráfico de resumen aparece en todos los tipos de visualización de la esquina, no solo en tablas improvisadas sin tendencias y números de resumen. También aparece en visualizaciones como [!UICONTROL Anillos], [!UICONTROL Flujo], [!UICONTROL Visita en el orden previsto], [!UICONTROL Cohorte], etc.

![](assets/ann-summary.png)

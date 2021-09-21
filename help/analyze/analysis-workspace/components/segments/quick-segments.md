---
description: Utilice segmentos rápidos en Analysis Workspace.
title: Segmentos rápidos
feature: Workspace Basics
role: User, Admin
source-git-commit: 9622131ebd4a856cb7756e6844d7d7979029e70e
workflow-type: tm+mt
source-wordcount: '327'
ht-degree: 4%

---


# Segmentos rápidos

Puede crear segmentos rápidos dentro de un proyecto para evitar la complejidad del [generador de segmentos](/help/components/segmentation/segmentation-workflow/seg-build.md) completo. Para ver una comparación de lo que pueden hacer los segmentos rápidos frente a los segmentos de nivel de componente completos, vaya [aquí](/help/analyze/analysis-workspace/components/segments/t-freeform-project-segment.md).

>[!IMPORTANT]
> Los segmentos rápidos están actualmente en pruebas limitadas y no están disponibles en general todavía.

## Crear segmentos rápidos

1. En una tabla improvisada, haga clic en el icono filter+ del encabezado del panel:

   ![](assets/quick-seg1.png)

   Tenga en cuenta que:

   - Solo hay un contenedor de segmentos que le permite incluir una dimensión, métrica o intervalo de fechas en el segmento (o excluirlo de).
   - Puede establecer el contenedor en el nivel de visita individual, visita o visitante. El valor predeterminado es Visita individual.

1. Añada una dimensión/métrica/intervalo de fechas de una de las 3 maneras siguientes:

   - Empiece a escribir y el Generador de segmentos rápidos encuentre automáticamente el componente adecuado.
   - Utilice la lista desplegable para buscar el componente.
   - Arrastre y suelte los componentes desde el carril izquierdo.

1. Especifique la primera regla, como `Page equals workspace`. Puede tener hasta tres reglas en las definiciones de segmentos. Simplemente haga clic en el signo &quot;+&quot; para agregar otra regla. Puede agregar calificadores &quot;AND&quot; u &quot;OR&quot; a las reglas, pero no puede combinar &quot;AND&quot; y &quot;OR&quot; en una sola definición de segmento.

   Este es un ejemplo de un segmento que combina dimensiones y métricas:

   ![](assets/quick-seg2.png)

1. Haga clic en **[!UICONTROL Aplicar]** para aplicar este segmento al panel.
El segmento aparece en la parte superior. Observe su barra lateral gris, a diferencia de la barra azul para los segmentos de nivel de componente a la izquierda.

   ![](assets/quick-seg3.png)

## Convertir segmentos rápidos en públicos

Puede convertir estos segmentos en públicos (globales) siguiendo estos pasos:

1. Pase el ratón sobre el segmento rápido y haga clic en el icono &quot;i&quot;.
1. Haga clic en **[!UICONTROL Abrir generador]**.
Se abrirá el segmento en el Generador de segmentos.
   >[!NOTE]
   >Una vez aplicado o guardado el segmento en el Generador de segmentos, ya no puede editarlo en el Generador de segmentos rápido.
1. Haga clic en **[!UICONTROL Aceptar]**.
1. En el Generador de segmentos, haga clic en **[!UICONTROL Aplicar]**.
1. Vuelva a Workspace y observe cómo el segmento ahora tiene una barra lateral azul, lo que indica que forma parte de la biblioteca de componentes.

   ![](assets/quick-seg4.png)


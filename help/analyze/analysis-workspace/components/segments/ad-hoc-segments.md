---
description: Utilice segmentos ad hoc en Analysis Workspace.
title: Segmentos ad hoc
feature: Segmentation
role: User, Admin
exl-id: 1c189abc-ab9f-413c-9be6-0d2fc457230e
source-git-commit: 931e9b0bd71abd852c515cd2e7d99dc9ae423a63
workflow-type: tm+mt
source-wordcount: '331'
ht-degree: 56%

---

# Segmentos de proyecto ad hoc

Los segmentos de proyecto ad hoc le permiten arrastrar y soltar cualquier componente directamente en la zona de colocación del panel para crear un segmento. El segmento se convierte en una [segmento de nivel de proyecto](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/segments/quick-segments.html?lang=es#what-are-project-only-segments) local al proyecto actual.

Aquí tiene un vídeo sobre la creación de segmentos de proyecto ad hoc:

>[!VIDEO](https://video.tv.adobe.com/v/23978/?quality=12)

1. Suelte cualquier tipo de componente (dimensión, elemento de dimensión, evento, métrica, segmento, plantilla de segmento, intervalo de fechas) en la zona de colocación de segmentos en la parte superior de un panel. Los tipos de componente se convierten automáticamente en segmentos ad hoc o [Segmentos rápidos](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/segments/quick-segments.html?lang=es) si es compatible.
Este es un ejemplo de cómo crear un segmento para el dominio de referencia de Twitter:

   ![](assets/ad-hoc1.png)

   El panel aplica automáticamente este segmento y puede ver los resultados al instante.

1. Puede añadir un número ilimitado de segmentos a un panel.
1. Si decide guardar este segmento, consulte la sección siguiente.

Recuerde:

* **No puede** soltar los siguientes tipos de componentes en la zona de segmento: métricas calculadas y dimensiones/métricas desde las que no se pueden crear segmentos.
* Para las dimensiones y eventos completos, Analysis Workspace crea segmentos de visita del tipo “existe”. Ejemplos: `Hit where eVar1 exists` o `Hit where event1 exists`.
* Si se suelta “sin especificar” o “ninguno” en la zona de colocación de segmentos, se convierten automáticamente en un segmento “no existe”, de modo que se los trate adecuadamente en la segmentación.

Para ver una comparación de los distintos segmentos que puede crear y aplicar dentro de un proyecto, vaya a [aquí](/help/analyze/analysis-workspace/components/segments/t-freeform-project-segment.md).

## Guardar segmentos ad hoc {#ad-hoc-save}

Los segmentos ad hoc se pueden poner a disposición de otros proyectos guardándolos.

1. Sitúese sobre el segmento de la zona de colocación y haga clic en el icono “i”.
1. Haga clic en el lápiz de edición para ir al Generador de segmentos.
1. Consulte **[!UICONTROL Hacer disponible en todos los proyectos y añadir a la lista de componentes]**.
1. Haga clic en **[!UICONTROL GUARDAR]**.

Una vez guardado, el segmento estará disponible en la lista de componentes del carril izquierdo y se podrá compartir con otros usuarios desde el Administrador de segmentos.

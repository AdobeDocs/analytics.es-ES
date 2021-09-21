---
description: Utilice segmentos ad hoc en Analysis Workspace.
title: Segmentos ad hoc
feature: Workspace Basics
role: User, Admin
source-git-commit: 9622131ebd4a856cb7756e6844d7d7979029e70e
workflow-type: tm+mt
source-wordcount: '253'
ht-degree: 45%

---


# Segmentos ad hoc

Aquí tiene un vídeo sobre la creación de segmentos ad hoc:

>[!VIDEO](https://video.tv.adobe.com/v/23978/?quality=12)

Puede crear segmentos ad-hoc si desea explorar rápidamente cómo un segmento podría afectar a su proyecto, sin ir al Generador de segmentos. Piense en estos segmentos como segmentos temporales a nivel de proyecto. Normalmente no formarán parte de la &quot;biblioteca&quot; de segmentos como los segmentos de componentes en el carril izquierdo. Sin embargo, puede hacerlas públicas, como se muestra a continuación.

1. Coloque cualquier tipo de componente (dimensión, elemento de dimensión, evento, métrica, segmento, plantilla de segmento, intervalo de fechas) en la zona de colocación de segmentos en la parte superior de un panel. Los tipos de componente se convierten automáticamente en segmentos.
Este es un ejemplo de cómo crear un segmento para el dominio de referencia de Twitter:

   ![](assets/ad-hoc1.png)

   El panel obtiene automáticamente este segmento aplicado y puede ver los resultados al instante.

1. Hasta

Recuerde:

* **No puede** soltar los siguientes tipos de componentes en la zona de segmento: métricas calculadas y dimensiones/métricas desde las que no se pueden crear segmentos.
* Para las dimensiones y eventos completos, Analysis Workspace crea segmentos de visita del tipo “existe”. Ejemplos: `Hit where eVar1 exists` o `Hit where event1 exists`.
* Si se suelta “sin especificar” o “ninguno” en la zona de colocación de segmentos, se convierten automáticamente en un segmento “no existe”, de modo que se los trate adecuadamente en la segmentación.

>[!NOTE]
>
>Los segmentos creados de esta forma son internos del proyecto.

## Hacer públicos los segmentos ad hoc {#ad-hoc-public}

Puede convertir estos segmentos en públicos (globales) siguiendo estos pasos:

1. Sitúese sobre el segmento de la zona de colocación y haga clic en el icono “i”.
1. En el panel de información que aparece, haga clic en **[!UICONTROL Convertir en público]**.

   ![](assets/segment-info.png)
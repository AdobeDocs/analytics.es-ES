---
title: Estado identificado
description: Un indicador que determina el reconocimiento por el gráfico del dispositivo.
translation-type: tm+mt
source-git-commit: 60fe85adaebee8ca390e59727dda949c12c1ee26
workflow-type: tm+mt
source-wordcount: '120'
ht-degree: 9%

---


# Estado identificado

La dimensión &#39;Estado identificado&#39; es específica de los grupos de informes virtuales de Analytics [](../cda/overview.md) entre dispositivos. Informa si el gráfico del dispositivo reconoce la ID del Experience Cloud en el momento de ejecutar el informe. Esta dimensión es útil para comprender cuán bien se comprimen los datos o puntos CDA.

## Rellene esta dimensión con datos

Siempre y cuando tenga Analytics [entre](../cda/overview.md) dispositivos configurado para un grupo de informes virtuales, esta dimensión funciona de forma predeterminada.

## Elementos de dimensión

Los elementos de dimensión incluyen `"Identified"` y `"Unidentified"`.

* **`"Identified"`**:: El gráfico del dispositivo reconoce el ID del Experience Cloud vinculado a la visita.
* **`"Unidentified"`**:: El gráfico del dispositivo no reconoce el ID de Experience Cloud o la visita no tiene un ID de Experience Cloud.

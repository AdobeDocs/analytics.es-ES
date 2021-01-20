---
title: Estado identificado
description: Un indicador que determina el reconocimiento por el gráfico del dispositivo.
translation-type: tm+mt
source-git-commit: 12c026fec44f2e66e2997e8b338823f2c7d790e4
workflow-type: tm+mt
source-wordcount: '120'
ht-degree: 12%

---


# Estado identificado

La dimensión &#39;Estado identificado&#39; es específica de los [grupos de informes virtuales de Analytics para varios dispositivos](../cda/overview.md). Informa si el gráfico del dispositivo reconoce la ID del Experience Cloud en el momento de ejecutar el informe. Esta dimensión es útil para comprender cuán bien se comprimen los datos o puntos CDA.

## Rellene esta dimensión con datos

Siempre que tenga [Análisis entre dispositivos](../cda/overview.md) configurado para un grupo de informes virtuales, esta dimensión funciona de forma predeterminada.

## Elementos de dimensión

Los elementos de dimensión incluyen `"Identified"` y `"Unidentified"`.

* **`"Identified"`**:: El gráfico del dispositivo reconoce el ID del Experience Cloud vinculado a la visita.
* **`"Unidentified"`**:: El gráfico del dispositivo no reconoce el ID de Experience Cloud o la visita no tiene un ID de Experience Cloud.

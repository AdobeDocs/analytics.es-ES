---
title: Estado identificado
description: Un indicador que determina el reconocimiento por el gráfico del dispositivo.
exl-id: 8c6e9003-96f8-460f-a490-203f67be6337
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '120'
ht-degree: 100%

---

# Estado identificado

La dimensión Estado identificado es específica de los grupos de informes virtuales de [Cross-Device Analytics](../cda/overview.md). Informa si el gráfico del dispositivo reconoce el Experience Cloud ID en el momento de ejecutar el informe. Esta dimensión es útil para comprender cómo comprime datos o vincula datos CDA.

## Rellene esta dimensión con datos

Siempre que tenga [Cross-Device Analytics](../cda/overview.md) configurado para un grupo de informes virtual, esta dimensión funciona de forma predeterminada.

## Elementos de dimensión

Los elementos de dimensión incluyen `"Identified"` y `"Unidentified"`.

* **`"Identified"`**: el gráfico del dispositivo reconoce el Experience Cloud ID vinculado a la visita.
* **`"Unidentified"`**: el gráfico del dispositivo no reconoce el Experience Cloud ID o la visita no tiene un Experience Cloud ID.

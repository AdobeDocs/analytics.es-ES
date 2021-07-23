---
title: Tipo de explorador
description: La organización que creó el explorador.
exl-id: 2a88ebc6-879e-4e5b-a8e5-40a32d54ac1b
source-git-commit: e6f3beadfba340cea07f5fd2694105ad31de9751
workflow-type: tm+mt
source-wordcount: '134'
ht-degree: 84%

---

# Tipo de explorador

La dimensión “Tipo de explorador” enumera las empresas que desarrollaron el explorador que utiliza el visitante. Esta dimensión es útil cuando desea ver qué exploradores generales utilizan los visitantes. Proporciona valor sobre la dimensión “Exploradores” en el sentido de que no lista versiones diferentes del mismo explorador como elementos de dimensión independientes.

## Rellene esta dimensión con datos

Esta dimensión hace referencia a una tabla de búsqueda interna de Adobe. El valor de búsqueda se basa en el encabezado HTTP `User-Agent` de las solicitudes de imagen. Si utiliza una biblioteca de AppMeasurement (por ejemplo, mediante etiquetas en Adobe Experience Platform), esta dimensión funciona de forma predeterminada.

## Elementos de dimensión

Los elementos de dimensión incluyen organizaciones que hacen exploradores. Los elementos de dimensión comunes incluyen `"Google"` (los creadores de [!DNL Chrome]), `"Apple"` (los creadores de [!DNL Safari]), `"Microsoft"` (los creadores de [!DNL Edge]) y `"Mozilla"` (los creadores de [!DNL Firefox]).

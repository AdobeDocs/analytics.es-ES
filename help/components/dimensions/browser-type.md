---
title: Tipo de explorador
description: La organización que creó el explorador.
translation-type: tm+mt
source-git-commit: 4a7b3a00bdbf557c219de530e3e692c2b2db4a84
workflow-type: tm+mt
source-wordcount: '133'
ht-degree: 3%

---


# Tipo de explorador

La dimensión &#39;Tipo de explorador&#39; lista las organizaciones que hicieron el explorador que utiliza el visitante. Esta dimensión es útil cuando desea ver qué visitantes de exploradores generales utilizan. Proporciona valor sobre la dimensión &#39;Exploradores&#39; en el sentido de que no lista versiones diferentes del mismo navegador como valores de dimensión independientes.

## Rellenar esta dimensión con datos

Esta dimensión hace referencia a una tabla de búsqueda interna de Adobe. El valor de búsqueda se basa en el encabezado `User-Agent` HTTP de las solicitudes de imagen. Si utiliza una biblioteca de AppMeasurement (por ejemplo, mediante Adobe Experience Platform Launch), esta dimensión funciona de forma predeterminada.

## Valores de dimensión

Los valores de dimensión incluyen organizaciones que realizan exploradores. Los valores de dimensión comunes incluyen `"Google"` (los creadores de [!DNL Chrome]), `"Apple"` (los creadores de [!DNL Safari]), `"Microsoft"` (los creadores de [!DNL Edge]) y `"Mozilla"` (los creadores de [!DNL Firefox]).

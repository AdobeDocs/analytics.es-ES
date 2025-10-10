---
title: Tipo de explorador
description: La organización que creó el explorador.
feature: Dimensions
exl-id: 2a88ebc6-879e-4e5b-a8e5-40a32d54ac1b
source-git-commit: e32821dd3f30404166554b8437c508172e4764e5
workflow-type: tm+mt
source-wordcount: '149'
ht-degree: 67%

---

# Tipo de explorador

La dimensión [tipo de explorador](overview.md) enumera las organizaciones que crearon el explorador que utiliza el visitante. Esta dimensión es útil cuando desea ver qué exploradores generales utilizan los visitantes. Proporciona valor sobre la dimensión “Exploradores” en el sentido de que no lista versiones diferentes del mismo explorador como elementos de dimensión independientes.

## Rellene esta dimensión con datos

Esta dimensión hace referencia a una tabla de búsqueda interna de Adobe. El valor de búsqueda se basa en el encabezado HTTP `User-Agent` de las solicitudes de imagen. Adobe se asocia con [DeviceAtlas](https://deviceatlas.com/) para mantener búsquedas entre el agente de usuario y el explorador.

* Para implementaciones de AppMeasurement, esta dimensión funciona de forma predeterminada.
* Para implementaciones de Web SDK, habilite [!UICONTROL Búsqueda de dispositivos] al [configurar una secuencia de datos](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=es).

## Elementos de dimensión

Los elementos de dimensión incluyen organizaciones que hacen exploradores. Los elementos de dimensión comunes incluyen `"Google"` (los creadores de [!DNL Chrome]), `"Apple"` (los creadores de [!DNL Safari]), `"Microsoft"` (los creadores de [!DNL Edge]) y `"Mozilla"` (los creadores de [!DNL Firefox]).

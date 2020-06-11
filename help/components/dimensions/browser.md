---
title: Explorador
description: Nombre y versión del explorador utilizado.
translation-type: tm+mt
source-git-commit: 4a7b3a00bdbf557c219de530e3e692c2b2db4a84
workflow-type: tm+mt
source-wordcount: '177'
ht-degree: 1%

---


# Explorador

La dimensión &#39;Explorador&#39; informa el nombre y la versión del explorador que envía la visita. Esta dimensión es útil para comprender qué exploradores más comunes utilizan los visitantes. Al probar las nuevas versiones del sitio, puede ejecutar esas pruebas en los exploradores principales de esta dimensión para maximizar los esfuerzos de control de calidad.

## Rellenar esta dimensión con datos

Esta dimensión hace referencia a una tabla de búsqueda interna de Adobe. El valor de búsqueda se basa en el encabezado `User-Agent` HTTP de las solicitudes de imagen. Si utiliza una biblioteca de AppMeasurement (por ejemplo, mediante Adobe Experience Platform Launch), esta dimensión funciona de forma predeterminada.

## Valores de dimensión

Los valores de dimensión incluyen los nombres y las versiones de los exploradores utilizados. Las distintas versiones del mismo navegador son valores de dimensión independientes.

Algunos valores de dimensión contienen `"(unknown version)"` en lugar de su número de versión. Este valor de dimensión hace referencia a una versión reciente del explorador que Adobe no ha agregado a sus tablas de búsqueda. Dado que los navegadores se actualizan con frecuencia, el `"(unknown version)"` de un navegador determinado es común y temporal. Adobe suele actualizar las tablas de búsqueda durante las revisiones de mantenimiento mensuales.

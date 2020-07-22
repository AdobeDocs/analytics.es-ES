---
title: Explorador
description: Nombre y versión del explorador utilizado.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '177'
ht-degree: 1%

---


# Explorador

La dimensión &#39;Explorador&#39; informa el nombre y la versión del explorador que envía la visita. Esta dimensión es útil para comprender qué exploradores más comunes utilizan los visitantes. Al probar las nuevas versiones del sitio, puede ejecutar esas pruebas en los exploradores principales de esta dimensión para maximizar los esfuerzos de control de calidad.

## Rellenar esta dimensión con datos

Esta dimensión hace referencia a una tabla de búsqueda interna de Adobe. El valor de búsqueda se basa en el encabezado `User-Agent` HTTP de las solicitudes de imagen. Si utiliza una biblioteca de AppMeasurement (por ejemplo, mediante Adobe Experience Platform Launch), esta dimensión funciona de forma predeterminada.

## Elementos de dimensión

Los elementos de dimensión incluyen los nombres y las versiones de los exploradores utilizados. Las distintas versiones del mismo navegador son elementos de dimensión independientes.

Algunos elementos de dimensión contienen `"(unknown version)"` en lugar de su número de versión. Este elemento de dimensión hace referencia a una versión reciente del explorador que Adobe no ha agregado a sus tablas de búsqueda. Dado que los navegadores se actualizan con frecuencia, el `"(unknown version)"` de un navegador determinado es común y temporal. Adobe suele actualizar las tablas de búsqueda durante las revisiones de mantenimiento mensuales.

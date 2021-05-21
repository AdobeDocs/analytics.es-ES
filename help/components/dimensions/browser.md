---
title: Explorador
description: Nombre y versión del explorador utilizado.
exl-id: 2bdf2a5a-3482-43fa-b2e1-fbea892918fb
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '177'
ht-degree: 100%

---

# Explorador

La dimensión “Explorador” informa del nombre y la versión del explorador que envía la visita. Esta dimensión es útil para comprender cuáles son los exploradores más comunes que utilizan los visitantes. Al probar las nuevas versiones del sitio, puede ejecutar esas pruebas en los exploradores principales de esta dimensión para maximizar los esfuerzos de control de calidad.

## Rellene esta dimensión con datos

Esta dimensión hace referencia a una tabla de búsqueda interna de Adobe. El valor de búsqueda se basa en el encabezado HTTP `User-Agent` de las solicitudes de imagen. Si utiliza una biblioteca de AppMeasurement (por ejemplo, mediante Adobe Experience Platform Launch), esta dimensión funciona de forma predeterminada.

## Elementos de dimensión

Los elementos de dimensión incluyen los nombres y las versiones de los exploradores utilizados. Las distintas versiones del mismo explorador son elementos de dimensión independientes.

Algunos elementos de dimensión contienen `"(unknown version)"` en lugar de su número de versión. Este elemento de dimensión hace referencia a una versión reciente del explorador que Adobe no ha agregado a sus tablas de búsqueda. Dado que los navegadores se actualizan con frecuencia, la `"(unknown version)"` de un navegador determinado es común y temporal. Adobe suele actualizar las tablas de búsqueda durante las revisiones de mantenimiento mensuales.

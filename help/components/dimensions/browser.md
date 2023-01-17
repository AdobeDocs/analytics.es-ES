---
title: Explorador
description: Nombre y versión del explorador utilizado.
feature: Dimensions
exl-id: 2bdf2a5a-3482-43fa-b2e1-fbea892918fb
source-git-commit: 39f1ac66fb6374c62f790f9a38a52fba3bf9bda1
workflow-type: tm+mt
source-wordcount: '397'
ht-degree: 38%

---

# Explorador

El[!UICONTROL Navegador]&#39; informa del nombre y la versión del explorador que envía la visita. Esta dimensión es útil para comprender los exploradores más comunes que utilizan los visitantes. Al probar las nuevas versiones del sitio, puede ejecutar esas pruebas en los exploradores principales de esta dimensión para maximizar los esfuerzos de control de calidad.

## Rellene esta dimensión con datos

Esta dimensión hace referencia a una tabla de búsqueda interna de Adobe. El valor de búsqueda se basa en el encabezado HTTP `User-Agent` de las solicitudes de imagen. Si utiliza una biblioteca de AppMeasurement (por ejemplo, mediante etiquetas en Adobe Experience Platform), esta dimensión funciona de forma predeterminada.

## Elementos de dimensión

Los elementos de dimensión incluyen los nombres y las versiones de los exploradores utilizados. Las distintas versiones del mismo explorador son elementos de dimensión independientes.

Algunos elementos de dimensión contienen `"(unknown version)"` en lugar de su número de versión. Este elemento de dimensión hace referencia a una versión reciente del explorador que Adobe no ha agregado a sus tablas de búsqueda. Dado que los navegadores se actualizan con frecuencia, la `"(unknown version)"` de un navegador determinado es común y temporal. Adobe suele actualizar las tablas de búsqueda durante las revisiones de mantenimiento mensuales.

## Cambios en el etiquetado y la definición

A continuación se muestra una lista de cambios en la forma en que se representan los exploradores en los informes. Estos cambios pueden afectar a sus informes o a cualquier lógica, como los segmentos, que dependa de estos valores.

### Eliminación de la empresa del explorador

A partir de la versión 100 para los navegadores Chrome, Edge y Firefox, el nombre de la empresa ya no aparecerá antes del explorador. Esto podría afectar a los usuarios si tienen definiciones de segmento basadas en el nombre del explorador. Por ejemplo, un segmento que incluya una definición de que &quot;el explorador contiene &quot;Google&quot; ya no identificará los navegadores Chrome a partir de la versión 110.

Ejemplos:

La versión 109 de Chrome aparecerá como &quot;Google Chrome 109&quot;.
La versión 110 de Chrome aparecerá como &quot;Chrome 109&quot;.

### Eliminación de la distinción entre móvil y no móvil para Chrome

A partir de Chrome 110, tanto las versiones móviles como no móviles de Chrome tendrán la misma etiqueta. Actualmente, las versiones móviles y no móviles se etiquetan por separado. Es importante que esto cambie el significado del nombre sin &quot;móvil&quot;. &quot;Chrome 109&quot; no es móvil (es decir, de escritorio) &quot;Chrome 110&quot; es móvil y no móvil. De nuevo, si tiene definiciones de segmento que hacen referencia a &quot;móvil&quot; en el nombre del explorador, es posible que ya no funcionen como se espera. Puede utilizar la segmentación móvil y los desgloses para comparar el tráfico móvil con el no móvil.

Ejemplos:

Mobile Chrome 109 aparecerá como &quot;Chrome Mobile 109&quot;.
Chrome 109 no móvil aparecerá como &quot;Chrome 109&quot;.

Mobile Chrome 110 aparecerá como &quot;Chrome 110&quot;.
Chrome 110 no móvil aparecerá como &quot;Chrome 110&quot;.

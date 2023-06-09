---
title: doubleEncodeLinkParameters
description: Habilite o deshabilite las variables de seguimiento de vínculos de codificación doble de AppMeasurement.
source-git-commit: d0e3b28590b24d630a192ee857a7d84c115dc8c1
workflow-type: tm+mt
source-wordcount: '302'
ht-degree: 7%

---

# doubleEncodeLinkParameters

El `doubleEncodeLinkParameters` es un booleano que determina si las variables de seguimiento de vínculos se codifican una vez (si se establece en ) `false`) o dos veces (si se configura como ) `true`). Solo afecta a `linkName` (parte del [`tl()`](../functions/tl-method.md) método) y [`linkURL`](linkurl.md). Requiere el AppMeasurement 2.23.1 o superior para su uso. El valor predeterminado de esta variable es `true`.

En versiones anteriores de AppMeasurement, las variables de seguimiento de vínculos siempre tenían codificación URL dos veces. Aunque no supone un problema para las implementaciones que generalmente dependen de caracteres de un solo byte, la codificación doble creaba valores codificados incorrectamente para caracteres de bytes múltiples en los informes. Configurando esta variable como `false` codifica una vez los valores de seguimiento de vínculos, que suele ser el comportamiento deseado.

* Si la implementación utiliza caracteres multibyte y las variables de seguimiento de vínculos tienen una URL descodificada para la codificación doble de AppMeasurement de desplazamiento, establezca esta variable como `true`. Este valor conserva la funcionalidad de AppMeasurement existente.
* Si la implementación utiliza caracteres multibyte y no descodifica los valores de seguimiento de vínculos mediante URL, Adobe recomienda configurar esta variable como `false`.
* Si la implementación no utiliza caracteres de bytes múltiples, esta variable no es obligatoria. Sin embargo, Adobe recomienda configurar esta variable como `false` en los casos en que se puedan enviar caracteres de bytes múltiples.

## Codificación doble de parámetros de vínculo mediante el SDK web

Esta variable es específica del AppMeasurement y no es necesaria en ningún tipo de implementación del SDK web.

## Codifique dos veces los parámetros de vínculo con la extensión Adobe Analytics

No hay ningún campo dedicado en la extensión de Adobe Analytics para utilizar esta variable. Utilice el editor de código personalizado siguiendo la sintaxis de AppMeasurement.

## s.doubleEncodeLinkParameters en el AppMeasurement y el editor de código personalizado de la extensión de Analytics

El `s.doubleEncodeLinkParameters` es una variable booleana que determina si los valores de seguimiento de vínculos se codifican dos veces. Si no se define esta variable, su valor predeterminado es `true` para conservar la funcionalidad de las implementaciones existentes. El Adobe recomienda establecer este valor en `false` para todas las implementaciones nuevas, especialmente si ve valores con codificación URL en los informes de seguimiento de vínculos.

```js
s.doubleEncodeLinkParameters = false;
```

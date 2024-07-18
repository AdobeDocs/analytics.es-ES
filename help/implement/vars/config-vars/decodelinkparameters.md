---
title: decodeLinkParameters
description: Habilite o deshabilite las variables de seguimiento de vínculos de doble codificación de AppMeasurement.
exl-id: 329c521a-b965-4114-93ce-f45f159d4a20
feature: Variables
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '303'
ht-degree: 8%

---

# decodeLinkParameters

La variable `decodeLinkParameters` es un booleano que determina si las variables de seguimiento de vínculos se codifican una vez (si se establecen en `true`) o dos veces (si se establecen en `false`). Solo afecta a `linkName` (parte del método [`tl()`](../functions/tl-method.md)) y a [`linkURL`](linkurl.md). Requiere el AppMeasurement v2.24.0 o superior para su uso. El valor predeterminado de esta variable es `false`.

En las versiones de AppMeasurement anteriores a la v2.24.0, las variables de seguimiento de vínculos siempre tenían codificación URL doble. Aunque no supone un problema para las implementaciones que generalmente dependen de caracteres de un solo byte, la codificación doble creaba valores codificados incorrectamente para caracteres de bytes múltiples en los informes. Al establecer esta variable en `true`, se codifican una vez los valores de seguimiento de vínculos, que suele ser el comportamiento deseado.

* Si la implementación utiliza caracteres multibyte y las variables de seguimiento de vínculos tienen una URL descodificada para la doble codificación del AppMeasurement de desplazamiento, establezca esta variable en `false`. Este valor conserva la funcionalidad de AppMeasurement existente.
* Si la implementación utiliza caracteres multibyte y no se descodifican los valores de seguimiento de vínculos mediante URL, Adobe recomienda establecer esta variable en `true`.
* Si la implementación no utiliza caracteres de bytes múltiples, esta variable no es obligatoria. Sin embargo, Adobe recomienda establecer esta variable en `true` en los casos en que se puedan enviar caracteres de bytes múltiples.

## Codificación doble de parámetros de vínculo mediante el SDK web

Esta variable es específica del AppMeasurement y no es necesaria en ningún tipo de implementación del SDK web.

## Codifique dos veces los parámetros de vínculo con la extensión Adobe Analytics

No hay ningún campo dedicado en la extensión de Adobe Analytics para utilizar esta variable. Utilice el editor de código personalizado siguiendo la sintaxis de AppMeasurement.

## s.decodeLinkParameters en el AppMeasurement y el editor de código personalizado de la extensión de Analytics

La variable `s.decodeLinkParameters` es un booleano que determina si los valores de seguimiento de vínculos se codifican dos veces. Si no se define esta variable, su valor predeterminado es `false` para conservar la funcionalidad de las implementaciones existentes. El Adobe recomienda establecer este valor en `true` para todas las implementaciones nuevas, especialmente si ve valores con codificación de dirección URL en los informes de seguimiento de vínculos.

```js
s.decodeLinkParameters = true;
```

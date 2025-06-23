---
title: decodeLinkParameters
description: Habilite o deshabilite las variables de seguimiento de vínculos de doble codificación de AppMeasurement.
exl-id: 329c521a-b965-4114-93ce-f45f159d4a20
feature: Appmeasurement Implementation
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '303'
ht-degree: 8%

---

# decodeLinkParameters

La variable `decodeLinkParameters` es un booleano que determina si las variables de seguimiento de vínculos se codifican una vez (si se establecen en `true`) o dos veces (si se establecen en `false`). Solo afecta a `linkName` (parte del método [`tl()`](../functions/tl-method.md)) y a [`linkURL`](linkurl.md). Requiere AppMeasurement v2.24.0 o superior para su uso. El valor predeterminado de esta variable es `false`.

En las versiones de AppMeasurement anteriores a la v2.24.0, las variables de seguimiento de vínculos siempre tenían codificación URL doble. Aunque no supone un problema para las implementaciones que generalmente dependen de caracteres de un solo byte, la codificación doble creaba valores codificados incorrectamente para caracteres de bytes múltiples en los informes. Al establecer esta variable en `true`, se codifican una vez los valores de seguimiento de vínculos, que suele ser el comportamiento deseado.

* Si la implementación utiliza caracteres multibyte y las variables de seguimiento de vínculos tienen una URL descodificada para compensar la codificación doble de AppMeasurement, establezca esta variable en `false`. Este valor conserva la funcionalidad existente de AppMeasurement.
* Si la implementación utiliza caracteres multibyte y no se descodifican los valores de seguimiento de vínculos mediante URL, Adobe recomienda establecer esta variable en `true`.
* Si la implementación no utiliza caracteres de bytes múltiples, esta variable no es obligatoria. Sin embargo, Adobe recomienda establecer esta variable en `true` en los casos en que se puedan enviar caracteres de bytes múltiples.

## Codifique dos veces los parámetros de vínculo mediante Web SDK

Esta variable es específica de AppMeasurement y no es necesaria en ningún tipo de implementación de Web SDK.

## Codifique dos veces los parámetros de vínculo con la extensión Adobe Analytics

No hay ningún campo dedicado en la extensión de Adobe Analytics para utilizar esta variable. Utilice el editor de código personalizado siguiendo la sintaxis de AppMeasurement.

## s.decodeLinkParameters en AppMeasurement y el editor de código personalizado de la extensión de Analytics

La variable `s.decodeLinkParameters` es un booleano que determina si los valores de seguimiento de vínculos se codifican dos veces. Si no se define esta variable, su valor predeterminado es `false` para conservar la funcionalidad de las implementaciones existentes. Adobe recomienda establecer este valor en `true` para todas las implementaciones nuevas, especialmente si ve valores con codificación de dirección URL en los informes de seguimiento de vínculos.

```js
s.decodeLinkParameters = true;
```

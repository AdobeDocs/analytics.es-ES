---
description: AppMeasurement para JavaScript es una nueva biblioteca que proporciona la misma funcionalidad principal que s_code.js, pero es más ligera y rápida de utilizar, tanto en sitios para móviles como de escritorio.
keywords: appmeasurement; Implementación de Analytics; javascript; appmeasurement para javascript; initialization; recuperar instancia de appmeasurement; clear vars; clearvars; appmeasurement utilities; appmeasurement instance; beneficios de appmeasurement
seo-description: AppMeasurement para JavaScript es una nueva biblioteca que proporciona la misma funcionalidad principal que s_code.js, pero es más ligera y rápida de utilizar, tanto en sitios para móviles como de escritorio.
seo-title: Acerca de AppMeasurement para JavaScript
solution: Analytics
subtopic: JavaScript AppMeasurement
title: Acerca de AppMeasurement para JavaScript
topic: Desarrollador e implementación
uuid: dc 71 ad 7 a -92 bd -40 cd -8 fab -707 f 6 f 8472 e 2
translation-type: tm+mt
source-git-commit: 76d0ce11d9b560e0df866be9e753804b6fa4bb3d

---


# Acerca de AppMeasurement para JavaScript

[!DNL AppMeasurement] para JavaScript es una nueva biblioteca que proporciona la misma funcionalidad principal que s_code.js, pero es más ligera y rápida de usar, tanto en sitios para móviles como de escritorio.

## Cosas que hay que saber antes de migrar {#section_B8E7B39E8469468883BA0B41234F21C4}

The following list contains changes you need to understand before switching to this new [!DNL AppMeasurement] version:

* Algunos complementos ya no son compatibles. See [AppMeasurement Plug-in Support](../../../implement/js-implementation/c-appmeasurement-js/plugins-support.md#concept_E31A189BC8A547738666EB5E00D2252A).
* The library does not support dynamic account selection ([dynamicAccountList](/help/implement/js-implementation/c-variables/configuration-variables.md), [dynamicAccountMatch](/help/implement/js-implementation/c-variables/configuration-variables.md), and [dynamicAccountSelection](/help/implement/js-implementation/c-variables/configuration-variables.md)).

* The library and page code can be deployed inside the `<head>` tag.
* The Media and Integrate modules are supported using updated module code that is in the JavaScript [!DNL AppMeasurement] download package. No se admite el módulo Survey.
* El código de página existente es compatible con la nueva versión.
* La biblioteca proporciona utilidades nativas para obtener parámetros de consulta, leer y escribir cookies y realizar un seguimiento de vínculos avanzado.

## Preguntas frecuentes {#section_9BD41B08F7B54197B230937714B9357A}

See the [FAQ](../../../implement/faq.md#concept_9BBC230E01114318BE9C08724F2040D3) for information about performance, video tracking, mobile, and more.

## Proceso de inicialización {#section_F6D5680F6D134B6AB1F01C6235860635}

Call `s_gi()`, passing the report suite ID to initialize an [!DNL AppMeasurement] instance:

```js
var s_account="INSERT-RSID-HERE"
var s=s_gi(s_account)
```

When `s_gi` is called, if an [!DNL AppMeasurement] instance does not exist for the specified `s_account`, a new instance is created. En caso contrario, se devuelve la instancia existente. Esto sirve para impedir que se creen objetos duplicados en una misma cuenta.

## Recuperar una instancia AppMeasurement {#section_6F05C96DCAB24C8C9B4B91C5739630A6}

Throughout your code, call the global [s_gi() function](../../../implement/js-implementation/function-s-gi.md#concept_50EE6629F61A478BB67781408FBA04BD) to retrieve an existing [!DNL AppMeasurement] instance.

## Utilidades {#section_0F47694DD0214645A24C94AB6A4142A0}

JavaScript [!DNL AppMeasurement] provides the following built-in utilities:

* [Util.cookieRead](../../../implement/js-implementation/util-cookieread.md#concept_33BD774A90504F2C8094DDC16D47440D)
* [Util.cookieWrite](../../../implement/js-implementation/util-cookiewrite.md#concept_9BE4F7D9CDAE4445B9AF3212BC7E61F2)
* [Util.getQueryParam](../../../implement/js-implementation/util-getqueryparam.md#concept_763AD2621BB44A3990204BE72D3C9FA5)

## clearVars {#section_597C411E7EDB42BC9A6A0508C9D57147}

Hay un nuevo método `clearVars` disponible para borrar los siguientes valores del objeto de instancia:

* `props`
* `eVars`
* `hier`
* `list`
* `events`
* `eventList`
* `products`
* `productsList`
* `channel`
* `purchaseID`
* `transactionID`
* `state`
* `zip`
* `campaign`

Por ejemplo:

```js
s.clearVars()
```

## Beneficios {#section_091E5A28E89E438E8A54A95F55165743}

* De 3 a 7 veces más rápido que el código H.25.
* Solo 21 k sin comprimir y 8 k comprimidos con gzip (el código H.25 tiene 33 k sin comprimir y 13 k comprimidos con gzip).
* Asistencia nativa para varios complementos habituales ().
* Pequeño y lo suficientemente rápido para su uso en sitios móviles, así como lo bastante sólido para su uso en el escritorio web completo, lo que le permitirá aprovechar una sola biblioteca en todos los entornos web.


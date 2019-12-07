---
description: AppMeasurement para JavaScript es una nueva biblioteca que proporciona la misma funcionalidad principal que s_code.js, pero es más ligera y rápida de utilizar, tanto en sitios para móviles como de escritorio.
keywords: appmeasurement;Analytics Implementation;javascript;appmeasurement for javascript;initialization;retrieve appmeasurement instance;clear vars;clearvars;appmeasurement utilities;appmeasurement instance;appmeasurement benefits
subtopic: JavaScript AppMeasurement
title: Acerca de AppMeasurement para JavaScript
topic: Developer and implementation
uuid: dc71ad7a-92bd-40cd-8fab-707f6f8472e2
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Acerca de AppMeasurement para JavaScript

[!DNL AppMeasurement] para JavaScript es una nueva biblioteca que proporciona la misma funcionalidad principal que s_code.js, pero es más ligera y rápida de usar, tanto en sitios para móviles como de escritorio.

## Cosas que hay que saber antes de migrar {#section_B8E7B39E8469468883BA0B41234F21C4}

La siguiente lista contiene los cambios que debe conocer antes de cambiar a esta nueva versión de [!DNL AppMeasurement]:

* Algunos complementos ya no son compatibles. Consulte [Asistencia del complemento de AppMeasurement](/help/implement/js-implementation/c-appmeasurement-js/plugins-support.md).
* La biblioteca no admite la selección dinámica de cuentas ([dynamicAccountList](/help/implement/js-implementation/c-variables/configuration-variables.md), [dynamicAccountMatch](/help/implement/js-implementation/c-variables/configuration-variables.md) y [dynamicAccountSelection](/help/implement/js-implementation/c-variables/configuration-variables.md)).

* El código de la página y la biblioteca se puede implementar dentro de la etiqueta `<head>`.
* Los módulos Media e Integrate se admiten usando el código de módulo actualizado que se encuentra en el paquete de descarga de JavaScript [!DNL AppMeasurement]. No se admite el módulo Survey.
* El código de página existente es compatible con la nueva versión.
* La biblioteca proporciona utilidades nativas para obtener parámetros de consulta, leer y escribir cookies y realizar un seguimiento de vínculos avanzado.

## Preguntas frecuentes {#section_9BD41B08F7B54197B230937714B9357A}

Consulte [Preguntas más frecuentes](/help/implement/faq.md) para obtener información sobre rendimiento, seguimiento de vídeo o móvil, entre otros.

## Proceso de inicialización {#section_F6D5680F6D134B6AB1F01C6235860635}

Realice la llamada `s_gi()`[!DNL AppMeasurement], pasando el ID de grupo de informes para inicializar una instancia:

```js
var s_account="INSERT-RSID-HERE"
var s=s_gi(s_account)
```

Si al realizar la llamada `s_gi` y no existe una instancia [!DNL AppMeasurement] para la cuenta `s_account` especificada, se crea una nueva. En caso contrario, se devuelve la instancia existente. Esto sirve para impedir que se creen objetos duplicados en una misma cuenta.

## Recuperar una instancia AppMeasurement {#section_6F05C96DCAB24C8C9B4B91C5739630A6}

En todo el código, llame a la función global[ s_gi()](/help/implement/js-implementation/function-s-gi.md) para recuperar una instancia [!DNL AppMeasurement] existente.

## Utilidades {#section_0F47694DD0214645A24C94AB6A4142A0}

JavaScript [!DNL AppMeasurement] proporciona las siguientes utilidades integradas:

* [Util.cookieRead](/help/implement/js-implementation/util-cookieread.md)
* [Util.cookieWrite](/help/implement/js-implementation/util-cookiewrite.md)
* [Util.getQueryParam](/help/implement/js-implementation/util-getqueryparam.md)

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


---
title: doPlugins
description: Configure la lógica justo antes de compilar una visita y enviarla a Adobe.
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# doPlugins

La `doPlugins` variable actúa como una &#39;última llamada&#39; para establecer los valores en la implementación. Si [`usePlugins`](../config-vars/useplugins.md) está activado, se ejecuta automáticamente justo antes de que se compile y envíe a Adobe cualquier tipo de solicitud de imagen, incluidos:

* Todas las llamadas a la vista de página ([`t()`](t-method.md))
* Todas las llamadas de seguimiento de vínculos ([`tl()`](tl-method.md)), incluidos los vínculos de descarga automática y los vínculos de salida

Utilice la `doPlugins` variable para llamar al código del complemento y establecer los valores de la variable final justo antes de compilar una solicitud de imagen y enviarla a Adobe.

## Complementos en Adobe Experience Platform Launch

No hay un campo dedicado en Launch para utilizar esta variable. Utilice el editor de código personalizado, siguiendo la sintaxis de AppMeasurement.

## s.doPlugins en el código personalizado AppMeasurement e Launch

Configure la `s.doPlugins` variable en una función que contenga el código deseado. La función se ejecuta automáticamente cuando realiza una llamada de seguimiento.

```js
s.doPlugins = function() {/* Desired code */};
```

> [!NOTE] Configure una función en la `doPlugins` variable sólo una vez en la implementación. Si establece la `doPlugins` variable más de una vez, solo se utilizará el código más reciente.

## Ejemplos

```js
// Set eVar1 to the web page's title
s.doPlugins = function() {
  s.eVar1 = window.document.title;
};

// Use the getPreviousValue plug-in (requires plug-in code outside the function)
s.doPlugins = function() {
  s.eVar1 = s.getPreviousValue(s.pageName,'gpv_pn');
}
```

> [!NOTE] Las versiones anteriores de AppMeasurement tenían un código ligeramente diferente `doPlugins()` . Adobe recomienda utilizar el formato anterior como práctica recomendada.

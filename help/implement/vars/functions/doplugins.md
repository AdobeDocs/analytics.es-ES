---
title: doPlugins
description: Configure la lógica justo antes de compilar una visita y enviarla a Adobe.
exl-id: c5113be3-04b3-4dd2-8481-ba13149750ca
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '182'
ht-degree: 100%

---

# doPlugins

La variable `doPlugins` actúa como una “última llamada” para establecer los valores en la implementación. Si [`usePlugins`](../config-vars/useplugins.md) está habilitada, se ejecuta automáticamente justo antes de que se compile y envíe a Adobe cualquier tipo de solicitud de imagen, lo que incluye:

* Todas las llamadas a la vista de página ([`t()`](t-method.md))
* Todas las llamadas de seguimiento de vínculos ([`tl()`](tl-method.md)), incluidos los vínculos de descarga automática y los vínculos de salida

Utilice la variable `doPlugins` para llamar al código del complemento y establecer los valores de la variable final justo antes de compilar una solicitud de imagen y enviarla a Adobe.

## Complementos en Adobe Experience Platform Launch

No hay un campo específico en Launch para utilizar esta variable. Utilice el editor de código personalizado siguiendo la sintaxis de AppMeasurement.

## s.doPlugins en el editor de código personalizado de AppMeasurement y Launch

Establezca la variable `s.doPlugins` como una función que contenga el código deseado. La función se ejecuta automáticamente cuando realiza una llamada de seguimiento.

```js
s.doPlugins = function() {/* Desired code */};
```

>[!NOTE]
>
>Establezca una función en la variable `doPlugins` solo una vez en la implementación. Si establece la variable `doPlugins` más de una vez, solo se utilizará el código más reciente.

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

>[!NOTE]
>
>Las versiones anteriores de AppMeasurement tenían un código ligeramente diferente `doPlugins()`. Adobe recomienda utilizar el formato anterior.

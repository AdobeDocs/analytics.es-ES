---
description: La función doPlugins generalmente llama a los complementos JavaScript, que se ejecutan cuando se llama a la función t() en el código para pegar.
keywords: Implementación de Analytics
seo-description: La función doPlugins generalmente llama a los complementos JavaScript, que se ejecutan cuando se llama a la función t() en el código para pegar.
seo-title: Llamada de complementos con la función doplugins
solution: Analytics
subtopic: Complementos
title: Llamada de complementos con la función doplugins
topic: Desarrollador e implementación
uuid: 95 dd 01 de -8136-4 ec 9-aac 9-4 a 3 d 5371 b 839
translation-type: tm+mt
source-git-commit: ee0cb9b64a3915786f8f77d80b55004daa68cab6

---


# Llamada de complementos con la función doplugins

La función doPlugins generalmente llama a los complementos JavaScript, que se ejecutan cuando se llama a la función t() en el código para pegar.

Consequently, if you set a variable in the *`doPlugins`* function, you can overwrite a variable you set on the HTML page. The only time the *`doPlugins`* function is not called is when the [!UICONTROL usePlugins] variable is set to 'false.'

## Código de ejemplo {#section_6940FD16F2E94753A1C39694D0CF5FBA}

The code example below is what the *`doPlugins`* function looks like in your JavaScript file:

AppMeasurement para JavaScript:

```js
/* Plugin Config */ 
s.usePlugins=true 
s.doPlugins=function(s) { 
 /* Add calls to plugins here */ 
}
```

Código H:

```js
/* Plugin Config */ 
s.usePlugins=true 
function s_doPlugins(s) { 
 /* Add calls to plugins here */ 
} 
s.doPlugins=s_doPlugins
```

>[!NOTE]
>
>El código H y las versiones anteriores utilizan una sintaxis diferente para admitir algunos exploradores muy antiguos (como IE 4 y 5).

## Renaming the doPlugins Function {#section_70B7D58E057B48058E25907AB3726725}

The *`doPlugins`* function is typically called *`s_doPlugins`*. In certain circumstances, (usually when more than one version of code may appear on a single page) the *`doPlugins`* function name may be changed. If the standard *`doPlugins`* function needs to be renamed to avoid conflicts, ensure that *`doPlugins`* is assigned the correct function name, as shown in the example below.

```js
/* Plugin Config */ 
s_mc.usePlugins=true 
function s_mc_doPlugins(s_mc) { 
 /* Add calls to plugins here */ 
} 
s_mc.doPlugins=s_mc_doPlugins 
```

## Uso de doPlugins {#section_FA5D901CC5214D54BCD08AB77BED7925}

The *`doPlugins`* function provides an easy way to give default values to variables or to take values from [!UICONTROL query string parameters] on any page of the site. Using *`doPlugins`* is often easier than populating the values in the HTML page because only one file must be updated. Recuerde que los cambios en el archivo JavaScript no siempre son inmediatos. A menudo, los visitantes de retorno al sitio utilizan versiones almacenadas en caché del archivo JavaScript. Esto significa que puede que las actualizaciones que se hagan en el archivo no se apliquen a todos los visitantes hasta un mes después de realizar el cambio.

El ejemplo siguiente muestra cómo se puede usar la función *`doPlugins`* para configurar un valor predeterminado para una variable y para obtener un valor de la cadena de consulta.

```js
/* Plugin Config */ 
s.usePlugins=true 
s.doPlugins=function(s) { 
 /* Add calls to plugins here */ 
 // if prop1 doesn't have a value, set it to "Default Value" 
 if(!s.prop1) 
s.prop1="Default Value" 
 
 // if campaign doesn't have a value, get cid from the query string 
 if(!s.campaign) 
s.campaign=s.getQueryParam('cid'); 
 
// Note: The code to read query parameters is different for  
// Appmeasurement for JavaScript since a plug-in is not required: 
// s.campaign=s.Util.getQueryParam('cid'); 
} 
```

## Complementos instalados {#section_C5494347D85940A78670032199787CD0}

Para saber si un complemento está incluido en el archivo JavaScript y está listo para usar, consulte la [!UICONTROL sección de complementos] del archivo JavaScript. El ejemplo siguiente muestra la función [!UICONTROL getQueryParam].

```js
/************************** PLUGINS SECTION *************************/ 
/* You may insert any plugins you wish to use here.                 */ 
/* 
 * Plugin: getQueryParam 1.3 - Return query string parameter values 
 */ 
s.getQueryParam=new Function("qp","d","" 
+"var s=this,v='',i,t;d=d?d:'';while(qp){i=qp.indexOf(',');i=i<0?qp.l" 
// 
// ... more code below ... 
// 
```


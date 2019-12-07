---
description: La función doPlugins generalmente llama a los complementos JavaScript, que se ejecutan cuando se llama a la función t() en el código para pegar.
keywords: Analytics Implementation
subtopic: Plug-ins
title: Llamadas a complementos con la función doPlugins
topic: Developer and implementation
uuid: 95dd01de-8136-4ec9-aac9-4a3d5371b839
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Llamadas a complementos con la función doPlugins

La función doPlugins generalmente llama a los complementos JavaScript, que se ejecutan cuando se llama a la función t() en el código para pegar.

En consecuencia, si configura una variable en la función *`doPlugins`*, puede sobrescribir una variable configurada en la página HTML. La única vez que no se llama a la función *`doPlugins`* es cuando la variable [!UICONTROL usePlugins] está configurada con el valor “False”.

## Código de ejemplo {#section_6940FD16F2E94753A1C39694D0CF5FBA}

El siguiente ejemplo de código muestra el aspecto de la función *`doPlugins`* en el archivo JavaScript:

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

> [!NOTE] El código H y las versiones anteriores usan una sintaxis diferente para admitir algunos exploradores muy antiguos (como IE 4 y 5).

## Cambio del nombre de la función doPlugins {#section_70B7D58E057B48058E25907AB3726725}

La función *`doPlugins`* generalmente se llama *`s_doPlugins`*. En algunas circunstancias (normalmente cuando puede aparecer más de una versión de código en una sola página), se puede cambiar el nombre de la función *`doPlugins`*. Si fuera necesario cambiar el nombre de la función *`doPlugins`* estándar para evitar conflictos, compruebe que se asigna el nombre de función correcto a *`doPlugins`*, tal como se muestra en el ejemplo siguiente.

```js
/* Plugin Config */ 
s_mc.usePlugins=true 
function s_mc_doPlugins(s_mc) { 
 /* Add calls to plugins here */ 
} 
s_mc.doPlugins=s_mc_doPlugins 
```

## Uso de doPlugins {#section_FA5D901CC5214D54BCD08AB77BED7925}

La función *`doPlugins`* es una manera fácil de proporcionar valores predeterminados a las variables o de tomar valores de los [!UICONTROL parámetros de cadena de consulta] en cualquier página del sitio. Usar *`doPlugins`* es más fácil que rellenar los valores en la página HTML porque solo es necesario actualizar un archivo. Recuerde que los cambios en el archivo JavaScript no siempre son inmediatos. A menudo, los visitantes de retorno al sitio utilizan versiones almacenadas en caché del archivo JavaScript. Esto significa que puede que las actualizaciones que se hagan en el archivo no se apliquen a todos los visitantes hasta un mes después de realizar el cambio.

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


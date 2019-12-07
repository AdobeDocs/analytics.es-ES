---
description: La función doPlugins generalmente llama a los complementos JavaScript, que se ejecutan cuando se llama a la función t() en el código para pegar.
keywords: Analytics Implementation
subtopic: Plug-ins
title: Función doPlugins
topic: Developer and implementation
uuid: 367d5550-f8e2-477d-8681-18ae9665d699
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Función doPlugins

La función doPlugins generalmente llama a los complementos JavaScript, que se ejecutan cuando se llama a la función t() en el código para pegar.

En consecuencia, si configura una variable en la función `doPlugins`, puede sobrescribir una variable configurada en la página HTML. La única vez que no se llama a la función `doPlugins` es cuando la variable *`usePlugins`* está configurada con el valor `false`.

**Código de ejemplo**

La función `doPlugins` generalmente se llama `s_doPlugins`. Sin embargo, en algunas circunstancias (normalmente cuando en una única página puede aparecer más de una versión del código de [!DNL Analytics]), es posible cambiar el nombre de la función `doPlugins`. Si fuera necesario cambiar el nombre de la función `doPlugins` estándar para evitar conflictos, asigne el nombre de función correcto a `doPlugins`, tal como se muestra en el ejemplo siguiente.

```js
/* Plugin Config */ 
s_mc.usePlugins=true 
function  
<b>s_mc_doPlugins</b>(s_mc) { 
/* Add calls to plugins here */ 
} 
s_mc.doPlugins= 
<b>s_mc_doPlugins</b>
```

**Uso de doPlugins**

Esta función brinda una manera fácil de proporcionar valores predeterminados a las variables, o de tomar valores de los parámetros de cadena de consultas en cualquier página del sitio. Usar `doPlugins` generalmente es más fácil que rellenar los valores en la página HTML porque solo es necesario actualizar un archivo. Los cambios realizados en el archivo JavaScript no siempre son inmediatos. A menudo, los visitantes de retorno al sitio utilizan versiones almacenadas en caché del archivo JavaScript. Es decir, puede que las actualizaciones que se hagan en el archivo no se apliquen a todos los visitantes hasta un mes después de realizar el cambio.

Los siguientes ejemplos muestran cómo puede utilizarse la función `doPlugins` para configurar un valor predeterminado de una variable y obtener un valor de la cadena de consultas.

```js
/* Plugin Config */ 
s.usePlugins=true 
function s_doPlugins(s) { 
/* Add calls to plugins here */ 
// if prop1 doesn't have a value, set it to "Default Value" 
if(!s.prop1) 
s.prop1="Default Value" 
 
// if campaign doesn't have a value, get cid from the query string 
if(!s.campaign) 
s.campaign=getQueryParam('cid'); 
} 
s.doPlugins=s_doPlugins
```

**Complementos instalados**

Para saber si un complemento está incluido en el archivo JavaScript y está listo para usar, mire la [!UICONTROL sección de complementos] del archivo JavaScript. El siguiente ejemplo muestra cómo se ve la función `getQueryParam` en la [!UICONTROL sección de complementos].

```js
/************************** PLUGINS SECTION *************************/ 
 
/* You may insert any plugins you wish to use here. */ 
/* 
* Plugin: getQueryParam 1.3 - Return query string parameter values 
*/ 
s.getQueryParam=new Function("qp","d","" 
+"vars=this,v='',i,t;d=d?d:'';while(qp){i=qp.indexOf(',');i=i<0?qp.l" 
// 
// ... more code below ...
// 
```


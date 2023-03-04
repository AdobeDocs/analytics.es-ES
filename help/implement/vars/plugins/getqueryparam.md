---
title: getQueryParam
description: Extraiga el valor de un parámetro de cadena de consulta de una dirección URL.
feature: Variables
exl-id: d2d542d1-3a18-43d9-a50d-c06d8bd473b8
source-git-commit: c53f886d5329e2a3b5023f9396c3aa2360a86901
workflow-type: tm+mt
source-wordcount: '507'
ht-degree: 93%

---

# Complemento de Adobe: getQueryParam

{{plug-in}}

El complemento `getQueryParam` le permite extraer el valor de cualquier parámetro de cadena de consulta contenido en una dirección URL. Resulta útil para extraer códigos de campaña, tanto internos como externos, de las direcciones URL de las páginas de aterrizaje. También resulta útil al extraer términos de búsqueda u otros parámetros de cadena de consulta.

Este complemento proporciona funciones sólidas para analizar direcciones URL complejas, incluidos hashes y direcciones URL que contienen varios parámetros de cadena de consulta. Si solo necesita parámetros de cadena de consulta simples, Adobe recomienda utilizar las funciones de parámetro de URL mediante el SDK web, la extensión de Adobe Analytics o el [`Util.getQueryParam()`](../functions/util-getqueryparam.md) método incluido en AppMeasurement.

<!--## Install the plug-in using the Web SDK or the Adobe Analytics extension

Adobe offers an extension that allows you to use most commonly-used plug-ins.

1. Log in to [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) using your AdobeID credentials.
1. Click the desired tag property.
1. Go to the [!UICONTROL Extensions] tab, then click on the [!UICONTROL Catalog] button
1. Install and publish the [!UICONTROL Common Analytics Plugins] extension
1. If you haven't already, create a rule labeled "Initialize Plug-ins" with the following configuration:
    * Condition: None
    * Event: Core – Library Loaded (Page Top)
1. Add an action to the above rule with the following configuration:
    * Extension: Common Analytics Plugins
    * Action Type: Initialize getQueryParam
1. Save and publish the changes to the rule.-->

## Instalación del complemento con el editor de código personalizado

Si no desea utilizar la extensión del complemento, puede utilizar el editor de código personalizado.

1. Inicie sesión en la [Recopilación de datos de Adobe Experience Platform](https://experience.adobe.com/data-collection) con sus credenciales de Adobe ID.
1. Haga clic en la propiedad deseada.
1. Vaya a la pestaña [!UICONTROL Extensiones] y, a continuación, haga clic en el botón **[!UICONTROL Configurar]** en la extensión de Adobe Analytics.
1. Expanda [!UICONTROL Configurar seguimiento con el código personalizado], que muestra el botón [!UICONTROL Abrir editor].
1. Abra el editor de código personalizado y pegue el código del complemento que se proporciona a continuación en la ventana de edición.
1. Guarde y publique los cambios en la extensión de Analytics.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getQueryParam v4.0.1  */
function getQueryParam(a,d,f){function n(g,c){c=c.split("?").join("&");c=c.split("#").join("&");var e=c.indexOf("&");if(g&&(-1<e||c.indexOf("=")>e)){e=c.substring(e+1);e=e.split("&");for(var h=0,p=e.length;h<p;h++){var l=e[h].split("="),q=l[1];if(l[0].toLowerCase()===g.toLowerCase())return decodeURIComponent(q||!0)}}return""}if("-v"===a)return{plugin:"getQueryParam",version:"4.0.1"};var b=function(){if("undefined"!==typeof window.s_c_il)for(var g=0,c;g<window.s_c_il.length;g++)if(c=window.s_c_il[g],c._c&&"s_c"===c._c)return c}();"undefined"!==typeof b&&(b.contextData.getQueryParam="4.0");if(a){d=d||"";f=(f||"undefined"!==typeof b&&b.pageURL||location.href)+"";(4<d.length||-1<d.indexOf("="))&&f&&4>f.length&&(b=d,d=f,f=b);b="";for(var m=a.split(","),r=m.length,k=0;k<r;k++)a=n(m[k],f),"string"===typeof a?(a=-1<a.indexOf("#")?a.substring(0,a.indexOf("#")):a,b+=b?d+a:a):b=""===b?a:b+(d+a);return b}};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Uso del complemento

La función `getQueryParam` utiliza los siguientes argumentos:

* **`qsp`** (obligatorio): Una lista delimitada por comas de parámetros de cadena de consulta que se buscarán en la dirección URL. Sin distinción de mayúsculas y minúsculas.
* **`de`** (opcional): El delimitador que se usará si coinciden varios parámetros de cadena de consulta. El valor predeterminado es una cadena vacía.
* **`url`** (opcional): Una dirección URL, cadena o variable personalizada desde la que extraer los valores de parámetro de cadena de consulta. El valor predeterminado es `window.location`.

La llamada a esta función hace que se devuelva un valor que depende de los argumentos anteriores y de la dirección URL:

* Si no se encuentra un parámetro de cadena de consulta coincidente, la función devuelve una cadena vacía.
* Si se encuentra un parámetro de cadena de consulta coincidente, la función devuelve el valor del parámetro de cadena de consulta.
* Si se encuentra un parámetro de cadena de consulta coincidente pero el valor está vacío, la función devuelve `true`.
* Si se encuentran varios parámetros de cadena de consulta coincidentes, la función devuelve una cadena con el valor de cada parámetro delimitado por la cadena en el argumento `de`.

## Ejemplos

```js
// Given the URL https://example.com/?cid=trackingcode
// Sets the campaign variable to "trackingcode"
s.campaign = getQueryParam('cid');

// Given the URL https://example.com/?cid=trackingcode&ecid=123
// Sets the campaign variable to "trackingcode:123"
s.campaign = getQueryParam('cid,ecid',':');

// Given the URL https://example.com/?cid=trackingcode&ecid=123
// Sets the campaign variable to "trackingcode123"
s.campaign = getQueryParam('cid,ecid');

// Given the URL https://example.com/?cid=trackingcode&ecid=123#location
// Sets the campaign variable to "123"
s.campaign = getQueryParam('ecid');

// Given the URL https://example.com/#location&cid=trackingcode&ecid=123
// Sets the campaign variable to "123"
// The plug-in replaces the URL's hash character with a question mark if a question mark doesn't exist.
s.campaign = getQueryParam('ecid');

// Given the URL https://example.com
// Does not set the campaign variable to a value.
s.pageURL = "https://example.com/?cid=trackingcode";
s.campaign = getQueryParam('cid');

// Given the URL https://example.com
// Sets the campaign variable to "trackingcode"
s.pageURL = "https://example.com/?cid=trackingcode";
s.campaign = getQueryParam('cid','',s.pageURL);

// Given the URL https://example.com
// Sets eVar2 to "123|trackingcode|true|300"
s.eVar1 = "https://example.com/?cid=trackingcode&ecid=123#location&pos=300";
s.eVar2 = getQueryParam('ecid,cid,location,pos','|',s.eVar1);
```

## Historial de versiones

### 4.0.1 (26 de marzo de 2021)

* Se ha actualizado el problema por el que se devolvía undefined en lugar de &quot;&quot; si el parámetro de consulta no estaba presente en la cadena de consulta.

### 4.0 (19 de marzo de 2021)

* Se ha añadido el número de versión como datos de contexto.
* Se han eliminado las dependencias del plug-in pt.

### 3.3 (24 de septiembre de 2019)

* Se ha omitido la lógica innecesaria para reducir el tamaño del código

### 3.2 (15 de mayo de 2018)

* Se han movido las funciones `findParameterValue` y `getParameterValue` a la función `getQueryParam`

### 3.1 (10 de mayo de 2018)

* Se ha corregido un problema con la captura de parámetros de cadena de consulta sin valor

### 3.0 (16 de abril de 2018)

* Versión puntual (compilada de nuevo, con un tamaño de código más pequeño).
* Se ha cambiado el nombre de las funciones de ayuda a `findParameterValue` y `getParameterValue` con fines de legibilidad.
* Se ha eliminado la necesidad de agregar un argumento para encontrar los parámetros contenidos en el hash de la dirección URL

### 2.5 (8 de enero de 2016)

* Compatible con el código H y con AppMeasurement (requiere `s.pt` con AppMeasurement).

### 2,4

* Se ha agregado el parámetro `h`, que permite que el código encuentre los parámetros de cadena de consulta que se encuentren después del carácter hash (`#`)

### 2,3

* Se ha corregido un problema de regresión en el que el complemento solo funcionaba cuando el hash aparecía después del código de seguimiento

### 2,2

* Ahora elimina los caracteres hash (y todo lo que haya a continuación) del valor devuelto

### 2,1

* Compatible con código H.10

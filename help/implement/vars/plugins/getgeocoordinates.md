---
title: getGeoCoordinates
description: Rastree la geolocalización de un visitante.
feature: Variables
exl-id: 8620d083-7fa6-432b-891c-e24907e7c466
source-git-commit: c53f886d5329e2a3b5023f9396c3aa2360a86901
workflow-type: tm+mt
source-wordcount: '321'
ht-degree: 100%

---

# Complemento de Adobe: getGeoCoordinates

{{plug-in}}

El complemento `getGeoCoordinates` le permite registrar la latitud y la longitud de los dispositivos de los visitantes. Adobe recomienda utilizar este complemento si desea obtener datos de localización geográfica en variables de Analytics.

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
    * Action Type: Initialize getGeoCoordinates
1. Save and publish the changes to the rule.-->

## Instalación del complemento con el editor de código personalizado

Si no desea utilizar la extensión del complemento, puede utilizar el editor de código personalizado.

1. Inicie sesión en la [Recopilación de datos de Adobe Experience Platform](https://experience.adobe.com/data-collection) con sus credenciales de Adobe ID.
1. Haga clic en la propiedad deseada.
1. Vaya a la pestaña [!UICONTROL Extensiones] y, a continuación, haga clic en el botón **[!UICONTROL Configurar]** en la extensión de Adobe Analytics.
1. Expanda [!UICONTROL Configurar seguimiento con el código personalizado], que muestra el botón [!UICONTROL Abrir editor].
1. Abra el editor de código personalizado y pegue el código del complemento que se proporciona a continuación en la ventana de edición.
1. Guarde y publique los cambios en la extensión de Analytics.

## Instalación del complemento con AppMeasurement

Copie y pegue el siguiente código en cualquier parte del archivo AppMeasurement después de crear una instancia del objeto de seguimiento de Analytics (con [`s_gi`](../functions/s-gi.md)). Conservar los comentarios y los números de versión del código en la implementación ayuda a Adobe a solucionar cualquier posible problema.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getGeoCoordinates v2.0  */
function getGeoCoordinates(){if(arguments&&"-v"===arguments[0])return{plugin:"getGeoCoordinates",version:"2.0"};var b=function(){if("undefined"!==typeof window.s_c_il)for(var a=0,c;a<window.s_c_il.length;a++)if(c=window.s_c_il[a],c._c&&"s_c"===c._c)return c}();"undefined"!==typeof b&&(b.contextData.getGeoCoordinates="2.0");window.cookieWrite=window.cookieWrite||function(a,c,f){if("string"===typeof a){var h=window.location.hostname,b=window.location.hostname.split(".").length-1;if(h&&!/^[0-9.]+$/.test(h)){b=2<b?b:2;var e=h.lastIndexOf(".");if(0<=e){for(;0<=e&&1<b;)e=h.lastIndexOf(".",e-1),b--;e=0<e?h.substring(e):h}}g=e;c="undefined"!==typeof c?""+c:"";if(f||""===c)if(""===c&&(f=-60),"number"===typeof f){var d=new Date;d.setTime(d.getTime()+6E4*f)}else d=f;return a&&(document.cookie=encodeURIComponent(a)+"="+encodeURIComponent(c)+"; path=/;"+(f?" expires="+d.toUTCString()+";":"")+(g?" domain="+g+";":""),"undefined"!==typeof cookieRead)?cookieRead(a)===c:!1}};window.cookieRead=window.cookieRead||function(a){if("string"===typeof a)a=encodeURIComponent(a);else return"";var c=" "+document.cookie,b=c.indexOf(" "+a+"="),d=0>b?b:c.indexOf(";",b);return(a=0>b?"":decodeURIComponent(c.substring(b+2+a.length,0>d?c.length:d)))?a:""};var d="";b=cookieRead("s_ggc").split("|");var k={timeout:5E3,maximumAge:0},l=function(a){a=a.coords;cookieWrite("s_ggc",parseFloat(a.latitude.toFixed(4))+"|"+parseFloat(a.longitude.toFixed(4)),30);d="latitude="+parseFloat(a.latitude.toFixed(4))+" | longitude="+parseFloat(a.longitude.toFixed(4))},m=function(a){d="error retrieving geo coordinates"};1<b.length&&(d="latitude="+b[0]+" | longitude="+b[1]);navigator.geolocation&&navigator.geolocation.getCurrentPosition(l,m,k);""===d&&(d="geo coordinates not available");return d};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Uso del complemento

La función `getGeoCoordinates` no utiliza ningún argumento. Devuelve uno de los siguientes valores:

* `"geo coordinates not available"`: Para dispositivos que no tienen datos de localización geográfica disponibles cuando se ejecuta el complemento. Este valor es habitual en la primera visita, especialmente cuando los visitantes deben consentir por primera vez que se rastree su ubicación.
* `"error retrieving geo coordinates"`: Cuando el complemento encuentra algún error al intentar recuperar la ubicación del dispositivo.
* `"latitude=[LATITUDE] | longtitude=[LONGITUDE]"`: Donde [LATITUDE]/[LONGITUDE] representan la latitud y la longitud, respectivamente.

>[!NOTE]
>
>Los valores de coordenadas se redondean al cuarto decimal más cercano. Por ejemplo, el valor de `"40.438635333"` se redondea a `"40.4386"` para limitar el número de valores únicos registrados. Los valores están lo suficientemente cerca como para señalar la ubicación exacta del dispositivo a unos 6 metros.

Este complemento utiliza una cookie denominada `"s_ggc"` para almacenar las coordenadas entre cada visita si fuese necesario.

## Ejemplos

```js
// Sets eVar1 to one of the above return values depending on the visitor's device status.
s.eVar1 = getGeoCoordinates();

// Extracts latitude and longitude into their own variables called finalLatitude and finalLongitude for use in other code/applications.
var coordinates = getGeoCoordinates();
if(coordinates.indexOf("latitude") > -1)
{
  var finalLatitude = Number(coordinates.split("|")[0].trim().split("=")[1]),
  finalLongitude = Number(coordinates.split("|")[1].trim().split("=")[1]);
}

// From there, you can determine whether a visitor is at, for example, the Statue of Liberty:
if(finalLatitude >= 40.6891 && finalLatitude <= 40.6893 && finalLongitude >= -74.0446 && finalLongitude <= -74.0444)
{
  var visitorAtStatueOfLiberty = true;
}
else
{
  var visitorAtStatueOfLiberty = false;
}
```

## Historial de versiones

### 2.0 (19 de marzo de 2021)

* Se ha añadido el número de versión como datos de contexto.

### 1.0 (25 de mayo de 2015)

* Versión inicial.

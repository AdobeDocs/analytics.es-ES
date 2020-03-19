---
title: getGeoCoordinates
description: Rastree la geoLocation de un visitante.
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# Complemento de Adobe: getGeoCoordinates

> [!IMPORTANT] Este complemento lo proporciona Adobe Consulting por cortesía para ayudarle a obtener más valor de Adobe Analytics. El Servicio de atención al cliente de Adobe no ofrece asistencia técnica con este complemento, incluida la instalación o solución de problemas. Si necesita ayuda con este complemento, póngase en contacto con el administrador de cuentas de su organización. Pueden organizar una reunión con un consultor para obtener ayuda.

El `getGeoCoordinates` complemento le permite capturar la latitud y la longitud de los dispositivos de los visitantes. Adobe recomienda utilizar este complemento si desea capturar datos de ubicación geográfica en variables de Analytics.

## Instalación del complemento con la extensión Adobe Experience Platform Launch

Adobe ofrece una extensión que le permite utilizar los complementos más utilizados.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
1. Haga clic en la propiedad que desee.
1. Vaya a la ficha [!UICONTROL Extensions] y haga clic en el [!UICONTROL Catalog]
1. Instalación y publicación de la [!UICONTROL Common Analytics Plugins] extensión
1. Si aún no lo ha hecho, cree una regla con la etiqueta &quot;Inicializar complementos&quot; con la siguiente configuración:
   * Condición: Ninguno
   * Evento: Core - Biblioteca cargada (Principio de página)
1. Agregue una acción a la regla anterior con la siguiente configuración:
   * Extensión: Complementos comunes de Analytics
   * Tipo de acción: Inicializar getGeoCoordinates
1. Guarde y publique los cambios en la regla.

## Instalación del complemento con el editor de código personalizado Iniciar

Si no desea utilizar la extensión del complemento, puede utilizar el editor de código personalizado.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
1. Haga clic en la propiedad deseada.
1. Vaya a la [!UICONTROL Extensions] ficha y, a continuación, haga clic en el [!UICONTROL Configure] botón situado debajo de la extensión de Adobe Analytics.
1. Expanda el [!UICONTROL Configure tracking using custom code] acordeón, que muestra el [!UICONTROL Open Editor] botón.
1. Abra el editor de código personalizado y pegue el código del complemento que se proporciona a continuación en la ventana de edición.
1. Guarde y publique los cambios en la extensión de Analytics.

## Instalación del complemento mediante AppMeasurement

Copie y pegue el siguiente código en cualquier parte del archivo AppMeasurement después de crear una instancia del objeto de seguimiento de Analytics (mediante [`s_gi`](../functions/s-gi.md)). La conservación de los comentarios y los números de versión del código en la implementación ayuda a Adobe a solucionar cualquier problema potencial.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getGeoCoordinates v1.0 */
s.getGeoCoordinates=function(){var d=this,b="",a=d.c_r("s_ggc").split("|"),e={timeout:5E3,maximumAge:0},f=function(c){c=c.coords;var a=new Date;a.setTime(a.getTime()+18E5);d.c_w("s_ggc",parseFloat(c.latitude.toFixed(4))+"|"+parseFloat(c.longitude.toFixed(4)),a); b="latitude="+parseFloat(c.latitude.toFixed(4))+" | longitude="+parseFloat(c.longitude.toFixed(4))},g=function(a){b="error retrieving geo coordinates"};1<a.length&&(b="latitude="+a[0]+" | longitude="+a[1]);navigator.geolocation&& navigator.geolocation.getCurrentPosition(f,g,e);""===b&&(b="geo coordinates not available");return b};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Utilizar el complemento

El `getGeoCoordinates` método no utiliza ningún argumento. Devuelve uno de los siguientes valores:

* `"geo coordinates not available"`:: Para dispositivos que no tienen datos de ubicación geográfica disponibles en el momento en que se ejecuta el complemento. Este valor es común en la primera visita individual de la visita, especialmente cuando los visitantes primero necesitan proporcionar consentimiento para rastrear su ubicación.
* `"error retrieving geo coordinates"`:: Cuando el complemento encuentra algún error al intentar recuperar la ubicación del dispositivo
* `"latitude=[LATITUDE] | longtitude=[LONGITUDE]"`:: Donde [LATITUDE]/[LONGITUDE] son la latitud y la longitud, respectivamente

> [!NOTE] Los valores de coordenadas se redondean al cuarto decimal más cercano. Por ejemplo, el valor de `"40.438635333"` se redondea a `"40.4386"` para limitar el número de valores únicos que se van a capturar. Los valores están lo suficientemente cerca como para señalar la ubicación exacta del dispositivo a unos 6 metros.

Este complemento utiliza una cookie denominada `"s_ggc"` para almacenar las coordenadas entre visitas si es necesario.

## Llamadas de ejemplo

### Ejemplo n.º 1

El siguiente código...

```js
s.eVar1 = s.getGeoCoordinates();
```

...establece eVar1 en uno de los valores de retorno anteriores, según el estado del dispositivo del visitante

### Ejemplo n.º 2

El siguiente código extrae la latitud y la longitud en sus propias variables denominadas finalLatitude y finalLongitude para su uso en otros códigos o aplicaciones

```js
var coordinates = s.getGeoCoordinates();
if(coordinates.indexOf("latitude") > -1)
{
  var finalLatitude = Number(coordinates.split("|")[0].trim().split("=")[1]),
  finalLongitude = Number(coordinates.split("|")[1].trim().split("=")[1]);
}
```

Desde allí, puede determinar si un visitante se encuentra, por ejemplo, en la Estatua de la Libertad:

```js
if(finalLatitude >= 40.6891 && finalLatitude <= 40.6893 && finalLongtude >= -74.0446 && finalLongitude <= -74.0444)
  var visitorAtStatueOfLiberty = true;
else
  var visitorAtStatueOfLiberty = false;
```

## Historial de versiones

### 1.0 (25 de mayo de 2015)

* Versión inicial.

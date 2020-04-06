---
title: getPageName
description: Cree un nombre de página fácil de leer a partir de la ruta del sitio web actual.
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Complemento de Adobe: getPageName

>[!IMPORTANT] Adobe Consulting proporciona este complemento por cortesía para ayudarle a sacar el máximo partido a Adobe Analytics. El Servicio de atención al cliente de Adobe no ofrece asistencia técnica con este complemento, incluida la instalación o solución de problemas. Si necesita ayuda con este complemento, póngase en contacto con el administrador de cuentas de su organización. Ellos podrán organizar una reunión con un consultor para ayudarle.

El complemento `getPageName` crea una versión fácil de leer y con formato sencillo de la dirección URL actual. Adobe recomienda utilizar este complemento si desea un valor [`pageName`](../page-vars/pagename.md) fácil de configurar y comprender en el sistema de informes. Este complemento no es necesario si ya tiene una estructura de nombres para la variable `pageName`, como por ejemplo a través de una capa de datos. Se recomienda utilizarlo cuando no tenga otra solución para configurar la variable `pageName`.

## Instalación del complemento con la extensión de Adobe Experience Platform Launch

Adobe ofrece una extensión que le permite disfrutar de los complementos más utilizados.

1. Inicie sesión en [launch.adobe.com](https://launch.adobe.com) con sus credenciales de Adobe ID.
1. Haga clic en la propiedad deseada.
1. Go to the [!UICONTROL Extensions] tab, then click on the [!UICONTROL Catalog] button
1. Install and publish the [!UICONTROL Common Analytics Plugins] extension
1. Si aún no lo ha hecho, cree una regla con la etiqueta “Inicializar complementos” con la siguiente configuración:
   * Condición: Ninguna
   * Evento: Core – Biblioteca cargada (Principio de página)
1. Añada una acción a la regla anterior con la siguiente configuración:
   * Extensión: Common Analytics Plugins
   * Tipo de acción: Inicializar getPageName
1. Guarde y publique los cambios en la regla.

## Instalación del complemento con el editor de código personalizado de Launch

Si no desea utilizar la extensión del complemento, puede utilizar el editor de código personalizado.

1. Inicie sesión en [launch.adobe.com](https://launch.adobe.com) con sus credenciales de Adobe ID.
1. Haga clic en la propiedad deseada.
1. Go to the [!UICONTROL Extensions] tab, then click the [!UICONTROL Configure] button under the Adobe Analytics extension.
1. Expanda el [!UICONTROL Configure tracking using custom code] acordeón, que muestra el [!UICONTROL Open Editor] botón.
1. Abra el editor de código personalizado y pegue el código del complemento que se proporciona a continuación en la ventana de edición.
1. Guarde y publique los cambios en la extensión de Analytics.

## Instalación del complemento con AppMeasurement

Copie y pegue el siguiente código en cualquier parte del archivo AppMeasurement después de crear una instancia del objeto de seguimiento de Analytics (con [`s_gi`](../functions/s-gi.md)). Conservar los comentarios y los números de versión del código en la implementación ayuda a Adobe a solucionar cualquier posible problema.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getPageName v4.0 */
var getPageName=function(si,qv,hv,de){var c=location.hostname,f=location.pathname.substring(1).split("/"),h=f.length, g=location.search.substring(1).split("&"),l=g.length,k=location.hash.substring(1).split("&"),m=k.length;de=de?de:": ";si=si?si:c;qv= qv?qv:"";hv=hv?hv:"";if(1===h&&""===f[0])si=si+de+"home";else for(c=0;c<h;c++)si=si+de+decodeURIComponent(f[c]); if(qv&&(1!==l||""!== g[0]))for(f=qv.split(","),h=f.length,c=0;c<h;c++)for(qv=0;qv<l;qv++)if(f[c]===g[qv].split("=")[0]){si=si+de+decodeURIComponent(g[qv]);break}if(hv&&(1!==m||""!==k[0]))for(hv=hv.split(","),g=hv.length,c=0;c<g;c++)for(qv=0;qv<m;qv++)if(hv[c]===k[qv].split("=")[0]){si=si+de+decodeURIComponent(k[qv]);break}return si.substring(si.length-de.length)===de?si.substring(0,si.length-de.length):si};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Uso del complemento

El método `getPageName` utiliza los siguientes argumentos:

* **`si`** (opcional, cadena): un ID insertado al principio de la cadena que representa el ID del sitio. Este valor puede ser un ID numérico o un nombre sencillo. Si no se establece, el valor predeterminado es el dominio actual.
* **`qv`** (opcional, cadena): una lista delimitada por comas de parámetros de cadena de consulta que, si se encuentran en la dirección URL, se agregan a la cadena
* **`hv`** (opcional, cadena): una lista delimitada por comas de parámetros encontrados en el hash de la URL que, si se encuentran en la dirección URL, se agregan a la cadena
* **`de`** (opcional, cadena): el delimitador para dividir partes individuales de la cadena. Valores predeterminados de una barra vertical (`|`).

El método devuelve una cadena que contiene una versión de la URL con formato sencillo. Esta cadena se suele asignar a la variable `pageName`, pero también se puede utilizar en otras variables.

## Llamadas de ejemplo

### Ejemplo 1

Si la dirección URL actual fuera...

```js
https://mail.google.com/mail/u/0/#inbox
```

... y se ejecuta el siguiente código...

```js
s.pageName = getPageName()
```

... el valor final de s.pageName será:

```js
s.pageName = "mail.google.com|mail|u|0";
```

### Ejemplo 2

Si la dirección URL actual fuera...

```js
https://mail.google.com/mail/u/0/#inbox
```

... y se ejecuta el siguiente código...

```js
s.pageName = getPageName("gmail")
```

... el valor final de s.pageName será:

```js
s.pageName = "gmail|mail|u|0";
```

### Ejemplo 3

Si la dirección URL actual fuera...

```js
https://www.google.com/
```

... y se ejecuta el siguiente código...

```js
s.pageName = getPageName()
```

... el valor final de s.pageName será:

```js
s.pageName = "www.google.com|home"
```

**Nota**: Cuando el código se ejecuta en una dirección URL que no contiene una ruta, siempre agrega el valor “home” al final del valor devuelto

### Ejemplo 4

Si la dirección URL actual fuera...

```js
https://www.google.com/
```

... y se ejecuta el siguiente código...

```js
s.pageName = getPageName("google","","","|")
```

... el valor final de s.pageName será:

```js
s.pageName = "google|home"
```

### Ejemplo 5

Si la dirección URL actual fuera...

```js
https://www.hotelrooms.com/en/booking/room-booking.html?cid=1235#/step2&arrive=2018-05-26&depart=2018-05-27&numGuests=2
```

... y se ejecuta el siguiente código...

```js
s.pageName = getPageName()
```

... el valor final de s.pageName será:

```js
s.pageName = "www.hotelrooms.com|en|booking|room-booking.html"
```

Sin embargo, si se ejecuta el siguiente código en su lugar...

```js
s.pageName = getPageName("hotelrooms","cid","arrive,numGuests",": ")
```

... el valor final de s.pageName será:

```js
s.pageName = "hotelrooms: en: booking: room-booking.html: cid=1235: arrive=2018-05-26: numGuests=2"
```

## Actualización desde versiones anteriores

La versión 4.0 o posterior del complemento getPageName no depende de la existencia del objeto AppMeasurement de Adobe Analytics (es decir, el objeto “s”) para que se ejecute.  Si decide actualizar a esta versión, asegúrese de cambiar el código que llama al complemento, para ello elimine cualquier instancia del objeto “s” de la llamada.
Por ejemplo, cambie esto:

```js
s.pageName = s.getPageName();
```

... por esto:

```js
s.pageName = getPageName();
```

## Historial de versiones

### 4.1 (17 de septiembre de 2019)

* Se ha cambiado el valor del delimitador predeterminado a un carácter de barra vertical (de dos puntos+espacio).

### 4.0 (22 de mayo de 2018)

* Reanálisis y reescritura completos del complemento

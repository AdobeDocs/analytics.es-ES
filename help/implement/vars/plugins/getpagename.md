---
title: getPageName
description: Cree un pageName fácil de leer a partir de la ruta del sitio web actual.
translation-type: tm+mt
source-git-commit: 26f06adbef1608a6e01df3ab1d3ad4ba78abc28f

---


# Complemento de Adobe: getPageName

> [!IMPORTANT] Este complemento lo proporciona Adobe Consulting por cortesía para ayudarle a obtener más valor con el uso de Adobe Analytics. El Servicio de atención al cliente de Adobe no ofrece asistencia técnica con este complemento, incluida la instalación o solución de problemas. Si necesita ayuda con este complemento, póngase en contacto con el administrador de cuentas de su organización. Pueden organizar una reunión con un consultor para obtener ayuda.

El `getPageName` complemento crea una versión fácil de leer y con formato sencillo de la dirección URL actual. Adobe recomienda utilizar este complemento si desea un `pageName` valor fácil de configurar y comprender en los informes. Este complemento no es necesario si ya tiene una estructura de nombres para la `pageName` variable, como por ejemplo a través de una capa de datos. Se recomienda utilizarlo cuando no tenga otra solución para configurar la `pageName` variable.

## Instalación del complemento con la extensión Adobe Experience Platform Launch

Adobe ofrece una extensión que le permite utilizar los complementos más utilizados.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
1. Haga clic en la propiedad que desee.
1. Vaya a la ficha [!UICONTROL Extensiones] y, a continuación, haga clic en el botón [!UICONTROL Catálogo]
1. Instalación y publicación de la extensión [!UICONTROL Common Analytics Plugins]
1. Para cualquier regla de inicio en la que desee utilizar el complemento, agregue una acción con la siguiente configuración:
   * Extensión: Complementos comunes de Analytics
   * Tipo de acción: Inicializar addProductEvar
1. Guardar y publicar los cambios en la regla

## Instalación del complemento con el editor de código personalizado Iniciar

Si no desea utilizar la extensión del complemento, puede utilizar el editor de código personalizado.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
1. Haga clic en la propiedad deseada.
1. Vaya a la ficha [!UICONTROL Extensiones] y, a continuación, haga clic en el botón [!UICONTROL Configurar] en la extensión de Adobe Analytics.
1. Expanda el seguimiento [!UICONTROL Configurar mediante el acordeón de código] personalizado, que muestra el botón [!UICONTROL Abrir editor] .
1. Abra el editor de código personalizado y pegue el código del complemento que se proporciona a continuación en la ventana de edición.
1. Guarde y publique los cambios en la extensión de Analytics.

## Instalación del complemento mediante AppMeasurement

Copie y pegue el siguiente código en cualquier parte del archivo AppMeasurement después de crear una instancia del objeto de seguimiento de Analytics (mediante `s_gi`). La conservación de los comentarios y los números de versión del código en la implementación ayuda a Adobe a solucionar cualquier problema potencial.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getPageName v4.0 */
var getPageName=function(si,qv,hv,de){var c=location.hostname,f=location.pathname.substring(1).split("/"),h=f.length, g=location.search.substring(1).split("&"),l=g.length,k=location.hash.substring(1).split("&"),m=k.length;de=de?de:": ";si=si?si:c;qv= qv?qv:"";hv=hv?hv:"";if(1===h&&""===f[0])si=si+de+"home";else for(c=0;c<h;c++)si=si+de+decodeURIComponent(f[c]); if(qv&&(1!==l||""!== g[0]))for(f=qv.split(","),h=f.length,c=0;c<h;c++)for(qv=0;qv<l;qv++)if(f[c]===g[qv].split("=")[0]){si=si+de+decodeURIComponent(g[qv]);break}if(hv&&(1!==m||""!==k[0]))for(hv=hv.split(","),g=hv.length,c=0;c<g;c++)for(qv=0;qv<m;qv++)if(hv[c]===k[qv].split("=")[0]){si=si+de+decodeURIComponent(k[qv]);break}return si.substring(si.length-de.length)===de?si.substring(0,si.length-de.length):si};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Utilizar el complemento

El `getPageName` método utiliza los siguientes argumentos:

* **`si`**(opcional, cadena): Un ID insertado al principio de la cadena que representa el ID del sitio. Este valor puede ser un ID numérico o un nombre descriptivo. Si no se establece, el valor predeterminado es el dominio actual.
* **`qv`**(opcional, cadena): Una lista delimitada por comas de parámetros de cadena de consulta que, si se encuentran en la dirección URL, se agregan a la cadena
* **`hv`**(opcional, cadena): Lista de parámetros delimitados por comas que se encuentran en el hash de URL y que, si se encuentran en la URL, se agregan a la cadena
* **`de`**(opcional, cadena): El delimitador que se va a dividir partes individuales de la cadena. Valores predeterminados de una barra vertical (`|`).

El método devuelve una cadena que contiene una versión de la URL con formato sencillo. Esta cadena se suele asignar a la `pageName` variable, pero también se puede utilizar en otras variables.

## Llamadas de ejemplo

### Ejemplo n.º 1

Si la dirección URL actual fuera...

```js
https://mail.google.com/mail/u/0/#inbox
```

...y se ejecuta el siguiente código...

```js
s.pageName = getPageName()
```

...el valor final de s.pageName será:

```js
s.pageName = "mail.google.com|mail|u|0";
```

### Ejemplo n.º 2

Si la dirección URL actual fuera...

```js
https://mail.google.com/mail/u/0/#inbox
```

...y se ejecuta el siguiente código...

```js
s.pageName = getPageName("gmail")
```

...el valor final de s.pageName será:

```js
s.pageName = "gmail|mail|u|0";
```

### Ejemplo n.º 3

Si la dirección URL actual fuera...

```js
https://www.google.com/
```

...y se ejecuta el siguiente código...

```js
s.pageName = getPageName()
```

...el valor final de s.pageName será:

```js
s.pageName = "www.google.com|home"
```

**Nota**: Cuando el código se ejecuta en una dirección URL que no contiene una ruta, siempre agrega el valor de &quot;home&quot; al final del valor devuelto

### Ejemplo n.º 4

Si la dirección URL actual fuera...

```js
https://www.google.com/
```

...y se ejecuta el siguiente código...

```js
s.pageName = getPageName("google","","","|")
```

...el valor final de s.pageName será:

```js
s.pageName = "google|home"
```

### Ejemplo n.º 5

Si la dirección URL actual fuera...

```js
https://www.hotelrooms.com/en/booking/room-booking.html?cid=1235#/step2&arrive=2018-05-26&depart=2018-05-27&numGuests=2
```

...y se ejecuta el siguiente código...

```js
s.pageName = getPageName()
```

...el valor final de s.pageName será:

```js
s.pageName = "www.hotelrooms.com|en|booking|room-booking.html"
```

Sin embargo, si se ejecuta el siguiente código en su lugar...

```js
s.pageName = getPageName("hotelrooms","cid","arrive,numGuests",": ")
```

...el valor final de s.pageName será:

```js
s.pageName = "hotelrooms: en: booking: room-booking.html: cid=1235: arrive=2018-05-26: numGuests=2"
```

## Actualización desde versiones anteriores

La versión 4.0 o posterior del complemento getPageName no depende de la existencia del objeto AppMeasurement de Adobe Analytics (es decir, el objeto &quot;s&quot;) que se va a ejecutar.  Si decide actualizar a esta versión, asegúrese de cambiar el código que llama al complemento eliminando cualquier instancia del objeto &quot;s&quot; de la llamada.
Por ejemplo, cambie esto:

```js
s.pageName = s.getPageName();
```

...por esto:

```js
s.pageName = getPageName();
```

## Historial de versiones

### 4.1 (17 de septiembre de 2019)

* Se ha cambiado el valor del delimitador predeterminado a un carácter de barra vertical (de dos puntos + espacio).

### 4.0 (22 de mayo de 2018)

* Reanálisis y reescritura completos del complemento

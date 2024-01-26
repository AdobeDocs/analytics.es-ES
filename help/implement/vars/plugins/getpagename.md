---
title: getPageName
description: Cree un nombre de página fácil de leer a partir de la ruta del sitio web actual.
feature: Variables
exl-id: a3aaeb5d-65cd-45c1-88bb-f3c0efaff110
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '684'
ht-degree: 75%

---

# Complemento de Adobe: getPageName

{{plug-in}}

El complemento `getPageName` crea una versión fácil de leer y con formato sencillo de la dirección URL actual. Adobe recomienda utilizar este complemento si desea un valor [`pageName`](../page-vars/pagename.md) fácil de configurar y comprender en el sistema de informes. Este complemento no es necesario si ya tiene una estructura de nombres para la variable `pageName`, como por ejemplo a través de una capa de datos. Se recomienda utilizarlo cuando no tenga otra solución para configurar la variable `pageName`.

## Instalación del complemento con la extensión del SDK web

Adobe ofrece una extensión que le permite utilizar los complementos más utilizados con el SDK web.

1. Inicie sesión en la [Recopilación de datos de Adobe Experience Platform](https://experience.adobe.com/data-collection) con sus credenciales de Adobe ID.
1. Clic **[!UICONTROL Etiquetas]** a la izquierda, haga clic en la propiedad de etiqueta que desee.
1. Clic **[!UICONTROL Extensiones]** a la izquierda y, a continuación, haga clic en **[!UICONTROL Catálogo]** pestaña
1. Busque e instale el **[!UICONTROL Complementos comunes del SDK web]** extensión.
1. Clic **[!UICONTROL Elementos de datos]** a la izquierda, haga clic en el elemento de datos deseado.
1. Establezca el nombre del elemento de datos deseado con la siguiente configuración:
   * Extensión: Common Web SDK Plugins
   * Elemento de datos: `getPageName`
1. Configure los parámetros deseados a la derecha.
1. Guarde y publique los cambios en el elemento de datos.

## Instalación manual del complemento mediante la implementación del SDK web

Este complemento aún no es compatible con una implementación manual del SDK web.

## Instalación del complemento con la extensión de Adobe Analytics

Adobe ofrece una extensión que le permite utilizar los complementos más utilizados con Adobe Analytics.

1. Inicie sesión en la [Recopilación de datos de Adobe Experience Platform](https://experience.adobe.com/data-collection) con sus credenciales de Adobe ID.
1. Haga clic en la propiedad de etiquetas deseada.
1. Vaya a la pestaña [!UICONTROL Extensiones] y, a continuación, haga clic en el botón [!UICONTROL Catálogo].
1. Instalación y publicación de la extensión [!UICONTROL Common Analytics Plugins].
1. Si aún no lo ha hecho, cree una regla con la etiqueta “Inicializar complementos” con la siguiente configuración:
   * Condición: Ninguna
   * Evento: Core – Biblioteca cargada (Principio de página)
1. Añada una acción a la regla anterior con la siguiente configuración:
   * Extensión: Common Analytics Plugins
   * Tipo de acción: Inicializar getPageName
1. Guarde y publique los cambios en la regla.

## Instalación del complemento con el editor de código personalizado de 

Si no desea utilizar la extensión de complemento Common Analytics Plugins, puede utilizar el editor de código personalizado.

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
/* Adobe Consulting Plugin: getPageName v4.2 */
var getPageName=function(si,qv,hv,de){var a=si,b=qv,f=hv,e=de;if("-v"===a)return{plugin:"getPageName",version:"4.2"};a:{if("undefined"!==typeof window.s_c_il){var d=0;for(var g;d<window.s_c_il.length;d++)if(g=window.s_c_il[d],g._c&&"s_c"===g._c){d=g;break a}}d=void 0}"undefined"!==typeof d&&(d.contextData.getPageName="4.2");var c=location.hostname,h=location.pathname.substring(1).split("/"),l=h.length,k=location.search.substring(1).split("&"),m=k.length;d=location.hash.substring(1).split("&");g=d.length;e=e?e:"|";a=a?a:c;b=b?b:"";f=f?f:"";if(1===l&&""===h[0])a=a+e+"home";else for(c=0;c<l;c++)a=a+e+decodeURIComponent(h[c]);if(b&&(1!==m||""!==k[0]))for(h=b.split(","),l=h.length,c=0;c<l;c++)for(b=0;b<m;b++)if(h[c]===k[b].split("=")[0]){a=a+e+decodeURIComponent(k[b]);break}if(f&&(1!==g||""!==d[0]))for(f=f.split(","),k=f.length,c=0;c<k;c++)for(b=0;b<g;b++)if(f[c]===d[b].split("=")[0]){a=a+e+decodeURIComponent(d[b]);break}return a.substring(a.length-e.length)===e?a.substring(0,a.length-e.length):a};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Uso del complemento

La función `getPageName` utiliza los argumentos siguientes:

* **`si`** (opcional, cadena): un ID insertado al principio de la cadena que representa el ID del sitio. Este valor puede ser un ID numérico o un nombre sencillo. Si no se establece, el valor predeterminado es el dominio actual.
* **`qv`** (opcional, cadena): una lista delimitada por comas de parámetros de cadena de consulta que, si se encuentran en la dirección URL, se agregan a la cadena
* **`hv`** (opcional, cadena): una lista delimitada por comas de parámetros encontrados en el hash de la URL que, si se encuentran en la dirección URL, se agregan a la cadena
* **`de`** (opcional, cadena): el delimitador para dividir partes individuales de la cadena. Valores predeterminados de una barra vertical (`|`).

La función devuelve una cadena que contiene una versión de la dirección URL con formato sencillo. Esta cadena se suele asignar a la variable `pageName`, pero también se puede utilizar en otras variables.

## Ejemplos

```js
// Given the URL https://mail.example.com/mail/u/0/#inbox, sets the page variable to "mail.example.com|mail|u|0".
s.pageName = getPageName();

// Given the URL https://mail.example.com/mail/u/0/#inbox, sets the page variable to "example|mail|u|0".
s.pageName = getPageName("example");

// Given the URL https://www.example.com/, sets the page variable to "www.example.com|home".
// When the code runs on a URL that does not contain a path, it always adds the value of "home" to the end of the return value.
s.pageName = getPageName();

// Given the URL https://www.example.com/, sets the page variable to "example|home".
s.pageName = getPageName("example","","","|");

// Given the URL https://www.example.com/en/booking/room-booking.html?cid=1235#/step2&arrive=05-26&depart=05-27&numGuests=2
// Sets the page variable to "www.example.com|en|booking|room-booking.html".
s.pageName = getPageName();

// Given the URL https://www.example.com/en/booking/room-booking.html?cid=1235#/step2&arrive=05-26&depart=05-27&numGuests=2
// Sets the page variable to "example: en: booking: room-booking.html: cid=1235: arrive=05-26: numGuests=2"
s.pageName = getPageName("example","cid","arrive,numGuests",": ");
```

## Actualización desde versiones anteriores

La versión 4.0 o posterior `getPageName` del complemento no depende de la existencia del objeto AppMeasurement de Adobe Analytics (es decir, del objeto `s`). Si decide actualizar a esta versión, asegúrese de cambiar el código que llama al complemento. Para ello, elimine las instancias del objeto `s` de la llamada. Por ejemplo, cambie `s.getPageName();` a `getPageName();`.

## Historial de versiones

### 4.2 (19 de marzo de 2021)

* Se ha añadido el número de versión como datos de contexto.

### 4.1 (17 de septiembre de 2019)

* Se ha cambiado el valor del delimitador predeterminado a un carácter de barra vertical (de dos puntos+espacio).

### 4.0 (22 de mayo de 2018)

* Reanálisis y reescritura completos del complemento

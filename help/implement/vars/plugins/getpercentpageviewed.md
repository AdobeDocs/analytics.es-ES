---
title: getPercentPageViewed
description: Recupere el porcentaje de la página que vio el visitante.
exl-id: 7a842cf0-f8cb-45a9-910e-5793849bcfb8
source-git-commit: ab078c5da7e0e38ab9f0f941b407cad0b42dd4d1
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Complemento de Adobe: getPercentPageViewed

>[!IMPORTANT]
>
>Adobe Consulting proporciona este complemento por cortesía para ayudarle a sacar el máximo partido a Adobe Analytics. El Servicio de atención al cliente de Adobe no ofrece asistencia técnica con este complemento, incluida la instalación o solución de problemas. Si necesita ayuda con este complemento, póngase en contacto con el administrador de cuentas de su organización. Ellos podrán organizar una reunión con un consultor para ayudarle.

El complemento `getPercentPageViewed` mide la actividad de desplazamiento de un visitante para comprobar cuánto ve de una página antes de pasar a otra. Este complemento no es necesario si las páginas tienen poca altura o si no desea medir la actividad de desplazamiento.

## Instalación del complemento con etiquetas en Adobe Experience Platform

Adobe ofrece una extensión que le permite disfrutar de los complementos más utilizados.

1. Inicie sesión en la [IU de recopilación de datos](https://experience.adobe.com/data-collection) con sus credenciales de Adobe ID.
1. Haga clic en la propiedad deseada.
1. Vaya a la pestaña [!UICONTROL Extensiones] y, a continuación, haga clic en el botón [!UICONTROL Catálogo].
1. Instalación y publicación de la extensión [!UICONTROL Common Analytics Plugins].
1. Si aún no lo ha hecho, cree una regla con la etiqueta “Inicializar complementos” con la siguiente configuración:
   * Condición: Ninguna
   * Evento: Core – Biblioteca cargada (Principio de página)
1. Añada una acción a la regla anterior con la siguiente configuración:
   * Extensión: Common Analytics Plugins
   * Tipo de acción: Inicializar getPercentPageViewed
1. Guarde y publique los cambios en la regla.

## Instalación del complemento con el editor de código personalizado de 

1. Inicie sesión en la [IU de recopilación de datos](https://experience.adobe.com/data-collection) con sus credenciales de Adobe ID.
1. Haga clic en la propiedad deseada.
1. Vaya a la pestaña [!UICONTROL Extensiones] y, a continuación, haga clic en el botón [!UICONTROL Configurar] en la extensión de Adobe Analytics.
1. Expanda [!UICONTROL Configurar seguimiento con el código personalizado], que muestra el botón [!UICONTROL Abrir editor].
1. Abra el editor de código personalizado y pegue el código del complemento que se proporciona a continuación en la ventana de edición.
1. Guarde y publique los cambios en la extensión de Analytics.

## Instalación del complemento con AppMeasurement

Copie y pegue el siguiente código en cualquier parte del archivo AppMeasurement después de crear una instancia del objeto de seguimiento de Analytics (con [`s_gi`](../functions/s-gi.md)). Conservar los comentarios y los números de versión del código en la implementación ayuda a Adobe a solucionar cualquier posible problema.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getPercentPageViewed v5.0.1 */
function getPercentPageViewed(pid,ch){var n=pid,r=ch;function p(){if(window.ppvID){var a=Math.max(Math.max(document.body.scrollHeight,document.documentElement.scrollHeight),Math.max(document.body.offsetHeight,document.documentElement.offsetHeight),Math.max(document.body.clientHeight,document.documentElement.clientHeight)),b=window.innerHeight||document.documentElement.clientHeight||document.body.clientHeight,d=(window.pageYOffset||window.document.documentElement.scrollTop||window.document.body.scrollTop)+b,f=Math.min(Math.round(d/a*100),100),l=Math.floor(d/b);b=Math.floor(a/b);var c="";if(!window.cookieRead("s_tp")||decodeURIComponent(window.cookieRead("s_ppv").split(",")[0])!==window.ppvID||window.p_fo(window.ppvID)||1==window.ppvChange&&window.cookieRead("s_tp")&&a!=window.cookieRead("s_tp")){(decodeURIComponent(window.cookieRead("s_ppv").split(",")[0])!==window.ppvID||window.p_fo(window.ppvID+"1"))&&window.cookieWrite("s_ips",d);if(window.cookieRead("s_tp")&&decodeURIComponent(window.cookieRead("s_ppv").split(",")[0])===window.ppvID){window.cookieRead("s_tp");c=window.cookieRead("s_ppv");var h=-1<c.indexOf(",")?c.split(","):[];c=h[0]?h[0]:"";h=h[3]?h[3]:"";var q=window.cookieRead("s_ips");c=c+","+Math.round(h/a*100)+","+Math.round(q/a*100)+","+h+","+l}window.cookieWrite("s_tp",a)}else c=window.cookieRead("s_ppv");var k=c&&-1<c.indexOf(",")?c.split(",",6):[];a=0<k.length?k[0]:encodeURIComponent(window.ppvID);h=1<k.length?parseInt(k[1]):f;q=2<k.length?parseInt(k[2]):f;var t=3<k.length?parseInt(k[3]):d,u=4<k.length?parseInt(k[4]):l;k=5<k.length?parseInt(k[5]):b;0<f&&(c=a+","+(f>h?f:h)+","+q+","+(d>t?d:t)+","+(l>u?l:u)+","+(b>k?b:k));window.cookieWrite("s_ppv",c)}}if("-v"===n)return{plugin:"getPercentPageViewed",version:"5.0.1"};var m=function(){if("undefined"!==typeof window.s_c_il)for(var a=0,b;a<window.s_c_il.length;a++)if(b=window.s_c_il[a],b._c&&"s_c"===b._c)return b}();"undefined"!==typeof m&&(m.contextData.getPercentPageViewed="5.0.1");window.pageName="undefined"!==typeof m&&m.pageName||"";window.cookieWrite=window.cookieWrite||function(a,b,d){if("string"===typeof a){var f=window.location.hostname,l=window.location.hostname.split(".").length-1;if(f&&!/^[0-9.]+$/.test(f)){l=2<l?l:2;var c=f.lastIndexOf(".");if(0<=c){for(;0<=c&&1<l;)c=f.lastIndexOf(".",c-1),l--;c=0<c?f.substring(c):f}}g=c;b="undefined"!==typeof b?""+b:"";if(d||""===b)if(""===b&&(d=-60),"number"===typeof d){var h=new Date;h.setTime(h.getTime()+6E4*d)}else h=d;return a&&(document.cookie=encodeURIComponent(a)+"="+encodeURIComponent(b)+"; path=/;"+(d?" expires="+h.toUTCString()+";":"")+(g?" domain="+g+";":""),"undefined"!==typeof window.cookieRead)?window.cookieRead(a)===b:!1}};window.cookieRead=window.cookieRead||function(a){if("string"===typeof a)a=encodeURIComponent(a);else return"";var b=" "+document.cookie,d=b.indexOf(" "+a+"="),f=0>d?d:b.indexOf(";",d);return(a=0>d?"":decodeURIComponent(b.substring(d+2+a.length,0>f?b.length:f)))?a:""};window.p_fo=window.p_fo||function(a){window.__fo||(window.__fo={});if(window.__fo[a])return!1;window.__fo[a]={};return!0};var e=window.cookieRead("s_ppv");e=-1<e.indexOf(",")?e.split(","):[];n=n?n:window.pageName?window.pageName:document.location.href;e[0]=decodeURIComponent(e[0]);window.ppvChange="undefined"===typeof r||1==r?!0:!1;"undefined"!==typeof m&&m.linkType&&"o"===m.linkType||(window.ppvID&&window.ppvID===n||(window.ppvID=n,window.cookieWrite("s_ppv",""),p()),window.p_fo("s_gppvLoad")&&window.addEventListener&&(window.addEventListener("load",p,!1),window.addEventListener("click",p,!1),window.addEventListener("scroll",p,!1)),this._ppvPreviousPage=e[0]?e[0]:"",this._ppvHighestPercentViewed=e[1]?e[1]:"",this._ppvInitialPercentViewed=e[2]?e[2]:"",this._ppvHighestPixelsSeen=e[3]?e[3]:"",this._ppvFoldsSeen=e[4]?e[4]:"",this._ppvFoldsAvailable=e[5]?e[5]:"")};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Uso del complemento

La función `getPercentPageViewed` utiliza los siguientes argumentos:

* **`pid`** (opcional, cadena): Identificador basado en páginas que usted puede correlacionar con los porcentajes que ofrecen las mediciones del complemento.  El valor predeterminado es la variable `pageName`.
* **`ch`** (opcional, booleano): Configúrelo en `false` (o `0`) si no desea que el complemento tenga en cuenta los cambios realizados en el tamaño de una página después de su carga inicial. Si se omite, el valor predeterminado de este argumento es `true`. Adobe recomienda omitir este argumento en la mayoría de los casos.

Llamar a esta función no devuelve nada; en su lugar, establece las siguientes variables:

* `s._ppvPreviousPage`: El nombre de la página anterior que vio el visitante. Las mediciones de desplazamiento finales de la página actual no estarán disponibles hasta que se cargue una página nueva.
* `s._ppvHighestPercentViewed`: El porcentaje más alto de la página anterior que vio el visitante (en altura). El punto más alejado al que se desplazó el visitante en la página anterior. Si toda la página está visible la primera vez que se carga, este valor es `100`.
* `s._ppvInitialPercentViewed`: El porcentaje de la página anterior que era visible cuando se cargó la página. Si toda la página está visible la primera vez que se carga, este valor es `100`.
* `s._ppvHighestPixelsSeen`: El número más elevado de píxeles vistos (en cuanto a altura) al desplazarse hacia abajo el visitante en la página anterior.
* `s._ppvFoldsSeen`: El número más elevado de “pliegues de página” alcanzados al desplazarse hacia abajo el visitante en la página anterior. Esta variable incluye el pliegue “principio de página”. Si toda la página está visible la primera vez que se carga, este valor es `1`.
* `s._ppvFoldsAvailable`: El número total de “pliegues de página” disponibles para desplazarse hacia abajo en la página anterior. Si toda la página está visible la primera vez que se carga, este valor es `1`.

Asigne una o más de estas variables a las eVars para ver los datos de dimensión en los informes.

Este complemento crea una cookie de origen llamada `s_ppv` que contiene los valores anteriores. Caduca al terminar la sesión del explorador.

## Ejemplos

```js
// 1. Runs the getPercentPageViewed function if the page variable is set
// 2. Sets prop1 to the previous value of the page variable
// 3. Sets prop2 to the highest percent viewed, the intial percent, the number of folds viewed, and total number of folds of the previous page
if(s.pageName) getPercentPageViewed();
if(_ppvPreviousPage)
{
  s.prop1 = _ppvPreviousPage;
  s.prop2 = "highestPercentViewed=" + _ppvHighestPercentViewed + " | initialPercentViewed=" + _ppvInitialPercentViewed + " | foldsSeen=" + _ppvFoldsSeen + " | foldsAvailable=" + _ppvFoldsAvailable;
}

// Given prop5 operates as a page type variable:
// 1. Runs the getPercentPageViewed function if prop5 has a value
// 2. Sets prop1 to the previous value of the page variable
// 3. Sets prop2 to the highest percent viewed and the initial percent viewed.
if(s.prop5) getPercentPageViewed(s.prop5);
if(_ppvPreviousPage)
{
  s.prop1 = _ppvPreviousPage;
  s.prop2 = "highestPercentViewed = " + _ppvHighestPercentViewed + " | initialPercentViewed=" + _ppvInitialPercentViewed;
}
```

## Historial de versiones

### 5.0.1 (22 de junio de 2021)

* Se ha corregido un problema por el cual algunos caracteres especiales provocaban que el plug-in se dañara

### 5.0 (19 de marzo de 2021)

* Se ha añadido el número de versión como datos de contexto.

### v4.0 (7 de octubre de 2019)

* Se agregaron las soluciones `s._ppvFoldsSeen` y `s._ppvFoldsAvailable`

### v3.01 (13 de agosto de 2018)

* Se ha corregido un problema en las páginas que tienen varios objetos AppMeasurement en una página

### v3.0 (13 de abril de 2018)

* Versión puntual (compilada de nuevo, con un tamaño de código más pequeño)
* Ahora, en lugar de valores devueltos, el complemento crea variables que asignar a variables de Adobe Analytics

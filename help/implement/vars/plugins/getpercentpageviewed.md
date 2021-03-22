---
title: getPercentPageViewed
description: Recupere el porcentaje de la página que vio el visitante.
translation-type: tm+mt
source-git-commit: f11ad012756b5d42b1b53483c8688e30b4b79c83
workflow-type: tm+mt
source-wordcount: '892'
ht-degree: 98%

---


# Complemento de Adobe: getPercentPageViewed

>[!IMPORTANT]
>
>Adobe Consulting proporciona este complemento por cortesía para ayudarle a sacar el máximo partido a Adobe Analytics. El Servicio de atención al cliente de Adobe no ofrece asistencia técnica con este complemento, incluida la instalación o solución de problemas. Si necesita ayuda con este complemento, póngase en contacto con el administrador de cuentas de su organización. Ellos podrán organizar una reunión con un consultor para ayudarle.

El complemento `getPercentPageViewed` mide la actividad de desplazamiento de un visitante para comprobar cuánto ve de una página antes de pasar a otra. Este complemento no es necesario si las páginas tienen poca altura o si no desea medir la actividad de desplazamiento.

## Instalación del complemento con la extensión de Adobe Experience Platform Launch

Adobe ofrece una extensión que le permite disfrutar de los complementos más utilizados.

1. Inicie sesión en [launch.adobe.com](https://launch.adobe.com) con sus credenciales de Adobe ID.
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

## Instalación del complemento con el editor de código personalizado de Launch

1. Inicie sesión en [launch.adobe.com](https://launch.adobe.com) con sus credenciales de Adobe ID.
1. Haga clic en la propiedad deseada.
1. Vaya a la pestaña [!UICONTROL Extensiones] y, a continuación, haga clic en el botón [!UICONTROL Configurar] en la extensión de Adobe Analytics.
1. Expanda [!UICONTROL Configurar seguimiento con el código personalizado], que muestra el botón [!UICONTROL Abrir editor].
1. Abra el editor de código personalizado y pegue el código del complemento que se proporciona a continuación en la ventana de edición.
1. Guarde y publique los cambios en la extensión de Analytics.

## Instalación del complemento con AppMeasurement

Copie y pegue el siguiente código en cualquier parte del archivo AppMeasurement después de crear una instancia del objeto de seguimiento de Analytics (con [`s_gi`](../functions/s-gi.md)). Conservar los comentarios y los números de versión del código en la implementación ayuda a Adobe a solucionar cualquier posible problema.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getPercentPageViewed v5.0 w/handlePPVevents helper function (Requires AppMeasurement and the p_fo plugin) */
function getPercentPageViewed(pid,ch){var l=pid,p=ch;function m(){if(window.ppvID){var c=Math.max(Math.max(document.body.scrollHeight,document.documentElement.scrollHeight),Math.max(document.body.offsetHeight,document.documentElement.offsetHeight),Math.max(document.body.clientHeight,document.documentElement.clientHeight)),b=window.innerHeight||document.documentElement.clientHeight||document.body.clientHeight,k=(window.pageYOffset||window.document.documentElement.scrollTop||window.document.body.scrollTop)+b,a=Math.min(Math.round(k/c*100),100),n=Math.floor(k/b);b=Math.floor(c/b);var d="";if(!window.cookieRead("s_tp")||decodeURIComponent(window.cookieRead("s_ppv").split(",")[0])!==window.ppvID||window.p_fo(window.ppvID)||1==window.ppvChange&&window.cookieRead("s_tp")&&c!=window.cookieRead("s_tp")){(decodeURIComponent(window.cookieRead("s_ppv").split(",")[0])!==window.ppvID||window.p_fo(window.ppvID+"1"))&&window.cookieWrite("s_ips",k);if(window.cookieRead("s_tp")&&decodeURIComponent(window.cookieRead("s_ppv").split(",")[0])===window.ppvID){window.cookieRead("s_tp");d=window.cookieRead("s_ppv");var f=-1<d.indexOf(",")?d.split(","):[];d=f[0]?f[0]:"";f=f[3]?f[3]:"";var e=window.cookieRead("s_ips");d=d+","+Math.round(f/c*100)+","+Math.round(e/c*100)+","+f+","+n}window.cookieWrite("s_tp",c)}else d=window.cookieRead("s_ppv");var h=d&&-1<d.indexOf(",")?d.split(",",6):[];c=0<h.length?h[0]:escape(window.ppvID);f=1<h.length?parseInt(h[1]):a;e=2<h.length?parseInt(h[2]):a;var l=3<h.length?parseInt(h[3]):k,m=4<h.length?parseInt(h[4]):n;h=5<h.length?parseInt(h[5]):b;0<a&&(d=c+","+(a>f?a:f)+","+e+","+(k>l?k:l)+","+(n>m?n:m)+","+(b>h?b:h));window.cookieWrite("s_ppv",d)}}if("-v"===l)return{plugin:"getPercentPageViewed",version:"5.0"};var e=function(){if("undefined"!==typeof window.s_c_il)for(var c=0,b;c<window.s_c_il.length;c++)if(b=window.s_c_il[c],b._c&&"s_c"===b._c)return b}();"undefined"!==typeof e&&(e.contextData.getPercentPageViewed="5.0");window.pageName="undefined"!==typeof e&&e.pageName||"";window.cookieWrite=window.cookieWrite||function(c,b,a){if("string"===typeof c){var k=window.location.hostname,e=window.location.hostname.split(".").length-1;if(k&&!/^[0-9.]+$/.test(k)){e=2<e?e:2;var d=k.lastIndexOf(".");if(0<=d){for(;0<=d&&1<e;)d=k.lastIndexOf(".",d-1),e--;d=0<d?k.substring(d):k}}g=d;b="undefined"!==typeof b?""+b:"";if(a||""===b)if(""===b&&(a=-60),"number"===typeof a){var f=new Date;f.setTime(f.getTime()+6E4*a)}else f=a;return c&&(document.cookie=encodeURIComponent(c)+"="+encodeURIComponent(b)+"; path=/;"+(a?" expires="+f.toUTCString()+";":"")+(g?" domain="+g+";":""),"undefined"!==typeof window.cookieRead)?window.cookieRead(c)===b:!1}};window.cookieRead=window.cookieRead||function(a){if("string"===typeof a)a=encodeURIComponent(a);else return"";var b=" "+document.cookie,c=b.indexOf(" "+a+"="),e=0>c?c:b.indexOf(";",c);return(a=0>c?"":decodeURIComponent(b.substring(c+2+a.length,0>e?b.length:e)))?a:""};window.p_fo=window.p_fo||function(a){window.__fo||(window.__fo={});if(window.__fo[a])return!1;window.__fo[a]={};return!0};var a=window.cookieRead("s_ppv");a=-1<a.indexOf(",")?a.split(","):[];l=l?l:window.pageName?window.pageName:document.location.href;a[0]=decodeURIComponent(a[0]);window.ppvChange="undefined"===typeof p||1==p?!0:!1;"undefined"!==typeof e&&e.linkType&&"o"===e.linkType||(window.ppvID&&window.ppvID===l||(window.ppvID=l,window.cookieWrite("s_ppv",""),m()),window.p_fo("s_gppvLoad")&&window.addEventListener&&(window.addEventListener("load",m,!1),window.addEventListener("click",m,!1),window.addEventListener("scroll",m,!1)),window._ppvPreviousPage=a[0]?a[0]:"",window._ppvHighestPercentViewed=a[1]?a[1]:"",window._ppvInitialPercentViewed=a[2]?a[2]:"",window._ppvHighestPixelsSeen=a[3]?a[3]:"",window._ppvFoldsSeen=a[4]?a[4]:"",window._ppvFoldsAvailable=a[5]?a[5]:"")};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Uso del complemento

El método `getPercentPageViewed` utiliza los siguientes argumentos:

* **`pid`** (opcional, cadena): Identificador basado en páginas que usted puede correlacionar con los porcentajes que ofrecen las mediciones del complemento.  El valor predeterminado es la variable `pageName`.
* **`ch`** (opcional, booleano): Configúrelo en `false` (o `0`) si no desea que el complemento tenga en cuenta los cambios realizados en el tamaño de una página después de su carga inicial. Si se omite, el valor predeterminado de este argumento es `true`. Adobe recomienda omitir este argumento en la mayoría de los casos.

Llamar a este método no devuelve nada; en su lugar, establece las siguientes variables:

* `s._ppvPreviousPage`: El nombre de la página anterior que vio el visitante. Las mediciones de desplazamiento finales de la página actual no estarán disponibles hasta que se cargue una página nueva.
* `s._ppvHighestPercentViewed`: El porcentaje más alto de la página anterior que vio el visitante (en altura). El punto más alejado al que se desplazó el visitante en la página anterior.
* `s._ppvInitialPercentViewed`: El porcentaje de la página anterior que era visible cuando se cargó la página.
* `s._ppvHighestPixelsSeen`: El número más elevado de píxeles vistos (en cuanto a altura) al desplazarse hacia abajo el visitante en la página anterior.
* `s._ppvFoldsSeen`: El número más elevado de “pliegues de página” alcanzados al desplazarse hacia abajo el visitante en la página anterior. Esta variable incluye el pliegue “principio de página”.
* `s._ppvFoldsAvailable`: El número total de “pliegues de página” disponibles para desplazarse hacia abajo en la página anterior.

Asigne una o más de estas variables a las eVars para ver los datos de dimensión en los informes.

Este complemento crea una cookie de origen llamada `s_ppv` que contiene los valores anteriores. Caduca al terminar la sesión del explorador.

## Llamadas de ejemplo

### Ejemplo 1

El siguiente código...

```js
if(s.pageName) s.getPercentPageViewed();
if(s._ppvPreviousPage)
{
  s.prop1 = s._ppvPreviousPage;
  s.prop2 = "highestPercentViewed=" + s._ppvHighestPercentViewed + " | initialPercentViewed=" + s._ppvInitialPercentViewed + " + | foldsSeen=" + s._ppvFoldsSeen + " | foldsAvailable=" + s._ppvFoldsAvailable;
}
```

* Determina si s.pageName está establecido y, si es así, el código ejecutará la función getPercentPageViewed
* Cuando se ejecuta la función getPercentPageViewed, creará las variables descritas en la sección “Devuelve” anterior
* Si las variables “Devuelve” se han configurado correctamente:
   * El código establece s.prop1 en el valor de s._ppvPreviousPage (es decir, el valor anterior de s.pageName o la página anterior)
   * El código también establece s.prop2 en el mayor porcentaje visto de la página anterior y en el porcentaje inicial visto de la página anterior, junto con la cantidad de pliegues que alcanzó el visitante y el número de pliegues disponibles

**Nota**: Si una página es visible por completo la primera vez que se carga, tanto la dimensión de mayor porcentaje visto como la de porcentaje inicial visto tendrán un valor 100, y tanto los pliegues vistos como los pliegues disponibles tendrán un valor 1.   Cuando una página no es visible por completo la primera vez que se carga pero el visitante no termina de desplazarse hacia abajo antes de pasar a la siguiente página, entonces las dimensiones de mayor porcentaje visto y de porcentaje inicial visto tendrán el mismo valor.

### Ejemplo 2

Supongamos que s.prop5 se ha reservado para capturar un “tipo de página” resumido en lugar del nombre completo de la página.

El siguiente código determina si se ha establecido s.prop5 y, si es así, almacena su valor como “página anterior” para correlacionarlo con las dimensiones de mayor porcentaje visto y de porcentaje inicial visto.  El valor aún se almacenará en la variable s._ppvPreviousPage, pero se puede tratar como si fuera el tipo de página anterior en lugar del nombre de página anterior.

```js
if(s.prop5) s.getPercentPageViewed(s.prop5);
if(s._ppvPreviousPage)
{
  s.prop1 = s._ppvPreviousPage;
  s.prop2 = "highestPercentViewed = " + s._ppvHighestPercentViewed + " | initialPercentViewed=" + s._ppvInitialPercentViewed;
}
```

## Historial de versiones

### 5.0 (19 de marzo de 2021)

* Se ha añadido el número de versión como datos de contexto.

### v4.0 (7 de octubre de 2019)

* Se agregaron las soluciones `s._ppvFoldsSeen` y `s._ppvFoldsAvailable`

### v3.01 (13 de agosto de 2018)

* Se ha corregido un problema en las páginas que tienen varios objetos AppMeasurement en una página

### v3.0 (13 de abril de 2018)

* Versión puntual (compilada de nuevo, con un tamaño de código más pequeño)
* Ahora, en lugar de valores devueltos, el complemento crea variables que asignar a variables de Adobe Analytics

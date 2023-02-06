---
title: getPercentPageViewed
description: Recupere el porcentaje de la página que vio el visitante.
feature: Variables
exl-id: 7a842cf0-f8cb-45a9-910e-5793849bcfb8
source-git-commit: bebd9e9e53c05d697adf52e5a2bdda3ca60796f2
workflow-type: tm+mt
source-wordcount: '644'
ht-degree: 87%

---

# Complemento de Adobe: getPercentPageViewed

>[!IMPORTANT]
>
>Adobe Consulting proporciona este complemento por cortesía para ayudarle a sacar el máximo partido a Adobe Analytics. El Servicio de atención al cliente de Adobe no ofrece asistencia técnica con este complemento, incluida la instalación o solución de problemas. Si necesita ayuda con este complemento, póngase en contacto con el administrador de cuentas de su organización. Ellos podrán organizar una reunión con un consultor para ayudarle.

El complemento `getPercentPageViewed` mide la actividad de desplazamiento de un visitante para comprobar cuánto ve de una página antes de pasar a otra. Este complemento no es necesario si las páginas tienen poca altura o si no desea medir la actividad de desplazamiento.

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
    * Action Type: Initialize getPercentPageViewed
1. Save and publish the changes to the rule.-->

## Instalación del complemento con el editor de código personalizado de 

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
/* Adobe Consulting Plugin: getPercentPageViewed v5.1 */
function getPercentPageViewed(pid,ch){var e=pid,i=ch;if("-v"===e)return{plugin:"getPercentPageViewed",version:"5.1"};var t=function(){if(void 0!==window.s_c_il){for(var e,i=0;i<window.s_c_il.length;i++)if((e=window.s_c_il[i])._c&&"s_c"===e._c)return e}}();function o(){if(window.ppvID){var e=Math.max(Math.max(document.body.scrollHeight,document.documentElement.scrollHeight),Math.max(document.body.offsetHeight,document.documentElement.offsetHeight),Math.max(document.body.clientHeight,document.documentElement.clientHeight)),i=window.innerHeight||document.documentElement.clientHeight||document.body.clientHeight,t=(window.pageYOffset||window.document.documentElement.scrollTop||window.document.body.scrollTop)+i,o=Math.min(Math.round(t/e*100),100),n=Math.floor(e/i),p=Math.floor(t/i),s="";if(!window.cookieRead("s_tp")||decodeURIComponent(window.cookieRead("s_ppv").split(",")[0])!==window.ppvID||window.p_fo(window.ppvID)||!0==window.ppvChange&&window.cookieRead("s_tp")&&e!=window.cookieRead("s_tp")){if((decodeURIComponent(window.cookieRead("s_ppv").split(",")[0])!==window.ppvID||window.p_fo(window.ppvID+"1"))&&window.cookieWrite("s_ips",t),window.cookieRead("s_tp")&&decodeURIComponent(window.cookieRead("s_ppv").split(",")[0])===window.ppvID){window.cookieRead("s_tp");var a=window.cookieRead("s_ppv"),c=a.indexOf(",")>-1?a.split(","):[],d=c[0]?c[0]:"",r=window.cookieRead("s_ips"),l=c[3]?c[3]:"";s=d+","+Math.round(r/e*100)+","+Math.round(l/e*100)+","+o+","+l+","+n+","+p}window.cookieWrite("s_tp",e)}else s=window.cookieRead("s_ppv");var v=s&&s.indexOf(",")>-1?s.split(",",7):[],f=v.length>0?v[0]:encodeURIComponent(window.ppvID),$=v.length>1?parseInt(v[1]):o,h=v.length>2?parseInt(v[2]):o,u=v.length>4?parseInt(v[4]):t,k=v.length>5?parseInt(v[5]):n,m=v.length>6?parseInt(v[6]):p;o>0&&(s=f+","+$+","+(o>h?o:h)+","+o+","+(t>u?t:u)+","+(n>k?n:k)+","+(p>m?p:m)),window.cookieWrite("s_ppv",s)}}void 0!==t&&(t.contextData.getPercentPageViewed="5.1"),window.pageName=void 0!==t&&t.pageName||"",window.cookieWrite=window.cookieWrite||function(e,i,t){if("string"==typeof e){if(g=function(){var e=window.location.hostname,i=window.location.hostname.split(".").length-1;if(e&&!/^[0-9.]+$/.test(e)){i=2<i?i:2;var t=e.lastIndexOf(".");if(0<=t){for(;0<=t&&1<i;)t=e.lastIndexOf(".",t-1),i--;t=0<t?e.substring(t):e}}return t}(),i=void 0!==i?""+i:"",t||""===i){if(""===i&&(t=-60),"number"==typeof t){var o=new Date;o.setTime(o.getTime()+6e4*t)}else o=t}return!!e&&(document.cookie=encodeURIComponent(e)+"="+encodeURIComponent(i)+"; path=/;"+(t?" expires="+o.toUTCString()+";":"")+(g?" domain="+g+";":""),void 0!==window.cookieRead)&&window.cookieRead(e)===i}},window.cookieRead=window.cookieRead||function(e){if("string"!=typeof e)return"";e=encodeURIComponent(e);var i=" "+document.cookie,t=i.indexOf(" "+e+"="),o=0>t?t:i.indexOf(";",t);return(e=0>t?"":decodeURIComponent(i.substring(t+2+e.length,0>o?i.length:o)))?e:""},window.p_fo=window.p_fo||function(e){return window.__fo||(window.__fo={}),!window.__fo[e]&&(window.__fo[e]={},!0)};var n=window.cookieRead("s_ppv"),p=n.indexOf(",")>-1?n.split(","):[];p[0]=p.length>0?decodeURIComponent(p[0]):"",e=e||(window.pageName?window.pageName:document.location.href),void 0===i||!0==i?window.ppvChange=!0:window.ppvChange=!1,void 0!==t&&t.linkType&&"o"===t.linkType||(window.ppvID&&window.ppvID===e||(window.ppvID=e,window.cookieWrite("s_ppv",""),o()),window.p_fo("s_gppvLoad2")&&window.addEventListener&&(window.addEventListener("load",o,!1),window.addEventListener("click",o,!1),window.addEventListener("scroll",o,!1)),this._ppvPreviousPage=p[0]?p[0]:"",this._ppvInitialPercentViewed=p[1]?p[1]:"",this._ppvHighestPercentViewed=p[2]?p[2]:"",this._ppvFinalPercentViewed=p[3]?p[3]:"",this._ppvHighestPixelsSeen=p[4]?p[4]:"",this._ppvFoldsAvailable=p[5]?p[5]:"",this._ppvFoldsSeen=p[6]?p[6]:"")}
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Uso del complemento

La función `getPercentPageViewed` utiliza los argumentos siguientes:

* **`pid`** (opcional, cadena): Variable o valor igual a la página actual. Valores predeterminados de AppMeasurement de Analytics `pageName` O la dirección URL actual si la variable pageName de AppMeasurement no está configurada.
* **`ch`** (opcional, booleano): Configúrelo en `false` (o `0`) si no desea que el complemento tenga en cuenta los cambios realizados en el tamaño de una página después de su carga inicial. Si se omite, el valor predeterminado de este argumento es `true`. Adobe recomienda omitir este argumento en la mayoría de los casos.

Llamar a esta función no devuelve nada; en su lugar, establece las siguientes variables:

* `window._ppvPreviousPage`: El nombre de la página anterior que vio el visitante. Las mediciones de desplazamiento finales de la página actual no estarán disponibles hasta que se cargue una página nueva.
* `window._ppvInitialPercentViewed`: El porcentaje de la página anterior que era visible cuando se cargó la página. Si toda la página está visible la primera vez que se carga, este valor es `100`.
* `window._ppvHighestPercentViewed`: El porcentaje más alto de la página anterior que vio el visitante (en altura). El punto más alejado al que se desplazó el visitante en la página anterior. Si toda la página está visible la primera vez que se carga, este valor es `100`.
* `window._ppvFinalPercentViewed`: El porcentaje de la página anterior que era visible en el momento en que el visitante se movió a la página actual. Este valor será igual o bueno al porcentaje inicial visto y también será igual o menor que el porcentaje más alto visto.
* `window._ppvHighestPixelsSeen`: El número más elevado de píxeles vistos (en cuanto a altura) al desplazarse hacia abajo el visitante en la página anterior.
* `window._ppvFoldsAvailable`: El número total de “pliegues de página” disponibles para desplazarse hacia abajo en la página anterior. Si toda la página está visible la primera vez que se carga, este valor es `1`.
* `window._ppvFoldsSeen`: El número más elevado de “pliegues de página” alcanzados al desplazarse hacia abajo el visitante en la página anterior. Esta variable incluye el pliegue “principio de página”. Si toda la página está visible la primera vez que se carga, este valor es `1`.

Asigne una o más de estas variables a las eVars para ver los datos de dimensión en los informes.

Este complemento crea una cookie de origen llamada `s_ppv` que contiene los valores anteriores. Caduca al terminar la sesión del explorador.

## Ejemplos

```js
// 1. Runs the getPercentPageViewed function if the page variable is set
// 2. Sets prop1 to the previous value of the page variable
// 3. Sets prop2 to the intial percent, the highest percent, and the final percent viewed; the number of folds available on the page, and the number of folds viewed ( of the previous page)
if(s.pageName) getPercentPageViewed();
if(_ppvPreviousPage)
{
  s.prop1 = _ppvPreviousPage;
  s.prop2 = "initialPercent=" + _ppvInitialPercent + " | highestPercent=" + _ppvHighestPercentViewed + " | finalPercent=" + _ppvFinalPercentViewed + " | foldsAvailable=" + _ppvFoldsAvailable + " | foldsSeen=" + _ppvFoldsSeen;
}

// Given prop5 operates as a page type variable:
// 1. Runs the getPercentPageViewed function if prop5 has a value
// 2. Sets prop1 to the previous value of the page type
// 3. Sets prop2 to the initial percent viewed and the highest percent viewed.
if(s.prop5) getPercentPageViewed(s.prop5);
if(_ppvPreviousPage)
{
  s.prop1 = _ppvPreviousPage;
  s.prop2 = "initialPercent=" + _ppvInitialPercent + " | highestPercent=" + _ppvHighestPercentViewed;
}
```

## Historial de versiones

### 5.1 (8 de diciembre de 2022)

* Se ha añadido la variable `_finalPercentViewed` solución

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

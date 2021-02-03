---
title: getPercentPageViewed
description: Recupere el porcentaje de la página que vio el visitante.
translation-type: tm+mt
source-git-commit: 69c1daa9dbf3bbf39072cc7104f2dd32fb95eb79
workflow-type: tm+mt
source-wordcount: '781'
ht-degree: 100%

---


# Complemento de Adobe: getPercentPageViewed

>[!IMPORTANT]
>
>Adobe Consulting proporciona este complemento por cortesía para ayudarle a sacar el máximo partido a Adobe Analytics. El Servicio de atención al cliente de Adobe no ofrece asistencia técnica con este complemento, incluida la instalación o solución de problemas. Si necesita ayuda con este complemento, póngase en contacto con el administrador de cuentas de su organización. Ellos podrán organizar una reunión con un consultor para ayudarle.

El complemento `getPercentPageViewed` mide la actividad de desplazamiento de un visitante para comprobar cuánto ve de una página antes de pasar a otra. Este complemento no es necesario si las páginas tienen poca altura o si no desea medir la actividad de desplazamiento.

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
/* Adobe Consulting Plugin: getPercentPageViewed v4.0 w/handlePPVevents helper function (Requires p_fo plug-in) */
s.getPercentPageViewed=function(pid,ch){var s=this,a=s.c_r("s_ppv");a=-1<a.indexOf(",")?a.split(","):[];a[0]=s.unescape(a[0]); pid=pid?pid:s.pageName?s.pageName:document.location.href;s.ppvChange="undefined"===typeof ch||!0==ch?!0:!1;if("undefined"=== typeof s.linkType||"o"!==s.linkType)s.ppvID&&s.ppvID===pid||(s.ppvID=pid,s.c_w("s_ppv",""),s.handlePPVevents()), s.p_fo("s_gppvLoad") &&window.addEventListener&&(window.addEventListener("load",s.handlePPVevents,!1),window.addEventListener("click",s.handlePPVevents, !1),window.addEventListener("scroll",s.handlePPVevents,!1)),s._ppvPreviousPage=a[0]?a[0]:"",s._ppvHighestPercentViewed=a[1]?a[1]:"",s._ppvInitialPercentViewed=a[2]?a[2]:"",s._ppvHighestPixelsSeen=a[3]?a[3]:"",s._ppvFoldsSeen=a[4]?a[4]:"",s._ppvFoldsAvailable=a[5]?a[5]:""};

/* Adobe Consulting Plugin: handlePPVevents helper function (for getPercentPageViewed v4.0 Plugin) */
s.handlePPVevents=function(){if("undefined"!==typeof s_c_il){for(var c=0,g=s_c_il.length;c<g;c++)if(s_c_il[c]&& (s_c_il[c].getPercentPageViewed||s_c_il[c].getPreviousPageActivity)){var s=s_c_il[c];break}if(s&&s.ppvID){var f=Math.max (Math.max(document.body.scrollHeight,document.documentElement.scrollHeight),Math.max(document.body.offsetHeight, document.documentElement.offsetHeight),Math.max(document.body.clientHeight,document.documentElement.clientHeight)),h= window.innerHeight||document.documentElement.clientHeight||document.body.clientHeight;c=(window.pageYOffset|| window.document.documentElement.scrollTop||window.document.body.scrollTop)+h;g=Math.min(Math.round(c/f*100),100);var k=Math.floor(c/h);h=Math.floor(f/h);var d="";if(!s.c_r("s_tp")||s.unescape(s.c_r("s_ppv").split(",")[0])!==s.ppvID||s.p_fo(s.ppvID) ||1==s.ppvChange&&s.c_r("s_tp")&&f!=s.c_r("s_tp")){(s.unescape(s.c_r("s_ppv").split(",")[0])!==s.ppvID||s.p_fo(s.ppvID+"1"))&&s.c_w("s_ips",c);if(s.c_r("s_tp")&&s.unescape(s.c_r("s_ppv").split(",")[0])===s.ppvID){s.c_r("s_tp");d=s.c_r("s_ppv");var e=-1< d.indexOf(",")?d.split(","):[];d=e[0]?e[0]:"";e=e[3]?e[3]:"";var l=s.c_r("s_ips");d=d+","+Math.round(e/f*100)+","+Math.round(l/ f*100)+","+e+","+k}s.c_w("s_tp",f)}else d=s.c_r("s_ppv");var b=d&&-1<d.indexOf(",")?d.split(",",6):[];f=0<b.length?b[0]: escape(s.ppvID);e=1<b.length?parseInt(b[1]):g;l=2<b.length?parseInt(b[2]):g;var m=3<b.length?parseInt(b[3]):c,n=4<b.length? parseInt(b[4]):k;b=5<b.length?parseInt(b[5]):h;0<g&&(d=f+","+(g>e?g:e)+","+l+","+(c>m?c:m)+","+(k>n?k:n)+","+(h>b?h:b)); s.c_w("s_ppv",d)}}};

/* Adobe Consulting Plugin: p_fo (pageFirstOnly) v2.0 */
s.p_fo=function(on){var s=this;s.__fo||(s.__fo={});if(s.__fo[on])return!1;s.__fo[on]={};return!0};
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

### v4.0 (7 de octubre de 2019)

* Se agregaron las soluciones `s._ppvFoldsSeen` y `s._ppvFoldsAvailable`

### v3.01 (13 de agosto de 2018)

* Se ha corregido un problema en las páginas que tienen varios objetos AppMeasurement en una página

### v3.0 (13 de abril de 2018)

* Versión puntual (compilada de nuevo, con un tamaño de código más pequeño)
* Ahora, en lugar de valores devueltos, el complemento crea variables que asignar a variables de Adobe Analytics

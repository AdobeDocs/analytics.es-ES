---
description: 'Mide la actividad de desplazamiento de un visitante para comprobar cuánto ve de una página antes de pasar a otra. Este complemento permite determinar la cantidad promedio de contenido que ven los usuarios. De este modo puede optimizar la longitud y el diseño de las páginas en función del comportamiento de los usuarios. '
keywords: Implementación de Analytics
seo-description: 'Mide la actividad de desplazamiento de un visitante para comprobar cuánto ve de una página antes de pasar a otra. Este complemento permite determinar la cantidad promedio de contenido que ven los usuarios. De este modo puede optimizar la longitud y el diseño de las páginas en función del comportamiento de los usuarios. '
seo-title: getPercentPageViewed
solution: Analytics
subtopic: Complementos
title: getPercentPageViewed
topic: Desarrollador e implementación
uuid: 1751 dcdb -699 f -4 bd 1-8 bcb -5 e 62 fa 24896 a
translation-type: tm+mt
source-git-commit: ee0cb9b64a3915786f8f77d80b55004daa68cab6

---


# getPercentPageViewed

El complemento getpercentpageviewed mide la actividad de desplazamiento de un visitante para ver la cantidad de páginas que vio el visitante antes de pasar a otra página.

>[!NOTE]
>No necesita utilizar el complemento getpercentpageviewed si las páginas Web son pequeñas y no es necesario medir el desplazamiento de los visitantes. Asimismo, si solo desea medir la actividad de desplazamiento en páginas de salida, no podrá utilizar este complemento.

## Requisitos previos

Debe tener appmeasurement y el complemento handleppvevents para ejecutar el complemento getpercentpageviewed.

## Implementación

To implement this plugin, copy and paste the code to anywhere within the **[!UICONTROL Plugins]** section of the [!DNL AppMeasurement] file.

>[!NOTE]
>Agregar los comentarios y las versiones de versión negrita del código al archivo appmeasurement ayuda a Adobe Consulting a solucionar los problemas de implementación potenciales.

You can run the `getPercentPageViewed` function as needed within the doPlugins function (see example calls below.)

## Argumentos para pasar

| Argumento | Definición |
|---|---|
| pid (opcional, string) | Identificador de página correlacionado con los porcentajes proporcionados por las mediciones de complemento. Toma el valor predeterminado de la variable pagename de Analytics o de la URL si no está configurada la variable pagename |
| ch (opcional, booleano) | " True "es el valor recomendado/predeterminado para este argumento. Establezca este valor igual a "false" si no desea que este complemento tenga en cuenta los cambios realizados en el tamaño de una página después de su carga inicial, debido a código de SPA, HTML dinámico, etc. |

## Devuelve

El complemento getpercentpageviewed no devuelve nada. Lo que hace es establecer las variables siguientes dentro del objeto AppMeasurement:

* `s._ppvPreviousPage`: El nombre de la página anterior vista (porque las mediciones finales no están disponibles hasta que se carga una nueva página).
* `s._ppvHighestPercentViewed`: El porcentaje más alto de la página anterior que el visitante vio (en sentido de altura). Es decir, el punto más cercano que el visitante desplazó hacia abajo en la página anterior.
* `s._ppvInitialPercentViewed`: Porcentaje de la página anterior que estaba visible cuando se cargó por primera vez la página anterior.
* `s._ppvHighestPixelSeen`: el número más elevado de píxeles vistos (en cuanto a altura) al desplazarse hacia abajo el visitante en la página anterior.

## Cookies

The getPercentPageViewed plugin creates a cookie, called `s_ppv`, that is passed from page to page. El contenido de la cookie contiene los valores insertados en las cuatro variables descritas anteriormente y caduca al final de la sesión.

## Llamadas de ejemplo

**Llamada de muestra 1**

```
if(s.pageName) s.getPercentPageViewed();
if(s._ppvPreviousPage)
{
s.prop1 = s._ppvPreviousPage;
s.prop2 = "highestPercentViewed=" + s._ppvHighestPercentViewed + "initialPercentViewed="s._ppvInitialPercentViewed;
}  
```

Ejemplo de código anterior:
* Determina si s. pagename está establecido y si es así, el código ejecutará la función getpercentpageviewed.
* When the `getPercentPageViewed` function runs, it creates the variables described in the "Returns" section above.
* Si las variables "Devuelve" se establecieron correctamente:

   * The code sets s.prop1 equal to the value of `s._ppvPreviousPag`e (i.e. the previous value of `s.pageName`, or the previous page.)
   * El código también establece s. prop 2 como el porcentaje más alto visto de la página anterior y el porcentaje inicial visto de la página anterior.

>[!NOTE]
>Si una página entera está visible cuando se carga por primera vez, tanto el Porcentaje más alto visto como el Porcentaje Porcentaje inicial pueden ser iguales a 100. Sin embargo, si una página entera no está visible cuando se carga por primera vez, pero el visitante nunca desplaza hacia abajo la página antes de pasar a la página siguiente, tanto el Porcentaje más alto visto como el Porcentaje Porcentaje inicial visualizado serán iguales al mismo valor.

**Llamada de muestra 2**

Supongamos que s. prop 5 se ha separado para capturar un "tipo de página" resumido en lugar del nombre completo de la página.

El siguiente código determina si se ha establecido s. prop 5 y, si es así, almacena su valor como «página anterior» para correlacionar con el porcentaje más alto visto y las dimensiones Porcentaje inicial visto. The value is still stored in the `s._ppvPreviousPage` variable but can be treated as if it were the previous page type instead of the previous page name.

```
if(s._ppvPreviousPage)
{
s.prop1 = s._ppvPreviousPage;
s.prop2 = "highestPercentViewed = " + s._ppvHighestPercentViewed + " | initialPercentViewed=" + s._ppvInitialPercentViewed;
}  
```

## Sustitución de objetos S

Cuando cree una instancia del objeto de biblioteca principal de appmeasurement con un nombre distinto de "s", cambie la siguiente parte del código de complemento de esta:

`s.getPercentPageViewed=function(pid,ch)`

a esto:

`[objectname].getPercentPageViewed=function(pid,ch)`

## Código que implementar

Sección de complementos: agregue el código siguiente al área del archivo `s_code.js` etiquetada SECCIÓN DE COMPLEMENTOS. No realice ningún cambio en esta parte del código de complemento.

```
/******************************************* BEGIN CODE TO DEPLOY *******************************************/ 
/* Adobe Consulting Plugin: getPercentPageViewed v3.01 w/handlePPVevents helper function (Requires AppMeasurement and p_fo plugin) */
s.getPercentPageViewed=function(pid,ch){var s=this,a=s.c_r("s_ppv");a=-1<a.indexOf(",")?a.split(","):[];a[0]=s.unescape(a[0]); 
pid=pid?pid:s.pageName?s.pageName:document.location.href;s.ppvChange=ch?ch:!0;if("undefined"===typeof s.linkType||"o"!==
s.linkType)s.ppvID&&s.ppvID===pid||(s.ppvID=pid,s.c_w("s_ppv",""),s.handlePPVevents()),s.p_fo("s_gppvLoad")&&window
.addEventListener&&(window.addEventListener("load",s.handlePPVevents,!1),window.addEventListener("click",s.handlePPVevents, !1),window.addEventListener("scroll",s.handlePPVevents,!1),window.addEventListener("resize",s.handlePPVevents,!1)),s._ppvPreviousPage
=a[0]?a[0]:"",s._ppvHighestPercentViewed=a[1]?a[1]:"",s._ppvInitialPercentViewed=a[2]?a[2]:"",s._ppvHighestPixelsSeen=a[3]?a[3]:""}; 

/* Adobe Consulting Plugin: handlePPVevents helper function (for getPercentPageViewed v3.01 Plugin) */ 
s.handlePPVevents=function(){if("undefined"!==typeof s_c_il){for(var c=0,d=s_c_il.length;c<d;c++)if(s_c_il[c]&&s_c_il[c].getPercentPageViewed){var a=s_c_il[c];break}if(a&&a.ppvID){var f=Math.max(Math.max(document.body.scrollHeight,document.documentElement.scrollHeight),Math.max(document.body.offsetHeight,document.documentElement.offsetHeight),Math.max(document.
body.clientHeight,document.documentElement.clientHeight));c=(window.pageYOffset||window.document.documentElement.scrollTop|
|window.document.body.scrollTop)+(window.innerHeight||document.documentElement.clientHeight||document.body.clientHeight);d=Math.min(Math.round
(c/f*100),100);var e="";!a.c_r("s_tp")||a.unescape(a.c_r("s_ppv").split(",")[0])!==a.ppvID||1==a.ppvChange&&
a.c_r("s_tp")&&f!= a.c_r("s_tp")?(a.c_w("s_tp",f),a.c_w("s_ppv","")):e=a.c_r("s_ppv");var b=e&&-1<e.indexOf(",")?e.split(",",4):[];f=0<b.length?b[0]:escape(a.ppvID);var g=1<b.length?parseInt(b[1]):d,h=2<b.length?parseInt(b[2]):d;b=3<b.length?parseInt(b[3]):c;0<d&&(e=f+","+(d>g?d:g)+","+h+","+(c>b?c:b));a.c_w("s_ppv",e)}}}; 

/* Adobe Consulting Plugin: p_fo (pageFirstOnly) v2.0 (Requires AppMeasurement) */ 
s.p_fo=function(on){var s=this;s.__fo||(s.__fo={});if(s.__fo[on])return!1;s.__fo[on]={};return!0}; 
/******************************************** END CODE TO DEPLOY ********************************************/
```

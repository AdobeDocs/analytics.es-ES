---
description: Mide la actividad de desplazamiento de un visitante para comprobar cuánto ve de una página antes de pasar a otra. Este complemento permite determinar la cantidad promedio de contenido que ven los usuarios. De este modo puede optimizar la longitud y el diseño de las páginas en función del comportamiento de los usuarios.
keywords: Analytics Implementation
subtopic: Plug-ins
title: getPercentPageViewed
topic: Developer and implementation
uuid: 1751dcdb-699f-4bd1-8bcb-5e62fa24896a
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# getPercentPageViewed

El complemento getPercentPageViewed mide la actividad de desplazamiento de un visitante para saber qué vio en una página antes de pasar a otra.

>[!NOTE]
>No es necesario utilizar el complemento getPercentPageViewed si las páginas web no son muy extensas y no es necesario medir hasta dónde se desplazan los visitantes. Además, si solo desea medir la actividad de desplazamiento en las páginas de salida, no puede utilizar este complemento.

## Requisitos previos

Para ejecutar el complemento getPercentPageViewed, debe tener AppMeasurement y el complemento de ayuda handlePPVevents.

## Implementación

Para implementar este complemento, copie y pegue el código en cualquier lugar dentro de la sección **[!UICONTROL Complementos]** del archivo [!DNL AppMeasurement].

>[!NOTE]
>Añadir los comentarios en negrita y los números de versión del código al archivo AppMeasurement ayuda al consultor de Adobe a solucionar los problemas de implementación.

Puede ejecutar la función `getPercentPageViewed` según sea necesario dentro de la función doPlugins (consulte las llamadas de ejemplo).

## Argumentos para pasar

| Argumento | Definición |
|---|---|
| pid (opcional, cadena) | Identificador de página que se correlaciona con los porcentajes proporcionados por las mediciones del complemento. Su valor predeterminado es la variable pageName de Analytics o la dirección URL si dicha variable no se ha establecido |
| ch (opcional, booleano) | “True” es el valor recomendado/predeterminado para este argumento. Configúrelo como “false” si no quiere que el complemento tenga en cuenta los cambios realizados en el tamaño de una página después de su carga inicial, debido a código SPA, HTML dinámico, etc. |

## Devuelve

El complemento getPercentPageViewed no devuelve nada. Lo que hace es establecer las variables siguientes dentro del objeto AppMeasurement:

* `s._ppvPreviousPage`: Nombre de la página anterior vista (porque las medidas finales no están disponibles hasta que se cargue una página nueva).
* `s._ppvHighestPercentViewed`: El porcentaje más alto de la página anterior que vio el visitante (en altura). En otras palabras, el punto más alejado que el visitante se desplazó hacia abajo en la página anterior.
* `s._ppvInitialPercentViewed`: El porcentaje de la página anterior que era visible cuando se cargó la página.
* `s._ppvHighestPixelSeen`: el número más elevado de píxeles vistos (en cuanto a altura) al desplazarse hacia abajo el visitante en la página anterior.

## Cookies

El complemento getPercentPageViewed crea una cookie, llamada `s_ppv`, que se pasa de página en página. El contenido de la cookie contiene los valores insertados en las cuatro variables descritas anteriormente y caducan al final de la sesión.

## Llamadas de ejemplo

**Ejemplo de llamada 1**

```
if(s.pageName) s.getPercentPageViewed();
if(s._ppvPreviousPage)
{
s.prop1 = s._ppvPreviousPage;
s.prop2 = "highestPercentViewed=" + s._ppvHighestPercentViewed + "initialPercentViewed="s._ppvInitialPercentViewed;
}  
```

Ejemplo de código anterior:
* Determina si s.pageName está establecido y, si es así, el código ejecutará la función getPercentPageViewed.
* Cuando se ejecuta la función `getPercentPageViewed`, crea las variables descritas en la sección “Devuelve” anterior.
* Si las variables “Devuelve” se configuraron correctamente:

   * El código establece s.prop1 igual al valor de `s._ppvPreviousPag`e (es decir, el valor anterior de `s.pageName` o la página anterior).
   * El código también establece s.prop2 en el porcentaje más alto visto de la página anterior y en el porcentaje inicial visto de la página anterior.

>[!NOTE]
>Si toda una página está visible la primera vez que se carga, las dimensiones Mayor porcentaje visto y Porcentaje inicial visto serían iguales a 100. Sin embargo, si una página entera no está visible cuando se carga por primera vez, pero el visitante nunca se desplaza hacia abajo por la página antes de pasar a la página siguiente, las dimensiones Mayor porcentaje visto y Porcentaje inicial visto serán iguales al mismo valor.

**Ejemplo de llamada 2**

Supongamos que s.prop5 se ha reservado para capturar un “tipo de página” resumido en lugar del nombre completo de la página.

El siguiente código determina si se ha establecido s.prop5 y, si es así, almacena su valor como la “página anterior” para correlacionarlo con el porcentaje más alto visto y las dimensiones del porcentaje inicial visto. El valor aún se almacena en la variable `s._ppvPreviousPage`, pero se puede tratar como si fuera el tipo de página anterior en lugar del nombre de página anterior.

```
if(s._ppvPreviousPage)
{
s.prop1 = s._ppvPreviousPage;
s.prop2 = "highestPercentViewed = " + s._ppvHighestPercentViewed + " | initialPercentViewed=" + s._ppvInitialPercentViewed;
}  
```

## Sustitución del objeto S

Al crear una instancia del objeto de biblioteca principal de AppMeasurement con un nombre distinto de “s”, cambie la siguiente parte del código del complemento de esta forma:

`s.getPercentPageViewed=function(pid,ch)`

por esto:

`[objectname].getPercentPageViewed=function(pid,ch)`

## Código para implementar

Sección de complementos: agregue el código siguiente al área del archivo `s_code.js` con el nombre SECCIÓN DE COMPLEMENTOS. No realice ningún cambio en esta parte del código de complemento.

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
body.clientHeight,document.documentElement.clientHeight));c=(window.pageYOffset||window.document.documentElement.scrollTop||window.document.body.scrollTop)+(window.innerHeight||document.documentElement.clientHeight||document.body.clientHeight);d=Math.min(Math.round
(c/f*100),100);var e="";!a.c_r("s_tp")||a.unescape(a.c_r("s_ppv").split(",")[0])!==a.ppvID||1==a.ppvChange&&
a.c_r("s_tp")&&f!= a.c_r("s_tp")?(a.c_w("s_tp",f),a.c_w("s_ppv","")):e=a.c_r("s_ppv");var b=e&&-1<e.indexOf(",")?e.split(",",4):[];f=0<b.length?b[0]:escape(a.ppvID);var g=1<b.length?parseInt(b[1]):d,h=2<b.length?parseInt(b[2]):d;b=3<b.length?parseInt(b[3]):c;0<d&&(e=f+","+(d>g?d:g)+","+h+","+(c>b?c:b));a.c_w("s_ppv",e)}}}; 

/* Adobe Consulting Plugin: p_fo (pageFirstOnly) v2.0 (Requires AppMeasurement) */ 
s.p_fo=function(on){var s=this;s.__fo||(s.__fo={});if(s.__fo[on])return!1;s.__fo[on]={};return!0}; 
/******************************************** END CODE TO DEPLOY ********************************************/
```

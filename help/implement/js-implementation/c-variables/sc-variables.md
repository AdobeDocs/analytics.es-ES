---
description: Analytics proporciona varias variables para recopilar los datos que necesita. Por ejemplo, el valor de la variable pageName es el nombre de la página web para la que se crea el informe. En esta sección se describen las variables que admite AppMeasurement.
keywords: Analytics Implementation;appmeasurement variables
subtopic: Variables
title: Resumen de las variables
topic: Developer and implementation
uuid: 067d0135-572a-4a44-af9e-445d3c4e9271
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Resumen de las variables

Analytics proporciona varias variables para recopilar los datos que necesita. Por ejemplo, el valor de la variable pageName es el nombre de la página web para la que se crea el informe. En esta sección se describen las variables que admite AppMeasurement.

Para obtener más información sobre las variables de página, vaya [aquí](/help/implement/js-implementation/page-variables/page-variables.md).
Para obtener más información sobre las variables de configuración, vaya [aquí](/help/implement/js-implementation/c-variables/configuration-variables.md).

## Cómo establecer variables

AppMeasurement requiere que todas las variables de configuración estén establecidas antes de la llamada inicial a la función de seguimiento, *`t()`*. Si las variables de configuración se configuran después de la llamada a *`t()`*, pueden producirse resultados inesperados.

Las variables de configuración se establecen dentro de la función *`doPlugins`*, a la que se llama durante la ejecución de la función track. La variable de configuración específica que causa este problema es *`trackInlineStats`*, que habilita la recopilación de datos de ClickMap. Esto deja el módulo de ClickMap en un estado indeterminado, que hace que la primera llamada de seguimiento anexe la cadena “Indefinido” a la señalización de Adobe Analytics, afectando al código de divisa.

Para resolver este problema, mueva todas las variables de configuración encima de la función doPlugins.

```
/************************** CONFIG SECTION **************************/ 
/* Ensure these variables are correct before deploying */ 
var s_account="[INSERT-REPORT-SUITE-ID-HERE]" 
var s=s_gi(s_account) 
s.trackingServer="[INSERT-TRACKING-SERVER-HERE]" 
s.visitorNamespace="[INSERT-VISITOR-NAMESPACE-HERE]" 
s.charSet="ISO-8859-1" 
s.currencyCode="USD" 
s.trackDownloadLinks=true 
s.trackExternalLinks=true 
s.trackInlineStats=true 
s.linkDownloadFileTypes="exe,zip,wav,mp3,mov,mpg,avi,wmv,doc,pdf,xls" 
s.linkInternalFilters="javascript:,three,two,one,dev16,.,nike" 
s.linkLeaveQueryString=false 
s.linkTrackVars="None" 
s.linkTrackEvents="None" 
s.debugTracking=true 
 
s.usePlugins=true; 
function s_doPlugins(s) { 
    //add your custom plugin code here 
} 
s.doPlugins=s_doPlugins; 
 
/* 
============== DO NOT ALTER ANYTHING BELOW THIS LINE ! =============== 
 
AppMeasurement for JavaScript version: 1.5.3 
Copyright 1996-2016 Adobe, Inc. All Rights Reserved 
More info available at https://www.omniture.com 
*/ 
function AppMeasurement(){var a=this;a.version="1.5.3";var k=window;k.s_c_in||(k.s_c_il=[],k.s_c_in=0);a._il=k.s_c_il;a._in=k.s_c_in;a._il[a._in]=a;k.s_c_in++;a._c="s_c";var q=k.AppMeasurement.zb;q||(q=null);var r=k,n,t;try{for(n=r.parent,t=r.location;n&&n.location&&t&&""+n.location!=""+t&&r.location&&""+n.location!=""+r.location&&n.location.host==t.host;)r=n,n=r.parent}catch(u){}a.ob=function(a){try{console.log(a)}catch(b){}};a.za=function(a){return""+parseInt(a)==""+a};a.replace=function(a,b,d){return!a|| 
0>a.indexOf(b)?a:a.split(b).join(d)};a.escape=function(c){var b,d;if(!c)return c;c=encodeURIComponent(c);for(b=0;7>b;b++)d="+~!*()'".substring(b,b+1),0<=c.indexOf(d)&&(c=a.replace(c,d,"%"+d.charCodeAt(0).toString(16).toUpperCase()));return c};a.unescape=function(c){if(!c)return c;c=0<=c.indexOf("+")?a.replace(c,"+"," "):c;try{return decodeURIComponent(c)}catch(b){}return unescape(c)};a.gb=function(){var c=k.location.hostname,b=a.fpCookieDomainPeriods,d;b||(b=a.cookieDomainPeriods);if(c&&!a.cookieDomain&& 
```


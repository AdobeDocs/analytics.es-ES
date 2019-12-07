---
description: Devuelve el valor de un parámetro de cadena de consulta especificado, si se encuentra en la dirección URL de la página. Puesto que los datos importantes (por ejemplo, códigos de seguimiento de campañas, palabras clave de búsqueda interna, etc.) están disponibles en la cadena de consulta en una página, getQueryParam ayuda a capturar los datos en variables de Analytics.
keywords: Analytics Implementation
subtopic: Plug-ins
title: getQueryParam
topic: Developer and implementation
uuid: ba202756-c728-4ebc-8fd9-5bc29a9f673b
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# getQueryParam

Devuelve el valor de un parámetro de cadena de consulta especificado, si se encuentra en la dirección URL de la página. Puesto que los datos importantes (por ejemplo, códigos de seguimiento de campañas, palabras clave de búsqueda interna, etc.) están disponibles en la cadena de consulta en una página, getQueryParam ayuda a capturar los datos en variables de Analytics.

>[!IMPORTANT]
>
>Este complemento solo se usa en el código H. [AppMeasurement para JavaScript](/help/implement/js-implementation/c-appmeasurement-js/appmeasure-mjs.md) proporciona esta funcionalidad de forma nativa mediante [Util.getQueryParam](/help/implement/js-implementation/util-getqueryparam.md).

Una vez instalado en el código de [!DNL AppMeasurement] para JavaScript, el complemento se configura seleccionando una variable de [!DNL Analytics] que se rellenará con datos encontrados en la cadena de consulta y especificando qué valores de la cadena de consulta se van a capturar. El complemento detecta la cadena de consulta especificada, si está presente, y rellena la variable seleccionada con su valor. Si no se encuentra un parámetro de cadena de consulta con ese valor, se devuelve una cadena vacía. Si existe un parámetro de cadena de consulta pero no dispone de un valor (como param1 en `?param1&param2=value`), se devolverá el valor *`true`*.

> [!NOTE] El código base para el complemento debe estar instalado en el código de [!DNL AppMeasurement] para JavaScript para que los ejemplos siguientes funcionen.

Si desea utilizar *`s.campaign`* para capturar los códigos de seguimiento de campaña disponibles como valores del parámetro de consulta *`cid`*, debe introducir lo siguiente en la función *`doPlugins()`* de [!DNL AppMeasurement] para el código de JavaScript:

`s.campaign=s.getQueryParam('cid')`

En este ejemplo, si el usuario llegó a una página de aterrizaje de un sitio cuya URL era [!DNL https://www.yoursite.com/index.html?cid=123456], entonces *`s.campaign`* tendría el valor *123456*. Esto puede verse con el depurador [!DNL DigitalPulse], que debería mostrar *v0=123456* como parte de la solicitud de imagen.

> [!NOTE] El parámetro *`cid`* y demás se utilizan como ejemplos. Puede sustituirlos por cualquier parámetro de cadena de consulta que exista en el sitio.

El complemento *`getQueryParam`* tiene dos argumentos adicionales (opciones) que se pueden usar para capturar datos en variables de Analytics:

```js
s.getQueryParam('p','d','u') 
 
where: 
p = comma-separated list of query parameters to locate (can also be a single value with no comma) 
d = delimiter for list of values (in case more than one specified parameter is found) 
u = where to search for value (e.g., document.referrer); set to current page URL by default
```

Si *p* es una lista de parámetros de cadena de consulta y en la URL hay más de un parámetro de cadena de consulta, todos los valores se devolverán en una lista separada por el delimitador, *d*, que puede ser un carácter único o una cadena de caracteres como " : " (espacio-dos puntos-espacio). Si se omite *d*, no se utilizará ningún delimitador entre los valores. Si un parámetro de cadena de consulta debe tener prioridad sobre otro cuando ambos están presentes, utilice una declaración *if* tal como se muestra a continuación.

```js
// cid takes precedence over iid if both exist in the query string 
s.campaign=s.getQueryParam('cid'); 
 if(!s.campaign) 
 s.campaign=s.getQueryParam('iid'); 
```

A partir de la versión *`getQueryParam`* v2.0, el complemento acepta un tercer argumento opcional, *u*, que permite especificar la dirección URL desde la cual se desea extraer los parámetros de cadena de consulta. De forma predeterminada (es decir, si este tercer argumento se omite o se deja en blanco), el complemento utiliza la dirección URL de la página. Por ejemplo, si desea extraer una cadena de consulta del referente, puede utilizar el código siguiente:

```js
// take the query string from the referrer 
 s.eVar1=s.getQueryParam('pid','',document.referrer); 
```

La etiqueta “f” debe usarse en este tercer argumento con marcos si el parámetro de cadena de consulta necesario se encuentra en la barra de direcciones en lugar de en la dirección URL del marco actual:

```js
// take the query string from the parent frame 
 s.eVar1=s.getQueryParam('pid','',f); 
```

Si se utilizan marcos y el parámetro *f*, es recomendable usar el complemento *`getValOnce`* para evitar que el código de seguimiento de campaña se envíe con cada vista de página.

> [!NOTE] Las instrucciones siguientes exigen modificar el código de recopilación de datos en el sitio. Esto puede afectar a la recopilación de datos en el sitio y solamente debe hacerlo un desarrollador con experiencia en el uso y la implementación de [!DNL Analytics].

**Código de complemento**

```js
/******************************************************************** 
 * 
 * Main Plug-in code (should be in Plug-ins section) 
 * 
 *******************************************************************/ 
/* 
 * Plugin: getQueryParam 2.3 
 */ 
s.getQueryParam=new Function("p","d","u","" 
+"var s=this,v='',i,t;d=d?d:'';u=u?u:(s.pageURL?s.pageURL:s.wd.locati" 
+"on);if(u=='f')u=s.gtfs().location;while(p){i=p.indexOf(',');i=i<0?p" 
+".length:i;t=s.p_gpv(p.substring(0,i),u+'');if(t){t=t.indexOf('#')>-" 
+"1?t.substring(0,t.indexOf('#')):t;}if(t)v+=v?d+t:t;p=p.substring(i=" 
+"=p.length?i:i+1)}return v"); 
s.p_gpv=new Function("k","u","" 
+"var s=this,v='',i=u.indexOf('?'),q;if(k&&i>-1){q=u.substring(i+1);v" 
+"=s.pt(q,'&','p_gvf',k)}return v"); 
s.p_gvf=new Function("t","k","" 
+"if(t){var s=this,i=t.indexOf('='),p=i<0?t:t.substring(0,i),v=i<0?'T" 
+"rue':t.substring(i+1);if(p.toLowerCase()==k.toLowerCase())return s." 
+"epa(v)}return ''"); 
 
/******************************************************************** 
 * 
 * Commented example of how to use this is doPlugins function 
 * 
 *******************************************************************/ 
 /* Plugin Example: getQueryParam 2.3 
 //single parameter 
 s.campaign=s.getQueryParam('cid'); 
 
 //multiple parameters 
 s.campaign=s.getQueryParam('cid,sid',':'); 
 
 //non-page URL example 
 s.campaign=s.getQueryParam('cid','',document.referrer); 
 
 //parent frame example 
 s.campaign=s.getQueryParam('cid','','f'); 
 
 */ 
 
/******************************************************************** 
 * 
 * Config variables (should be above doPlugins section) 
 * 
 *******************************************************************/ 
 
 None 
 
/******************************************************************** 
 * 
 * Utility functions that may be shared between plug-ins (name only) 
 * 
 *******************************************************************/ 
  
 None
```


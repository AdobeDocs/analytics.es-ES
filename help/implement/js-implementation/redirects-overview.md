---
description: Las redirecciones llevan al navegador a una nueva ubicación sin interacción del usuario. Se ejecutan en el navegador web (redirección del lado del cliente) o el servidor web (redirección del lado del servidor).
keywords: Implementación de Analytics
seo-description: Las redirecciones llevan al navegador a una nueva ubicación sin interacción del usuario. Se ejecutan en el navegador web (redirección del lado del cliente) o el servidor web (redirección del lado del servidor).
seo-title: Redirecciones y alias
solution: Analytics
subtopic: Redirecciones
title: Redirecciones y alias
topic: Desarrollador e implementación
uuid: 11 f 9 ad 7 a -5 c 45-410 f -86 dd-b 7 d 2 cec 2 aae 3
translation-type: tm+mt
source-git-commit: 76d0ce11d9b560e0df866be9e753804b6fa4bb3d

---


# Redirecciones y alias

Las redirecciones llevan al navegador a una nueva ubicación sin interacción del usuario. Se ejecutan en el navegador web (redirección del lado del cliente) o el servidor web (redirección del lado del servidor).

## Redirects and aliases {#concept_F4F1D53D473947FE8554897332545763}

Las redirecciones llevan al navegador a una nueva ubicación sin interacción del usuario. Se ejecutan en el navegador web (redirección del lado del cliente) o el servidor web (redirección del lado del servidor).

Dado que las redirecciones no requieren interacción del usuario, se suelen ejecutar sin que el usuario lo note. Lo único que indica que se ha producido una redirección es la barra de direcciones del explorador. Esta barra muestra una dirección URL que es distinta del vínculo que solicitó inicialmente el explorador.

Aunque solo existen dos tipos de redirecciones, pueden implementarse de muchas maneras. Por ejemplo: las redirecciones del lado del cliente se pueden producir porque la página web a la que el usuario ha apuntado su navegador contiene un código HTML especial o una secuencia de comandos que redirecciona el navegador a otra dirección URL. Las redirecciones del lado del servidor se producen porque la página contiene secuencias de comandos del lado del servidor o porque el servidor web se ha configurado para dirigir al usuario hacia otra URL.

## Analytics and redirects {#concept_F9132879D0CB4AC1BE7AF45E388A47F7}

[!DNL Analytics] recopila algunos de sus datos del navegador y se basa en algunas de sus propiedades. Dos de esas propiedades, la “dirección URL de referencia” (o “referente”) y la “dirección URL actual” se pueden cambiar por una redirección del lado del servidor. El navegador, al ver que se ha solicitado una dirección URL pero se ha devuelto otra diferente, borra la dirección URL de referencia. El resultado es que la dirección URL de referencia está en blanco y [!DNL Analytics] podría notificar que no existe un referente para la página.

<!-- 

redirects_sc.xml

 -->

Los siguientes ejemplos muestran los efectos sobre la navegación con y sin redirecciones:

* [Ejemplo: navegación sin redirecciones](../../implement/js-implementation/redirects-overview.md#section_5C835A4D665A4625A23333C2C21F152D)
* [Ejemplo: navegación con redirecciones](../../implement/js-implementation/redirects-overview.md#section_921DDD32932847848C4A901ACEF06248)

## Ejemplo: navegación sin redirecciones {#section_5C835A4D665A4625A23333C2C21F152D}

Imagine la siguiente situación hipotética en la que el usuario no se topa con ninguna redirección:

1. El usuario dirige el navegador a `www.google.com`**, escribe “billetes avión descuento” en el campo de búsqueda y luego hace clic en el botón[!UICONTROL Buscar].**
1. The browser displays the search results including a link to your site, [!DNL https://www.flywithus.com/]. After displaying the search results, the browser's address bar displays the search terms that the user entered in the search field ( `https://www.google.com/search?hl=en&ie=UTF-8&q=discount+airline+tickets`). Observe que los términos de búsqueda se incluyen en los parámetros de la cadena de consulta de la dirección URL que están después de `https://www.google.com/search?`.
1. The user clicks the link to your hypothetical site [!DNL https://www.flywithus.com/]. When the user clicks this link and lands on the [!DNL flywithus.com] website, [!DNL Analytics] uses JavaScript to collect the referring URL ( `https://www.google.com/search?hl=en&ie=UTF-8&q=discount+airline+tickets`) as well as the current URL ( `https://www.flywithus.com/`).
1. [!DNL Analytics] informa la información recopilada durante esta interacción en varios informes, como Dominios [!UICONTROL de referencia], [!UICONTROL Motores de búsqueda]y [!DNL Search Keywords].

## Ejemplo: navegación con redirecciones {#section_921DDD32932847848C4A901ACEF06248}

Las redirecciones pueden hacer que el navegador borre la verdadera dirección URL de referencia. Imagine la siguiente situación:

1. User points his or her browser to `https://www.google.com`, and types, *discount airline tickets* into the search field, and then clicks the **[!UICONTROL Search]** button.
1. The browser window's address bar displays the search terms that the user typed into the search field `https://www.google.com/search?hl=en&ie=UTF-8&q=discount+airline+tickets`. Observe que los términos de búsqueda se incluyen en los parámetros de la cadena de consulta de la dirección URL que están después de `https://www.google.com/search?`. The browser also displays a page that contains the search results including a link to one of your domain names: [!DNL https://www.flytohawaiiforfree.com/]. This *vanity* domain is configured to redirect the user to `https://www.flywithus.com/`.
1. The user clicks on the link `https://www.flytohawaiiforfree.com/` and is redirected by the server to your main site, `https://www.flywithus.com`. Cuando se produce la redirección, se pierden datos importantes para la recopilación de datos de [!DNL Analytics] porque el explorador borra la dirección URL de referencia. Por ello, se pierde la información de la búsqueda original que se usa en los informes de [!DNL Analytics] (por ejemplo: [!UICONTROL Dominios de referencia], [!UICONTROL Motores de búsqueda] y [!UICONTROL Palabras clave de búsqueda]).

[Implementación de redirecciones](../../implement/js-implementation/redirects-overview.md#concept_5EC2EE9677A44CC5B90A38ECF28152E7) describe cómo aprovechar las variables de [!DNL Analytics] para captar los datos que se pierden en la redirección. En particular, la sección explica cómo solucionar la situación de los “billetes de avión con descuento” que se ha descrito más arriba.

## Implement redirects {#concept_5EC2EE9677A44CC5B90A38ECF28152E7}

Para captar los datos de [!DNL Analytics][!DNL AppMeasurement] provenientes de las redirecciones, es necesario realizar cuatro pequeñas modificaciones en el código que crea la redirección y el archivo de para JavaScripts.

<!-- 

redirects_implement.xml

 -->

Completing the following steps will retain the information that the original referrer (for example, `https://www.google.com/search?hl=en&ie=UTF-8&q=discount+airline+tickets` in the scenario above) passes to your site:

## Configure referrer override JavaScript code {#section_87BB1D47D9C345C18339078824645CC4}

<!-- 

redirects_js_override.xml

 -->

The code snippet below shows two JavaScript variables, *`s_referrer`* and *`s_pageURL`*. El código se sitúa en la página de aterrizaje definitiva de la redirección.

```js
<script language="JavaScript" src="//INSERT-DOMAIN-AND-PATH-TO-CODE-HERE/AppMeasurement.js"></script> 
<script language="JavaScript"><!-- 
/* You may give each page an identifying name, server, and channel on 
the next lines. */ 
s.pageName="" 
s.server="" 
s.campaign="" 
s.referrer="" 
s.pageURL=""
```

>[!IMPORTANT]
>
>Set *`s.referrer`* only once on the page. Si la establece más de una vez con cada llamada de seguimiento o con cada clic de vínculo que se rastree ocasiona el recuento doble del referente y dimensiones relacionadas, como motores de búsqueda y palabras clave.

## Redirecciones mediante getQueryParam {#section_EE924E399F7A431C8FC8E8A2BEF84DEC}

Si bien [!UICONTROL getQueryParam] permite rellenar fácilmente las variables de [!DNL Analytics] con valores de las cadenas de consulta, este complemento se debe implementar junto con una variable temporal para que los referentes legítimos no se sobrescriban cuando la cadena de consulta esté vacía. La mejor manera de usar [!UICONTROL getQueryParam] es con el complemento [!UICONTROL getValue] tal como se indica con el seudocódigo siguiente.

```js
// AppMeasurement 1.x 
var tempVar=s.Util.getQueryParam('origref') 
if(tempVar) 
  s.referrer=tempVar;
```

```js
// H Code 
var tempVar=s.getQueryParam('origref') 
if(tempVar) 
  s.referrer=tempVar;
```

## Modify the redirect mechanism {#section_2FF9921E8FCA4440B6FF90F15386E548}

<!-- 

redirects_modify_mechanism.xml

 -->

Puesto que el explorador elimina la dirección URL de referencia, se debe configurar el mecanismo que se ocupa de la redirección (por ejemplo: servidor web, código del lado del servidor, código del lado del cliente) de modo que transmita la información del referente original. Si, además, desea registrar la dirección URL del vínculo de alias, esta también se debe transferir a la página de aterrizaje definitiva. Use la variable *`s_pageURL`* para ignorar la URL actual.

Dado que existen varias formas de implementar una redirección, es posible que tenga que consultar al grupo de operaciones web o a su socio de publicidad en línea cuáles son los mecanismos concretos que ejecutan las redirecciones en su sitio web.

## Capture the original referrer {#section_7F1A77F447CF485385B456A64B174050}

<!-- 

redirects_referrer.xml

 -->

En general, [!DNL Analytics] obtiene la dirección URL de referencia de la propiedad [!UICONTROL document.referrer] del explorador, y la dirección URL actual de la propiedad [!UICONTROL document.location]. By passing values to the *`referrer`* and *`pageURL`* variables, you can override the default processing. Al transferir un valor a la variable referrer, [!DNL Analytics] interpreta que debe ignorar la información del referente que se encuentra en la propiedad [!UICONTROL document.referrer] y utilizar un valor alternativo que usted defina.

Por lo tanto, la versión final de la página de aterrizaje debería contener el siguiente código para corregir los problemas introducidos en la situación de “billetes de avión con descuento”.

```js
<script language="JavaScript" src="https://INSERT-DOMAIN-AND-PATH-TO-CODE-HERE/AppMeasurement.js"></script> 
<script language="JavaScript"><!-- 
/* You may give each page an identifying name, server, and channel on 
the next lines. */ 
s.pageName="" 
s.server="" 
s.campaign="" 
s.referrer="https://www.google.com/search?hl=en&ie=UTF-8&q=discount+airline+tickets" 
// Setting the s.pageURL variable is optional. 
s.pageURL="https://www.flytohawaiiforfree.com"
```

## Verify the referrer with the Adobe Debugger {#section_B3E85941982E4E1698B271375AD669B9}

<!-- 

redirects_verify_referrer.xml

 -->

Run a test to verify that the referrer, originating URL ( *`s_server`*) and campaign variables are being captured.

These variables will be represented as the following parameters in the [Experience Cloud Debugger](https://marketing.adobe.com/resources/help/en_US/experience-cloud-debugger/).

<table id="table_5F3B987D4D514CA283F7B9F52EBC2301"> 
 <thead> 
  <tr> 
   <th class="entry"> </th> 
   <th class="entry"> <b>Valor de la cadena de consulta o dirección URL</b> </th> 
   <th class="entry"> <b>Valor como se muestra en DigitalPulse Debugger</b> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> <p>Referente original </p> </td> 
   <td> <p> <span class="filepath"> https://www.google.com/search%3F hl % 3 Den % 26 ie % 3 DUTF 826 q % 3 Dbilletes % 2 Bbilletes % 2 Bbilletes </span> </p> </td> 
   <td> <p> <span class="filepath"> r = https:/ref=www.google.com/search?hl=en&amp;ie=UTF -8 &amp; q = descuento + pasajes + aéreos + </span> </p> </td> 
  </tr> 
  <tr> 
   <td> <p>URL de la página </p> </td> 
   <td> <p> <span class="filepath"> https://www.flytohawaiiforfree.com </span> </p> </td> 
   <td> <p> <span class="filepath"> g = https://www.flytohawaiiforfree.com </span> </p> <p>This value will appear in the DigitalPulse Debugger if the <span class="varname"> pageURL </span> variable is used. </p> </td> 
  </tr> 
  <tr> 
   <td> <p>Dirección URL de la página de aterrizaje definitiva </p> </td> 
   <td> <p> <span class="filepath"> https://www.flywithus.com </span> </p> </td> 
   <td> <p>This value will NOT appear in the DigitalPulse Debugger if the <span class="varname"> pageURL </span> variable is used. </p> </td> 
  </tr> 
 </tbody> 
</table>

El texto que muestra el depurador debe corresponder al siguiente ejemplo:

```
Image 
 
https://flywithuscom.112.2o7.net/b/ss/flywithuscom/1/JS-1.4/s61944015791667?[AQB] 
ndh=1 
t=4/8/2014 13:34:28 4 360 
pageName=Welcome to FlyWithUs.com 
r=https://ref=www.google.com/search?hl=en&ie=UTF-8&q=discount+airline+tickets 
cc=USD 
g=https://www.flytohawaiiforfree.com 
s=1280x1024 
c=32 
j=1.3 
v=Y 
k=Y 
bw=1029 
bh=716 
ct=lan 
hp=N 
[AQE]
```

After verifying that the Adobe [!UICONTROL Debugger] displays these variables, it is always helpful to confirm that the search terms and the original referring domain (prior to the redirect) are registering traffic in reports.

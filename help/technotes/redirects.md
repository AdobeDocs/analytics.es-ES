---
description: Las redirecciones llevan al navegador a una nueva ubicación sin interacción del usuario. Se ejecutan en el navegador web (redirección del lado del cliente) o el servidor web (redirección del lado del servidor).
keywords: Implementación de Analytics
subtopic: Redirects
title: Redirecciones y alias
topic-fix: Developer and implementation
uuid: 11f9ad7a-5c45-410f-86dd-b7d2cec2aae3
exl-id: 0ed2aa9b-ab42-415d-985b-2ce782b6ab51
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '1125'
ht-degree: 100%

---

# Redirecciones y alias

Las redirecciones llevan al navegador a una nueva ubicación sin interacción del usuario. Se ejecutan en el navegador web (redirección del lado del cliente) o el servidor web (redirección del lado del servidor).

## Redirecciones y alias {#concept_F4F1D53D473947FE8554897332545763}

Las redirecciones llevan al navegador a una nueva ubicación sin interacción del usuario. Se ejecutan en el navegador web (redirección del lado del cliente) o el servidor web (redirección del lado del servidor).

Dado que las redirecciones no requieren interacción del usuario, se suelen ejecutar sin que el usuario lo note. Lo único que indica que se ha producido una redirección es la barra de direcciones del explorador. Esta barra muestra una dirección URL que es distinta del vínculo que solicitó inicialmente el explorador.

Aunque solo existen dos tipos de redirecciones, pueden implementarse de muchas maneras. Por ejemplo: las redirecciones del lado del cliente se pueden producir porque la página web a la que el usuario ha apuntado su navegador contiene un código HTML especial o una secuencia de comandos que redirecciona el navegador a otra dirección URL. Las redirecciones del lado del servidor se producen porque la página contiene secuencias de comandos del lado del servidor o porque el servidor web se ha configurado para dirigir al usuario hacia otra URL.

## Analytics y redirecciones {#concept_F9132879D0CB4AC1BE7AF45E388A47F7}

[!DNL Analytics] recopila algunos de sus datos del navegador y se basa en algunas de sus propiedades. Dos de esas propiedades, la “dirección URL de referencia” (o “referente”) y la “dirección URL actual” se pueden cambiar por una redirección del lado del servidor. El navegador, al ver que se ha solicitado una dirección URL pero se ha devuelto otra diferente, borra la dirección URL de referencia. El resultado es que la dirección URL de referencia está en blanco y [!DNL Analytics] podría notificar que no existe un referente para la página.

## Ejemplo: navegación sin redirecciones {#section_5C835A4D665A4625A23333C2C21F152D}

Imagine la siguiente situación hipotética en la que el usuario no se topa con ninguna redirección:

1. El usuario dirige el navegador a `www.google.com`, escribe “billetes avión descuento” en el campo de búsqueda y luego hace clic en el botón **[!UICONTROL Buscar]**.
1. El navegador muestra los resultados de la búsqueda, entre los que se encuentra su sitio, [!DNL https://www.example.com/]. Después de mostrar los resultados de la búsqueda, la barra de direcciones del explorador muestra los términos de búsqueda que el usuario ingresó en el campo de búsqueda (`https://www.google.com/search?hl=en&ie=UTF-8&q=discount+airline+tickets`). Observe que los términos de búsqueda se incluyen en los parámetros de la cadena de consulta de la dirección URL que están después de `https://www.google.com/search?`.
1. El usuario hace clic en el vínculo de su sitio hipotético, [!DNL https://www.example.com/]. Cuando el usuario hace clic en este vínculo y aterriza en el sitio web de [!DNL example.com], [!DNL Analytics] utiliza JavaScript para recopilar la dirección URL de referencia (`https://www.google.com/search?hl=en&ie=UTF-8&q=discount+airline+tickets`) así como la dirección URL actual (`https://www.example.com/`).
1. [!DNL Analytics] registra la información recopilada durante la interacción en distintos informes, como [!UICONTROL Dominios de referencia], [!UICONTROL Motores de búsqueda] y [!DNL Search Keywords].

## Ejemplo: navegación con redirecciones {#section_921DDD32932847848C4A901ACEF06248}

Las redirecciones pueden hacer que el navegador borre la verdadera dirección URL de referencia. Imagine la siguiente situación:

1. El usuario dirige el navegador a `https://www.google.com`, y luego escribe *billetes avión descuento* en el campo de búsqueda y hace clic en el botón **[!UICONTROL Buscar]**.
1. La barra de direcciones de la ventana del explorador muestra los términos de búsqueda que el usuario escribió en el campo de búsqueda `https://www.google.com/search?hl=en&ie=UTF-8&q=discount+airline+tickets`. Observe que los términos de búsqueda se incluyen en los parámetros de la cadena de consulta de la dirección URL que están después de `https://www.google.com/search?`. El navegador también muestra una página que contiene los resultados de la búsqueda, entre los que se incluye un vínculo a uno de sus nombres de dominio: [!DNL https://www.flytohawaiiforfree.com/]. Este dominio *mnemónico* está configurado para redireccionar al usuario a `https://www.example.com/`.
1. El usuario hace clic en el vínculo `https://www.flytohawaiiforfree.com/` y el servidor lo redirecciona a su sitio principal, `https://www.example.com`. Cuando se produce la redirección, se pierden datos importantes para la recopilación de datos de [!DNL Analytics] porque el explorador borra la dirección URL de referencia. Por ello, se pierde la información de la búsqueda original que se usa en los informes de [!DNL Analytics] (por ejemplo: [!UICONTROL Dominios de referencia], [!UICONTROL Motores de búsqueda] y [!UICONTROL Palabras clave de búsqueda]).

## Implementar redirecciones {#concept_5EC2EE9677A44CC5B90A38ECF28152E7}

Para captar los datos de [!DNL Analytics] provenientes de las redirecciones, es necesario realizar cuatro pequeñas modificaciones en el código que crea la redirección y el [!DNL AppMeasurement] archivo de para JavaScripts.

<!-- 

redirects_implement.xml

 -->

Al llevar a cabo los siguientes pasos, se conservará la información que transfiere a su sitio el referente original (por ejemplo, `https://www.google.com/search?hl=en&ie=UTF-8&q=discount+airline+tickets` en el caso anterior):

## Configuración del código de JavaScript para ignorar el referente {#section_87BB1D47D9C345C18339078824645CC4}

<!-- 

redirects_js_override.xml

 -->

El siguiente fragmento de código muestra dos variables de JavaScript, *`s_referrer`* y *`s_pageURL`*. El código se sitúa en la página de aterrizaje definitiva de la redirección.

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
>Configurar *`s.referrer`* solo una vez en la página. Si la establece más de una vez con cada llamada de seguimiento o con cada clic en el vínculo que se rastree ocasiona el recuento doble del referente y dimensiones relacionadas, como motores de búsqueda y palabras clave.

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

## Modificación del mecanismo de redirección {#section_2FF9921E8FCA4440B6FF90F15386E548}

<!-- 

redirects_modify_mechanism.xml

 -->

Puesto que el explorador elimina la dirección URL de referencia, se debe configurar el mecanismo que se ocupa de la redirección (por ejemplo: servidor web, código del lado del servidor, código del lado del cliente) de modo que transmita la información del referente original. Si, además, desea registrar la dirección URL del vínculo de alias, esta también se debe transferir a la página de aterrizaje definitiva. Use la variable *`s_pageURL`* para ignorar la URL actual.

Dado que existen varias formas de implementar una redirección, es posible que tenga que consultar al grupo de operaciones web o a su socio de publicidad en línea cuáles son los mecanismos concretos que ejecutan las redirecciones en su sitio web.

## Captación del referente original {#section_7F1A77F447CF485385B456A64B174050}

<!-- 

redirects_referrer.xml

 -->

En general, [!DNL Analytics] obtiene la dirección URL de referencia de la propiedad [!UICONTROL document.referrer] del explorador, y la dirección URL actual de la propiedad [!UICONTROL document.location]. Al pasar valores a las variables *`referrer`* y *`pageURL`*, puede anular el procesamiento predeterminado. Al transferir un valor a la variable referrer, [!DNL Analytics] interpreta que debe ignorar la información del referente que se encuentra en la propiedad [!UICONTROL document.referrer] y utilizar un valor alternativo que usted defina.

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

## Comprobación del referente con Adobe Debugger {#section_B3E85941982E4E1698B271375AD669B9}

<!-- 

redirects_verify_referrer.xml

 -->

Ejecute una prueba para comprobar si se captan las variables campaign, dirección URL de origen (*`s_server`*) y referente.

Estas variables se representarán como los siguientes parámetros en [Experience Cloud Debugger](https://docs.adobe.com/content/help/es-ES/debugger/using/experience-cloud-debugger.html).

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
   <td> <p> <span class="filepath">https://www.google.com/search%3F hl%3Den %26ie%3DUTF826q%3 Ddiscount%2Bairline%2Btickets</span> </p> </td> 
   <td> <p> <span class="filepath"> r=https:/ref=www.google.com/search?hl=en&amp;ie=UTF -8&amp;q=discount+airline+tickets </span> </p> </td> 
  </tr> 
  <tr> 
   <td> <p>URL de la página </p> </td> 
   <td> <p> <span class="filepath">https://www.flytohawaiiforfree.com</span> </p> </td> 
   <td> <p> <span class="filepath"> g=https://www.flytohawaiiforfree.com </span> </p> <p>Este valor aparecerá en DigitalPulse Debugger si se utiliza la variable <span class="varname">pageURL</span>. </p> </td> 
  </tr> 
  <tr> 
   <td> <p>URL de la página de aterrizaje definitiva </p> </td> 
   <td> <p> <span class="filepath">https://www.example.com</span> </p> </td> 
   <td> <p>Este valor NO aparecerá en DigitalPulse Debugger si se utiliza la variable <span class="varname">pageURL</span>. </p> </td> 
  </tr> 
 </tbody> 
</table>

El texto que muestra el depurador debe corresponder al siguiente ejemplo:

```
Image 
 
https://examplecom.112.2o7.net/b/ss/examplecom/1/JS-1.4/s61944015791667?[AQB] 
ndh=1 
t=4/8/2014 13:34:28 4 360 
pageName=Welcome to example.com 
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

Después de comprobar que Adobe [!UICONTROL Debugger] muestra estas variables, siempre es conveniente confirmar que los términos de búsqueda y el dominio de referencia original (anterior a la redirección) registran el tráfico en los informes.

---
description: Las redirecciones dirigen el explorador a una nueva ubicación sin que intervenga el usuario. Se ejecutan en el explorador web (redirección del lado del cliente) o en el servidor web (redirección del lado del servidor).
keywords: Implementación de Analytics
title: Redirecciones y alias
feature: Implementation Basics
exl-id: 0ed2aa9b-ab42-415d-985b-2ce782b6ab51
TQID: https://experienceleague.adobe.com/iDwKqSKsjzEvgVCNKdTwDZHN2cPDmsuM1SV7PLisw3g
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 1139
ht-degree: 71%

---

# Redirecciones y alias

Las redirecciones dirigen el explorador a una nueva ubicación sin que intervenga el usuario. Se ejecutan en el explorador web (redirección del lado del cliente) o en el servidor web (redirección del lado del servidor).

## Redirecciones y alias {#aliases}

Las redirecciones dirigen el explorador a una nueva ubicación sin que intervenga el usuario. Se ejecutan en el explorador web (redirección del lado del cliente) o en el servidor web (redirección del lado del servidor).

Dado que las redirecciones no requieren la interacción del usuario, suelen ejecutarse sin que el usuario se dé cuenta. Lo único que indica que se ha producido una redirección es la barra de direcciones del explorador. La barra de direcciones muestra una dirección URL diferente del vínculo que solicitó inicialmente el explorador.

Aunque solo hay dos tipos de redirecciones, se pueden implementar de numerosas maneras. Por ejemplo, las redirecciones del lado del cliente pueden producirse porque la página web a la que un usuario ha dirigido su explorador contiene secuencias de comandos o código HTML especial que redirige el explorador a otra dirección URL. Las redirecciones del lado del servidor pueden producirse porque la página contiene secuencias de comandos del lado del servidor o porque el servidor web se ha configurado para señalar al usuario a otra dirección URL.

## Analytics y redirecciones {#aa-redirects}

[!DNL Analytics] recopila algunos de sus datos del navegador y se basa en algunas de sus propiedades. Dos de estas propiedades, la &quot;URL de referencia&quot; (o &quot;referente&quot;) y la &quot;URL actual&quot; se pueden cambiar mediante un redireccionamiento del lado del servidor. Dado que el explorador sabe que se ha solicitado una dirección URL, pero se ha devuelto una dirección URL diferente, borra la dirección URL de referencia. El resultado es que la dirección URL de referencia está en blanco y [!DNL Analytics] podría notificar que no existe un referente para la página.

## Ejemplo: navegación sin redirecciones {#browse-without}

Imagine la siguiente situación hipotética en la que el usuario no se topa con ninguna redirección:

1. El usuario dirige el navegador a `www.google.com`, escribe “billetes avión descuento” en el campo de búsqueda y luego hace clic en el botón **[!UICONTROL Buscar]**.
1. El navegador muestra los resultados de la búsqueda, entre los que se encuentra su sitio, [!DNL https://www.example.com/]. Después de mostrar los resultados de la búsqueda, la barra de direcciones del explorador muestra los términos de búsqueda que el usuario ingresó en el campo de búsqueda (`https://www.google.com/search?hl=en&ie=UTF-8&q=discount+airline+tickets`). Observe que los términos de búsqueda se incluyen en los parámetros de la cadena de consulta de la dirección URL que están después de `https://www.google.com/search?`.
1. El usuario hace clic en el vínculo de su sitio hipotético, [!DNL https://www.example.com/]. Cuando el usuario hace clic en este vínculo y aterriza en el sitio web de [!DNL example.com], [!DNL Analytics] utiliza JavaScript para recopilar la dirección URL de referencia (`https://www.google.com/search?hl=en&ie=UTF-8&q=discount+airline+tickets`) así como la dirección URL actual (`https://www.example.com/`).
1. [!DNL Analytics] registra la información recopilada durante la interacción en distintos informes, como [!UICONTROL Dominios de referencia], [!UICONTROL Motores de búsqueda] y [!DNL Search Keywords].

## Ejemplo: navegación con redirecciones {#browse-with}

Las redirecciones pueden hacer que el explorador vacíe la dirección URL de referencia verdadera. Imagine la siguiente situación:

1. El usuario dirige el navegador a `https://www.google.com`, y luego escribe *billetes avión descuento* en el campo de búsqueda y hace clic en el botón **[!UICONTROL Buscar]**.
1. La barra de direcciones de la ventana del explorador muestra los términos de búsqueda que el usuario escribió en el campo de búsqueda `https://www.google.com/search?hl=en&ie=UTF-8&q=discount+airline+tickets`. Observe que los términos de búsqueda se incluyen en los parámetros de la cadena de consulta de la dirección URL que están después de `https://www.google.com/search?`. El navegador también muestra una página que contiene los resultados de la búsqueda, entre los que se incluye un vínculo a uno de sus nombres de dominio: [!DNL https://www.flytohawaii.example/]. Este dominio *mnemónico* está configurado para redireccionar al usuario a `https://www.example.com/`.
1. El usuario hace clic en el vínculo `https://www.flytohawaii.example/` y el servidor lo redirecciona a su sitio principal, `https://www.example.com`. Cuando se produce la redirección, se pierden datos importantes para la recopilación de datos de [!DNL Analytics] porque el explorador borra la dirección URL de referencia. Por ello, se pierde la información de la búsqueda original que se usa en los informes de [!DNL Analytics] (por ejemplo: [!UICONTROL Dominios de referencia], [!UICONTROL Motores de búsqueda] y [!UICONTROL Palabras clave de búsqueda]).

## Implementar redirecciones {#implement}

Para captar los datos de [!DNL Analytics] provenientes de las redirecciones, es necesario realizar cuatro pequeñas modificaciones en el código que crea la redirección y el [!DNL AppMeasurement] archivo de para JavaScripts.

Al llevar a cabo los siguientes pasos, se conservará la información que transfiere a su sitio el referente original (por ejemplo, `https://www.google.com/search?hl=en&ie=UTF-8&q=discount+airline+tickets` en el caso anterior):

## Configuración del código de JavaScript para ignorar el referente {#override}

El siguiente fragmento de código muestra dos variables de JavaScript, `s.referrer` y `s.pageURL`. El código se sitúa en la página de destino definitiva de la redirección.

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

## Redirecciones mediante getQueryParam {#getqueryparam}

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

## Modificación del mecanismo de redirección {#modify}

Dado que el explorador elimina la dirección URL de referencia, debe configurar el mecanismo que gestiona la redirección (por ejemplo, el servidor web, el código del lado del servidor o el código del lado del cliente) para pasar la información del referente original. Si, además, desea registrar la dirección URL del vínculo de alias, esta también se debe transferir a la página de destino definitiva. Utilice la variable *`s_pageURL`* para anular la dirección URL actual.

Dado que existen varias formas de implementar una redirección, es posible que tenga que consultar al grupo de operaciones web o a su socio de publicidad en línea cuáles son los mecanismos concretos que ejecutan las redirecciones en su sitio web.

## Captación del referente original {#original}

En general, [!DNL Analytics] obtiene la dirección URL de referencia de la propiedad [!UICONTROL document.referrer] del explorador, y la dirección URL actual de la propiedad [!UICONTROL document.location]. Al pasar valores a las variables *`referrer`* y *`pageURL`*, puede anular el procesamiento predeterminado. Al transferir un valor a la variable referrer, [!DNL Analytics] interpreta que debe ignorar la información del referente que se encuentra en la propiedad [!UICONTROL document.referrer] y utilizar un valor alternativo que usted defina.

Por lo tanto, la versión final de la página de destino debería contener el siguiente código para corregir los problemas introducidos en la situación de “billetes de avión con descuento”.

```js
<script language="JavaScript" src="AppMeasurement.js"></script> 
<script language="JavaScript"><!-- 
/* You may give each page an identifying name, server, and channel on 
the next lines. */ 
s.pageName="" 
s.server="" 
s.campaign="" 
s.referrer="https://www.google.com/search?hl=en&ie=UTF-8&q=discount+airline+tickets" 
// Setting the s.pageURL variable is optional.
s.pageURL="https://www.flytohawaii.example"
```

## Comprobación del referente con Adobe Debugger {#verify}

Ejecute una prueba para comprobar si se captan las variables campaign, dirección URL de origen (*`s_server`*) y referente.

Estas variables se representarán como los siguientes parámetros en [Experience Cloud Debugger](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html?lang=es).

<table id="table_5F3B987D4D514CA283F7B9F52EBC2301"> 
 <thead> 
  <tr> 
   <th class="entry"> </th> 
   <th class="entry"> <b>URL o valor de cadena de consulta</b> </th> 
   <th class="entry"> <b>Valor tal como se muestra en DigitalPulse Debugger</b> </th> 
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
   <td> <p> <span class="filepath"> https://www.flytohawaii.example </span> </p> </td> 
   <td> <p> <span class="filepath"> g=https://www.flytohawaii.example </span> </p> <p>Este valor aparecerá en DigitalPulse Debugger si se utiliza la variable <span class="varname">pageURL</span>. </p> </td> 
  </tr> 
  <tr> 
   <td> <p>URL de la página de destino definitiva </p> </td> 
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
t=4/8/20XX 13:34:28 4 360 
pageName=Welcome to example.com 
r=https://ref=www.google.com/search?hl=en&ie=UTF-8&q=discount+airline+tickets 
cc=USD 
g=https://www.flytohawaii.example 
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

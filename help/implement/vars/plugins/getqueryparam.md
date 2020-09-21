---
title: getQueryParam
description: Extraiga el valor de un parámetro de cadena de consulta de una dirección URL.
translation-type: ht
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: ht
source-wordcount: '885'
ht-degree: 100%

---


# Complemento de Adobe: getQueryParam

>[!IMPORTANT]
>
>Adobe Consulting proporciona este complemento por cortesía para ayudarle a sacar el máximo partido a Adobe Analytics. El Servicio de atención al cliente de Adobe no ofrece asistencia técnica con este complemento, incluida la instalación o solución de problemas. Si necesita ayuda con este complemento, póngase en contacto con el administrador de cuentas de su organización. Ellos podrán organizar una reunión con un consultor para ayudarle.

El complemento `getQueryParam` le permite extraer el valor de cualquier parámetro de cadena de consulta contenido en una dirección URL. Resulta útil para extraer códigos de campaña, tanto internos como externos, de las direcciones URL de las páginas de aterrizaje. También resulta útil al extraer términos de búsqueda u otros parámetros de cadena de consulta.

Este complemento proporciona funciones sólidas para analizar direcciones URL complejas, incluidos hashes y direcciones URL que contienen varios parámetros de cadena de consulta. Si solo necesita parámetros de cadena de consulta simples, Adobe recomienda utilizar las funciones de parámetro de URL en Launch o el método [`Util.getQueryParam()`](../functions/util-getqueryparam.md) incluido en AppMeasurement.

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
   * Tipo de acción: Inicializar getQueryParam
1. Guarde y publique los cambios en la regla.

## Instalación del complemento con el editor de código personalizado de Launch

Si no desea utilizar la extensión del complemento, puede utilizar el editor de código personalizado.

1. Inicie sesión en [launch.adobe.com](https://launch.adobe.com) con sus credenciales de Adobe ID.
1. Haga clic en la propiedad deseada.
1. Vaya a la pestaña [!UICONTROL Extensiones] y, a continuación, haga clic en el botón [!UICONTROL Configurar] en la extensión de Adobe Analytics.
1. Expanda [!UICONTROL Configurar seguimiento con el código personalizado], que muestra el botón [!UICONTROL Abrir editor].
1. Abra el editor de código personalizado y pegue el código del complemento que se proporciona a continuación en la ventana de edición.
1. Guarde y publique los cambios en la extensión de Analytics.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getQueryParam v3.3 (Requires pt plug-in) */
s.getQueryParam=function(qsp,de,url){var g=this,e="",k=function(b,de){de=de.split("?").join("&");de=de.split("#").join("&");var d=de.indexOf("&"),url="";b&&(-1<d||de.indexOf("=")>d)&&(d=de.substring(d+1),url=g.pt(d,"&","gpval",b));return url};qsp=qsp.split(",");var l=qsp.length;g.gpval=function(de,b){if(de){var d=de.split("="),url=d[0];d=d[1]?d[1]:!0;if(b.toLowerCase() ==url.toLowerCase())return"boolean"===typeof d?d:this.unescape(d)}return""};de=de?de:"";url=(url?url:g.pageURL?g.pageURL: location.href)+"";if((4<de.length||-1<de.indexOf("="))&&url&&4>url.length){var b=de;de=url;url=b}for(var h=0;h<l;h++)b=k(qsp[h],url) ,"string"===typeof b?(b=-1<b.indexOf("#")?b.substring(0,b.indexOf("#")):b,e+=e?de+b:b):e=""===e?b:e+(de+b);return e};

/* Adobe Consulting Plugin: pt v2.01 */ 
s.pt=function(l,de,cf,fa){if(l&&this[cf]){l=l.split(de||",");de=l.length;for(var e,c=0;c<de;c++)if(e=this[cf](l[c],fa))return e}};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Uso del complemento

El método `getQueryParam` utiliza los siguientes argumentos:

* **`qsp`** (obligatorio): Una lista delimitada por comas de parámetros de cadena de consulta que se buscarán en la dirección URL. Sin distinción de mayúsculas y minúsculas.
* **`de`** (opcional): El delimitador que se usará si coinciden varios parámetros de cadena de consulta. El valor predeterminado es una cadena vacía.
* **`url`** (opcional): Una dirección URL, cadena o variable personalizada desde la que extraer los valores de parámetro de cadena de consulta. El valor predeterminado es `window.location`.

Llamar a este método devuelve un valor según los argumentos anteriores y la dirección URL:

* Si no se encuentra un parámetro de cadena de consulta coincidente, el método devuelve una cadena vacía.
* Si se encuentra un parámetro de cadena de consulta coincidente, el método devuelve el valor del parámetro de cadena de consulta.
* Si se encuentra un parámetro de cadena de consulta coincidente pero el valor está vacío, el método devuelve `true`.
* Si se encuentran varios parámetros de cadena de consulta coincidentes, el método devuelve una cadena con cada valor de parámetro delimitado por la cadena en el argumento `de`.

## Llamadas de ejemplo

### Ejemplo 1

Si la dirección URL actual es la siguiente:

```js
http://www.abc123.com/?cid=trackingcode1
```

El siguiente código establecerá s.campaign en “trackingcode1”:

```js
s.campaign=s.getQueryParam('cid');
```

### Ejemplo 2

Si la dirección URL actual es la siguiente:

```js
http://www.abc123.com/?cid=trackingcode1&ecid=123456
```

El siguiente código establecerá s.campaign en “trackingcode1:123456”:

```js
s.campaign=s.getQueryParam('cid,ecid',':');
```

### Ejemplo 3

Si la dirección URL actual es la siguiente:

```js
http://www.abc123.com/?cid=trackingcode1&ecid=123456
```

El siguiente código establecerá s.campaign en “trackingcode1123456”:

```js
s.campaign=s.getQueryParam('cid,ecid');
```

### Ejemplo 4

Si la dirección URL actual es la siguiente:

```js
http://www.abc123.com/?cid=trackingcode1&ecid=123456#location
```

El siguiente código establecerá s.campaign en “123456”:

```js
s.campaign=s.getQueryParam('ecid');
```

### Ejemplo 5

Si la dirección URL actual es la siguiente:

```js
http://www.abc123.com/#location&cid=trackingcode1&ecid=123456
```

El siguiente código establecerá s.campaign en “123456”

```js
s.campaign=s.getQueryParam('ecid');
```

**Nota:** El complemento reemplaza el carácter hash de comprobación de la dirección URL por un signo de interrogación si no lo hubiera.  Si la dirección URL contiene un signo de interrogación antes del carácter hash, el complemento reemplazará el carácter hash de comprobación de la dirección URL por un signo ampersand;

### Ejemplo 6

Si la dirección URL actual es la siguiente:

```js
http://www.abc123.com/
```

... y si la variable s.testURL está establecida de la siguiente manera:

```js
s.testURL="http://www.abc123.com/?cid=trackingcode1&ecid=123456#location&pos=300";
```

El siguiente código no configurará s.campaign en absoluto:

```js
s.campaign=s.getQueryParam('cid');
```

Sin embargo, el siguiente código establecerá s.campaign como “trackingcode1”:

```js
s.campaign=s.getQueryParam('cid','',s.testURL);
```

**Nota:** El tercer parámetro puede ser cualquier cadena o variable que el código utilice para intentar encontrar los parámetros de cadena de consulta en

El siguiente código establecerá s.eVar2 en “123456|trackingcode1|true|300”:

```js
s.eVar2=s.getQueryParam('ecid,cid,location,pos','|',s.testURL);
```

* El valor de 123456 se obtiene del parámetro ecid en la variable s.testURL
* El valor de trackingcode1 se obtiene del parámetro cid en la variable s.testURL
* El valor de true se obtiene de la existencia (pero no del valor) del parámetro de ubicación después del carácter hash en la variable s.testURL

El valor de 300 se obtiene del valor del parámetro pos en la variable s.testURL

## Historial de versiones

### 3.3 (24 de septiembre de 2019)

* Se ha omitido la lógica innecesaria para reducir el tamaño del código

### 3.2 (15 de mayo de 2018)

* Se han movido las funciones `findParameterValue` y `getParameterValue` a la función `getQueryParam`

### 3.1 (10 de mayo de 2018)

* Se ha corregido un problema con la captura de parámetros de cadena de consulta sin valor

### 3.0 (16 de abril de 2018)

* Versión puntual (compilada de nuevo, con un tamaño de código más pequeño).
* Se ha cambiado el nombre de las funciones de ayuda a `findParameterValue` y `getParameterValue` con fines de legibilidad.
* Se ha eliminado la necesidad de agregar un argumento para encontrar los parámetros contenidos en el hash de la dirección URL

### 2.5 (8 de enero de 2016)

* Compatible con el código H y con AppMeasurement (requiere `s.pt` con AppMeasurement).

### 2,4

* Se ha agregado el parámetro `h`, que permite que el código encuentre los parámetros de cadena de consulta que se encuentren después del carácter hash (`#`)

### 2,3

* Se ha corregido un problema de regresión en el que el complemento solo funcionaba cuando el hash aparecía después del código de seguimiento

### 2,2

* Ahora elimina los caracteres hash (y todo lo que haya a continuación) del valor devuelto

### 2,1

* Compatible con código H.10

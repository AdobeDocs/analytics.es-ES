---
title: inList
description: Compruebe si un valor está contenido en otro valor delimitado por caracteres.
translation-type: tm+mt
source-git-commit: 365944140bb1dfc9bc8669ae530c631e8ff1629b

---


# Complemento de Adobe:inList

> [!IMPORTANT] Este complemento lo proporciona Adobe Consulting por cortesía para ayudarle a obtener más valor de Adobe Analytics. El Servicio de atención al cliente de Adobe no ofrece asistencia técnica con este complemento, incluida la instalación o solución de problemas. Si necesita ayuda con este complemento, póngase en contacto con el administrador de cuentas de su organización. Pueden organizar una reunión con un consultor para obtener ayuda.

El complemento le permite comprobar si ya existe un valor en una cadena delimitada o en un objeto de matriz JavaScript. `inList` Otros complementos dependen del `inList` complemento para funcionar. Este complemento proporciona una clara ventaja sobre el método JavaScript `indexOf()` , en el que no coincide con cadenas parciales. Por ejemplo, si utilizó este complemento para buscar `"event2"`, no coincidirá con una cadena que contenga `"event25"`. Este complemento no es necesario si no necesita comprobar los valores de cadenas o matrices delimitadas o si desea utilizar su propia `indexOf()` lógica.

## Instalación del complemento con la extensión Adobe Experience Platform Launch

Adobe ofrece una extensión que le permite utilizar los complementos más utilizados.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
1. Haga clic en la propiedad que desee.
1. Vaya a la ficha [!UICONTROL Extensiones] y, a continuación, haga clic en el botón [!UICONTROL Catálogo]
1. Instalación y publicación de la extensión [!UICONTROL Common Analytics Plugins]
1. Para cualquier regla de inicio en la que desee utilizar el complemento, agregue una acción con la siguiente configuración:
   * Extensión: Complementos comunes de Analytics
   * Tipo de acción: Inicializar addProductEvar
1. Guardar y publicar los cambios en la regla

## Instalación del complemento con el editor de código personalizado Iniciar

Si no desea utilizar la extensión del complemento, puede utilizar el editor de código personalizado.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
1. Haga clic en la propiedad deseada.
1. Vaya a la ficha [!UICONTROL Extensiones] y, a continuación, haga clic en el botón [!UICONTROL Configurar] en la extensión de Adobe Analytics.
1. Expanda el seguimiento [!UICONTROL Configurar mediante el acordeón de código] personalizado, que muestra el botón [!UICONTROL Abrir editor] .
1. Abra el editor de código personalizado y pegue el código del complemento que se proporciona a continuación en la ventana de edición.
1. Guarde y publique los cambios en la extensión de Analytics.

## Instalación del complemento mediante AppMeasurement

Copie y pegue el siguiente código en cualquier parte del archivo AppMeasurement después de crear una instancia del objeto de seguimiento de Analytics (mediante `s_gi`). La conservación de los comentarios y los números de versión del código en la implementación ayuda a Adobe a solucionar cualquier problema potencial.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: inList v2.1 */
s.inList=function(lv,vtc,d,cc){if("string"!==typeof vtc)return!1;if("string"===typeof lv)lv=lv.split(d||",");else if("object"!== typeof lv)return!1;d=0;for(var e=lv.length;d<e;d++)if(1==cc&&vtc===lv[d]||vtc.toLowerCase()===lv[d].toLowerCase())return!0;return!1};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Utilizar el complemento

El `inList` método utiliza los siguientes argumentos:

* **`lv`**(requerido, cadena o matriz): Una lista delimitada de valores o un objeto de matriz JavaScript para buscar
* **`vtc`**(requerido, cadena): El valor que se va a buscar
* **`d`**(opcional, cadena): El delimitador utilizado para separar valores individuales en el`lv`argumento. El valor predeterminado es una coma (`,`) cuando no se establece.
* **`cc`**(opcional, booleano): Si se establece en`true`, se realiza una comprobación que distingue entre mayúsculas y minúsculas. Si se define como`false`o se omite, se realiza una comprobación que no distingue entre mayúsculas y minúsculas. El valor predeterminado es`false`.

Llamar a este método devuelve `true` si encuentra una coincidencia y `false` si no encuentra una coincidencia.

## Llamadas de ejemplo

### Ejemplo n.º 1

Si...

```js
s.events="event22,event24";
```

...y se ejecuta el siguiente código...

```js
if(s.inList(s.events,"event22"))
```

...la afirmación condicional if será true

### Ejemplo n.º 2

Si...

```js
s.events="event22,event24";
```

...y se ejecuta el siguiente código...

```js
if(s.inList(s.events,"event2"))
```

...la afirmación condicional if será false porque la llamada inList no realizó una coincidencia exacta entre event2 y cualquiera de los valores delimitados de s.events

### Ejemplo n.º 3

Si...

```js
s.events="event22,event24";
```

...y se ejecuta el siguiente código...

```js
if(!s.inList(s.events,"event23"))
```

...la afirmación condicional if será verdadera porque la llamada inList no realizó una coincidencia exacta entre event23 y cualquiera de los valores delimitados en s.events (observe el operador &quot;NOT&quot; al principio de la llamada a la variable inList).

### Ejemplo n.º 4

Si...

```js
s.events = "event22,event23";
```

...y se ejecuta el siguiente código...

```js
if(s.inList(s.events,"EVenT23","",1))
```

...la afirmación condicional if será false.  Aunque este ejemplo no es práctico, demuestra la necesidad de tener cuidado al utilizar el indicador que distingue entre mayúsculas y minúsculas.

### Ejemplo n.º 5

Si...

```js
s.linkTrackVars = "events,eVar1";
```

...y se ejecuta el siguiente código...

```js
if(s.inList(s.linkTrackVars,"eVar1","|"))
```

...la afirmación condicional if será false.  El valor del argumento d pasado a la llamada (por ejemplo: &quot;|&quot;) supone que los valores individuales de s.linkTrackVars están delimitados por un carácter de barra vertical, mientras que en realidad, los valores están delimitados por una coma.  En este caso, el complemento intentará hacer una coincidencia entre todo el valor de s.linkTrackVars (por ejemplo: &quot;events,eVar1&quot;) y el valor que se debe buscar (por ejemplo: &quot;eVar1&quot;).

## Historial de versiones

### v2.1 (26 de septiembre de 2019)

* Se agregó la opción para que el `cc` argumento no sea booleano. Por ejemplo, `1` es un valor válido para la comprobación de mayúsculas y minúsculas.

### v2.0 (17 de abril de 2018)

* Versión puntual (recompilada, tamaño de código más pequeño).

### v1.01 (27 de septiembre de 2017)

* Código optimizado para reducir el tamaño

### v1.0 (2009)

* Versión inicial.



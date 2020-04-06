---
title: inList
description: Compruebe si un valor está contenido en otro valor delimitado por caracteres.
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Complemento de Adobe: inList

>[!IMPORTANT] Adobe Consulting proporciona este complemento por cortesía para ayudarle a sacar el máximo partido a Adobe Analytics. El Servicio de atención al cliente de Adobe no ofrece asistencia técnica con este complemento, incluida la instalación o solución de problemas. Si necesita ayuda con este complemento, póngase en contacto con el administrador de cuentas de su organización. Ellos podrán organizar una reunión con un consultor para ayudarle.

El complemento `inList` le permite comprobar si ya existe un valor en una cadena delimitada o en un objeto de matriz JavaScript. Otros complementos dependen del complemento `inList` para funcionar. Este complemento proporciona una clara ventaja sobre el método `indexOf()` de JavaScript, que no comprueba si coincide con cadenas parciales. Por ejemplo, si utilizó este complemento para buscar `"event2"`, no coincidirá con una cadena que contenga `"event25"`. Este complemento no es necesario si no necesita comprobar los valores de cadenas o matrices delimitadas o si desea utilizar su propia lógica `indexOf()`.

## Instalación del complemento con la extensión de Adobe Experience Platform Launch

Adobe ofrece una extensión que le permite disfrutar de los complementos más utilizados.

1. Inicie sesión en [launch.adobe.com](https://launch.adobe.com) con sus credenciales de Adobe ID.
1. Haga clic en la propiedad deseada.
1. Go to the [!UICONTROL Extensions] tab, then click on the [!UICONTROL Catalog] button
1. Install and publish the [!UICONTROL Common Analytics Plugins] extension
1. Si aún no lo ha hecho, cree una regla con la etiqueta “Inicializar complementos” con la siguiente configuración:
   * Condición: Ninguna
   * Evento: Core – Biblioteca cargada (Principio de página)
1. Añada una acción a la regla anterior con la siguiente configuración:
   * Extensión: Common Analytics Plugins
   * Tipo de acción: Inicializar inList
1. Guarde y publique los cambios en la regla.

## Instalación del complemento con el editor de código personalizado de Launch

Si no desea utilizar la extensión del complemento, puede utilizar el editor de código personalizado.

1. Inicie sesión en [launch.adobe.com](https://launch.adobe.com) con sus credenciales de Adobe ID.
1. Haga clic en la propiedad deseada.
1. Go to the [!UICONTROL Extensions] tab, then click the [!UICONTROL Configure] button under the Adobe Analytics extension.
1. Expanda el [!UICONTROL Configure tracking using custom code] acordeón, que muestra el [!UICONTROL Open Editor] botón.
1. Abra el editor de código personalizado y pegue el código del complemento que se proporciona a continuación en la ventana de edición.
1. Guarde y publique los cambios en la extensión de Analytics.

## Instalación del complemento con AppMeasurement

Copie y pegue el siguiente código en cualquier parte del archivo AppMeasurement después de crear una instancia del objeto de seguimiento de Analytics (con [`s_gi`](../functions/s-gi.md)). Conservar los comentarios y los números de versión del código en la implementación ayuda a Adobe a solucionar cualquier posible problema.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: inList v2.1 */
s.inList=function(lv,vtc,d,cc){if("string"!==typeof vtc)return!1;if("string"===typeof lv)lv=lv.split(d||",");else if("object"!== typeof lv)return!1;d=0;for(var e=lv.length;d<e;d++)if(1==cc&&vtc===lv[d]||vtc.toLowerCase()===lv[d].toLowerCase())return!0;return!1};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Uso del complemento

El método `inList` utiliza los siguientes argumentos:

* **`lv`** (obligatorio, cadena o matriz): Una lista delimitada de valores o un objeto de matriz JavaScript que buscar
* **`vtc`** (obligatorio, cadena): El valor que se va a buscar
* **`d`** (opcional, cadena): El delimitador utilizado para separar valores individuales en el argumento `lv`. Si no se configura de forma distinta, el valor predeterminado es una coma (`,`).
* **`cc`** (opcional, booleano): Si se establece en `true`, se realiza una comprobación que distingue entre mayúsculas y minúsculas. Si se define como `false` o se omite, se realiza una comprobación que no distingue entre mayúsculas y minúsculas. El valor predeterminado es `false`.

Llamar a este método devuelve `true` si encuentra una coincidencia y `false` si no encuentra una coincidencia.

## Llamadas de ejemplo

### Ejemplo 1

Si...

```js
s.events="event22,event24";
```

... y se ejecuta el siguiente código...

```js
if(s.inList(s.events,"event22"))
```

... el enunciado condicional tendrá el valor true

### Ejemplo 2

Si...

```js
s.events="event22,event24";
```

... y se ejecuta el siguiente código...

```js
if(s.inList(s.events,"event2"))
```

... el enunciado condicional si tendrá un valor false porque la llamada inList no encontró una coincidencia exacta entre event2 y cualquiera de los valores delimitados de s.events

### Ejemplo 3

Si...

```js
s.events="event22,event24";
```

... y se ejecuta el siguiente código...

```js
if(!s.inList(s.events,"event23"))
```

... el enunciado condicional tendrá el valor true porque la llamada inList no encontró una coincidencia exacta entre event23 y cualquiera de los valores delimitados en s.events (observe el operador “NO” al principio de la llamada a la variable inList).

### Ejemplo 4

Si...

```js
s.events = "event22,event23";
```

... y se ejecuta el siguiente código...

```js
if(s.inList(s.events,"EVenT23","",1))
```

... el enunciado condicional si tendrá un valor false.  Aunque este ejemplo no es práctico, demuestra la necesidad de tener cuidado al utilizar el indicador que distingue entre mayúsculas y minúsculas.

### Ejemplo 5

Si...

```js
s.linkTrackVars = "events,eVar1";
```

... y se ejecuta el siguiente código...

```js
if(s.inList(s.linkTrackVars,"eVar1","|"))
```

... el enunciado condicional si tendrá un valor false.  El valor del argumento d pasado a la llamada (es decir, “|”) supone que los valores individuales de s.linkTrackVars están delimitados por un carácter de barra vertical, mientras que en realidad, los valores están delimitados por una coma.  En este caso, el complemento intentará encontrar una coincidencia entre todo el valor de s.linkTrackVars (es decir, “events,eVar1”) y el valor que se debe buscar (es decir, “eVar1”).

## Historial de versiones

### v2.1 (26 de septiembre de 2019)

* Se ha agregado la opción para que el argumento `cc` no sea booleano. Por ejemplo, `1` es un valor válido para la comprobación de mayúsculas y minúsculas.

### v2.0 (17 de abril de 2018)

* Versión puntual (compilada de nuevo, con un tamaño de código más pequeño).

### v1.01 (27 de septiembre de 2017)

* Código optimizado para reducir el tamaño

### v1.0 (2009)

* Versión inicial.



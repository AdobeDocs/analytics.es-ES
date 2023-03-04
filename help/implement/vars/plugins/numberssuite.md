---
title: Numbers Suite
description: Produzca y manipule números para utilizarlos en otras variables de JavaScript.
feature: Variables
exl-id: 7af88dce-baf3-4581-b5b6-0d6e41922266
source-git-commit: c53f886d5329e2a3b5023f9396c3aa2360a86901
workflow-type: tm+mt
source-wordcount: '481'
ht-degree: 100%

---

# Complemento de Adobe: Numbers Suite

{{plug-in}}

Numbers Suite contiene una serie de funciones de JavaScript. Incluye los siguientes complementos:

* **`zeroPad`**: Agregue un número específico de ceros al principio de un número. Este complemento es útil si una variable requiere un determinado número de dígitos, por ejemplo si trabaja con objetos de fecha de JavaScript y desea dar formato al mes y al día de una fecha con dos dígitos en lugar de uno solo. Por ejemplo, `01/09/2020` en lugar de `1/9/2020`.
* **`randomNumber`**: Genera un número aleatorio con un número específico de dígitos. Este complemento resulta útil si implementa etiquetas de terceros y desea un número aleatorio que elimine la caché.
* **`twoDecimals`**: Redondea un número hasta la centésima más cercana. Este complemento es útil para fines monetarios, ya que le permite redondear un número a un valor de moneda válido.

<!--## Install the plug-in using the Web SDK or the Adobe Analytics extension

Adobe offers an extension that allows you to use most commonly-used plug-ins.

1. Log in to [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) using your AdobeID credentials.
1. Click the desired tag property.
1. Go to the [!UICONTROL Extensions] tab, then click on the [!UICONTROL Catalog] button
1. Install and publish the [!UICONTROL Common Analytics Plugins] extension
1. If you haven't already, create a rule labeled "Initialize Plug-ins" with the following configuration:
    * Condition: None
    * Event: Core – Library Loaded (Page Top)
1. Add an action to the above rule with the following configuration:
    * Extension: Common Analytics Plugins
    * Action Type: Initialize Numbers Suite
1. Save and publish the changes to the rule.-->

## Instalación del complemento con el editor de código personalizado

Si no desea utilizar la extensión del complemento, puede utilizar el editor de código personalizado.

1. Inicie sesión en la [Recopilación de datos de Adobe Experience Platform](https://experience.adobe.com/data-collection) con sus credenciales de Adobe ID.
1. Haga clic en la propiedad deseada.
1. Vaya a la pestaña [!UICONTROL Extensiones] y, a continuación, haga clic en el botón **[!UICONTROL Configurar]** en la extensión de Adobe Analytics.
1. Expanda [!UICONTROL Configurar seguimiento con el código personalizado], que muestra el botón [!UICONTROL Abrir editor].
1. Abra el editor de código personalizado y pegue el código del complemento que se proporciona a continuación en la ventana de edición.
1. Guarde y publique los cambios en la extensión de Analytics.

## Instalación del complemento con AppMeasurement

Copie y pegue el siguiente código en cualquier parte del archivo AppMeasurement después de crear una instancia del objeto de seguimiento de Analytics (con [`s_gi`](../functions/s-gi.md)). Conservar los comentarios y los números de versión del código en la implementación ayuda a Adobe a solucionar cualquier posible problema.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: zeroPad v1.0 */
function zeroPad(num,nod){num=parseInt(num);nod=parseInt(nod);if(isNaN(num)||isNaN(nod))return"";var c=nod-num.toString().length+ 1;return Array(+(0<c&&c)).join("0")+num};

/* Adobe Consulting Plugin: randomNumber v2.0 (zeroPad plug-in optional)*/
function randomNumber(nod){nod="number"===typeof nod?17>Math.abs(nod)?Math.round(Math.abs(nod)):17:10;for(var a="1",c=0;c<nod;c++) a+="0";a=Number(a);a=Math.floor(Math.random().toFixed(nod)*a)+"";a.length!==nod&&"undefined"!==typeof zeroPad&&(a=zeroPad(a,nod)); return a};

/* Adobe Consulting Plugin: twoDecimals v1.0 */
function twoDecimals(v){return"undefined"===typeof v||void 0===v||isNaN(v)?0:Number(Number(v).toFixed(2))};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Uso de los complementos

La función `zeroPad` utiliza los siguientes argumentos:

* **num** (obligatorio, entero): El número que se va a rellenar. La función redondea el valor de este argumento si contiene decimales.
* **nod** (obligatorio, entero): El número de dígitos en el valor devuelto final. Si el número que se va a rellenar tiene menos dígitos que el número de dígitos a los que se va a rellenar, el complemento agrega ceros al principio del argumento `num`.

La función `randomNumber` utiliza los siguientes argumentos:

* **nod** (opcional, entero): El número de dígitos del número aleatorio que desea generar. El valor máximo es de 17 dígitos. El valor predeterminado son 10 dígitos.

La función `twoDecimals` utiliza los siguientes argumentos:

* **val** (obligatorio, número): Un número (representado por una cadena o un objeto numérico) que desea redondear a la centésima más cercana.

## Devuelve

* La función **zeroPad** devuelve una cadena igual al argumento `num`, pero con un número específico de ceros agregados al principio de su valor, lo que garantiza que el valor devuelto tenga el número correcto de dígitos.
* La función **randomNumber** devuelve una cadena equivalente a un número aleatorio con el número deseado de dígitos.
* La función **twoDecimals** devuelve un objeto numérico redondeado a la centésima más cercana.

## Llamadas de ejemplo

### ejemplos de zeroPad

```js
s.eVar25 = zeroPad(25.5562, 5) //sets eVar25 equal to "00025"

s.prop1 = zeroPad(25, 1) //sets prop1 equal to "25"

s.prop1 = zeroPad(232425235,23) //sets prop1 equal to "00000000000000232425235"
```

### ejemplos de randomNumber

```js
s.eVar65 = randomNumber(15) //sets eVar65 equal to "721759731750342" or some other random 15-digit number

randomNumber() //returns a random 10-digit number but is useless since this isn't used in an expression

var j = randomNumber(35) //sets a variable named j equal to "15476068651810060" or another random 17-digit number
```

### ejemplos de twoDecimals

```js
s.events = "event10=" + twoDecimals("85.4827128694") //sets s.events="event10=85.48"

var fivehundredthirtytwo = twoDecimals(532.000000001) //sets the variable fivehundredthirtytwo equal to 532

s.eVar65 = twoDecimals("672132.9699736457") //sets s.eVar65 equal to 672132.97
```

## Historial de versiones

### 1.0 (25 de mayo de 2019)

* Versión inicial.

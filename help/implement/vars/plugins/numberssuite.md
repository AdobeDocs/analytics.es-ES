---
title: Numbers Suite
description: Produzca y manipule números para utilizarlos en otras variables de JavaScript.
exl-id: 7af88dce-baf3-4581-b5b6-0d6e41922266
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '638'
ht-degree: 100%

---

# Complemento de Adobe: Numbers Suite

>[!IMPORTANT]
>
>Adobe Consulting proporciona este complemento por cortesía para ayudarle a sacar el máximo partido a Adobe Analytics. El Servicio de atención al cliente de Adobe no ofrece asistencia técnica con este complemento, incluida la instalación o solución de problemas. Si necesita ayuda con este complemento, póngase en contacto con el administrador de cuentas de su organización. Ellos podrán organizar una reunión con un consultor para ayudarle.

Numbers Suite contiene una serie de funciones de JavaScript. Incluye los siguientes complementos:

* **`zeroPad`**: Agregue un número específico de ceros al principio de un número. Este complemento es útil si una variable requiere un determinado número de dígitos, por ejemplo si trabaja con objetos de fecha de JavaScript y desea dar formato al mes y al día de una fecha con dos dígitos en lugar de uno solo. Por ejemplo, `01/09/2020` en lugar de `1/9/2020`.
* **`randomNumber`**: Genera un número aleatorio con un número específico de dígitos. Este complemento resulta útil si implementa etiquetas de terceros y desea un número aleatorio que elimine la caché.
* **`twoDecimals`**: Redondea un número hasta la centésima más cercana. Este complemento es útil para fines monetarios, ya que le permite redondear un número a un valor de moneda válido.

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
   * Tipo de acción: Inicializar grupo de números
1. Guarde y publique los cambios en la regla.

## Instalación del complemento con el editor de código personalizado de Launch

Si no desea utilizar la extensión del complemento, puede utilizar el editor de código personalizado.

1. Inicie sesión en [launch.adobe.com](https://launch.adobe.com) con sus credenciales de Adobe ID.
1. Haga clic en la propiedad deseada.
1. Vaya a la pestaña [!UICONTROL Extensiones] y, a continuación, haga clic en el botón [!UICONTROL Configurar] en la extensión de Adobe Analytics.
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

El método `zeroPad` utiliza los siguientes argumentos:

* **num** (obligatorio, entero): El número que se va a rellenar. El método redondea el valor de este argumento si contiene decimales.
* **nod** (obligatorio, entero): El número de dígitos en el valor devuelto final. Si el número que se va a rellenar tiene menos dígitos que el número de dígitos a los que se va a rellenar, el complemento agrega ceros al principio del argumento `num`.

El método `randomNumber` utiliza los siguientes argumentos:

* **nod** (opcional, entero): El número de dígitos del número aleatorio que desea generar. El valor máximo es de 17 dígitos. El valor predeterminado son 10 dígitos.

El método `twoDecimals` utiliza los siguientes argumentos:

* **val** (obligatorio, número): Un número (representado por una cadena o un objeto numérico) que desea redondear a la centésima más cercana.

## Devuelve

* El método **zeroPad** devuelve una cadena igual al argumento `num` pero con un número específico de ceros agregados al principio de su valor, lo que garantiza que el valor devuelto tenga el número correcto de dígitos.
* El método **randomNumber** devuelve una cadena equivalente a un número aleatorio con el número deseado de dígitos.
* El método **twoDecimals** devuelve un objeto numérico redondeado a la centésima más cercana.

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

---
title: formatTime
description: Convierta un número de segundos en su equivalente en minutos, horas, etc.
feature: Appmeasurement Implementation
exl-id: 4b98e7fe-f05b-4346-b284-697268adc1a2
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '582'
ht-degree: 88%

---

# Complemento de Adobe: formatTime

{{plug-in}}

El complemento `formatTime` le permite presentar cualquier cifra en segundos en un formato agrupado, redondeada al valor de referencia deseado. Adobe recomienda utilizar este complemento si desea registrar un valor de tiempo en segundos y convertirlo en un formato agrupado (como minutos, días o semanas). Este complemento no es necesario si no desea incluir valores basados en segundos en un formato redondeado de tiempo.

## Instalación del complemento con la extensión Web SDK o Web SDK

Este complemento aún no es compatible con el uso en Web SDK.

## Instalación del complemento con la extensión de Adobe Analytics

Adobe ofrece una extensión que le permite utilizar los complementos más utilizados con Adobe Analytics.

1. Inicie sesión en la [Recopilación de datos de Adobe Experience Platform](https://experience.adobe.com/data-collection) con sus credenciales de Adobe ID.
1. Haga clic en la propiedad de etiquetas deseada.
1. Vaya a la pestaña [!UICONTROL Extensiones] y, a continuación, haga clic en el botón [!UICONTROL Catálogo].
1. Instalación y publicación de la extensión [!UICONTROL Common Analytics Plugins].
1. Si aún no lo ha hecho, cree una regla con la etiqueta “Inicializar complementos” con la siguiente configuración:
   * Condición: Ninguna
   * Evento: Core – Biblioteca cargada (Principio de página)
1. Añada una acción a la regla anterior con la siguiente configuración:
   * Extensión: Common Analytics Plugins
   * Tipo de acción: Inicializar formatTime
1. Guarde y publique los cambios en la regla.

## Instalación del complemento con el editor de código personalizado de 

Si no desea utilizar la extensión de complemento Common Analytics Plugins, puede utilizar el editor de código personalizado.

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
/* Adobe Consulting Plugin: formatTime v2.0 */
function formatTime(ns,tf,bml){var f=ns,d=tf,e=bml;function h(b,d,c,e){if("string"!==typeof d)return!1;if("string"===typeof b)b=b.split(c||",");else if("object"!==typeof b)return!1;c=0;for(a=b.length;c<a;c++)if(1==e&&d===b[c]||d.toLowerCase()===b[c].toLowerCase())return!0;return!1}if(arguments&&"-v"===arguments[0])return{plugin:"formatTime",version:"2.0"};var b=function(){if("undefined"!==typeof window.s_c_il)for(var b=0,c;b<window.s_c_il.length;b++)if(c=window.s_c_il[b],c._c&&"s_c"===c._c)return c}();"undefined"!==typeof b&&(b.contextData.formatTime="2.0");if(!("undefined"===typeof f||isNaN(f)||0>Number(f))){b="";if("string"===typeof d&&"d"===d||("string"!==typeof d||!h("h,m,s",d))&&86400<=f){var c=86400;var g="days";b=isNaN(e)?1:c/(e*c)}else"string"===typeof d&&"h"===d||("string"!==typeof d||!h("m,s",d))&&3600<=f?(c=3600,g="hours",b=isNaN(e)?4:c/(e*c)):"string"===typeof d&&"m"===d||("string"!==typeof d||!h("s",d))&&60<=f?(c=60,g="minutes",b=isNaN(e)?2:c/(e*c)):(c=1,g="seconds",b=isNaN(e)?.2:c/e);b=Math.round(f*b/c)/b+" "+g;0===b.indexOf("1 ")&&(b=b.substring(0,b.length-1));return b}};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Uso del complemento

La función `formatTime` utiliza los siguientes argumentos:

* **`ns`** (obligatorio, entero): El número de segundos que convertir o al que dar formato.
* **`tf`** (opcional, cadena): Tipo de formato en el que se devuelven los segundos. Formato predeterminado: segundos.
   * Establézcalo en `"d"` si desea la hora en días (redondeada al valor de referencia de 1/4 días más cercano de forma predeterminada).
   * Establézcalo en `"h"` si desea la hora en horas (redondeada al valor de referencia de 1/4 horas más cercano de forma predeterminada).
   * Establézcalo en `"m"` si desea el tiempo en minutos (redondeado al valor de referencia de 1/2 minutos más cercano de forma predeterminada).
   * Establézcalo en `"s"` si desea el tiempo en segundos (redondeado al valor de referencia de 5 segundos más cercano de forma predeterminada).
* **`bml`** (opcional, número): Duración de los puntos de referencia de redondeo. Valores predeterminados de los puntos de referencia enumerados en el argumento `tf`

La función recupera el número de segundos formateados mediante la unidad especificada en el argumento `tf`. Si el argumento `tf` no está establecido:

* Cualquier valor inferior a un minuto se redondea al valor de referencia de 5 segundos más cercano.
* Cualquier valor entre un minuto y una hora se redondea al punto de referencia de medio minuto más cercano.
* Cualquier valor entre una hora y un día se redondea al valor de referencia un cuarto de hora más cercano.
* Cualquier valor superior a un día se redondea al valor de referencia del día más próximo.

## Ejemplos

```js
// Sets eVar1 to "10.5 hours".
// 38242 seconds equals 10 hours, 37 minutes, and 22 seconds. Since the tf argument is not set, the value returned is the number of seconds converted to the nearest quarter-hour benchmark.
s.eVar1 = formatTime(38242);

// Sets eVar4 to "10.75 hours".
// 38250 seconds equals 10 hours, 37 minutes, and 30 seconds. This value rounds up to the nearest quarter hour.
s.eVar4 = formatTime(38250);

// Sets eVar9 to "637.5 minutes".
s.eVar9 = formatTime(38242, "m");

// Sets eVar14 to "640 minutes".
// The tf argument forces the returned value to minutes, while the bml argument forces the value to the nearest 20-minute increment.
s.eVar14 = formatTime(38242, "m", 20);

// Sets eVar2 to "126 seconds", the closest 2-second benchmark to 125 seconds.
s.eVar2 = formatTime(125, "s", 2);

// Sets eVar7 to "3 minutes", the closest 3-minute benchmark to 125 seconds.
s.eVar7 = formatTime(125, "m", 3);

// Sets eVar55 to "2.4 minutes, the closest 2/5-minute benchmark to 145 seconds.
s.eVar55 = formatTime(145, "m", .4);
```

## Historial de versiones

### 2.0 (19 de marzo de 2021)

* Se ha añadido el número de versión como datos de contexto.

### 1.1 (21 de mayo de 2018)

* Se agregó el argumento `bml` para permitir una mayor flexibilidad en el redondeo

### 1.0 (15 de abril de 2018)

* Versión inicial.

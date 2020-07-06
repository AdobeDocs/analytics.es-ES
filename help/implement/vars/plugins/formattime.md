---
title: formatTime
description: Convierta un número de segundos en su equivalente en minutos, horas, etc.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '817'
ht-degree: 100%

---


# Complemento de Adobe: formatTime

>[!IMPORTANT]
>
>Adobe Consulting proporciona este complemento por cortesía para ayudarle a sacar el máximo partido a Adobe Analytics. El Servicio de atención al cliente de Adobe no ofrece asistencia técnica con este complemento, incluida la instalación o solución de problemas. Si necesita ayuda con este complemento, póngase en contacto con el administrador de cuentas de su organización. Ellos podrán organizar una reunión con un consultor para ayudarle.

El complemento `formatTime` le permite presentar cualquier cifra en segundos en un formato agrupado, redondeada al valor de referencia deseado. Adobe recomienda utilizar este complemento si desea registrar un valor de tiempo en segundos y convertirlo en un formato agrupado (como minutos, días o semanas). Este complemento no es necesario si no desea incluir valores basados en segundos en un formato redondeado de tiempo.

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
   * Tipo de acción: Inicializar formatTime
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
/* Adobe Consulting Plugin: formatTime v1.1 (Requires inList plug-in) */
s.formatTime=function(ns,tf,bml){var s=this;if(!("undefined"===typeof ns||isNaN(ns)||0>Number(ns))){if("string"===typeof tf&&"d"===tf||("string"!==typeof tf||!s.inList("h,m,s",tf))&&86400<=ns){tf=86400;var d="days";bml=isNaN(bml)?1:tf/(bml*tf)} else"string"===typeof tf&&"h"===tf||("string"!==typeof tf||!s.inList("m,s",tf))&&3600<=ns?(tf=3600,d="hours", bml=isNaN(bml)?4: tf/(bml*tf)):"string"===typeof tf&&"m"===tf||("string"!==typeof tf||!s.inList("s",tf))&&60<=ns?(tf=60,d="minutes",bml=isNaN(bml)?2: tf/(bml*tf)):(tf=1,d="seconds",bml=isNaN(bml)?.2:tf/bml);ns=Math.round(ns*bml/tf)/bml+" "+d;0===ns.indexOf("1 ")&&(ns=ns.substring(0, ns.length-1));return ns}};

/* Adobe Consulting Plugin: inList v2.1 */
s.inList=function(lv,vtc,d,cc){if("string"!==typeof vtc)return!1;if("string"===typeof lv)lv=lv.split(d||",");else if("object"!== typeof lv)return!1;d=0;for(var e=lv.length;d<e;d++)if(1==cc&&vtc===lv[d]||vtc.toLowerCase()===lv[d].toLowerCase())return!0;return!1};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Uso del complemento

El método `formatTime` utiliza los siguientes argumentos:

* **`ns`** (obligatorio, entero): El número de segundos que convertir o al que dar formato.
* **`tf`** (opcional, cadena): Tipo de formato en el que se devuelven los segundos. Formato predeterminado: segundos.
   * Establézcalo en `"d"` si desea la hora en días (redondeada al valor de referencia de 1/4 días más cercano de forma predeterminada).
   * Establézcalo en `"h"` si desea la hora en horas (redondeada al valor de referencia de 1/4 horas más cercano de forma predeterminada).
   * Establézcalo en `"m"` si desea el tiempo en minutos (redondeado al valor de referencia de 1/2 minutos más cercano de forma predeterminada).
   * Establézcalo en `"s"` si desea el tiempo en segundos (redondeado al valor de referencia de 5 segundos más cercano de forma predeterminada).
* **`bml`** (opcional, número): Duración de los puntos de referencia de redondeo. Valores predeterminados de los puntos de referencia enumerados en el argumento `tf`

El método recupera el número de segundos formateados con la unidad especificada en el argumento `tf`. Si el argumento `tf` no está establecido:

* Cualquier valor inferior a un minuto se redondea al valor de referencia de 5 segundos más cercano.
* Cualquier valor entre un minuto y una hora se redondea al punto de referencia de medio minuto más cercano.
* Cualquier valor entre una hora y un día se redondea al valor de referencia un cuarto de hora más cercano.
* Cualquier valor superior a un día se redondea al valor de referencia del día más próximo.

## Ejemplos

### Ejemplo 1

El siguiente código...

```js
s.eVar1 = s.formatTime(38242);
```

... configura s.eVar1 igual a “10,5 horas”

El argumento pasado (38242 segundos) es igual a 10 horas, 37 minutos y 22 segundos.  Dado que el argumento tf no se establece en esta llamada y el número de segundos pasados es entre una hora y un día, el complemento recupera el número de segundos convertidos con el valor de referencia de trimestre más cercano.

### Ejemplo 2

El siguiente código...

```js
s.eVar1 = s.formatTime(38250);
```

... configura s.eVar1 igual a “10,75 horas”
El argumento pasado (38250 segundos) es igual a 10 horas, 37 minutos y 30 segundos.  Si redondea el número de segundos pasados al valor de referencia de trimestre-hora más cercano en este caso, el valor final se establece en 10,75 horas.

### Ejemplo 3

El siguiente código...

```js
s.eVar1 = s.formatTime(38242, "m");
```

... es s.eVar1 igual a “637,5 minutos”

En este caso, el argumento “m” fuerza al complemento a convertir los segundos al punto de referencia de medio minuto más cercano.

### Ejemplo 4

El siguiente código...

```js
s.eVar1 = s.formatTime(38242, "m", 20);
```

... es s.eVar1 igual a “640 minutos”

El valor del argumento tf (“m”) fuerza al complemento a convertir los segundos en minutos, pero el valor del argumento bml (20) también fuerza al complemento a redondear la conversión de minutos al punto de referencia de 20 minutos más cercano.

### Ejemplo 5

El siguiente código...

```js
s.eVar1 = s.formatTime(125, "s", 2);
```

... es s.eVar1 igual a “126 segundos”, que es el valor de referencia de 2 segundos más cercano a 125 segundos.

### Ejemplo 6

El siguiente código...

```js
s.eVar1 = s.formatTime(125, "m", 3);
```

... es s.eVar1 igual a “3 segundos”, que es el valor de referencia de 3 minutos más cercano a 125 segundos.

### Ejemplo 7

El siguiente código...

```js
s.eVar1 = s.formatTime(145, "m", .4);
```

... es.eVar1 será igual a “2,4 minutos”, que es el punto de referencia de 2/5 minutos más cercano (p. ej. .4 = 2/5) a 145 segundos.

## Historial de versiones

### 1.1 (21 de mayo de 2018)

* Se agregó el argumento `bml` para permitir una mayor flexibilidad en el redondeo

### 1.0 (15 de abril de 2018)

* Versión inicial.

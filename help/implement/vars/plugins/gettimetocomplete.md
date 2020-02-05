---
title: getTimeToComplete
description: Mida la cantidad de tiempo que se tarda en completar una tarea.
translation-type: tm+mt
source-git-commit: 180ad544541f25d02b3a257559bc045abed7387b

---


# Complemento de Adobe: getTimeToComplete

> [!IMPORTANT] Este complemento lo proporciona Adobe Consulting por cortesía para ayudarle a obtener más valor de Adobe Analytics. El Servicio de atención al cliente de Adobe no ofrece asistencia técnica con este complemento, incluida la instalación o solución de problemas. Si necesita ayuda con este complemento, póngase en contacto con el administrador de cuentas de su organización. Pueden organizar una reunión con un consultor para obtener ayuda.

El `getTimeToComplete` complemento rastrea el tiempo que un usuario tarda en completar un proceso en un sitio. El &quot;reloj&quot; comienza cuando se llama a la `start` acción y finaliza cuando se llama a la `stop` acción. Adobe recomienda utilizar este complemento si hay un flujo de trabajo en el sitio que tarde algún tiempo en completarse y desea saber cuánto tiempo tardan los visitantes en completarlo. No es necesario utilizar este complemento si el flujo de trabajo del sitio tarda un corto período de tiempo (menos de 3 segundos) porque la granularidad se reduce sólo al segundo completo.

## Instalación del complemento con la extensión Adobe Experience Platform Launch

Adobe ofrece una extensión que le permite utilizar los complementos más utilizados.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
1. Haga clic en la propiedad que desee.
1. Vaya a la ficha [!UICONTROL Extensiones] y, a continuación, haga clic en el botón [!UICONTROL Catálogo]
1. Instalación y publicación de la extensión [!UICONTROL Common Analytics Plugins]
1. Si aún no lo ha hecho, cree una regla con la etiqueta &quot;Inicializar complementos&quot; con la siguiente configuración:
   * Condición: Ninguno
   * Evento: Core - Biblioteca cargada (Principio de página)
1. Agregue una acción a la regla anterior con la siguiente configuración:
   * Extensión: Complementos comunes de Analytics
   * Tipo de acción: Inicializar getTimeToComplete
1. Guarde y publique los cambios en la regla.

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
/* Adobe Consulting Plugin: getTimeToComplete v3.1 (Requires formatTime and inList plug-ins) */
s.getTimeToComplete=function(sos,cn,exp){sos=sos?sos.toLowerCase():"start";if("stop"===sos||"start"===sos){cn=cn?cn:"s_gttc";exp=exp?exp:0;var s=this,d=s.c_r(cn),e=new Date;if("start"===sos&&!d)s.c_w(cn,e.getTime(),exp?new Date(e.getTime()+864E5*exp):0);else if("stop"===sos&&d)return sos=Math.round((e.getTime()-d)/1E3),s.c_w(cn,"",0),s.formatTime(sos)}};

/* Adobe Consulting Plugin: formatTime v1.1 (Requires inList plug-in) */
s.formatTime=function(ns,tf,bml){var s=this;if(!("undefined"===typeof ns||isNaN(ns)||0>Number(ns))){if("string"===typeof tf&&"d"===tf||("string"!==typeof tf||!s.inList("h,m,s",tf))&&86400<=ns){tf=86400;var d="days";bml=isNaN(bml)?1:tf/(bml*tf)} else"string"===typeof tf&&"h"===tf||("string"!==typeof tf||!s.inList("m,s",tf))&&3600<=ns?(tf=3600,d="hours", bml=isNaN(bml)?4: tf/(bml*tf)):"string"===typeof tf&&"m"===tf||("string"!==typeof tf||!s.inList("s",tf))&&60<=ns?(tf=60,d="minutes",bml=isNaN(bml)?2: tf/(bml*tf)):(tf=1,d="seconds",bml=isNaN(bml)?.2:tf/bml);ns=Math.round(ns*bml/tf)/bml+" "+d;0===ns.indexOf("1 ")&&(ns=ns.substring(0,ns.length-1));return ns}};

/* Adobe Consulting Plugin: inList v2.1 */
s.inList=function(lv,vtc,d,cc){if("string"!==typeof vtc)return!1;if("string"===typeof lv)lv=lv.split(d||",");else if("object"!== typeof lv)return!1;d=0;for(var e=lv.length;d<e;d++)if(1==cc&&vtc===lv[d]||vtc.toLowerCase()===lv[d].toLowerCase())return!0;return!1};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Utilizar el complemento

El `getTimeToComplete` método utiliza los siguientes argumentos:

* **`sos`**(opcional, cadena): Establezca en`"start"`cuando desee iniciar el temporizador. Establezca en`"stop"`cuando desee detener el temporizador. El valor predeterminado es`"start"`.
* **`cn`**(opcional, cadena): El nombre de la cookie para almacenar la hora de inicio. El valor predeterminado es`"s_gttc"`.
* **`exp`**(opcional, entero): Número de días que caduca la cookie (y el temporizador). El valor predeterminado es`0`, que representa el final de la sesión del explorador.

Al llamar a este método se devuelve una cadena que contiene el número de días, horas, minutos y/o segundos que transcurrió entre la acción `"start"` y `"stop"` .

## Llamadas de ejemplo

### Ejemplo #1

Utilice estas llamadas para determinar el tiempo que transcurre entre el momento en que un visitante inicia el proceso de cierre de compra y el momento en que realiza una compra.

Inicie el temporizador cuando el visitante inicie el cierre de compra:

```js
if(s.events.indexOf("scCheckout") > -1) s.getTimeToComplete("start");
```

Detenga el temporizador cuando el visitante realice la compra y establezca prop1 en la diferencia horaria entre detención e inicio:

```js
if(s.events.indexOf("purchase") > -1) s.prop1 = s.getTimeToComplete("stop");
```

s.prop1 capturará la cantidad de tiempo necesario para completar el proceso de compra

### Ejemplo #2

Si desea que varios temporizadores se ejecuten al mismo tiempo (para medir diferentes procesos), deberá configurar manualmente el argumento cn cookie.  Por ejemplo: si desea medir la cantidad de tiempo necesaria para que se complete una compra, debe establecer el siguiente código...

```javascript
if(s.inList(s.events, "scCheckout")) s.getTimeToComplete("start", "gttcpurchase");
if(s.inList(s.events, "purchase")) s.prop1 = s.getTimeToComplete("start", "gttcpurchase");
```

...pero si también desea medir (al mismo tiempo) la cantidad de tiempo necesaria para rellenar un formulario de registro, también debe ejecutar el siguiente código:

```js
if(s.inList(s.events, "event1")) s.getTimeToComplete("start", "gttcregister", 7);
if(s.inList(s.events, "event2")) s.prop2 = s.getTimeToComplete("stop", "gttcregister", 7);
```

En el segundo ejemplo, event1 tiene el propósito de capturar el inicio de un proceso de registro que puede llevar hasta 7 días para completarse, por cualquier motivo, y event2 tiene el propósito de capturar la finalización del registro.  s.prop2 capturará la cantidad de tiempo necesaria para completar el proceso de registro

## Historial de versiones

### 3.1 (30 de septiembre de 2019)

* Se ha añadido una lógica que requiere un valor de &quot;start&quot; o &quot;stop&quot; en el primer argumento.  Todos los demás valores pasados detienen la ejecución del complemento.
* Se ha actualizado `inList 2.0` el complemento a `inList 2.1`.

### 3.0 (23 de agosto de 2018)

* Se ha actualizado el `formatTime v1.0` complemento a `formatTime v1.1`.

### 3.0 (17 de abril de 2018)

* Versión puntual (recompilada, tamaño de código más pequeño).
* Se han corregido errores menores.

### 2.0 21 de junio de 2016)

* Se eliminó la dependencia del `p_fo` complemento.
* Se agregó compatibilidad con el código H y AppMeasurement.
* Se agregó el registro de la consola.

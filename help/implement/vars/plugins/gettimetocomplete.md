---
title: getTimeToComplete
description: Mida el tiempo que se tarda en completar una tarea.
translation-type: ht
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Complemento de Adobe: getTimeToComplete

>[!IMPORTANT] Adobe Consulting proporciona este complemento por cortesía para ayudarle a sacar el máximo partido a Adobe Analytics. El Servicio de atención al cliente de Adobe no ofrece asistencia técnica con este complemento, incluida la instalación o solución de problemas. Si necesita ayuda con este complemento, póngase en contacto con el administrador de cuentas de su organización. Ellos podrán organizar una reunión con un consultor para ayudarle.

El complemento `getTimeToComplete` rastrea el tiempo que un usuario tarda en completar un proceso en un sitio. El “reloj” comienza cuando se llama a la acción `start` y finaliza cuando se llama a la acción `stop`. Adobe recomienda utilizar este complemento si hay un flujo de trabajo en el sitio que lleve cierto tiempo completar y si desea saber cuánto tiempo tardan los visitantes en completarlo. No es necesario utilizar este complemento si el flujo de trabajo del sitio lleva un breve periodo de tiempo (menos de 3 segundos) porque la granularidad solo se reduce al segundo completo.

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
   * Tipo de acción: Inicializar getTimeToComplete
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
/* Adobe Consulting Plugin: getTimeToComplete v3.1 (Requires formatTime and inList plug-ins) */
s.getTimeToComplete=function(sos,cn,exp){sos=sos?sos.toLowerCase():"start";if("stop"===sos||"start"===sos){cn=cn?cn:"s_gttc";exp=exp?exp:0;var s=this,d=s.c_r(cn),e=new Date;if("start"===sos&&!d)s.c_w(cn,e.getTime(),exp?new Date(e.getTime()+864E5*exp):0);else if("stop"===sos&&d)return sos=Math.round((e.getTime()-d)/1E3),s.c_w(cn,"",0),s.formatTime(sos)}};

/* Adobe Consulting Plugin: formatTime v1.1 (Requires inList plug-in) */
s.formatTime=function(ns,tf,bml){var s=this;if(!("undefined"===typeof ns||isNaN(ns)||0>Number(ns))){if("string"===typeof tf&&"d"===tf||("string"!==typeof tf||!s.inList("h,m,s",tf))&&86400<=ns){tf=86400;var d="days";bml=isNaN(bml)?1:tf/(bml*tf)} else"string"===typeof tf&&"h"===tf||("string"!==typeof tf||!s.inList("m,s",tf))&&3600<=ns?(tf=3600,d="hours", bml=isNaN(bml)?4: tf/(bml*tf)):"string"===typeof tf&&"m"===tf||("string"!==typeof tf||!s.inList("s",tf))&&60<=ns?(tf=60,d="minutes",bml=isNaN(bml)?2: tf/(bml*tf)):(tf=1,d="seconds",bml=isNaN(bml)?.2:tf/bml);ns=Math.round(ns*bml/tf)/bml+" "+d;0===ns.indexOf("1 ")&&(ns=ns.substring(0,ns.length-1));return ns}};

/* Adobe Consulting Plugin: inList v2.1 */
s.inList=function(lv,vtc,d,cc){if("string"!==typeof vtc)return!1;if("string"===typeof lv)lv=lv.split(d||",");else if("object"!== typeof lv)return!1;d=0;for(var e=lv.length;d<e;d++)if(1==cc&&vtc===lv[d]||vtc.toLowerCase()===lv[d].toLowerCase())return!0;return!1};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Uso del complemento

El método `getTimeToComplete` utiliza los siguientes argumentos:

* **`sos`** (opcional, cadena): Configúrelo en `"start"` cuando desee iniciar el temporizador. Configúrelo en `"stop"` cuando desee detener el temporizador. El valor predeterminado es `"start"`.
* **`cn`** (opcional, cadena): El nombre de la cookie para almacenar la hora de inicio. El valor predeterminado es `"s_gttc"`.
* **`exp`** (opcional, entero): El número de días en que caduca la cookie (y el temporizador). El valor predeterminado es `0`, que representa el final de la sesión del explorador.

Llamar a este método devuelve una cadena que contiene el número de días, horas, minutos y/o segundos que transcurridos entre la acción `"start"` y `"stop"`.

## Llamadas de ejemplo

### Ejemplo 1

Utilice estas llamadas para determinar el tiempo que transcurre entre el momento en que un visitante inicia el proceso de cierre de compra y el momento en que realiza una compra.

Inicie el temporizador cuando el visitante inicie el cierre de compra:

```js
if(s.events.indexOf("scCheckout") > -1) s.getTimeToComplete("start");
```

Detenga el temporizador cuando el visitante realice la compra y configure prop1 en la diferencia horaria entre la detención y el inicio:

```js
if(s.events.indexOf("purchase") > -1) s.prop1 = s.getTimeToComplete("stop");
```

s.prop1 registrará el tiempo necesario para completar el proceso de compra

### Ejemplo 2

Si desea que varios temporizadores se ejecuten al mismo tiempo (para medir diferentes procesos), deberá configurar manualmente el argumento de cookie cn.  Por ejemplo: Si desea medir el tiempo necesario para completar una compra, debe establecer el siguiente código...

```javascript
if(s.inList(s.events, "scCheckout")) s.getTimeToComplete("start", "gttcpurchase");
if(s.inList(s.events, "purchase")) s.prop1 = s.getTimeToComplete("start", "gttcpurchase");
```

...pero si también desea medir (a la vez) el tiempo necesario para rellenar un formulario de registro, también debe ejecutar el siguiente código:

```js
if(s.inList(s.events, "event1")) s.getTimeToComplete("start", "gttcregister", 7);
if(s.inList(s.events, "event2")) s.prop2 = s.getTimeToComplete("stop", "gttcregister", 7);
```

En el segundo ejemplo, event1 tiene el propósito de registrar el inicio de un proceso de registro que, por cualquier razón, puede llevar hasta 7 días completar y event2 tiene el propósito de capturar la finalización del registro.  s.prop2 registrará el tiempo necesario para completar el proceso de registro

## Historial de versiones

### 3.1 (30 de septiembre de 2019)

* Se ha añadido una lógica que requiere un valor de “start” o “stop” en el primer argumento.  El resto de valores pasados detienen la ejecución del complemento.
* Se ha actualizado el complemento `inList 2.0` a `inList 2.1`.

### 3.0 (23 de agosto de 2018)

* Se ha actualizado el complemento `formatTime v1.0` a `formatTime v1.1`.

### 3.0 (17 de abril de 2018)

* Versión puntual (compilada de nuevo, con un tamaño de código más pequeño).
* Se han corregido errores menores.

### 2.0 (21 de junio de 2016)

* Se ha eliminado la dependencia del complemento `p_fo`.
* Se ha agregado compatibilidad con el código H y con AppMeasurement.
* Se ha agregado el registro de la consola.

---
title: ' getTimeBetweenEvents'
description: Mida la cantidad de tiempo entre dos eventos.
translation-type: tm+mt
source-git-commit: 365944140bb1dfc9bc8669ae530c631e8ff1629b

---


# Complemento de Adobe: getTimeBetweenEvents

> [!IMPORTANT] Este complemento lo proporciona Adobe Consulting por cortesía para ayudarle a obtener más valor de Adobe Analytics. El Servicio de atención al cliente de Adobe no ofrece asistencia técnica con este complemento, incluida la instalación o solución de problemas. Si necesita ayuda con este complemento, póngase en contacto con el administrador de cuentas de su organización. Pueden organizar una reunión con un consultor para obtener ayuda.

El `getTimeBetweenEvents` complemento le permite realizar un seguimiento de la cantidad de tiempo entre dos eventos de Analytics cualesquiera, incluidos el carro de compras y los eventos personalizados. Resulta útil para rastrear la cantidad de tiempo que tarda un proceso de cierre de compra en completarse o cualquier otro proceso que desee medir. Este complemento es innecesario si no tiene ningún proceso de conversión que desee medir cuánto tiempo tardan.

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
/* Adobe Consulting Plugin: getTimeBetweenEvents v2.1 (Requires formatTime and inList plug-ins) */
s.getTimeBetweenEvents=function(ste,rt,stp,res,cn,etd,fmt,bml,rte){var s=this;if("string"===typeof ste&&"undefined"!==typeof rt&&"string"===typeof stp&&"undefined"!==typeof res){cn=cn?cn:"s_tbe";etd=isNaN(etd)?1:Number(etd);var f=!1,g=!1,n=!1, p=ste.split(","),q=stp.split(",");rte=rte?rte.split(","):[];for(var h=s.c_r(cn),k,v=new Date,r=v.getTime(),c=new Date,a=0; a<rte.length;++a)s.inList(s.events,rte[a])&&(n=!0);c.setTime(c.getTime()+864E5*etd);for(a=0;a<p.length&&!f&&(f=s.inList(s.events,p[a]),!0!==f);++a);for(a=0;a<q.length&&!g&&(g=s.inList(s.events,q[a]),!0!==g);++a);1===p.length&&1===q.length&&ste===stp&&f&&g?(h&&(k=(r-h)/1E3),s.c_w(cn,r,etd?c:0)):(!f||1!=rt&&h||s.c_w(cn,r,etd?c:0),g&&h&&(k=(v.getTime()-h)/1E3,!0===res&&(n=!0)));!0===n&&(c.setDate( c.getDate()-1),s.c_w(cn,"",c));return k?s.formatTime(k,fmt,bml):""}};

/* Adobe Consulting Plugin: formatTime v1.1 (Requires inList plug-in) */
s.formatTime=function(ns,tf,bml){var s=this;if(!("undefined"===typeof ns||isNaN(ns)||0>Number(ns))){if("string"===typeof tf&&"d"===tf||("string"!==typeof tf||!s.inList("h,m,s",tf))&&86400<=ns){tf=86400;var d="days";bml=isNaN(bml)?1:tf/(bml*tf)} else"string"===typeof tf&&"h"===tf||("string"!==typeof tf||!s.inList("m,s",tf))&&3600<=ns?(tf=3600,d="hours", bml=isNaN(bml)?4: tf/(bml*tf)):"string"===typeof tf&&"m"===tf||("string"!==typeof tf||!s.inList("s",tf))&&60<=ns?(tf=60,d="minutes",bml=isNaN(bml)?2: tf/(bml*tf)):(tf=1,d="seconds",bml=isNaN(bml)?.2:tf/bml);ns=Math.round(ns*bml/tf)/bml+" "+d;0===ns.indexOf("1 ")&&(ns=ns.substring(0,ns.length-1));return ns}};

/* Adobe Consulting Plugin: inList v2.1 */
s.inList=function(lv,vtc,d,cc){if("string"!==typeof vtc)return!1;if("string"===typeof lv)lv=lv.split(d||",");else if("object"!== typeof lv)return!1;d=0;for(var e=lv.length;d<e;d++)if(1==cc&&vtc===lv[d]||vtc.toLowerCase()===lv[d].toLowerCase())return!0;return!1};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Utilizar el complemento

El `getTimeBetweenEvents` método utiliza los siguientes argumentos:

* **`ste`**(requerido, cadena): Iniciar eventos de temporizador. Una cadena de eventos de Analytics delimitada por comas para &quot;iniciar el temporizador&quot;.
* **`rt`**(requerido, booleano): Reinicie la opción del temporizador. Se establece en`true`si desea reiniciar el temporizador cada vez que la`events`variable contenga un evento de temporizador de inicio. Se establece en`false`si no desea que el temporizador se reinicie cuando vea un evento de temporizador de inicio.
* **`stp`**(requerido, cadena): Detenga los eventos de temporizador. Cadena delimitada por comas de eventos de Analytics que &quot;detienen el temporizador&quot;.
* **`res`**(requerido, booleano): Opción Restablecer temporizador. Establezca en`true`si desea registrar el tiempo desde que se inició el temporizador Y restablezca el temporizador después de que se detenga. Se establece en`false`si desea registrar la hora pero no detener el temporizador. Si se establece en`false`, el temporizador continúa ejecutándose después de que la variable events registre un evento stop.
   > [!TIP] Si establece este argumento en `false`, se recomienda configurar el `rte` argumento siguiente.
* **`cn`**(opcional, cadena): Nombre de la cookie en la que se almacena la hora del primer evento. El valor predeterminado es`"s_tbe"`.
* **`etd`**(opcional, entero): Tiempo de caducidad de la cookie en días. Se configura para que`0`caduque al final de la sesión del explorador. El valor predeterminado es 1 día cuando no se establece.
* **`fmt`**(opcional, cadena): Formato del tiempo en el que se devuelve el número de segundos (el valor predeterminado es nada)
   * `"s"` durante segundos
   * `"m"` durante minutos
   * `"h"` durante horas
   * `"d"` durante días
   * Si no se establece, el formato del valor devuelto se basa en las siguientes reglas:
      * Todo menos de un minuto se redondea al punto de referencia de 5 segundos más cercano. Por ejemplo, 10 segundos, 15 segundos
      * Todo lo que haya entre un minuto y una hora se redondea al punto de referencia de 1/2 minutos más cercano. Por ejemplo, 30,5 minutos, 31 minutos
      * Cualquier cosa entre una hora y un día se redondea al valor de referencia de cuarto de hora más cercano. Por ejemplo, 2,25 horas, 3,5 horas
      * Cualquier valor mayor que un día se redondea al valor de referencia del día más próximo. Por ejemplo: 1 día, 3 días, 9 días
* **`bml`**(opcional, número): Duración del índice de redondeo según el formato del`fmt`argumento. Por ejemplo, si el`fmt`argumento es`"s"`y este argumento es`2`, el valor devuelto se redondea al valor de referencia de 2 segundos más cercano. Si`fmt`el argumento es`"m"`y este argumento es`0.5`, el valor devuelto se redondea al valor de referencia de medio minuto más cercano.
* **`rte`**(opcional, cadena): Cadena delimitada por comas de eventos de Analytics que eliminan o eliminan el temporizador. El valor predeterminado no es nada.

Al llamar a este método se devuelve un entero que representa la cantidad de tiempo entre el evento de temporizador de inicio y el evento de temporizador de parada en el formato deseado.

## Llamadas de ejemplo

### Ejemplo n.º 1

El siguiente código...

```js
s.eVar1 = s.getTimeBetweenEvents("event1", true, "event2", true, "", 0, "s", 2, "event3");
```

...está configurado para comportarse de la siguiente manera:

* El temporizador se iniciará cuando s.events contenga event1.
* El temporizador se reiniciará cada vez que s.events contenga event1
* El temporizador se detendrá cuando s.events contenga event2
* El temporizador se restablecerá (es decir, pasará a 0 segundos) cada vez que s.events contenga event2
* El temporizador también se restablecerá cuando s.events contenga event3 O si el visitante cierra su explorador
* Cuando se registra un tiempo real entre event1 y event2, el complemento establece eVar1 igual al número de segundos entre los dos eventos que se configuran, redondeado al valor de referencia de 2 segundos más cercano (por ejemplo: 0 segundos, 2 segundos, 4 segundos, 10 segundos, 184 segundos, etc.)
* Si s.events contiene event2 antes de que se inicie un temporizador, no se configurará eVar1.

### Ejemplo n.º 2

El siguiente código...

```js
s.eVar1 = s.getTimeBetweenEvents("event1", false, "event2", false, "s_20", 20, "h", 1.5, "event3");
```

...está configurado para comportarse de la siguiente manera:

* El temporizador se iniciará cuando s.events contenga event1.
* El temporizador NO se reiniciará cada vez que s.events contenga event1, sino que el temporizador original seguirá ejecutándose
* El temporizador NO se detendrá cuando s.events contenga event2, pero el complemento registrará la hora desde que se registró la configuración de event1 original
* El temporizador se almacena en una cookie llamada &quot;s_20&quot;
* El temporizador se restablecerá solamente cuando s.events contenga event3 OR si han transcurrido 20 días desde que se inició el temporizador
* Cuando se registra un tiempo entre el evento1 (original) y el evento2, el complemento configurará eVar1 igual al número de horas entre los dos eventos que se configuran, redondeado al valor de referencia de 1/2 horas más cercano (por ejemplo: 0 horas, 1,5 horas, 3 horas, 7,5 horas, 478,5 horas, etc.)

### Ejemplo n.º 3

El siguiente código...

```js
s.eVar1 = s.getTimeBetweenEvents("event1", true, "event2", true);
```

...producirá resultados similares al primer ejemplo anterior; sin embargo, el valor de eVar1 se devuelve en segundos, minutos, horas o días, según la duración final del temporizador.  Además, el temporizador caducará un día después de que se haya establecido por primera vez en lugar de cuando el visitante cierre su explorador.

## Historial de versiones

### 2.1 (26 de mayo de 2018)

* Adapta los cambios realizados a la nueva versión del `formatTime` complemento.

### 2.0 (6 de abril de 2018)

* Reescritura/reanálisis completo del complemento.

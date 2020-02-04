---
title: getVisitNum
description: Rastrear el número de visitas actual de un visitante.
translation-type: tm+mt
source-git-commit: 180ad544541f25d02b3a257559bc045abed7387b

---


# Complemento de Adobe: getVisitNum

> [!IMPORTANT] Este complemento lo proporciona Adobe Consulting por cortesía para ayudarle a obtener más valor de Adobe Analytics. El Servicio de atención al cliente de Adobe no ofrece asistencia técnica con este complemento, incluida la instalación o solución de problemas. Si necesita ayuda con este complemento, póngase en contacto con el administrador de cuentas de su organización. Pueden organizar una reunión con un consultor para obtener ayuda.

El `getVisitNum` complemento devuelve el número de visitas de todos los visitantes que llegan al sitio dentro del número de días deseado. Analysis Workspace ofrece una dimensión &#39;Número de visita&#39; que proporciona una funcionalidad similar. Adobe recomienda utilizar este complemento si desea controlar mejor cómo se incrementa el número de visitas. Este complemento no es necesario si la dimensión &#39;Número de visita&#39; integrada en Analysis Workspace es suficiente para sus necesidades de informes.

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
   * Tipo de acción: Inicializar getVisitNum
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
/* Adobe Consulting Plugin: getVisitNum v4.11 (Requires endOfDatePeriod plug-in) */
s.getVisitNum=function(rp,erp){var s=this,c=function(rp){return isNaN(rp)?!1:(parseFloat(rp)|0)===parseFloat(rp)};rp=rp?rp:365;erp= "undefined"!==typeof erp?!!erp:c(rp)?!0:!1;var e=(new Date).getTime(),b=endOfDatePeriod(rp);if(s.c_r("s_vnc"+rp))var g=s.c_r("s_vnc"+rp).split("&vn="),d=g[1];if(s.c_r("s_ivc"))return d?(b.setTime(e+18E5),s.c_w("s_ivc",!0,b),d):"unknown visit number";if("undefined"!==typeof d)return d++,c=erp&&c(rp)?e+864E5*rp:g[0],b.setTime(c),s.c_w("s_vnc"+rp,c+"&vn="+d,b),b.setTime(e+ 18E5),s.c_w("s_ivc",!0,b),d;c=c(rp)?e+864E5*rp:endOfDatePeriod(rp).getTime();s.c_w("s_vnc"+rp,c+"&vn=1",b);b.setTime(e+18E5); s.c_w("s_ivc",!0,b);return"1"};

/* Adobe Consulting Plugin: endOfDatePeriod v1.1 */
var endOfDatePeriod=function(dp){var a=new Date,b=isNaN(dp)?0:Math.floor(dp);a.setHours(23);a.setMinutes(59);a.setSeconds(59); "w"===dp&&(b=6-a.getDay());if("m"===dp){b=a.getMonth()+1;var d=a.getFullYear();b=(new Date(d?d:1970,b?b:1,0)).getDate()-a.getDate()}a.setDate(a.getDate()+b);"y"===dp&&(a.setMonth(11),a.setDate(31));return a};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Utilizar el complemento

El `getVisitNum` método utiliza los siguientes argumentos:

* **`rp`**(opcional, entero O cadena): Número de días antes de que se restablezca el contador de números de visitas.  El valor predeterminado es`365`cuando no se establece.
   * Cuando este argumento es `"w"`, el contador se restablece al final de la semana (este sábado a las 11:59 pm)
   * Cuando este argumento es `"m"`, el contador se restablece al final del mes (el último día de este mes)
   * Cuando este argumento es `"y"`, el contador se restablece al final del año (31 de diciembre)
* **`erp`**(opcional, booleano): Cuando el`rp`argumento es un número, este argumento determina si se debe ampliar la caducidad del número de visita. Si se establece en`true`, las visitas posteriores al sitio restablecen el contador de números de visitas. Si se establece en`false`, las visitas posteriores al sitio no se extienden cuando se restablece el contador de números de visitas. El valor predeterminado es`true`. Este argumento no es válido cuando el`rp`argumento es una cadena.

El número de visitas aumenta cada vez que el visitante regresa al sitio después de 30 minutos de inactividad. Al llamar a este método se devuelve un entero que representa el número de visita actual del visitante.

Este complemento establece una cookie de origen llamada `"s_vnc[LENGTH]"` , donde `[LENGTH]` es el valor que se pasa al `rp` argumento. Por ejemplo, `"s_vncw"`, `"s_vncm"`o `"s_vnc365"`. El valor de la cookie es una combinación de una marca de tiempo Unix que representa cuándo se restablece el contador de visitas, como fin de semana, fin de mes o después de 365 días de inactividad. También contiene el número de visita actual. Este complemento establece otra cookie denominada `"s_ivc"` que se establece en `true` y caduca tras 30 minutos de inactividad.

## Llamadas de ejemplo

### Ejemplo n.º 1

Para un visitante que no ha estado en el sitio en los últimos 365 días, el siguiente código establecerá s.prop1 en el valor de 1:

```js
s.prop1=s.getVisitNum();
```

### Ejemplo n.º 2

Para un visitante que regresa al sitio dentro de los 364 días posteriores a su primera visita, el siguiente código establecerá s.prop1 en 2:

```js
s.prop1=s.getVisitNum(365);
```

Si este visitante regresa al sitio dentro de los 364 días posteriores a su segunda visita, el siguiente código establecerá s.prop1 en 3:

```js
s.prop1=s.getVisitNum(365);
```

### Ejemplo n.º 3

Para un visitante que regresa al sitio dentro de los 179 días posteriores a su primera visita, el siguiente código establecerá s.prop1 en 2:

```js
s.prop1=s.getVisitNum(180,false);
```

Sin embargo, si este visitante regresa al sitio 1 o más días después de su segunda visita, el siguiente código establecerá s.prop1 en 1:

```js
s.prop1=s.getVisitNum(180,false);
```

Cuando el segundo argumento de la llamada es igual a false, la rutina que determina cuándo se debe &quot;restablecer&quot; el número de visita a 1 lo hará &quot;x&quot; número de días (en este ejemplo, 365 días) después de la primera visita del visitante al sitio.

Cuando el segundo argumento es igual a true (o no está establecido), el complemento restablecerá el número de visita a 1 solamente después de &quot;x&quot; número de días (nuevamente, en este ejemplo, 365 días) de inactividad del visitante.

### Ejemplo n.º 4

Para todos los visitantes que ingresan al sitio por primera vez durante la semana actual (comenzando el domingo), el siguiente código establecerá s.prop1 en 1:

```js
s.prop1=s.getVisitNum("w");
```

### Ejemplo n.º 5

Para todos los visitantes que ingresan al sitio por primera vez durante el mes actual (comenzando el primer día de cada mes), el siguiente código establecerá s.prop1 en 1:

```js
s.prop1=s.getVisitNum("m");
```

Tenga en cuenta que el complemento getVisitNum no tiene en cuenta los calendarios basados en minoristas (por ejemplo: 4-5-4, 4-4-5, etc.)

### Ejemplo n.º 6

Para todos los visitantes que ingresan al sitio por primera vez durante el año actual (a partir del 1 de enero), el siguiente código establecerá s.prop1 en 1:

```js
s.prop1=s.getVisitNum("y");
```

### Ejemplo n.º 7

Si desea rastrear el número de visita de un visitante para la semana, el número de visita de un visitante para el mes y el número de visita de un visitante para el año (todo dentro de distintas variables de Analytics), debe utilizar un código similar al siguiente:

```js
s.prop1=s.getVisitNum("w");
s.prop2=s.getVisitNum("m");
s.prop3=s.getVisitNum("y");
```

En este caso, el complemento creará tres cookies diferentes, una para cada uno de los diferentes períodos de tiempo, para realizar un seguimiento del número de visita individual por período de tiempo.

## Historial de versiones

### 4.11 (30 de septiembre de 2019)

* Se corrigió un problema en el cual el `erp` argumento se establecía explícitamente en `false`.

### 4.1 (21 de mayo de 2018)

* Se ha actualizado el `endOfDatePeriod` complemento a v1.1.

### 4.0 (17 de abril de 2018)

* Versión puntual (recompilada, tamaño de código más pequeño).
* Se han eliminado los argumentos de cookies, ya que el complemento ahora genera cookies de forma dinámica en función del `rp` argumento)

### 3.0 (5 de junio de 2016)

* Revisión completa
* Se han combinado todas las soluciones anteriores disponibles en varias versiones del `getVisitNum` complemento.

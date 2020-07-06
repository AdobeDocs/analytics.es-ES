---
title: getVisitNum
description: Rastree el número de la visita actual de un visitante.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '1041'
ht-degree: 100%

---


# Complemento de Adobe: getVisitNum

>[!IMPORTANT]
>
>Adobe Consulting proporciona este complemento por cortesía para ayudarle a sacar el máximo partido a Adobe Analytics. El Servicio de atención al cliente de Adobe no ofrece asistencia técnica con este complemento, incluida la instalación o solución de problemas. Si necesita ayuda con este complemento, póngase en contacto con el administrador de cuentas de su organización. Ellos podrán organizar una reunión con un consultor para ayudarle.

El complemento `getVisitNum` devuelve el número de la visita de todos los visitantes que acceden al sitio dentro del número de días deseado. Analysis Workspace ofrece una dimensión “Número de visita” que proporciona una funcionalidad similar. Adobe recomienda utilizar este complemento si desea controlar mejor cómo se incrementa el número de visitas. Este complemento no es necesario si la dimensión “Número de visita” integrada en Analysis Workspace resulta suficiente para los informes que necesita.

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
   * Tipo de acción: Inicializar getVisitNum
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
/* Adobe Consulting Plugin: getVisitNum v4.11 (Requires endOfDatePeriod plug-in) */
s.getVisitNum=function(rp,erp){var s=this,c=function(rp){return isNaN(rp)?!1:(parseFloat(rp)|0)===parseFloat(rp)};rp=rp?rp:365;erp= "undefined"!==typeof erp?!!erp:c(rp)?!0:!1;var e=(new Date).getTime(),b=endOfDatePeriod(rp);if(s.c_r("s_vnc"+rp))var g=s.c_r("s_vnc"+rp).split("&vn="),d=g[1];if(s.c_r("s_ivc"))return d?(b.setTime(e+18E5),s.c_w("s_ivc",!0,b),d):"unknown visit number";if("undefined"!==typeof d)return d++,c=erp&&c(rp)?e+864E5*rp:g[0],b.setTime(c),s.c_w("s_vnc"+rp,c+"&vn="+d,b),b.setTime(e+ 18E5),s.c_w("s_ivc",!0,b),d;c=c(rp)?e+864E5*rp:endOfDatePeriod(rp).getTime();s.c_w("s_vnc"+rp,c+"&vn=1",b);b.setTime(e+18E5); s.c_w("s_ivc",!0,b);return"1"};

/* Adobe Consulting Plugin: endOfDatePeriod v1.1 */
var endOfDatePeriod=function(dp){var a=new Date,b=isNaN(dp)?0:Math.floor(dp);a.setHours(23);a.setMinutes(59);a.setSeconds(59); "w"===dp&&(b=6-a.getDay());if("m"===dp){b=a.getMonth()+1;var d=a.getFullYear();b=(new Date(d?d:1970,b?b:1,0)).getDate()-a.getDate()}a.setDate(a.getDate()+b);"y"===dp&&(a.setMonth(11),a.setDate(31));return a};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Uso del complemento

El método `getVisitNum` utiliza los siguientes argumentos:

* **`rp`** (opcional, entero O cadena): El número de días antes de que se restablezca el contador de números de visitas.  Si no se configura de forma distinta, el valor predeterminado es `365`.
   * Cuando este argumento es `"w"`, el contador se restablece al final de la semana (este sábado a las 23:59 h)
   * Cuando este argumento es `"m"`, el contador se restablece al final del mes (el último día del mes en curso)
   * Cuando este argumento es `"y"`, el contador se restablece al final del año (31 de diciembre)
* **`erp`** (opcional, booleano): Cuando el argumento `rp` es un número, este argumento determina si se debe ampliar la caducidad del número de visita. Si se establece en `true`, las posteriores visitas al sitio restablecerán el contador de número de visitas. Si se establece en `false`, las posteriores visitas al sitio no se amplían cuando se restablece el contador de número de visitas. El valor predeterminado es `true`. Este argumento no es válido cuando el argumento `rp` es una cadena.

El número de visitas aumenta cada vez que el visitante regresa al sitio después de 30 minutos de inactividad. Llamar a este método devuelve un entero que representa el número de visita actual.

Este complemento establece una cookie de origen llamada `"s_vnc[LENGTH]"`, donde `[LENGTH]` es el valor que se pasa al argumento `rp`. Por ejemplo, `"s_vncw"`, `"s_vncm"`o `"s_vnc365"`. El valor de la cookie es una combinación de una marca de tiempo Unix que representa cuándo se restablece el contador de visitas, como fin de semana, fin de mes o tras 365 días de inactividad. También contiene el número de visita actual. Este complemento establece otra cookie denominada `"s_ivc"` que se establece en `true` y caduca tras 30 minutos de inactividad.

## Llamadas de ejemplo

### Ejemplo 1

Para un visitante que no ha estado en el sitio en los últimos 365 días, el siguiente código establecerá s.prop1 en el valor 1:

```js
s.prop1=s.getVisitNum();
```

### Ejemplo 2

Para un visitante que regresa al sitio dentro de los 364 días posteriores a su primera visita, el siguiente código establecerá s.prop1 en 2:

```js
s.prop1=s.getVisitNum(365);
```

Si este visitante regresa al sitio dentro de los 364 días posteriores a su segunda visita, el siguiente código establecerá s.prop1 en 3:

```js
s.prop1=s.getVisitNum(365);
```

### Ejemplo 3

Para un visitante que regresa al sitio dentro de los 179 días posteriores a su primera visita, el siguiente código establecerá s.prop1 en 2:

```js
s.prop1=s.getVisitNum(180,false);
```

Sin embargo, si este visitante regresa al sitio al menos un día después de su segunda visita, el siguiente código establecerá s.prop1 en 1:

```js
s.prop1=s.getVisitNum(180,false);
```

Cuando el segundo argumento de la llamada tiene un valor false, la rutina que determina cuándo se debe “restablecer” a 1 el número de visita lo hará “x” días después (en este ejemplo, 365 días) de la primera visita al sitio.

Cuando el segundo argumento tiene un valor true (o no está establecido), el complemento restablecerá el número de visita a 1 solo después de “x” días (de nuevo, en este ejemplo, 365 días) de inactividad del visitante.

### Ejemplo 4

Para todos los visitantes que acceden al sitio por primera vez durante la semana en curso (que comienza el domingo), el siguiente código establecerá s.prop1 en 1:

```js
s.prop1=s.getVisitNum("w");
```

### Ejemplo 5

Para todos los visitantes que acceden al sitio por primera vez durante el mes en curso (a partir del primer día de cada mes), el siguiente código establecerá s.prop1 en 1:

```js
s.prop1=s.getVisitNum("m");
```

Tenga en cuenta que el complemento getVisitNum no tiene en cuenta los calendarios de comercio minorista (es decir, los calendarios 4-5-4, 4-4-5, etc.)

### Ejemplo 6

Para todos los visitantes que acceden al sitio por primera vez durante el año en curso (a partir del 1 de enero), el siguiente código establecerá s.prop1 en 1:

```js
s.prop1=s.getVisitNum("y");
```

### Ejemplo 7

Si desea rastrear el número de visita de un visitante en la semana, el número de visita de un visitante en el mes y el número de visita de un visitante en el año (todo dentro de distintas variables de Analytics), debe utilizar un código similar al siguiente:

```js
s.prop1=s.getVisitNum("w");
s.prop2=s.getVisitNum("m");
s.prop3=s.getVisitNum("y");
```

En este caso, el complemento creará tres cookies diferentes, una para cada uno de los diferentes periodos de tiempo, para realizar un seguimiento del número de visita individual por periodo de tiempo.

## Historial de versiones

### 4.11 (30 de septiembre de 2019)

* Se ha corregido un problema en el que el argumento `erp` se establecía explícitamente en `false`.

### 4.1 (21 de mayo de 2018)

* Se ha actualizado el complemento `endOfDatePeriod` a v1.1.

### 4.0 (17 de abril de 2018)

* Versión puntual (compilada de nuevo, con un tamaño de código más pequeño).
* Se han eliminado los argumentos de cookies, ya que el complemento ahora genera cookies de forma dinámica en función del argumento `rp`.

### 3.0 (5 de junio de 2016)

* Revisión completa.
* Se han combinado todas las soluciones anteriores disponibles en varias versiones del complemento `getVisitNum`.

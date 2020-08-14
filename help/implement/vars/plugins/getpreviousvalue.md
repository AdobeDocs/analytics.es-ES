---
title: getPreviousValue
description: Obtenga el último valor que se haya pasado a una variable.
translation-type: ht
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: ht
source-wordcount: '888'
ht-degree: 100%

---


# Complemento de Adobe: getPreviousValue

>[!IMPORTANT]
>
>Adobe Consulting proporciona este complemento por cortesía para ayudarle a sacar el máximo partido a Adobe Analytics. El Servicio de atención al cliente de Adobe no ofrece asistencia técnica con este complemento, incluida la instalación o solución de problemas. Si necesita ayuda con este complemento, póngase en contacto con el administrador de cuentas de su organización. Ellos podrán organizar una reunión con un consultor para ayudarle.

El complemento `getPreviousValue` le permite establecer una variable en un valor establecido en una visita anterior. Este complemento no es necesario si la implementación contiene todos los valores deseados en la visita actual.

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
   * Tipo de acción: Inicializar getPreviousValue
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
/* Adobe Consulting Plugin: getPreviousValue v2.0 */
s.getPreviousValue=function(v,c){var s=this,d;c=c||"s_gpv";var b=new Date;b.setTime(b.getTime()+18E5);s.c_r(c)&&(d=s.c_r(c)); v?s.c_w(c,v,b):s.c_w(c,d,b);return d};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Uso del complemento

El método `getPreviousValue` utiliza los siguientes argumentos:

* **`v`** (cadena, obligatorio): La variable que tiene el valor que desea pasar a la siguiente solicitud de imagen. Una variable común es `s.pageName` y se utiliza para recuperar el valor de la página anterior.
* **`c`** (cadena, opcional): El nombre de la cookie que almacena el valor.  Si no se establece este argumento, el valor predeterminado es `"s_gpv"`.

Cuando llama a este método, devuelve el valor de cadena contenido en la cookie. A continuación, el complemento restablece la caducidad de la cookie y le asigna el valor de variable del argumento `v`. La cookie caduca tras 30 minutos de inactividad.

## Llamadas de ejemplo

### Ejemplo 1

El siguiente código...

```js
s.prop7=s.getPreviousValue(s.pageName,"gpv_Page")
```

* Primero establece s.prop7 en el valor pasado a s.pageName en la solicitud de imagen anterior (es decir, el valor almacenado en la cookie “gpv_Page”)
* El código restablecerá la cookie “gpv_Page”, haciéndola igual al valor actual de s.pageName
* Si s.pageName no se configura en el momento de ejecutar este código, entonces el código restablecerá la caducidad del valor actual de la cookie

### Ejemplo 2

El siguiente código establece s.prop7 en el último valor pasado a s.pageName, pero solo si event1 también está contenido en s.events, según se determina mediante el complemento inList, en el momento en que se realiza la llamada.

```js
if(s.inList(s.events,"event1")) s.prop7=s.getPreviousValue(s.pageName,"gpv_Page");
```

### Ejemplo 3

El siguiente código establece s.prop7 en el último valor pasado a s.pageName pero solo si en ese momento s.pageName está establecido en la página al mismo tiempo.

```js
if(s.pageName) s.prop7=s.getPreviousValue(s.pageName,"gpv_Page");
```

### Ejemplo 4

El siguiente código establece s.eVar10 en el valor pasado a s.eVar1 en la solicitud de imagen anterior.   El valor anterior de eVar1 se habría incluido en la cookie “s_gpv”.  El código establecerá entonces la cookie “s_gpv” en el valor actual de s.eVar1.

```js
s.eVar10 = s.getPreviousValue(s.eVar1)
```

## Particularidades improbables

Si la variable asociada con el argumento v se establece en un nuevo valor y se ejecuta el complemento getPreviousValue PERO NO se envía una llamada al servidor de Analytics al mismo tiempo, el nuevo valor del argumento v seguirá considerándose el “valor anterior” la próxima vez que se ejecute el complemento.
Por ejemplo, supongamos que el siguiente código se ejecuta en la primera página de la visita:

```js
s.pageName="home"
s.prop7=s.getPreviousValue(s.pageName,"gpv_Page")
s.t();
```

Este código produciría una llamada al servidor donde el argumento pageName es igual a “home” y el argumento p7 (prop7) no está establecido.  Sin embargo, la llamada a s.getPreviousValue almacenaría el valor de s.pageName (es decir, “home”) en la cookie especificada en la llamada (es decir, la cookie “gpv_Page”).
Ahora, supongamos que inmediatamente después, en la misma página, se ejecuta el siguiente código (por cualquier razón):

```js
s.pageName="happy value"
s.prop7=s.getPreviousValue(s.pageName,"gpv_Page")
```

Dado que la función s.t() no se ejecuta en este bloque de código, no se creará otra solicitud de imagen.  Sin embargo, cuando el código de la función s.getPreviousValue() se ejecute esta vez, s.prop7 se establecerá en el valor anterior de s.pageName (es decir, “home”) y, a continuación, almacenará el nuevo valor de s.pageName (es decir, “happy value”) en la cookie “gpv_Page”.
Supongamos que el visitante navega a una página diferente y que se ejecuta el siguiente código en esta página:

```js
s.pageName="page 2"
s.prop7=s.getPreviousValue(s.pageName,"gpv_Page")
s.t();
```

Cuando se ejecuta la función de llamada s.t(), se crea una solicitud de imagen donde s.pageName=“page 2” y s.prop7 es igual a “happy value”, que era el valor de s.pageName cuando se realizó la última llamada a getPreviousValue.   El valor de s.prop7 como “home” nunca se incluyó en ninguna solicitud de imagen real aunque “home” fuera el primer valor pasado a s.pageName.

## Historial de versiones

### v2.0 (7 de octubre de 2019)

* Versión puntual (reescritura lógica completa).

---
title: getPreviousValue
description: Obtenga el último valor pasado a una variable.
translation-type: tm+mt
source-git-commit: 26f06adbef1608a6e01df3ab1d3ad4ba78abc28f

---


# Complemento de Adobe: getPreviousValue

> [!IMPORTANT] Este complemento lo proporciona Adobe Consulting por cortesía para ayudarle a obtener más valor con el uso de Adobe Analytics. El Servicio de atención al cliente de Adobe no ofrece asistencia técnica con este complemento, incluida la instalación o solución de problemas. Si necesita ayuda con este complemento, póngase en contacto con el administrador de cuentas de su organización. Pueden organizar una reunión con un consultor para obtener ayuda.

El `getPreviousValue` complemento le permite establecer una variable en un valor establecido en una visita anterior. Este complemento no es necesario si la implementación contiene todos los valores deseados en la visita actual.

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
/* Adobe Consulting Plugin: getPreviousValue v2.0 */
s.getPreviousValue=function(v,c){var s=this,d;c=c||"s_gpv";var b=new Date;b.setTime(b.getTime()+18E5);s.c_r(c)&&(d=s.c_r(c)); v?s.c_w(c,v,b):s.c_w(c,d,b);return d};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Utilizar el complemento

El `getPreviousValue` método utiliza los siguientes argumentos:

* **`v`**(cadena, requerido): Variable que tiene el valor que desea pasar a la siguiente solicitud de imagen. Una variable común utilizada es`s.pageName`recuperar el valor de página anterior.
* **`c`**(cadena, opcional): Nombre de la cookie que almacena el valor.  Si no se establece este argumento, el valor predeterminado es`"s_gpv"`.

Cuando llama a este método, devuelve el valor de cadena contenido en la cookie. A continuación, el complemento restablece la caducidad de la cookie y le asigna el valor de variable del `v` argumento. La cookie caduca tras 30 minutos de inactividad.

## Llamadas de ejemplo

### Ejemplo n.º 1

El siguiente código...

```js
s.prop7=s.getPreviousValue(s.pageName,"gpv_Page")
```

* Primero establece s.prop7 igual al valor pasado a s.pageName en la solicitud de imagen anterior (es decir, el valor almacenado en la cookie &quot;gpv_Page&quot;)
* El código restablecerá la cookie &quot;gpv_Page&quot;, haciéndola igual al valor actual de s.pageName
* Si s.pageName no se configura en el momento de ejecutar este código, entonces el código restablecerá la caducidad del valor actual de la cookie

### Ejemplo n.º 2

El código siguiente establece s.prop7 como el último valor pasado a s.pageName, pero sólo si event1 también está contenido en s.events, según se determina mediante el complemento inList, en el momento en que se realiza la llamada.

```js
if(s.inList(s.events,"event1")) s.prop7=s.getPreviousValue(s.pageName,"gpv_Page");
```

### Ejemplo n.º 3

El siguiente código establece s.prop7 como el último valor pasado a s.pageName pero solo si s.pageName está actualmente establecido en la página al mismo tiempo.

```js
if(s.pageName) s.prop7=s.getPreviousValue(s.pageName,"gpv_Page");
```

### Ejemplo n.º 4

El siguiente código establece s.eVar10 igual al valor pasado a s.eVar1 en la solicitud de imagen anterior.   El valor anterior de eVar1 se habría incluido en la cookie &quot;s_gpv&quot;.  El código establecerá entonces la cookie &quot;s_gpv&quot; igual al valor actual de s.eVar1.

```js
s.eVar10 = s.getPreviousValue(s.eVar1)
```

## Cuchillos improbables

Si la variable asociada con el argumento v se establece en un nuevo valor y se ejecuta el complemento getPreviousValue PERO NO se envía una llamada al servidor de Analytics al mismo tiempo, el nuevo valor del argumento v seguirá considerándose el &quot;valor anterior&quot; la próxima vez que se ejecute el complemento.
Por ejemplo, supongamos que el siguiente código se ejecuta en la primera página de la visita:

```js
s.pageName="home"
s.prop7=s.getPreviousValue(s.pageName,"gpv_Page")
s.t();
```

Este código produciría una llamada al servidor donde el argumento pageName es igual a &quot;home&quot; y el argumento p7 (prop7) no está establecido.  Sin embargo, la llamada a s.getPreviousValue almacenaría el valor de s.pageName (por ejemplo: &quot;home&quot;) en la cookie especificada en la llamada (es decir, la cookie &quot;gpv_Page&quot;).
Ahora, supongamos que inmediatamente después, en la misma página, se ejecuta el siguiente código (por cualquier razón):

```js
s.pageName="happy value"
s.prop7=s.getPreviousValue(s.pageName,"gpv_Page")
```

Dado que la función s.t() no se ejecuta en este bloque de código, no se creará otra solicitud de imagen.  Sin embargo, cuando el código de la función s.getPreviousValue() se ejecute esta vez, s.prop7 se establecerá igual al valor anterior de s.pageName (por ejemplo: &quot;home&quot;) y, a continuación, almacenará el nuevo valor de s.pageName (es decir, &quot;valor feliz&quot;) en la cookie &quot;gpv_Page&quot;.
Supongamos que el visitante navega a una página diferente y que el código siguiente se ejecuta en esta página:

```js
s.pageName="page 2"
s.prop7=s.getPreviousValue(s.pageName,"gpv_Page")
s.t();
```

Cuando se ejecuta la función de llamada s.t(), se crea una solicitud de imagen donde s.pageName=&quot;page 2&quot; y s.prop7 es igual a &quot;valor feliz&quot;, que era el valor de s.pageName cuando se realizó la última llamada a getPreviousValue.   El valor s.prop7 de &quot;home&quot; nunca se incluyó en ninguna solicitud de imagen real aunque &quot;home&quot; fuera el primer valor que se pasaba a s.pageName.

## Historial de versiones

### v2.0 (7 de octubre de 2019)

* Versión de punto (reescritura lógica completa).

---
title: getPreviousValue
description: Obtenga el último valor que se haya pasado a una variable.
feature: Appmeasurement Implementation
exl-id: 235c504b-ba97-4399-a07b-b0bfc764f1ba
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '751'
ht-degree: 77%

---

# Complemento de Adobe: getPreviousValue

{{plug-in}}

El complemento `getPreviousValue` le permite establecer una variable en un valor establecido en una visita anterior. Este complemento no es necesario si la implementación contiene todos los valores deseados en la visita actual.

## Instalación del complemento con la extensión Web SDK

Adobe ofrece una extensión que le permite utilizar los complementos más utilizados con Web SDK.

1. Inicie sesión en la [Recopilación de datos de Adobe Experience Platform](https://experience.adobe.com/data-collection) con sus credenciales de Adobe ID.
1. Haga clic en **[!UICONTROL Etiquetas]** a la izquierda y luego haga clic en la propiedad de etiquetas deseada.
1. Haga clic en **[!UICONTROL Extensiones]** a la izquierda y, a continuación, haga clic en la ficha **[!UICONTROL Catálogo]**
1. Busque e instale la extensión **[!UICONTROL Common Web SDK Plugins]**.
1. Haga clic en **[!UICONTROL Elementos de datos]** a la izquierda y, a continuación, haga clic en el elemento de datos deseado.
1. Establezca el nombre del elemento de datos deseado con la siguiente configuración:
   * Extensión: Common Web SDK Plugins
   * Elemento de datos: `getPreviousValue`
1. Configure los parámetros deseados a la derecha.
1. Guarde y publique los cambios en el elemento de datos.

## Instalación manual del complemento que implementa Web SDK

Este complemento aún no es compatible con una implementación manual de Web SDK.

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
   * Tipo de acción: Inicializar getPreviousValue
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
/* Adobe Consulting Plugin: getPreviousValue v3.0 */
function getPreviousValue(v,c){var k=v,d=c;if("-v"===k)return{plugin:"getPreviousValue",version:"3.0"};var a=function(){if("undefined"!==typeof window.s_c_il)for(var c=0,b;c<window.s_c_il.length;c++)if(b=window.s_c_il[c],b._c&&"s_c"===b._c)return b}();"undefined"!==typeof a&&(a.contextData.getPreviousValue="3.0");window.cookieWrite=window.cookieWrite||function(c,b,f){if("string"===typeof c){var h=window.location.hostname,a=window.location.hostname.split(".").length-1;if(h&&!/^[0-9.]+$/.test(h)){a=2<a?a:2;var e=h.lastIndexOf(".");if(0<=e){for(;0<=e&&1<a;)e=h.lastIndexOf(".",e-1),a--;e=0<e?h.substring(e):h}}g=e;b="undefined"!==typeof b?""+b:"";if(f||""===b)if(""===b&&(f=-60),"number"===typeof f){var d=new Date;d.setTime(d.getTime()+6E4*f)}else d=f;return c&&(document.cookie=encodeURIComponent(c)+"="+encodeURIComponent(b)+"; path=/;"+(f?" expires="+d.toUTCString()+";":"")+(g?" domain="+g+";":""),"undefined"!==typeof cookieRead)?cookieRead(c)===b:!1}};window.cookieRead=window.cookieRead||function(c){if("string"===typeof c)c=encodeURIComponent(c);else return"";var b=" "+document.cookie,a=b.indexOf(" "+c+"="),d=0>a?a:b.indexOf(";",a);return(c=0>a?"":decodeURIComponent(b.substring(a+2+c.length,0>d?b.length:d)))?c:""};var l;d=d||"s_gpv";a=new Date;a.setTime(a.getTime()+18E5);window.cookieRead(d)&&(l=window.cookieRead(d));k?window.cookieWrite(d,k,a):window.cookieWrite(d,l,a);return l};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Uso del complemento

La función `getPreviousValue` utiliza los siguientes argumentos:

* **`v`** (cadena, obligatorio): La variable que tiene el valor que desea pasar a la siguiente solicitud de imagen. Una variable común es `s.pageName` y se utiliza para recuperar el valor de la página anterior.
* **`c`** (cadena, opcional): El nombre de la cookie que almacena el valor.  Si no se establece este argumento, el valor predeterminado es `"s_gpv"`.

Cuando llama a esta función, devuelve el valor de cadena contenido en la cookie. A continuación, el complemento restablece la caducidad de la cookie y le asigna el valor de variable del argumento `v`. La cookie caduca tras 30 minutos de inactividad.

## Ejemplos

```js
// 1. Sets prop7 to the cookie value contained in gpv_Page
// 2. Resets the gpv_Page cookie value to the page variable
// 3. If the page variable is not set, reset the gpv_Page cookie expiration
s.prop7 = getPreviousValue(s.pageName,"gpv_Page");

// Sets prop7 to the cookie value contained in gpv_Page, but only if event1 is in the events variable.
if(inList(s.events,"event1")) s.prop7 = getPreviousValue(s.pageName,"gpv_Page");

// Sets prop7 to the cookie value contained in gpv_Page, but only if the page variable is currently set on the page
if(s.pageName) s.prop7 = getPreviousValue(s.pageName,"gpv_Page");

// Sets eVar10 equal to the cookie value contained in s_gpv, then sets the s_gpv cookie to the current value of eVar1.
s.eVar10 = getPreviousValue(s.eVar1);
```

## Particularidades improbables

Si la variable asociada con el argumento `v` se establece en un nuevo valor y se ejecuta el complemento `getPreviousValue` PERO NO se envía una llamada al servidor de Analytics al mismo tiempo, el nuevo valor del argumento `v` seguirá considerándose el &quot;valor anterior&quot; la próxima vez que se ejecute el complemento.
Por ejemplo, supongamos que el siguiente código se ejecuta en la primera página de la visita:

```js
s.pageName = "Home";
s.prop7 = getPreviousValue(s.pageName,"gpv_Page");
s.t();
```

Este código produce una llamada al servidor donde `pageName` es &quot;Home&quot; y prop7 no está configurado.  Sin embargo, la llamada a `getPreviousValue` almacena el valor de `pageName` en la cookie `gpv_Page`. Supongamos que inmediatamente después, en la misma página, se ejecuta el siguiente código:

```js
s.pageName = "New value";
s.prop7 = getPreviousValue(s.pageName,"gpv_Page");
```

Dado que la función `t()` no se ejecuta en este bloque de código, no se creará otra solicitud de imagen.  Sin embargo, cuando el código de la función `getPreviousValue` se ejecuta esta vez, `prop7` se establece en el valor anterior de `pageName` (&quot;Home&quot;) y, a continuación, almacena el nuevo valor de `pageName` (&quot;New value&quot;) en la cookie `gpv_Page`. A continuación, supongamos que el visitante navega a una página diferente y que se ejecuta el siguiente código en esta página:

```js
s.pageName = "Page 2";
s.prop7 = getPreviousValue(s.pageName,"gpv_Page");
s.t();
```

Cuando se ejecuta la función `t()`, crea una solicitud de imagen donde `pageName` es &quot;Página 2&quot; y `prop7` es &quot;Nuevo valor&quot;, que era el valor de `pageName` cuando se realizó la última llamada a `getPreviousValue`. El valor `prop7` de `"Home"` nunca se incluyó en ninguna solicitud de imagen real aunque &quot;home&quot; fuera el primer valor pasado a `pageName`.

## Historial de versiones

### 3.0 (19 de marzo de 2021)

* Se ha añadido el número de versión como datos de contexto.

### v2.0 (7 de octubre de 2019)

* Versión puntual (reescritura lógica completa).

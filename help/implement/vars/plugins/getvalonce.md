---
title: getValOnce
description: Impida que una variable de Analytics se establezca en el mismo valor dos veces seguidas.
translation-type: tm+mt
source-git-commit: 5a81754ca6137d7bc1e790fe537acbb4bbdb8efb
workflow-type: tm+mt
source-wordcount: '729'
ht-degree: 99%

---


# Complemento de Adobe: getValOnce

>[!IMPORTANT]
>
>Adobe Consulting proporciona este complemento por cortesía para ayudarle a sacar el máximo partido a Adobe Analytics. El Servicio de atención al cliente de Adobe no ofrece asistencia técnica con este complemento, incluida la instalación o solución de problemas. Si necesita ayuda con este complemento, póngase en contacto con el administrador de cuentas de su organización. Ellos podrán organizar una reunión con un consultor para ayudarle.

El complemento `getValOnce` evita que una variable se establezca en el mismo valor más de una vez. Adobe recomienda utilizar este complemento cuando desee anular la duplicación de incidencias cuando un visitante actualiza una página o visita una página determinada varias veces. Este complemento no es necesario si no le preocupa la métrica “Ocurrencias” de Analysis Workspace.

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
   * Tipo de acción: Inicializar getValOnce
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
/* Adobe Consulting Plugin: getValOnce v3.0 (Requires AppMeasurement) */
function getValOnce(vtc,cn,et,ep){var e=vtc,k=cn,l=et,m=ep;if(arguments&&"-v"===arguments[0])return{plugin:"getValOnce",version:"3.0"};var c=function(){if("undefined"!==typeof window.s_c_il)for(var b=0,a;b<window.s_c_il.length;b++)if(a=window.s_c_il[b],a._c&&"s_c"===a._c)return a}();"undefined"!==typeof c&&(c.contextData.getValOnce="3.0");window.cookieWrite=window.cookieWrite||function(b,a,d){if("string"===typeof b){var h=window.location.hostname,c=window.location.hostname.split(".").length-1;if(h&&!/^[0-9.]+$/.test(h)){c=2<c?
c:2;var f=h.lastIndexOf(".");if(0<=f){for(;0<=f&&1<c;)f=h.lastIndexOf(".",f-1),c--;f=0<f?h.substring(f):h}}g=f;a="undefined"!==typeof a?""+a:"";if(d||""===a)if(""===a&&(d=-60),"number"===typeof d){var e=new Date;e.setTime(e.getTime()+6E4*d)}else e=d;return b&&(document.cookie=encodeURIComponent(b)+"="+encodeURIComponent(a)+"; path=/;"+(d?" expires="+e.toUTCString()+";":"")+(g?" domain="+g+";":""),"undefined"!==typeof cookieRead)?cookieRead(b)===a:!1}};window.cookieRead=window.cookieRead||function(b){if("string"===
typeof b)b=encodeURIComponent(b);else return"";var a=" "+document.cookie,d=a.indexOf(" "+b+"="),c=0>d?d:a.indexOf(";",d);return(b=0>d?"":decodeURIComponent(a.substring(d+2+b.length,0>c?a.length:c)))?b:""};return e&&(k=k||"s_gvo",l=l||0,m="m"===m?6E4:864E5,e!==this.c_r(k))?(c=new Date,c.setTime(c.getTime()+l*m),cookieWrite(k,e,0===l?0:m),e):""};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Uso del complemento

El método `getValOnce` utiliza los siguientes argumentos:

* **`vtc`** (obligatorio, cadena): La variable para comprobar y ver si anteriormente se ha definido en un valor idéntico
* **`cn`** (opcional, cadena): El nombre de la cookie que contiene el valor que se va a comprobar. El valor predeterminado es `"s_gvo"`
* **`et`** (opcional, entero): La caducidad de la cookie en días (o minutos, según el argumento `ep`). El valor predeterminado es `0`, que caduca al final de la sesión del explorador
* **`ep`** (opcional, cadena): Establezca este argumento solo si también establece el argumento `et`. Establezca este argumento en `"m"` si desea que el argumento `et` caduque en minutos en lugar de en días. El valor predeterminado es `"d"`, que establece el argumento `et` en días.

Si el argumento `vtc` y el valor de la cookie coinciden, este método devuelve una cadena vacía. Si el argumento `vtc` y el valor de la cookie no coinciden, el método devuelve el argumento `vtc` como una cadena.

## Llamadas de ejemplo

### Ejemplo 1

Utilice esta llamada para evitar que el mismo valor se pase a s.campaign más de una vez seguidas en los 30 días siguientes:

```js
s.campaign=s.getValOnce(s.campaign,"s_campaign",30);
```

En la llamada anterior, el complemento comparará primero el valor que contiene la cookie s_campaign con el valor proveniente de la variable s.campaign actual.   Si no coinciden, el complemento establecerá la cookie s_campaign en el nuevo valor obtenido de s.campaign y, a continuación, devolverá el nuevo valor.   Esta comparación se realizará durante los próximos treinta días.

### Ejemplo 2

Utilice esta llamada para evitar que se establezca el mismo valor durante toda la sesión:

```js
s.eVar2=s.getValOnce(s.eVar2,"s_ev2",0,"m");
```

Este código evita que el mismo valor se pase a s.eVar2 más de una vez seguidas durante toda la sesión del usuario.  También ignora el valor “m” del argumento ep (al final de la llamada), ya que la hora de caducidad es igual a 0.   El código también almacena el valor de comparación en la cookie s_ev2.

## Historial de versiones

### 3.0 (19 de marzo de 2021)

* Se ha añadido el número de versión como datos de contexto.

### 2,01

* Se ha corregido un problema con la escritura de cookies.

### 2,0

* Versión puntual (compilada de nuevo, con un tamaño de código más pequeño).

### 1,1

* Se ha agregado la opción de elegir minutos o días para la caducidad mediante el parámetro `t`.
* Se ha corregido el ámbito de la variable `k` utilizada para restringirla solo al complemento. Este cambio evita posibles interferencias con otro código de la página.

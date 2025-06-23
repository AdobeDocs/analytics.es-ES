---
title: getAndPersistValue
description: Almacene un valor que pueda utilizarse posteriormente en cualquier momento.
feature: Appmeasurement Implementation
exl-id: b562f9ad-3844-4535-b729-bd3f63f6f0ae
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '677'
ht-degree: 70%

---

# Complemento de Adobe: getAndPersistValue

{{plug-in}}

El complemento `getAndPersistValue` le permite almacenar un valor en una cookie que se puede utilizar más adelante durante una visita. Cumple una función similar a la de la característica [!UICONTROL Duración del almacenamiento] de la extensión de Adobe Analytics en la recopilación de datos de Adobe Experience Platform. Adobe recomienda utilizar este complemento si desea mantener automáticamente una variable de Analytics con el mismo valor en las visitas posteriores después de configurar la variable. Este complemento no es necesario si la característica [!UICONTROL Duración del almacenamiento] de la extensión de Analytics es suficiente. Tampoco es necesario utilizar este complemento si no requiere establecer y mantener variables con el mismo valor en las visitas posteriores. La persistencia integrada de eVars no requiere el uso de este complemento, ya que Adobe mantiene eVars en el lado del servidor.

## Instalación del complemento con la extensión Web SDK

Adobe ofrece una extensión que le permite utilizar los complementos más utilizados con Web SDK.

1. Inicie sesión en la [Recopilación de datos de Adobe Experience Platform](https://experience.adobe.com/data-collection) con sus credenciales de Adobe ID.
1. Haga clic en **[!UICONTROL Etiquetas]** a la izquierda y luego haga clic en la propiedad de etiquetas deseada.
1. Haga clic en **[!UICONTROL Extensiones]** a la izquierda y, a continuación, haga clic en la ficha **[!UICONTROL Catálogo]**
1. Busque e instale la extensión **[!UICONTROL Common Web SDK Plugins]**.
1. Haga clic en **[!UICONTROL Elementos de datos]** a la izquierda y, a continuación, haga clic en el elemento de datos deseado.
1. Establezca el nombre del elemento de datos deseado con la siguiente configuración:
   * Extensión: Common Web SDK Plugins
   * Elemento de datos: `getAndPersistValue`
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
   * Tipo de acción: Inicializar getAndPersistValue
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
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getAndPersistValue v3.0 (Requires AppMeasurement) */
function getAndPersistValue(vtp,cn,ex){var d=vtp,k=cn,l=ex;if("undefined"!==typeof d&&"-v"===d)return{plugin:"getAndPersistValue",version:"3.0"};var a=function(){if("undefined"!==typeof window.s_c_il)for(var c=0,b;c<window.s_c_il.length;c++)if(b=window.s_c_il[c],b._c&&"s_c"===b._c)return b}();"undefined"!==typeof a&&(a.contextData.getAndPersistValue="3.0");window.cookieWrite=window.cookieWrite||function(c,b,f){if("string"===typeof c){var h=window.location.hostname,a=window.location.hostname.split(".").length-1;if(h&&!/^[0-9.]+$/.test(h)){a=2<a?a:2;var e=h.lastIndexOf(".");if(0<=e){for(;0<=e&&1<a;)e=h.lastIndexOf(".",e-1),a--;e=0<e?h.substring(e):h}}g=e;b="undefined"!==typeof b?""+b:"";if(f||""===b)if(""===b&&(f=-60),"number"===typeof f){var d=new Date;d.setTime(d.getTime()+6E4*f)}else d=f;return c&&(document.cookie=encodeURIComponent(c)+"="+encodeURIComponent(b)+"; path=/;"+(f?" expires="+d.toUTCString()+";":"")+(g?" domain="+g+";":""),"undefined"!==typeof cookieRead)?cookieRead(c)===b:!1}};window.cookieRead=window.cookieRead||function(c){if("string"===typeof c)c=encodeURIComponent(c);else return"";var b=" "+document.cookie,a=b.indexOf(" "+c+"="),d=0>a?a:b.indexOf(";",a);return(c=0>a?"":decodeURIComponent(b.substring(a+2+c.length,0>d?b.length:d)))?c:""};a=new Date;k=k?k:"s_gapv";(l=l?l:0)?a.setTime(a.getTime()+864E5*l):a.setTime(a.getTime()+18E5);"undefined"!==typeof d&&d||(d=cookieRead(k));cookieWrite(k,d,a);return d};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Uso del complemento

La función `getAndPersist` utiliza los argumentos siguientes:

* **`vtp`** (obligatorio): El valor que se va a mantener de página en página.
* **`cn`** (opcional): El nombre de la cookie para almacenar el valor. Si no se establece este argumento, se llamará a la cookie `"s_gapv"`.
* **`ex`** (opcional): Número de días antes de que caduque la cookie. Si este argumento está establecido en `0` o no, la cookie caduca al final de la visita (a los 30 minutos de inactividad).

Si se establece la variable en el argumento `vtp`, el complemento establece la cookie y recupera el valor de la cookie. Si no se establece la variable en el argumento `vtp`, el complemento solo recupera el valor de la cookie.

## Ejemplos

```js
// Sets eVar21 to "raccoon", and sets the ev21gapv cookie to "raccoon" (which expires in 28 days).
s.eVar21 = "raccoon";
s.eVar21 = getAndPersistValue(s.eVar21,"ev21gapv",28);

// Checks the "ev21gapv" cookie for a value and assigns it to eVar21. It does not set a cookie value or reset an existing cookie's expiration since the value is not set on the page.
// If there is a cookie, assigns eVar21 to that value. Otherwise, eVar21 is blank.
s.eVar21 = getAndPersistValue(s.eVar21,"ev21gapv",28);

// Checks the "ev21gapv" cookie for a value and assigns it to prop35. It does not set a cookie value or reset an existing cookie's expiration since eVar21 is not set on the page.
s.prop35 = getAndPersistValue(s.eVar21,"ev21gapv",28);

// Sets eVar21 to "panda", and sets the ev21gapv cookie to "panda" (which expires in 14 days). It then sets prop35 to the value contained in the ev21gapv cookie.
// Ultimately both eVar21 and prop35 contain the value "panda".
s.eVar21 = "panda";
s.prop35 = getAndPersistValue(s.eVar21,"ev21gapv",14);

// Sets eVar30 to "shopping", and sets the s_gapv cookie to "shopping" (which expires at the end of the browser session).
s.eVar30 = "shopping";
s.eVar30 = getAndPersistValue(s.eVar30);
```

## Historial de versiones

### 3.0 (19 de marzo de 2021)

* Se ha añadido el número de versión como datos de contexto.

### 2.0 (16 de abril de 2018)

* Versión puntual (tamaño de código más pequeño)
* Pasar 0 al argumento `ex` ahora fuerza la caducidad después de 30 minutos de inactividad en lugar de al final de la sesión en el explorador.

### 1.0 (18 de enero de 2016)

* Versión inicial.

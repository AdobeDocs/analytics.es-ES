---
title: getTimeSinceLastVisit
description: Mida el tiempo transcurrido entre dos visitas.
feature: Appmeasurement Implementation
exl-id: c5cef219-8a8a-4e57-a372-f2e063325a67
role: Admin, Developer
TQID: https://experienceleague.adobe.com/lqO0TMLt9-tpo9kt6P4FkRkkx0hElh7dLJEVH2TSQwE
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 624
ht-degree: 73%

---

# Complemento de Adobe: getTimeSinceLastVisit

{{plug-in}}

El complemento `getTimeSinceLastVisit` le permite rastrear cuánto tiempo ha tardado un visitante en regresar a su sitio después de su última visita.

## Instalación del complemento con la extensión Web SDK

Adobe ofrece una extensión que le permite utilizar los complementos más utilizados con Web SDK.

1. Inicie sesión en la [Recopilación de datos de Adobe Experience Platform](https://experience.adobe.com/data-collection) con sus credenciales de Adobe ID.
1. Haga clic en **[!UICONTROL Etiquetas]** a la izquierda y luego haga clic en la propiedad de etiquetas deseada.
1. Haga clic en **[!UICONTROL Extensiones]** a la izquierda y, a continuación, haga clic en la ficha **[!UICONTROL Catálogo]**
1. Busque e instale la extensión **[!UICONTROL Common Web SDK Plugins]**.
1. Haga clic en **[!UICONTROL Elementos de datos]** a la izquierda y, a continuación, haga clic en el elemento de datos deseado.
1. Establezca el nombre del elemento de datos deseado con la siguiente configuración:
   * Extensión: Common Web SDK Plugins
   * Elemento de datos: `getTimeSinceLastVisit`
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
   * Tipo de acción: Inicializar getTimeSinceLastVisit
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
/* Adobe Consulting Plugin: getTimeSinceLastVisit v2.0 */
 function getTimeSinceLastVisit(){if(arguments&&"-v"===arguments[0])return{plugin:"getTimeSinceLastVisit",version:"2.0"};var h=function(){if("undefined"!==typeof window.s_c_il)for(var c=0,b;c<window.s_c_il.length;c++)if(b=window.s_c_il[c],b._c&&"s_c"===b._c)return b}();"undefined"!==typeof h&&(h.contextData.getTimeSinceLastVisit="2.0");window.formatTime=window.formatTime||function(c,b,d){function f(b,d,c,e){if("string"!==typeof d)return!1;if("string"===typeof b)b=b.split(c||",");else if("object"!==typeof b)return!1;c=0;for(a=b.length;c<a;c++)if(1==e&&d===b[c]||d.toLowerCase()===b[c].toLowerCase())return!0;return!1}if(!("undefined"===typeof c||isNaN(c)||0>Number(c))){var e="";"string"===typeof b&&"d"===b||("string"!==typeof b||!f("h,m,s",b))&&86400<=c?(b=86400,e="days",d=isNaN(d)?1:b/(d*b)):"string"===typeof b&&"h"===b||("string"!==typeof b||!f("m,s",b))&&3600<=c?(b=3600,e="hours",d=isNaN(d)?4:b/(d*b)):"string"===typeof b&&"m"===b||("string"!==typeof b||!f("s",b))&&60<=c?(b=60,e="minutes",d=isNaN(d)?2:b/(d*b)):(b=1,e="seconds",d=isNaN(d)?.2:b/d);e=Math.round(c*d/b)/d+" "+e;0===e.indexOf("1 ")&&(e=e.substring(0,e.length-1));return e}};window.cookieWrite=window.cookieWrite||function(c,b,d){if("string"===typeof c){var f=window.location.hostname,e=window.location.hostname.split(".").length-1;if(f&&!/^[0-9.]+$/.test(f)){e=2<e?e:2;var k=f.lastIndexOf(".");if(0<=k){for(;0<=k&&1<e;)k=f.lastIndexOf(".",k-1),e--;k=0<k?f.substring(k):f}}g=k;b="undefined"!==typeof b?""+b:"";if(d||""===b)if(""===b&&(d=-60),"number"===typeof d){var h=new Date;h.setTime(h.getTime()+6E4*d)}else h=d;return c&&(document.cookie=encodeURIComponent(c)+"="+encodeURIComponent(b)+"; path=/;"+(d?" expires="+h.toUTCString()+";":"")+(g?" domain="+g+";":""),"undefined"!==typeof cookieRead)?cookieRead(c)===b:!1}};window.cookieRead=window.cookieRead||function(c){if("string"===typeof c)c=encodeURIComponent(c);else return"";var b=" "+document.cookie,d=b.indexOf(" "+c+"="),f=0>d?d:b.indexOf(";",d);return(c=0>d?"":decodeURIComponent(b.substring(d+2+c.length,0>f?b.length:f)))?c:""};h=new Date;var m=h.getTime(),n=cookieRead("s_tslv")||0,l=Math.round((m-n)/1E3);h.setTime(m+63072E6);cookieWrite("s_tslv",m,h);return n?1800<l||cookieRead("s_inv")?(cookieRead("s_inv")&&(l=cookieRead("s_inv")),cookieWrite("s_inv",l,30),"0"!==l?formatTime(l):"New Visitor"):"":(cookieWrite("s_inv","0",30),"New Visitor")};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Uso del complemento

La función `getTimeSinceLastVisit` no utiliza ningún argumento. Devuelve el tiempo transcurrido desde la última vez que el visitante accedió al sitio, agrupado en el siguiente formato:

* Un valor entre 30 minutos y una hora desde la última visita se establece en la referencia de medio minuto más cercana. Por ejemplo, `"30.5 minutes"`, `"53 minutes"`.
* Un valor entre una hora y un día se redondea a la referencia de cuarto de hora más cercana. Por ejemplo, `"2.25 hours"`, `"7.5 hours"`.
* Un valor mayor que un día se redondea a la referencia del día más próximo. Por ejemplo, `"1 day"`, `"3 days"`, `"9 days"`, `"372 days"`.
* Si es la primera visita de un visitante o si el tiempo transcurrido supera los dos años, el valor se establece en `"New Visitor"`.

>[!NOTE]
>
>Este complemento solo devuelve un valor en la primera visita.

Este complemento crea una cookie de origen denominada `"s_tslv"` establecida en una marca de tiempo Unix de la hora actual. La cookie caduca tras dos años de inactividad.

## Ejemplos

```js
// Given a visitor's first visit to the site
// Sets prop1 to "New Visitor"
s.prop1 = getTimeSinceLastVisit();

// 35 minutes later, the same visitor returns
// Sets prop1 to "35 minutes"
s.prop1 = getTimeSinceLastVisit();

// 4 days later, the same visitor returns
// Sets prop1 to "4 days"
s.prop1 = getTimeSinceLastVisit();
```

## Historial de versiones

### 2.0 (19 de marzo de 2021)

* Se ha añadido el número de versión como datos de contexto.

### 1.0 (16 de abril de 2018)

* Versión puntual (código compilado de nuevo y tamaño más pequeño).
* Código derivado del complemento `getDaysSinceLastVisit` (ahora obsoleto y con un nuevo nombre).
* Ahora utiliza los complementos `formatTime` y `inList` para el valor devuelto.

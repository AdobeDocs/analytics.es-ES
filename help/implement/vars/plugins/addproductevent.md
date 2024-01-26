---
title: addProductEvent
description: Agrega eventos personalizados a la variable products y events.
feature: Variables
exl-id: 74f4cb93-714a-4d2b-88f3-408d032f6811
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '491'
ht-degree: 86%

---

# Complemento de Adobe: addProductEvent

{{plug-in}}

El complemento `addProductEvent` agrega un evento numérico o de divisa a la variable [`products`](../page-vars/products.md). Adobe recomienda utilizar este complemento si desea agregar un evento numérico o de divisa a la variable `products` sin tener que preocuparse por el formato de la cadena de producto. Este complemento no es necesario si no se utilizan eventos numéricos o de divisa en la variable `products`.

## Instalación del complemento con el SDK web o la extensión del SDK web

Este complemento aún no es compatible con el SDK web.

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
   * Tipo de acción: Inicializar addProductEvent
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
/* Adobe Consulting Plugin: addProductEvent v2.0 */
function addProductEvent(en,ev,ap){var f=en,g=ev,c=ap;if("-v"===f)return{plugin:"addProductEvent",version:"2.0"};var d=function(){if("undefined"!==typeof window.s_c_il)for(var b=0,e;b<window.s_c_il.length;b++)if(e=window.s_c_il[b],e._c&&"s_c"===e._c)return e}();if("undefined"!==typeof d&&(d.contextData.addProductEvent="2.0",window.apl=window.apl||function(b,e,c,d,f){function g(b,d,c,e){if("string"!==typeof d)return!1;if("string"===typeof b)b=b.split(c||",");else if("object"!==typeof b)return!1;c=0;for(a=b.length;c<a;c++)if(1==e&&d===b[c]||d.toLowerCase()===b[c].toLowerCase())return!0;return!1}if(!b||"string"===typeof b){if("string"!==typeof e||""===e)return b;c=c||",";d=d||c;1==d&&(d=c,f||(f=1));2==d&&1!=f&&(d=c);e=e.split(",");k=e.length;for(var h=0;h<k;h++)g(b,e[h],c,f)||(b=b?b+d+e[h]:e[h])}return b},"string"===typeof f))if(g=isNaN(g)?"1":String(g),c=c||!1,d.events=window.apl(d.events,f),d.products){var l=d.products.split(","),m=l.length;c=c?0:m-1;for(var b;c<m;c++)b=l[c].split(";"),b[4]&&-1<b[4].indexOf("event")?b[4]=b[4]+"|"+f+"="+g:b[5]?b[4]=f+"="+g:b[4]||(b[3]||(b[3]=""),b[2]||(b[2]=""),b[1]||(b[1]=""),b[4]=f+"="+g),l[c]=b.join(";");d.products=l.join(",")}else d.products=";;;;"+f+"="+g};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Uso del complemento

La función `addProductEvent` utiliza los siguientes argumentos:

* **`en`** (obligatorio, cadena): Evento que se agregará a la última entrada de la variable `products`. Si la variable `products` está vacía, se crea una entrada de producto “en blanco” con el evento (y su valor) adjunto.
* **`ev`** (obligatorio, cadena): El valor asignado al evento numérico o de divisa del argumento `en`.  Si no se configura de forma distinta, el valor predeterminado es `1`. Los números que no aparecen entre comillas también son válidos.
* **`ap`** (opcional, booleano): Si la variable products contiene actualmente más de una entrada de producto, un valor de `true` (o `1`) agrega el evento a todas las entradas de producto.  Si no se configura de forma distinta, el valor predeterminado es `false`.

`addProductEvent` no devuelve nada. En su lugar, agrega el evento y su valor a la variable `products`. El complemento también agrega automáticamente el evento a la variable [`events`](../page-vars/events/events-overview.md), puesto que también es obligatorio en ella.

## Cookies

La función `addProductEvent` no crea ni utiliza cookies.

## Ejemplos

```js
// Sets the products variable to ";product1;3;300,;product2;2;122,;product3;1;25;event35=25".
// Also sets the events variable to "purchase,event35".
s.products = ";product1;3;300,;product2;2;122,;product3;1;25";
s.events = "purchase";
addProductEvent("event35", "25");

// Sets the products variable to ";product1;3;300;event35=25,;product2;2;122;event35=25,;product3;1;25;event35=25".
s.products = ";product1;3;300,;product2;2;122,;product3;1;25";
addProductEvent("event35", 25, true);

// Sets the products variable to ";product1;3;300;event2=10;eVar33=large|eVar34=men|eVar35=blue,;product2;2;122,;product3;1;25;event33= 12|event34=10|event35=15"
// Also sets the s.events variable to "purchase,event2,event33,event34,event35".
s.products=";product1;3;300;event2=10;eVar33=large|eVar34=men|eVar35=blue,;product2;2;122,;product3;1;25";
s.events="purchase,event2";
addProductEvent("event33", "12");
addProductEvent("event34", "10");
addProductEvent("event35", "15");

// Sets the products variable to ";product1;3;300;event2=10|event33=12|event34=10|event35=15;eVar33=large|eVar34=men|eVar35=blue,;product2;2;122;event33=12|event34=10|event35=15,;product3;1;25;event33=12|event34=10|event35=15".
// Also sets the events variable to "purchase,event2,event33,event34,event35".
s.products=";product1;3;300;event2=10;eVar33=large|eVar34=men|eVar35=blue,;product2;2;122,;product3;1;25"
s.events="purchase,event2"
addProductEvent("event33", "12", 1);
addProductEvent("event34", 10, 1);
addProductEvent("event35", "15", 1);

// If the products variable isn't already set, sets it to ";;;;event35=25".
// Also appends event35 to the events variable.
addProductEvent("event35", "25");
```

## Historial de versiones

### 2.0 (19 de marzo de 2021)

* Se ha añadido el número de versión como datos de contexto.

### 1.0 (7 de octubre de 2019)

* Versión inicial.

---
title: addProductEvent
description: Agrega eventos personalizados a la variable products y events.
exl-id: 74f4cb93-714a-4d2b-88f3-408d032f6811
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '632'
ht-degree: 100%

---

# Complemento de Adobe: addProductEvent

>[!IMPORTANT]
>
>Adobe Consulting proporciona este complemento por cortesía para ayudarle a sacar el máximo partido a Adobe Analytics. El Servicio de atención al cliente de Adobe no ofrece asistencia técnica con este complemento, incluida la instalación o solución de problemas. Si necesita ayuda con este complemento, póngase en contacto con el administrador de cuentas de su organización. Ellos podrán organizar una reunión con un consultor para ayudarle.

El complemento `addProductEvent` agrega un evento numérico o de divisa a la variable [`products`](../page-vars/products.md). Adobe recomienda utilizar este complemento si desea agregar un evento numérico o de divisa a la variable `products` sin tener que preocuparse por el formato de la cadena de producto. Este complemento no es necesario si no se utilizan eventos numéricos o de divisa en la variable `products`.

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
   * Tipo de acción: Inicializar addProductEvent
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
/* Adobe Consulting Plugin: addProductEvent v2.0 */
function addProductEvent(en,ev,ap){var f=en,g=ev,c=ap;if("-v"===f)return{plugin:"addProductEvent",version:"2.0"};var d=function(){if("undefined"!==typeof window.s_c_il)for(var b=0,e;b<window.s_c_il.length;b++)if(e=window.s_c_il[b],e._c&&"s_c"===e._c)return e}();if("undefined"!==typeof d&&(d.contextData.addProductEvent="2.0",window.apl=window.apl||function(b,e,c,d,f){function g(b,d,c,e){if("string"!==typeof d)return!1;if("string"===typeof b)b=b.split(c||",");else if("object"!==typeof b)return!1;c=0;for(a=b.length;c<a;c++)if(1==e&&d===b[c]||d.toLowerCase()===b[c].toLowerCase())return!0;return!1}if(!b||"string"===typeof b){if("string"!==typeof e||""===e)return b;c=c||",";d=d||c;1==d&&(d=c,f||(f=1));2==d&&1!=f&&(d=c);e=e.split(",");k=e.length;for(var h=0;h<k;h++)g(b,e[h],c,f)||(b=b?b+d+e[h]:e[h])}return b},"string"===typeof f))if(g=isNaN(g)?"1":String(g),c=c||!1,d.events=window.apl(d.events,f),d.products){var l=d.products.split(","),m=l.length;c=c?0:m-1;for(var b;c<m;c++)b=l[c].split(";"),b[4]&&-1<b[4].indexOf("event")?b[4]=b[4]+"|"+f+"="+g:b[5]?b[4]=f+"="+g:b[4]||(b[3]||(b[3]=""),b[2]||(b[2]=""),b[1]||(b[1]=""),b[4]=f+"="+g),l[c]=b.join(";");d.products=l.join(",")}else d.products=";;;;"+f+"="+g};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Uso del complemento

El método `addProductEvent` utiliza los siguientes argumentos:

* **`en`** (obligatorio, cadena): Evento que se agregará a la última entrada de la variable `products`. Si la variable `products` está vacía, se crea una entrada de producto “en blanco” con el evento (y su valor) adjunto.
* **`ev`** (obligatorio, cadena): El valor asignado al evento numérico o de divisa del argumento `en`.  Si no se configura de forma distinta, el valor predeterminado es `1`.
* **`ap`** (opcional, booleano): Si la variable products contiene actualmente más de una entrada de producto, un valor de `true` (o `1`) agrega el evento a todas las entradas de producto.  Si no se configura de forma distinta, el valor predeterminado es `false`.

`addProductEvent` no devuelve nada. En su lugar, agrega el evento y su valor a la variable `products`. El complemento también agrega automáticamente el evento a la variable [`events`](../page-vars/events/events-overview.md), puesto que también es obligatorio en ella.

## Cookies

El complemento addProductEvent no crea ni utiliza cookies.

## Llamadas de ejemplo

### Ejemplo 1

El siguiente código establece la variable `s.products` en `";product1;3;300,;product2;2;122,;product3;1;25;event35=25"`.

```js
s.products=";product1;3;300,;product2;2;122,;product3;1;25"
s.events="purchase";
s.addProductEvent("event35", "25");
```

El código anterior también establece la variable `s.events` en `"purchase,event35"`

### Ejemplo 2

El siguiente código establece la variable `s.products` en `";product1;3;300;event35=25,;product2;2;122;event35=25,;product3;1;25;event35=25"`

```js
s.products=";product1;3;300,;product2;2;122,;product3;1;25";
s.addProductEvent("event35", 25, 1);
```

Cuando el tercer argumento de la llamada `addProductEvent` es `true` (o `1`), cada entrada de producto tiene el evento especificado en la llamada agregada a su valor.

### Ejemplo 3

El siguiente código establece la variable `s.products` en `";product1;3;300;event2=10;eVar33=large|eVar34=men|eVar35=blue,;product2;2;122,;product3;1;25;event33= 12|event34=10|event35=15"`

```js
s.products=";product1;3;300;event2=10;eVar33=large|eVar34=men|eVar35=blue,;product2;2;122,;product3;1;25";
s.events="purchase,event2";
s.addProductEvent("event33", "12");
s.addProductEvent("event34", "10");
s.addProductEvent("event35", "15");
```

El código anterior también establece la variable `s.events` en `"purchase,event2,event33,event34,event35"`

### Ejemplo 4

El siguiente código establece la variable `s.products` en `";product1;3;300;event2=10|event33=12|event34=10|event35=15;eVar33=large|eVar34=men|eVar35=blue, ;product2;2;122;event33=12|event34=10|event35=15,;product3;1;25;event33=12|event34=10|event35=15"`

```js
s.products=";product1;3;300;event2=10;eVar33=large|eVar34=men|eVar35=blue,;product2;2;122,;product3;1;25"
s.events="purchase,event2"
s.addProductEvent("event33", "12", 1);
s.addProductEvent("event34", 10, 1);
s.addProductEvent("event35", "15", 1);
```

El código anterior también establece la variable `s.events` en `"purchase,event2,event33,event34,event35"`

>[!NOTE]
>
>El segundo argumento de la llamada puede ser un entero **o** una cadena que represente un número/número entero

### Ejemplo 5

Si `s.products` aún no se ha establecido, el siguiente código lo establece en `";;;;event35=25"`

```js
s.addProductEvent("event35", "25");
```

El código anterior también anexa `"event35"` al final de `s.events` o **; si** `s.events` no se ha establecido, el código anterior configura `s.events` en `"event35"`

## Historial de versiones

### 2.0 (19 de marzo de 2021)

* Se ha añadido el número de versión como datos de contexto.

### 1.0 (7 de octubre de 2019)

* Versión inicial.

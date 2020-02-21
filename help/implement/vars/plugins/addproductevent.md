---
title: addProductEvent
description: Agrega eventos personalizados a la variable products y events.
translation-type: tm+mt
source-git-commit: 7a455fb9eb355617bab016218b171dffa8d21958

---


# Complemento de Adobe:addProductEvent

> [!IMPORTANT] Este complemento lo proporciona Adobe Consulting por cortesía para ayudarle a obtener más valor de Adobe Analytics. El Servicio de atención al cliente de Adobe no ofrece asistencia técnica con este complemento, incluida la instalación o solución de problemas. Si necesita ayuda con este complemento, póngase en contacto con el administrador de cuentas de su organización. Pueden organizar una reunión con un consultor para obtener ayuda.

El `addProductEvent` complemento agrega un evento numérico o de moneda a la `products` variable. Adobe recomienda utilizar este complemento si desea agregar un evento numérico o monetario a la `products` variable sin preocuparse por el formato de la cadena de producto. Este complemento no es necesario si no se utilizan eventos numéricos o monetarios en la `products` variable.

## Instalación del complemento con la extensión Adobe Experience Platform Launch

Adobe ofrece una extensión que le permite utilizar los complementos más utilizados.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
1. Haga clic en la propiedad que desee.
1. Vaya a la ficha [!UICONTROL Extensions] y haga clic en el [!UICONTROL Catalog]
1. Instalación y publicación de la [!UICONTROL Common Analytics Plugins] extensión
1. Si aún no lo ha hecho, cree una regla con la etiqueta &quot;Inicializar complementos&quot; con la siguiente configuración:
   * Condición: Ninguno
   * Evento: Core - Biblioteca cargada (Principio de página)
1. Agregue una acción a la regla anterior con la siguiente configuración:
   * Extensión: Complementos comunes de Analytics
   * Tipo de acción: Inicializar addProductEvent
1. Guarde y publique los cambios en la regla.

## Instalación del complemento con el editor de código personalizado Iniciar

Si no desea utilizar la extensión del complemento, puede utilizar el editor de código personalizado.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
1. Haga clic en la propiedad deseada.
1. Vaya a la [!UICONTROL Extensions] ficha y, a continuación, haga clic en el [!UICONTROL Configure] botón situado debajo de la extensión de Adobe Analytics.
1. Expanda el [!UICONTROL Configure tracking using custom code] acordeón, que muestra el [!UICONTROL Open Editor] botón.
1. Abra el editor de código personalizado y pegue el código del complemento que se proporciona a continuación en la ventana de edición.
1. Guarde y publique los cambios en la extensión de Analytics.

## Instalación del complemento mediante AppMeasurement

Copie y pegue el siguiente código en cualquier parte del archivo AppMeasurement después de crear una instancia del objeto de seguimiento de Analytics (mediante `s_gi`). La conservación de los comentarios y los números de versión del código en la implementación ayuda a Adobe a solucionar cualquier problema potencial.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: addProductEvent v1.0 (Requires apl v3.1 and inList v2.0+ plug-ins) */
s.addProductEvent=function(en,ev,ap){var s=this;if("string"===typeof en)if(ev=isNaN(ev)?"1":String(ev),ap=ap||!1,s.events= s.apl(s.events,en),s.products){var e=s.products.split(",");ap=ap?0:e.length-1;for(var a;ap<e.length;ap++)a=e[ap].split(";") ,a[4]&&a[4].includes("event")?a[4]=a[4]+"|"+en+"="+ev:a[5]?a[4]=en+"="+ev:a[4]||(a[3]||(a[3]=""),a[2]||(a[2]=""),a[1]||(a[1]=""),a[4]=en+"="+ev),e[ap]=a.join(";");s.products=e.join(",")}else s.products=";;;;"+en+"="+ev};

/* Adobe Consulting Plugin: apl (appendToList) v3.2 (Requires inList v2.0 or higher) */
s.apl=function(lv,vta,d1,d2,cc){if(!lv||"string"===typeof lv){if("undefined"===typeof this.inList||"string"!==typeof vta||""===vta)return lv;d1=d1||",";d2=d2||d1;1==d2&&(d2=d1,cc||(cc=1));2==d2&&1!=cc&&(d2=d1);vta=vta.split(",");for(var g=vta.length,e=0;e<g;e++)this.inList(lv,vta[e],d1,cc)||(lv=lv?lv+d2+vta[e]:vta[e])}return lv};

/* Adobe Consulting Plugin: inList v2.1 */
s.inList=function(lv,vtc,d,cc){if("string"!==typeof vtc)return!1;if("string"===typeof lv)lv=lv.split(d||",");else if("object"!== typeof lv)return!1;d=0;for(var e=lv.length;d<e;d++)if(1==cc&&vtc===lv[d]||vtc.toLowerCase()===lv[d].toLowerCase())return!0;return!1};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Utilizar el complemento

El `addProductEvent` método utiliza los siguientes argumentos:

* **`en`** (requerido, cadena): Evento que se agregará a la última entrada de la `products` variable. Si la `products` variable está vacía, se crea una entrada de producto &quot;en blanco&quot; con el evento (y su valor) adjunto.
* **`ev`** (requerido, cadena): El valor asignado al evento numérico o de moneda en el `en` argumento.  El valor predeterminado es `1` cuando no se establece.
* **`ap`** (opcional, booleano): Si la variable products contiene actualmente más de una entrada de producto, un valor de `true` (o `1`) agrega el evento a todas las entradas de producto.  El valor predeterminado es `false` cuando no se establece.

El `addProductEvent` no devuelve nada. En su lugar, agrega el evento y su valor a la `products` variable. El complemento también agrega automáticamente el evento a la `events` variable, ya que también se requiere allí.

## Cookies

El complemento addProductEvent no crea ni utiliza cookies

## Llamadas de ejemplo

### Ejemplo n.º 1

El siguiente código establece la `s.products` variable en `";product1;3;300,;product2;2;122,;product3;1;25;event35=25"`.

```js
s.products=";product1;3;300,;product2;2;122,;product3;1;25"
s.events="purchase";
s.addProductEvent("event35", "25");
```

El código anterior también establece la `s.events` variable en `"purchase,event35"`

### Ejemplo n.º 2

El siguiente código establece la `s.products` variable en `";product1;3;300;event35=25,;product2;2;122;event35=25,;product3;1;25;event35=25"`

```js
s.products=";product1;3;300,;product2;2;122,;product3;1;25";
s.addProductEvent("event35", 25, 1);
```

Cuando el tercer argumento de la `addProductEvent` llamada es `true` (o `1`), cada entrada de producto tiene el evento especificado en la llamada agregado a su valor.

### Ejemplo n.º 3

El siguiente código establece la `s.products` variable en `";product1;3;300;event2=10;eVar33=large|eVar34=men|eVar35=blue,;product2;2;122,;product3;1;25;event33= 12|event34=10|event35=15"`

```js
s.products=";product1;3;300;event2=10;eVar33=large|eVar34=men|eVar35=blue,;product2;2;122,;product3;1;25";
s.events="purchase,event2";
s.addProductEvent("event33", "12");
s.addProductEvent("event34", "10");
s.addProductEvent("event35", "15");
```

El código anterior también establece la `s.events` variable en `"purchase,event2,event33,event34,event35"`

### Ejemplo n.º 4

El siguiente código establece la `s.products` variable en `";product1;3;300;event2=10|event33=12|event34=10|event35=15;eVar33=large|eVar34=men|eVar35=blue, ;product2;2;122;event33=12|event34=10|event35=15,;product3;1;25;event33=12|event34=10|event35=15"`

```js
s.products=";product1;3;300;event2=10;eVar33=large|eVar34=men|eVar35=blue,;product2;2;122,;product3;1;25"
s.events="purchase,event2"
s.addProductEvent("event33", "12", 1);
s.addProductEvent("event34", 10, 1);
s.addProductEvent("event35", "15", 1);
```

El código anterior también establece la `s.events` variable en `"purchase,event2,event33,event34,event35"`.

> [!NOTE] El segundo argumento de la llamada puede ser un entero **o** una cadena que represente un número/número entero

### Ejemplo n.º 5

Si `s.products` aún no se ha establecido, el siguiente código lo establece en `";;;;event35=25"`

```js
s.addProductEvent("event35", "25");
```

El código anterior también se anexa `"event35"` al final de `s.events` o **, si** no se ha establecido, el código anterior se establece `s.events` `s.events` en `"event35"`

## Historial de versiones

### 1.0 (7 de octubre de 2019)

* Versión inicial.

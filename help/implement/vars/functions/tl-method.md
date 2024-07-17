---
title: tl
description: Envíe una llamada de seguimiento de vínculos a Adobe.
feature: Variables
exl-id: 470662b2-ce07-4432-b2d5-a670fbb77771
role: Admin, Developer
source-git-commit: 72b38970e573b928e4dc4a8c8efdbfb753be0f4e
workflow-type: tm+mt
source-wordcount: '865'
ht-degree: 62%

---

# tl

El método `tl()` es un componente principal importante de Adobe Analytics. Toma todas las variables de Analytics definidas en la página, las compila en una solicitud de imagen y envía esos datos a los servidores de recopilación de datos de Adobe. Funciona de manera similar al método [`t()`](t-method.md), pero este no incrementa las vistas de página. Es útil para rastrear vínculos y otros elementos que no se considerarían una carga de página completa.

Si [`trackDownloadLinks`](../config-vars/trackdownloadlinks.md) o [`trackExternalLinks`](../config-vars/trackexternallinks.md) están activados, AppMeasurement llama automáticamente al método `tl()` para enviar datos de seguimiento de vínculos de descarga y de salida. Si su organización prefiere tener más control sobre los vínculos que quiere rastrear y su comportamiento, puede llamar al método `tl()` manualmente. Los vínculos personalizados solo se pueden rastrear manualmente.

## Seguimiento de vínculos mediante el SDK web

El SDK web no diferencia entre las llamadas de vista de página y las llamadas de seguimiento de vínculos; ambas utilizan el comando `sendEvent`.

Si utiliza un objeto XDM y desea que Adobe Analytics cuente un evento determinado como una llamada de seguimiento de vínculos, asegúrese de que los datos XDM incluyan:

* Nombre del vínculo: asignado a `xdm.web.webInteraction.name`.
* URL de vínculo: asignado a `xdm.web.webInteraction.URL`.
* Tipo de vínculo: asignado a `xdm.web.webInteraction.type`. Los valores válidos incluyen `other` (vínculos personalizados), `download` (vínculos de descarga) y `exit` (vínculos de salida).

```js
alloy("sendEvent", {
  "xdm": {
    "web": {
      "webInteraction": {
        "name": "My Custom Link",
        "URL": "https://example.com",
        "type": "other"
      }
    }
  }
});
```

Si utiliza un objeto de datos y desea que Adobe Analytics cuente un evento determinado como una llamada de seguimiento de vínculos, asegúrese de que el objeto de datos incluya:

* Nombre del vínculo: asignado a `data.__adobe.analytics.linkName`.
* URL de vínculo: asignado a `data.__adobe.analytics.linkURL`.
* Tipo de vínculo: asignado a `data.__adobe.analytics.linkType`. Los valores válidos incluyen `o` (vínculos personalizados), `d` (vínculos de descarga) y `e` (vínculos de salida).

```js
alloy("sendEvent", {
  "data": {
    "__adobe": {
      "analytics": {
        "linkName": "My custom link",
        "linkURL": "https://example.com",
        "linkType": "o"
      }
    }
  }
});
```

## Seguimiento de vínculos con la extensión Adobe Analytics

La extensión de Adobe Analytics tiene una ubicación específica para establecer una llamada de seguimiento de vínculos.

1. Inicie sesión en la [Recopilación de datos de Adobe Experience Platform](https://experience.adobe.com/data-collection) con sus credenciales de Adobe ID.
1. Haga clic en la propiedad de etiquetas deseada.
1. Vaya a la pestaña [!UICONTROL Reglas] y, a continuación, haga clic en la regla que desee (o cree una regla).
1. En [!UICONTROL Acciones], haga clic en la acción que desee o en el icono **&#39;+&#39;** para agregar una acción.
1. Establezca la lista desplegable [!UICONTROL Extension] en **[!UICONTROL Adobe Analytics]** y [!UICONTROL Action Type] en **[!UICONTROL Send Beacon]**.
1. Haga clic en el botón de opción `s.tl()`.

No puede establecer ningún argumento opcional en la extensión de Analytics.

## El método s.tl() en AppMeasurement y el editor de código personalizado de la extensión de Analytics

Llame al método `s.tl()` cuando desee enviar una llamada de seguimiento a Adobe.

```js
s.tl([Link object],[Link type],[Link name],[Override variable]);
```

### Objeto de vinculación (obligatorio)

El argumento del objeto de vinculación determina si el explorador espera hasta 500 ms antes de salir de la página. Si una solicitud de imagen se envía antes de 500 ms, la página se desplaza inmediatamente al vínculo donde se hizo clic.

>[!NOTE]
>
>AppMeasurement habilita automáticamente la variable [`useBeacon`](../config-vars/usebeacon.md) para los vínculos de salida, por lo que este argumento ya no se necesita en los exploradores modernos. Este argumento se usaba con mayor frecuencia en versiones anteriores de AppMeasurement.

* `this`: Esperar hasta 500 ms para que AppMeasurement tenga tiempo de enviar una solicitud de imagen. Valor predeterminado.
* `true`: No esperar.

```JavaScript
// Include a 500ms delay with an exit link
s.tl(this,"e","Example exit link");

// Do not include a 500ms delay with an exit link
s.tl(true,"e","Example exit link");
```

### Tipo de vínculo (obligatorio)

El argumento del tipo de vínculo es una cadena de un solo carácter que determina el tipo de llamada de seguimiento de vínculos. Existen tres valores válidos.

* `o`: el vínculo es un [vínculo personalizado](/help/components/dimensions/custom-link.md).
* `d`: el vínculo es un [vínculo de descarga](/help/components/dimensions/download-link.md).
* `e`: el vínculo es un [vínculo de salida](/help/components/dimensions/exit-link.md).

```js
// Send a custom link
s.tl(true,"o","Example custom link");

// Send a download link
s.tl(true,"d","Example download link");

// Send an exit link
s.tl(true,"e","Example exit link");
```

### Nombre del vínculo (recomendado)

El argumento del nombre de la vinculación es una cadena que determina el elemento de la dimensión de seguimiento del vínculo. Al utilizar las dimensiones [Vínculo personalizado](/help/components/dimensions/custom-link.md), [Vínculo de descarga](/help/components/dimensions/download-link.md) o [Vínculo de salida](/help/components/dimensions/exit-link.md) en la creación de informes, esta cadena contiene el elemento de dimensión. Si no se establece este argumento, se utiliza la variable [linkURL](../config-vars/linkurl.md).

```js
// When using the Download link dimension, this method call increases the occurrences metric for "Sea turtle PDF report" by 1.
s.tl(true,"d","Sea turtle PDF report");
```

### Anulaciones de variables (opcional)

Permite cambiar los valores de las variables para una sola llamada. Consulte las [anulaciones de variables](../../js/overrides.md) para obtener más información.

```js
var y = new Object();
y.eVar1 = "Override value";
y.linkTrackVars = "eVar1";
s.tl(true,"o","Example custom link",y);
```

## Ejemplos y casos de uso

Envíe una llamada de seguimiento de vínculos básica directamente dentro de un vínculo HTML:

```HTML
<a href="example.html" onClick="s.tl(true,'o','Example link');">Click here</a>
```

Utilice JavaScript para hacer una llamada de seguimiento de vínculos básica con argumentos de método:

```JavaScript
s.tl(true,"o","Example link");
```

### Realizar llamadas de seguimiento de vínculos dentro de una función personalizada

Puede consolidar el código de seguimiento de vínculos en una función JavaScript independiente. Las llamadas se pueden realizar en la función `onClick` de cada vínculo. Establezca lo siguiente en un archivo JavaScript:

```JavaScript
function trackClickInteraction(name){
  s.linkTrackVars = "eVar1,eVar2";
  s.eVar1 = name;
  s.eVar2 = s.pageName;
  s.tl(true,"o",name);
}
```

A continuación, puede llamar a la función siempre que desee rastrear una vinculación determinada:

```HTML
<!-- Use wherever you want to track links -->
<a href="example.html" onClick="trackClickInteraction('Example link');">Click here</a>
```

>[!NOTE]
>Llamar indirectamente al método `tl()` puede hacer que los informes de superposición de Activity Map sean menos prácticos. Debe hacer clic en cada vínculo para registrar la función con el elemento de vínculo. Sin embargo, las dimensiones de Activity Map en Workspace se rastrean del mismo modo.

### Evitar el seguimiento de vínculos duplicados

Si `trackDownloadLinks` o `trackExternalLinks` están activados, AppMeasurement realiza automáticamente una llamada de seguimiento de vínculos si coinciden los filtros correctos. Si también llama manualmente a `s.tl()` para estos clics en vínculos, puede enviar datos duplicados a Adobe. La duplicación de datos infla los números del informe y los hace menos precisos.

Por ejemplo: la siguiente función enviaría dos llamadas de seguimiento de vínculos para el mismo clic en vínculo (vínculos de descarga manuales y automáticos):

```JavaScript
function trackDownload(obj) {
  s.tl(obj,"d","Example PDF download");
}
```

Puede ayudar a evitar llamadas de seguimiento de vínculos duplicados mediante la siguiente función modificada. Primero comprueba si existe un objeto de vinculación y solo envía una llamada de seguimiento manual si el objeto de vinculación es una cadena vacía.

```JavaScript
function linkCode(obj) {
  var lt = obj.href != null ? s.lt(obj.href) : "";
  if (lt=="") {
    s.tl(obj,"d","Example PDF download");
  }
}
```

### Utilizar el método `tl()` con el Activity Map

Puede usar el método `tl()` para hacer un seguimiento de elementos personalizados y configurar la representación de las superposiciones en el contenido dinámico. El parámetro `linkName` también se usa para establecer la dimensión [Vínculo de Activity Map](/help/components/dimensions/activity-map-link.md).

Cuando se llama directamente al método `tl()` desde el evento en el que se hace clic del elemento HTML, el Activity Map puede mostrar una superposición para ese elemento al cargar la página web. Por ejemplo:

```html
<a href="index.html" onclick="s.tl(this,'o','Example custom link');">Example link text</a>
```

Cuando no se llama directamente al método `tl()` desde el evento en el que se hace clic del elemento HTML, el Activity Map solo puede mostrar una superposición cuando se ha hecho clic en el elemento. Por ejemplo:

```html
<a href="index.html" onclick="someFn(event);">Example link text</a>
<script>
  function someFn (event) {
    s.tl(event.srcElement,'o','Example custom link');
  }
</script>
```

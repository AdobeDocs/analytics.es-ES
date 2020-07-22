---
title: tl
description: Envíe una llamada de seguimiento de vínculos a Adobe.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '584'
ht-degree: 97%

---


# tl

El método `tl()` es un componente principal importante de Adobe Analytics. Toma todas las variables de Analytics definidas en la página, las compila en una solicitud de imagen y envía esos datos a los servidores de recopilación de datos de Adobe. Funciona de manera similar al método [`t()`](t-method.md), pero este no incrementa las vistas de página. Es útil para rastrear vínculos y otros elementos que no se considerarían una carga de página completa.

Si [`trackDownloadLinks`](../config-vars/trackdownloadlinks.md) o [`trackExternalLinks`](../config-vars/trackexternallinks.md) están activados, AppMeasurement llama automáticamente al método `tl()` para enviar datos de seguimiento de vínculos de descarga y de salida. Si su organización prefiere tener más control sobre los vínculos que quiere rastrear y su comportamiento, puede llamar al método `tl()` manualmente. Los vínculos personalizados solo se pueden rastrear manualmente.

## Llamada de seguimiento de vínculos en Adobe Experience Platform Launch

Launch tiene una ubicación dedicada configurada como llamada de seguimiento de vínculos.

1. Inicie sesión en [launch.adobe.com](https://launch.adobe.com) con sus credenciales de Adobe ID.
1. Haga clic en la propiedad deseada.
1. Vaya a la pestaña [!UICONTROL Reglas] y, a continuación, haga clic en la regla que desee (o cree una regla).
1. En [!UICONTROL Acciones], haga clic en el icono “+”.
1. Establezca la lista desplegable [!UICONTROL Extensión] en Adobe Analytics y el [!UICONTROL tipo de acción] en Enviar señalización.
1. Haga clic en el botón de opción `s.tl()`.

No puede establecer ningún argumento opcional en Launch.

## El método s.tl() en el editor de código personalizado de AppMeasurement y Launch

Llame al método `s.tl()` cuando desee enviar una llamada de seguimiento a Adobe.

```js
s.tl();
```

Opcionalmente, este método acepta varios argumentos:

```js
s.tl([Link object],[Link type],[Link name],[Override variable]);
```

### Objeto de vinculación

El argumento del objeto de vinculación determina si el explorador espera hasta 500 ms antes de salir de la página. Si una solicitud de imagen se envía antes de 500 ms, la página se desplaza inmediatamente al vínculo donde se hizo clic.

>[!NOTE]
>
>AppMeasurement habilita automáticamente la variable [`useBeacon`](../config-vars/usebeacon.md) para los vínculos de salida, por lo que este argumento ya no se necesita en los exploradores modernos. Este argumento se usaba con mayor frecuencia en versiones anteriores de AppMeasurement.

* `this`: Esperar hasta 500 ms para que AppMeasurement tenga tiempo de enviar una solicitud de imagen. Valor predeterminado.
* `true`: No esperar.

```JavaScript
// Include a 500ms delay
s.tl(this);

// Do not include a 500ms delay
s.tl(true);
```

### Tipo de vínculo

El argumento del tipo de vinculación es una cadena de una sola letra que determina el tipo de llamada de seguimiento de vínculos. Es lo mismo que configurar la variable [`linkType`](../config-vars/linktype.md).

```js
// Send a custom link
s.tl(true,"o");

// Send a download link
s.tl(true,"d");

// Send an exit link
s.tl(true,"e");
```

### Nombre de la vinculación

El argumento del nombre del vínculo es una cadena que determina el elemento de dimensión de seguimiento del vínculo. Es lo mismo que configurar la variable [`linkName`](../config-vars/linkname.md).

```js
s.tl(true,"d","Example download link");
```

### Anulaciones de variables

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

Utilice JavaScript para hacer la misma llamada básica de seguimiento de vínculos con variables independientes:

```js
s.linkType = "o";
s.linkName = "Example link";
s.tl();
```

### Realizar llamadas de seguimiento de vínculos dentro de una función personalizada

Puede consolidar el código de seguimiento de vínculos en una función JavaScript independiente definida en la página o en un archivo JavaScript vinculado. Las llamadas se pueden realizar en la función onClick de cada vínculo. Establezca lo siguiente en un archivo JavaScript:

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

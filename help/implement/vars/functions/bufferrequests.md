---
title: bufferRequests
description: Aumente la fiabilidad de la captura de solicitudes de seguimiento de vínculos para los exploradores que descargan inmediatamente la página.
feature: Variables
exl-id: f103deb4-f449-4325-b1a0-23e58a3c9ba0
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '443'
ht-degree: 5%

---

# bufferRequests

El `bufferRequests()` El método permite almacenar en caché las solicitudes de imagen en la página actual en lugar de enviarlas a la Adobe. La activación de este método es útil en situaciones en las que un explorador no es compatible [`navigator.sendBeacon()`](https://developer.mozilla.org/es-ES/docs/Web/API/Navigator/sendBeacon) o cancela las solicitudes de imagen cuando se descarga una página. Muchas versiones de los exploradores WebKit, como Safari, suelen mostrar el comportamiento de detener una solicitud de imagen al hacer clic en un vínculo. El `bufferRequests()` El método está disponible en todas las versiones de AppMeasurement v2.25.0 o posterior.

Cuando llama a [`t()`](t-method.md) o [`tl()`](tl-method.md) en una página posterior de la misma sesión del explorador y `bufferRequests()` aún no se ha llamado a en esa página, todas las solicitudes almacenadas en búfer se envían además de la solicitud de imagen de esa página. Las solicitudes almacenadas en búfer se envían en el orden correcto, donde se envía en último lugar la solicitud de imagen de la página actual.

>[!TIP]
>
>La marca de tiempo de las solicitudes almacenadas en el búfer se comparte con la página a la que se envían los datos. Si desea obtener más precisión en el segundo exacto en el que se registra una solicitud almacenada en búfer, puede establecer la variable [`timestamp`](../page-vars/timestamp.md) antes de almacenar en búfer la solicitud. Si utiliza esta variable, asegúrese de que [Marcas de hora opcionales](/help/technotes/timestamps-optional.md) está habilitado: si no lo está, todas las visitas con marca de tiempo se pierden de forma permanente.

## Limitaciones

Al llamar a `bufferRequests()` , tenga en cuenta las siguientes limitaciones. Dado que este método utiliza [`Window.sessionStorage`](https://developer.mozilla.org/en-US/docs/Web/API/Web_Storage_API)Sin embargo, se aplican muchas de las mismas limitaciones:

* El vínculo de destino debe residir en el mismo dominio y subdominio. Las solicitudes almacenadas en búfer no funcionan entre dominios o subdominios, aunque ambos tengan la misma implementación de Adobe Analytics. Esta limitación también significa que no puede utilizar solicitudes almacenadas en búfer para rastrear vínculos de salida.
* El vínculo de destino debe utilizar el mismo protocolo que la página actual. No puede enviar solicitudes en búfer entre HTTP y HTTPS.
* Las solicitudes almacenadas en búfer se almacenan hasta que llama a `t()` o `tl()` sin llamar `bufferRequests()` primero, o hasta que se cierre el explorador o la pestaña. Si finaliza una sesión del explorador antes de poder enviar esos datos al Adobe, las solicitudes en búfer no enviadas se pierden de forma permanente.
* Si un explorador no admite [API de almacenamiento web](https://developer.mozilla.org/en-US/docs/Web/API/Web_Storage_API) o el [API DE JSON](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/JSON), se envía una advertencia a la consola del explorador y el AppMeasurement intenta enviar inmediatamente la solicitud de imagen utilizando `t()` método.

## Solicitudes almacenadas en búfer en el SDK web

Actualmente, el SDK web no ofrece la capacidad de almacenar solicitudes en búfer.

## Solicitudes almacenadas en búfer con la extensión Adobe Analytics

No hay ningún campo dedicado en la extensión de Adobe Analytics para utilizar esta variable. Utilice el editor de código personalizado siguiendo la sintaxis de AppMeasurement.

## s.bufferRequests() en el AppMeasurement y el editor de código personalizado de la extensión de Analytics

Llame a `bufferRequests()` método antes de llamar a `t()` o `tl()`. Cuándo `bufferRequests()` se llama a, las llamadas de seguimiento subsiguientes se escriben en el almacenamiento de sesión en lugar de enviarse a los servidores de recopilación de datos de Adobe.

```js
// Instantiate the tracking object
var s = s_gi("examplersid");

// Flag the request to be buffered
s.bufferRequests();

// The t() or tl() method then writes the data to session storage instead of sending it to Adobe
s.tl(true,"o","Example link click");

// On a subsequent page, the tracking call sends both the above link tracking call and the page view call
s.t();
```

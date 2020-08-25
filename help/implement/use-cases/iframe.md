---
title: Uso de AppMeasurement con iframes
description: Acceda a las variables de Adobe Analytics dentro de un iframe o una página principal mientras se encuentra en un iframe.
translation-type: tm+mt
source-git-commit: 355985a6baa1a1112e75446012be72f5c0a1d0c2
workflow-type: tm+mt
source-wordcount: '327'
ht-degree: 6%

---


# Uso de AppMeasurement con iframes

Puede hacer referencia a las variables de AppMeasurement desde los iframes secundario y principal. Es necesario definir todas las variables en la misma ubicación donde existe la biblioteca AppMeasurement. Los siguientes ejemplos explican cómo configurar los métodos y las variables de AppMeasurement básicas dentro y fuera de un iframe.

Si utiliza Adobe Experience Platform Launch, asegúrese de que el objeto tracker sea accesible globalmente. Consulte Información general [sobre la extensión de](https://docs.adobe.com/content/help/es-ES/launch/using/extensions-ref/adobe-extension/analytics-extension/overview.html) Adobe Analytics en la guía del usuario Launch.

>!![CAUTION]
Evite incluir bibliotecas de AppMeasurement tanto en una página principal como en un iframe. Al hacerlo, se presentan riesgos de enviar varias solicitudes de imagen, inflar informes y aumentar las llamadas al servidor facturables.

## Acceso a AppMeasurement que reside en un iframe

Puede acceder a las variables de AppMeasurement a través del objeto iframe. En estos ejemplos se establece [pageName](../vars/page-vars/pagename.md) y se llama al método [](../vars/functions/t-method.md) t() de dos formas diferentes de hacer referencia al objeto iframe.

```js
// Reference AppMeasurement code that resides within an iframe and send an image request
document.getElementById('targetFrame').contentWindow.s.pageName="Page name within iframe";
document.getElementById('targetFrame').contentWindow.s.t();

// An alternate method to the above if there's only one iframe on the page
window.frames[0].contentWindow.s.pageName = "Page name within iframe";
window.frames[0].contentWindow.s.t();
```

## Acceso a AppMeasurement desde dentro de un iframe

Puede acceder a las variables de AppMeasurement en una página principal desde dentro de un iframe. En este ejemplo se establece [pageName](../vars/page-vars/pagename.md) y se llama al método [](../vars/functions/t-method.md) t() mediante la [`parent`](https://www.w3schools.com/jsref/prop_win_parent.asp) propiedad .

```js
// Reference AppMeasurement code on a parent page from within an iframe and send an image request
parent.s.pageName = "Page Name on Hosted Window";
parent.s.t();
```

## Uso `postMessage` y evento de oyentes

De forma alternativa, puede utilizar los oyentes `postMessage` y eventos para establecer variables. Este método no requiere una referencia directa a un iframe.

```js
// Place this code in your parent window
function listenMessage(e) {
    if(e.data == "Example page view call") {
        s.pageName = "Page name using postMessage";
        s.t();
    }
}
window.addEventListener("message", listenMessage, false);

// Place this code in the iframe
window.top.postMessage("Example page view call","https://example.com");
```

## Limitaciones

* Al igual que con otros códigos JavaScript, los iframes sólo pueden comunicarse cuando coinciden dominios y protocolos. Estos ejemplos no funcionan si el contenido de iframe reside en un dominio diferente al dominio principal.
* Si AppMeasurement reside en un iframe, la [`referrer`](../vars/page-vars/referrer.md) variable se establece en la dirección URL principal, no en la dirección URL de referencia real. Puede configurar manualmente la `referrer` variable para resolver este problema.
* El depurador [de](https://docs.adobe.com/content/help/es-ES/debugger/using/experience-cloud-debugger.html) Adobe Experience Cloud no reconoce las solicitudes de imagen activadas dentro de iframes.
* Activity Map no muestra el mapa de calor sobre los vínculos en los que se hace clic dentro de los iframes. El iframe completo se resalta en su lugar.

---
title: Uso de AppMeasurement con iFrames
description: Acceda a variables de Adobe Analytics dentro de un iframe o de una página principal mientras se encuentra en un iframe.
exl-id: 59b9cd4f-8599-41ee-8b54-a6a556198ecd
source-git-commit: 40bf2bbb522a94a678d0da1a645d83a5121c93d0
workflow-type: tm+mt
source-wordcount: '327'
ht-degree: 100%

---

# Uso de AppMeasurement con iFrames

Puede hacer referencia a variables de AppMeasurement desde iFrames secundarios y principales. Es necesario definir todas las variables en la misma ubicación donde existe la biblioteca AppMeasurement. En los siguientes ejemplos se explica cómo configurar variables y métodos básicos de AppMeasurement dentro y fuera de un iframe.

Si utiliza Adobe Experience Platform Launch, asegúrese de que el objeto de seguimiento es accesible globalmente. Consulte [Descripción general de la extensión de Adobe Analytics](https://docs.adobe.com/content/help/es-ES/launch/using/extensions-ref/adobe-extension/analytics-extension/overview.html) en la guía del usuario de Launch.

>[!CAUTION]
>
>Evite incluir bibliotecas de AppMeasurement tanto en una página principal como en un iframe. Al hacerlo, se corre el riesgo de enviar varias solicitudes de imagen, inflar informes y aumentar las llamadas facturables al servidor.

## Acceso a AppMeasurement que reside en un iframe

Puede acceder a las variables de AppMeasurement a través del objeto iframe. En estos ejemplos se establece [pageName](../vars/page-vars/pagename.md) y se llama al método [t()](../vars/functions/t-method.md) de dos formas diferentes de hacer referencia al objeto iframe.

```js
// Reference AppMeasurement code that resides within an iframe and send an image request
document.getElementById('targetFrame').contentWindow.s.pageName="Page name within iframe";
document.getElementById('targetFrame').contentWindow.s.t();

// An alternate method to the above if there's only one iframe on the page
window.frames[0].contentWindow.s.pageName = "Page name within iframe";
window.frames[0].contentWindow.s.t();
```

## Acceso a AppMeasurement desde dentro de un iframe

Puede acceder a las variables de AppMeasurement en una página principal desde un iframe. En este ejemplo se establece [pageName](../vars/page-vars/pagename.md) y se llama al método [t()](../vars/functions/t-method.md) mediante la propiedad [`parent`](https://www.w3schools.com/jsref/prop_win_parent.asp).

```js
// Reference AppMeasurement code on a parent page from within an iframe and send an image request
parent.s.pageName = "Page Name on Hosted Window";
parent.s.t();
```

## Uso de `postMessage` y detectores de eventos

Como alternativa, puede utilizar `postMessage` y detectores de eventos para establecer variables. Este método no requiere una referencia directa a un iframe.

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

* Al igual que con otros códigos JavaScript, los iFrames solo pueden comunicarse cuando los dominios y el protocolo coinciden. Estos ejemplos no funcionan si el contenido del iframe reside en un dominio diferente al dominio principal.
* Si AppMeasurement reside en un iframe, la variable [`referrer`](../vars/page-vars/referrer.md) se establece en la dirección URL principal, no en la dirección URL de referencia real. Puede configurar manualmente la variable `referrer` para resolver este problema.
* El [depurador de Adobe Experience Cloud](https://docs.adobe.com/content/help/es-ES/debugger/using/experience-cloud-debugger.html) no reconoce solicitudes de imagen activadas dentro de iFrames.
* Activity Map no muestra el mapa de calor sobre los vínculos en los que se hace clic dentro de los iFrames. Todo el iframe se resalta en su lugar.

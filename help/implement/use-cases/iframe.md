---
title: Uso de AppMeasurement con iFrames
description: Acceda a variables de Adobe Analytics dentro de un iframe o de una página principal mientras se encuentra en un iframe.
exl-id: 59b9cd4f-8599-41ee-8b54-a6a556198ecd
source-git-commit: 3986084eaab81842b6ea0dbabc7bdb78e39f887a
workflow-type: ht
source-wordcount: '319'
ht-degree: 100%

---

# Uso de AppMeasurement con iFrames

Puede hacer referencia a variables de AppMeasurement desde iFrames secundarios y principales. Es necesario definir todas las variables en la misma ubicación donde existe la biblioteca AppMeasurement. En los siguientes ejemplos se explica cómo configurar variables y métodos básicos de AppMeasurement dentro y fuera de un iframe.

Si utiliza etiquetas en Adobe Experience Platform, asegúrese de que el objeto de seguimiento es accesible globalmente. Consulte [Información general sobre la extensión Adobe Analytics](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/analytics/overview.html?lang=es).

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
* El [depurador de Adobe Experience Cloud](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html?lang=es) no reconoce solicitudes de imagen activadas dentro de iFrames.
* Activity Map no muestra el mapa de calor sobre los vínculos en los que se hace clic dentro de los iFrames. Todo el iframe se resalta en su lugar.

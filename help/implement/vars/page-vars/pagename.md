---
title: pageName
description: Nombre de la página del sitio.
translation-type: tm+mt
source-git-commit: c7d596be4f70c820039725be6a5fddc8572156d9

---


# pageName

La `pageName` variable generalmente almacena el nombre de una página determinada. Es útil determinar qué páginas individuales son más populares. Esta variable rellena la dimensión &#39;Nombre de página&#39;.

> [!NOTE] Esta dimensión siempre se elimina de las llamadas de seguimiento de vínculos. Si desea ver el nombre de la página donde se rastreó un vínculo, considere copiar esta variable en una eVar.

Si esta variable no está definida en una llamada de seguimiento de página determinada, se utiliza la `pageURL` variable en su lugar.

## Nombre de página en Adobe Experience Platform Launch

Puede definir el nombre de la página al configurar la extensión de Analytics (variables globales) o en reglas.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. Haga clic en la propiedad que desee.
3. Vaya a la ficha [!UICONTROL Reglas] y, a continuación, haga clic en la regla que desee (o cree una regla).
4. En [!UICONTROL Acciones], haga clic en una acción existente de [!UICONTROL Adobe Analytics - Establecer variables] o haga clic en el icono &#39;+&#39;.
5. Defina el menú desplegable [!UICONTROL Extensión] en Adobe Analytics y el tipo [!UICONTROL de] acción en [!UICONTROL Establecer variables].
6. Busque la sección Nombre [!UICONTROL de la] página.

Puede establecer el nombre de la página en cualquier valor de cadena, incluidos los elementos de datos.

## s.pageName en AppMeasurement e inicie el editor de código personalizado

La `s.pageName` variable es una cadena que generalmente contiene el nombre de la página. Tiene un valor máximo de 100 bytes; los valores más largos se truncan. Este truncamiento incluye instancias a las que se devuelve `pageURL` si esta variable está en blanco.

```js
// Set page name to a static value
s.pageName = "Example page name";

// Set page name to the page's title
s.pageName = window.document.title;
```

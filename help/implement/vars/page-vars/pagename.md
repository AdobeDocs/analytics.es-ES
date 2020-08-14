---
title: pageName
description: El nombre de la página del sitio.
translation-type: ht
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: ht
source-wordcount: '226'
ht-degree: 100%

---


# pageName

La variable `pageName` generalmente almacena el nombre de una página determinada. Es útil determinar qué páginas individuales son más populares. Esta variable rellena la dimensión “Nombre de página”.

>[!NOTE]
>
>Esta dimensión siempre se elimina de las llamadas de seguimiento de vínculos. Si desea ver el nombre de la página donde se ha registrado un vínculo, pruebe a copiar esta variable en una eVar.

Si esta variable no está definida en una llamada de seguimiento de página determinada, se utiliza la variable [`pageURL`](pageurl.md) en su lugar.

## Nombre de página en Adobe Experience Platform Launch

Puede definir el nombre de la página al configurar la extensión de Analytics (variables globales) o en reglas.

1. Inicie sesión en [launch.adobe.com](https://launch.adobe.com) con sus credenciales de Adobe ID.
2. Haga clic en la propiedad deseada.
3. Vaya a la pestaña [!UICONTROL Reglas] y, a continuación, haga clic en la regla que desee (o cree una regla).
4. En [!UICONTROL Acciones], haga clic en una acción existente de [!UICONTROL Adobe Analytics: Establecer variables] o haga clic en el icono “+”.
5. Establezca el menú desplegable [!UICONTROL Extensión] en Adobe Analytics y el [!UICONTROL tipo de acción] en [!UICONTROL Establecer variables].
6. Busque la sección [!UICONTROL Nombre de la página].

Puede establecer el nombre de la página en cualquier valor de cadena, incluidos los elementos de datos.

## “s.pageName” en el editor de código personalizado de AppMeasurement y Launch

La variable `s.pageName` es una cadena que generalmente contiene el nombre de la página. Tiene un valor máximo de 100 bytes. Los valores más largos se truncan. Este truncamiento incluye instancias a las que se recupera `pageURL` si esta variable está en blanco.

```js
// Set page name to a static value
s.pageName = "Example page name";

// Set page name to the page's title
s.pageName = window.document.title;
```

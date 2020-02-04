---
title: canal
description: Rellene la dimensión 'Secciones del sitio'.
translation-type: tm+mt
source-git-commit: c7d596be4f70c820039725be6a5fddc8572156d9

---


# canal

La `channel` variable generalmente almacena la sección del sitio en la que se encuentra una página determinada. Es útil determinar qué grupos del sitio son los más populares. Esta variable rellena la dimensión &#39;Secciones del sitio&#39;.

## Canal en Adobe Experience Platform Launch

Puede establecer channel durante la configuración de la extensión de Analytics (variables globales) o en reglas.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. Haga clic en la propiedad que desee.
3. Vaya a la ficha [!UICONTROL Reglas] y, a continuación, haga clic en la regla que desee (o cree una regla).
4. En [!UICONTROL Acciones], haga clic en una acción existente de [!UICONTROL Adobe Analytics - Establecer variables] o haga clic en el icono &#39;+&#39;.
5. Defina el menú desplegable [!UICONTROL Extensión] en Adobe Analytics y el tipo [!UICONTROL de] acción en [!UICONTROL Establecer variables].
6. Busque la sección [!UICONTROL Canal] .

Puede establecer channel en cualquier valor de cadena o elemento de datos.

## s.channel en AppMeasurement e inicie el editor de código personalizado

La `s.channel` variable es una cadena que generalmente contiene la sección del sitio de la página. Tiene un valor máximo de 100 bytes; los valores más largos se truncan.

```js
s.channel = "Example site section";
```

---
title: servidor
description: Rellene la dimensión 'Servidores'.
translation-type: tm+mt
source-git-commit: c7d596be4f70c820039725be6a5fddc8572156d9

---


# servidor

La `server` variable generalmente almacena el nombre de host del sitio. Normalmente se utiliza en grupos de informes que contienen datos de varios dominios. Funcionalmente es idéntico a una propiedad.

## Servidor en Adobe Experience Platform Launch

Puede configurar el servidor durante la configuración de la extensión de Analytics (variables globales) o en reglas.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. Haga clic en la propiedad que desee.
3. Vaya a la ficha [!UICONTROL Reglas] y, a continuación, haga clic en la regla que desee (o cree una regla).
4. En [!UICONTROL Acciones], haga clic en una acción existente de [!UICONTROL Adobe Analytics - Establecer variables] o haga clic en el icono &#39;+&#39;.
5. Defina el menú desplegable [!UICONTROL Extensión] en Adobe Analytics y el tipo [!UICONTROL de] acción en [!UICONTROL Establecer variables].
6. Busque la sección [!UICONTROL Servidor] .

Puede establecer server en cualquier valor de cadena o elemento de datos.

## s.server en AppMeasurement e Iniciar editor de código personalizado

La `s.server` variable es una cadena que generalmente contiene el nombre de host del sitio. Tiene un valor máximo de 100 bytes; los valores más largos se truncan.

```js
// Set the server variable to a static string
s.server = "Example server";

// Automatically set the server variable to the site's hostname
s.server = window.location.hostname;
```

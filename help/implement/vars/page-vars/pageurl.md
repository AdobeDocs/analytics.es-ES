---
title: pageURL
description: Omitir la dirección URL de la página recopilada automáticamente en el sitio.
translation-type: tm+mt
source-git-commit: f75c6759feb6576017733f1aac5bff2e21d4b0af

---


# pageURL

AppMeasurement recopila automáticamente la dirección URL de la página en cada visita. Si desea anular la dirección URL de la página recopilada automáticamente por AppMeasurement, puede utilizar esta variable. No es necesario configurar esta variable en la mayoría de los casos.

> [!NOTE] Esta variable no es una dimensión disponible en Analysis Workspace. Solo está disponible en Almacén de datos y en Fuentes de datos. Si desea utilizar la dirección URL de la página como dimensión en Analysis Workspace, considere pasar la variable a una eVar en cada visita. `pageURL`

A veces, las direcciones URL tienen más de 255 bytes. AppMeasurement utiliza el parámetro de cadena de `g` consulta para los primeros 255 bytes de la dirección URL en las solicitudes de imagen. Si una dirección URL tiene más de 255 bytes, el resto de la dirección URL se almacena en el parámetro de cadena de `-g` consulta. Las cadenas de consulta y protocolo de la dirección URL se incluyen en esta variable.

## Dirección URL de la página en Adobe Experience Platform Launch

Launch rellena automáticamente la dirección URL de la página. Sin embargo, puede establecer la anulación de la dirección URL de la página al configurar la extensión de Analytics (variables globales) o en reglas.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. Haga clic en la propiedad que desee.
3. Vaya a la ficha [!UICONTROL Reglas] y, a continuación, haga clic en la regla que desee (o cree una regla).
4. En [!UICONTROL Acciones], haga clic en una acción existente de [!UICONTROL Adobe Analytics - Establecer variables] o haga clic en el icono &#39;+&#39;.
5. Defina el menú desplegable [!UICONTROL Extensión] en Adobe Analytics y el tipo [!UICONTROL de] acción en [!UICONTROL Establecer variables].
6. Busque la sección Dirección URL [!UICONTROL de la] página.

Puede establecer la dirección URL de la página en cualquier valor de cadena.

## s.pageURL en AppMeasurement e inicie el editor de código personalizado

La `s.pageURL` variable es una cadena que contiene la dirección URL de la página. AppMeasurement recopila automáticamente esta variable, aunque puede anular su valor si lo desea.

```js
s.pageURL = "https://example.com";
```

Si desea utilizar la dirección URL de la página como dimensión en los informes, considere la posibilidad de utilizar lo siguiente en la implementación:

```js
// Set eVar1 to page URL without protocol or query strings
s.eVar1 = window.location.hostname + window.location.pathname;
```

---
title: zip
description: Rellene manualmente la dimensión 'Código postal' si la configuración del grupo de informes lo permite.
translation-type: tm+mt
source-git-commit: f75c6759feb6576017733f1aac5bff2e21d4b0af

---


# zip

La `zip` variable permite rellenar manualmente la dimensión &#39;Código postal&#39; si la opción  Zip en la configuración del grupo de informes lo permite. En versiones anteriores de Adobe Analytics, esta variable solo se podía establecer manualmente, normalmente al introducir información de envío en un sitio de venta minorista. Las mejoras en Adobe Analytics permiten que esta variable se establezca automáticamente mediante datos de ubicación geográfica. Esta variable no persiste más allá de la visita que se ha establecido.

> [!IMPORTANT] Asegúrese de que la opción [!UICONTROL Zip] de la configuración del grupo de informes está establecida en el valor deseado. No puede utilizar esta variable si siempre se utiliza [!UICONTROL geo zip] . See [General Account Settings](/help/admin/admin/general-acct-settings-admin.md) in the Admin user guide for more information.

## Código postal en Adobe Experience Platform Launch

Puede establecer el código postal al configurar la extensión de Analytics (variables globales) o en reglas.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. Haga clic en la propiedad que desee.
3. Vaya a la ficha [!UICONTROL Reglas] y, a continuación, haga clic en la regla que desee (o cree una regla).
4. En [!UICONTROL Acciones], haga clic en una acción existente de [!UICONTROL Adobe Analytics - Establecer variables] o haga clic en el icono &#39;+&#39;.
5. Defina el menú desplegable [!UICONTROL Extensión] en Adobe Analytics y el tipo [!UICONTROL de] acción en [!UICONTROL Establecer variables].
6. Busque la sección [!UICONTROL Zip] .

Puede establecer Código postal en cualquier valor de cadena, incluidos los elementos de datos.

## s.zip en AppMeasurement e inicie el editor de código personalizado

La `s.zip` variable es una cadena que generalmente contiene un código postal, pero puede contener cualquier valor deseado de hasta 50 bytes de longitud.

```js
s.zip = "84043";
```

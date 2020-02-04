---
title: cookieLifetime
description: Anule la caducidad de las cookies que crea AppMeasurement.
translation-type: tm+mt
source-git-commit: 979a95ca749a3e21c4ddf48ba2d2a95672938a20

---


# cookieLifetime

Las cookies configuradas por AppMeasurement suelen tener una caducidad de 2 años. Utilice la `cookieLifetime` variable para anular la fecha de caducidad de las cookies establecidas por AppMeasurement.

> [!NOTE] Esta variable afecta a los recuentos y la atribución de visitantes únicos. Tenga cuidado al configurar esta variable.

## Duración de la cookie en el lanzamiento de la plataforma Adobe Experience

Duración de la cookie es un menú desplegable en el acordeón [!UICONTROL Cookies] al configurar la extensión de Adobe Analytics.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. Haga clic en la propiedad que desee.
3. Vaya a la ficha [!UICONTROL Extensiones] y, a continuación, haga clic en el botón [!UICONTROL Configurar] en Adobe Analytics.
4. Expanda el acordeón [!UICONTROL Cookies] , que muestra el menú desplegable Duración [!UICONTROL de la] cookie.

Este menú desplegable contiene los siguientes valores:

* **Predeterminado**: La cookie caduca pasados 2 años.
* **Ninguno**: AppMeasurement no establece cookies.
* **Sesión**: La cookie caduca al final de la sesión del visitante.
* **Segundos**: La cookie caduca después de que haya transcurrido el número de segundos especificado. Por ejemplo, si se establece este menú desplegable en [!UICONTROL Segundos] y se coloca `86400` en el campo personalizado, las cookies caducan exactamente después de 24 horas.

## s.cookieLifetime en AppMeasurement e inicie el editor de código personalizado

La `s.cookieLifetime` variable es una cadena que determina la fecha de caducidad de las cookies establecidas por AppMeasurement.

* Si se establece en `SESSION`, las cookies configuradas por AppMeasurement caducan después de que se complete la sesión del explorador.
* Si se establece en `NONE`, AppMeasurement no intenta establecer cookies.
* Si se establece en una cadena entera, las cookies configuradas por AppMeasurement caducan después de que transcurra el número especificado de segundos.

```js
// Expire cookies after each session
s.cookieLifetime = "SESSION";

// Expire cookies after exactly 24 hours
s.cookieLifetime = "86400";


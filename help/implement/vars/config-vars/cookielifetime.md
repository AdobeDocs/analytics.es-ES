---
title: cookieLifetime
description: Anule la caducidad de las cookies que crea AppMeasurement.
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# cookieLifetime

Las cookies configuradas por AppMeasurement suelen tener una caducidad de 2 años. Utilice la variable `cookieLifetime` para anular la fecha de caducidad de las cookies establecidas por AppMeasurement.

>[!NOTE] Esta variable afecta a los recuentos y la atribución de visitantes únicos. Tenga cuidado al configurar esta variable.

## Duración de la cookie en Adobe Experience Platform Launch

Duración de la cookie es un menú desplegable en el acordeón de [!UICONTROL Cookies] al configurar la extensión de Adobe Analytics.

1. Inicie sesión en [launch.adobe.com](https://launch.adobe.com) con sus credenciales de Adobe ID.
2. Haga clic en la propiedad deseada.
3. Go to the [!UICONTROL Extensions] tab, then click the [!UICONTROL Configure] button under Adobe Analytics.
4. Expanda el [!UICONTROL Cookies] acordeón, que muestra el [!UICONTROL Cookie Lifetime] menú desplegable.

Este menú desplegable contiene los siguientes valores:

* **Predeterminado**: La cookie caduca pasados 2 años.
* **Ninguno**: AppMeasurement no establece cookies.
* **Sesión**: La cookie caduca al final de la sesión del visitante.
* **Segundos**: La cookie caduca después de que haya transcurrido el número de segundos especificado. For example, setting this dropdown to [!UICONTROL Seconds] and placing `86400` into the custom field forces cookies to expire after exactly 24 hours.

## s.cookieLifetime en el editor de código personalizado de AppMeasurement y Launch

La variable `s.cookieLifetime` es una cadena que determina la fecha de caducidad de las cookies establecidas por AppMeasurement.

* Si se establece como `SESSION`, las cookies configuradas por AppMeasurement caducan después de que se complete la sesión del explorador.
* Si se establece como `NONE`, AppMeasurement no intenta establecer cookies.
* Si se establece en una cadena entera, las cookies configuradas por AppMeasurement caducan después de que transcurra el número especificado de segundos.

```js
// Expire cookies after each session
s.cookieLifetime = "SESSION";

// Expire cookies after exactly 24 hours
s.cookieLifetime = "86400";


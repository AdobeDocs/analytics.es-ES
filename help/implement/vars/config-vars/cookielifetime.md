---
title: cookieLifetime
description: Anule la caducidad de las cookies que crea AppMeasurement.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '229'
ht-degree: 100%

---


# cookieLifetime

Las cookies configuradas por AppMeasurement suelen tener una caducidad de 2 años. Utilice la variable `cookieLifetime` para anular la fecha de caducidad de las cookies establecidas por AppMeasurement.

>[!NOTE]
>
>Esta variable afecta a los recuentos y la atribución de visitantes únicos. Tenga cuidado al configurar esta variable.

## Duración de la cookie en Adobe Experience Platform Launch

Duración de la cookie es un menú desplegable en el acordeón de [!UICONTROL Cookies] al configurar la extensión de Adobe Analytics.

1. Inicie sesión en [launch.adobe.com](https://launch.adobe.com) con sus credenciales de Adobe ID.
2. Haga clic en la propiedad deseada.
3. Vaya a la pestaña [!UICONTROL Extensiones] y, a continuación, haga clic en el botón [!UICONTROL Configurar] en Adobe Analytics.
4. Expanda el acordeón [!UICONTROL Cookies], que muestra el menú desplegable [!UICONTROL Duración de la cookie].

Este menú desplegable contiene los siguientes valores:

* **Predeterminado**: La cookie caduca pasados 2 años.
* **Ninguno**: AppMeasurement no establece cookies.
* **Sesión**: La cookie caduca al final de la sesión del visitante.
* **Segundos**: La cookie caduca después de que haya transcurrido el número de segundos especificado. Por ejemplo, si se establece este menú desplegable en [!UICONTROL Segundos] y se coloca `86400` en el campo personalizado, las cookies caducan exactamente después de 24 horas.

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


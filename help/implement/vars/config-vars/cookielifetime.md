---
title: cookieLifetime
description: Anule la caducidad de las cookies que crea AppMeasurement.
feature: Variables
exl-id: 2cd64301-9f12-4e77-abae-af431e4b499d
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '264'
ht-degree: 64%

---

# cookieLifetime

Las cookies configuradas por AppMeasurement suelen tener una caducidad de 2 años. Utilice la variable `cookieLifetime` para anular la fecha de caducidad de las cookies establecidas por AppMeasurement.

>[!NOTE]
>
>Esta variable afecta a los recuentos y la atribución de visitantes únicos. Tenga cuidado al configurar esta variable.

## Duración de la cookie mediante el SDK web

El SDK web aún no ofrece personalización durante la duración de las cookies que establece.

## Duración de la cookie mediante la extensión Adobe Analytics

Duración de la cookie es una lista desplegable en el acordeón [!UICONTROL Cookies] al configurar la extensión de Adobe Analytics.

1. Inicie sesión en la [Recopilación de datos de Adobe Experience Platform](https://experience.adobe.com/data-collection) con sus credenciales de Adobe ID.
1. Haga clic en la propiedad de etiquetas deseada.
1. Vaya a la pestaña [!UICONTROL Extensiones] y, a continuación, haga clic en el botón **[!UICONTROL Configurar]** en Adobe Analytics.
1. Expanda el acordeón [!UICONTROL Cookies], que muestra la lista desplegable [!UICONTROL Duración de la cookie].

Esta lista desplegable contiene los siguientes valores:

* **Predeterminado**: La cookie caduca pasados 2 años.
* **Ninguno**: AppMeasurement no establece cookies.
* **Sesión**: La cookie caduca al final de la sesión del visitante.
* **Segundos**: La cookie caduca después de que haya transcurrido el número de segundos especificado. Por ejemplo, si establece esta lista desplegable en [!UICONTROL Segundos] y coloca `86400` en el campo personalizado, las cookies caducarán exactamente después de 24 horas.

## s.cookieLifetime en el AppMeasurement y el editor de código personalizado de la extensión de Analytics

La variable `s.cookieLifetime` es una cadena que determina la fecha de caducidad de las cookies establecidas por AppMeasurement.

* Si se establece como `SESSION`, las cookies configuradas por AppMeasurement caducan después de que se complete la sesión del explorador.
* Si se establece como `NONE`, AppMeasurement no intenta establecer cookies.
* Si se establece en una cadena entera, las cookies configuradas por AppMeasurement caducan después de que transcurra el número especificado de segundos.

```js
// Expire cookies after each session
s.cookieLifetime = "SESSION";

// Expire cookies after exactly 24 hours
s.cookieLifetime = "86400";
```

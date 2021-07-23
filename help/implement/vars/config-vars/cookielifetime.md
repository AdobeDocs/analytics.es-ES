---
title: cookieLifetime
description: Anule la caducidad de las cookies que crea AppMeasurement.
exl-id: 2cd64301-9f12-4e77-abae-af431e4b499d
source-git-commit: 3986084eaab81842b6ea0dbabc7bdb78e39f887a
workflow-type: tm+mt
source-wordcount: '240'
ht-degree: 85%

---

# cookieLifetime

Las cookies configuradas por AppMeasurement suelen tener una caducidad de 2 años. Utilice la variable `cookieLifetime` para anular la fecha de caducidad de las cookies establecidas por AppMeasurement.

>[!NOTE]
>
>Esta variable afecta a los recuentos y la atribución de visitantes únicos. Tenga cuidado al configurar esta variable.

## Duración de la cookie en etiquetas de Adobe Experience Platform

Duración de la cookie es un menú desplegable en el acordeón de [!UICONTROL Cookies] al configurar la extensión de Adobe Analytics.

1. Vaya a `experience.adobe.com` e inicie sesión cuando se le solicite.
1. Seleccione [!UICONTROL Iniciar / Recopilación de datos].
1. Haga clic en [!UICONTROL Ir a Launch / Data Collection] y seleccione [!UICONTROL Etiquetas].
1. Haga clic en la propiedad deseada.
1. Vaya a la pestaña [!UICONTROL Extensiones] y, a continuación, haga clic en el botón [!UICONTROL Configurar] en Adobe Analytics.
1. Expanda el acordeón [!UICONTROL Cookies], que muestra el menú desplegable [!UICONTROL Duración de la cookie].

Este menú desplegable contiene los siguientes valores:

* **Predeterminado**: La cookie caduca pasados 2 años.
* **Ninguno**: AppMeasurement no establece cookies.
* **Sesión**: La cookie caduca al final de la sesión del visitante.
* **Segundos**: La cookie caduca después de que haya transcurrido el número de segundos especificado. Por ejemplo, si se establece este menú desplegable en [!UICONTROL Segundos] y se coloca `86400` en el campo personalizado, las cookies caducan exactamente después de 24 horas.

## s.cookieLifetime en el editor de código personalizado de AppMeasurement y recopilación de datos

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

---
title: visitorID
description: Utilice un ID de visitante personalizado.
translation-type: tm+mt
source-git-commit: 979a95ca749a3e21c4ddf48ba2d2a95672938a20

---


# visitorID

Adobe utiliza diferentes métodos para identificar a los visitantes del sitio. La `visitorID` variable anula todos los demás métodos de identificación del visitante.

> [!IMPORTANT] Adobe recomienda no utilizar esta variable. En su lugar, utilice el servicio [de identidad de](https://docs.adobe.com/content/help/en/id-service/using/home.html) Adobe Experience Cloud.

## ID de visitante en Adobe Experience Platform Launch

[!UICONTROL ID] de visitante es un campo en el acordeón [!UICONTROL Cookies] al configurar la extensión de Adobe Analytics.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. Haga clic en la propiedad que desee.
3. Vaya a la ficha [!UICONTROL Extensiones] y, a continuación, haga clic en el botón [!UICONTROL Configurar] en Adobe Analytics.
4. Expanda el acordeón [!UICONTROL Cookies] , que muestra el campo ID [!UICONTROL del] visitante.

Asigne este campo al elemento de datos que contenga su ID de visitante personalizada. No establezca este campo en un valor estático.

## s.visitorID en el editor de código personalizado AppMeasurement e Launch

La `s.visitorID` variable es una cadena que contiene un identificador único personalizado para el visitante. Los valores válidos incluyen caracteres alfanuméricos de hasta 100 bytes. Evite utilizar guiones, espacios, guiones bajos o símbolos en esta variable.

> [!WARNING] Si establece la `visitorID` variable partway a través de una visita, los datos resultan en dos visitantes únicos independientes.

```js
s.visitorID = "abc123";
```

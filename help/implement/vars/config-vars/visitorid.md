---
title: visitorID
description: Utilice un ID de visitante personalizado.
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# visitorID

Adobe utiliza diferentes métodos para identificar a los visitantes del sitio. La variable `visitorID` anula todos los demás métodos de identificación del visitante.

>[!IMPORTANT] Adobe recomienda evitar esta variable. En su lugar, utilice el [servicio de identidad de Adobe Experience Cloud](https://docs.adobe.com/content/help/es-ES/id-service/using/home.html).

## ID de visitante en Adobe Experience Platform Launch

[!UICONTROL Visitor ID] es un campo bajo el [!UICONTROL Cookies] acordeón al configurar la extensión de Adobe Analytics.

1. Inicie sesión en [launch.adobe.com](https://launch.adobe.com) con sus credenciales de Adobe ID.
2. Haga clic en la propiedad deseada.
3. Go to the [!UICONTROL Extensions] tab, then click the [!UICONTROL Configure] button under Adobe Analytics.
4. Expanda el [!UICONTROL Cookies] acordeón, que muestra el [!UICONTROL Visitor ID] campo.

Asigne este campo al elemento de datos que contenga su ID de visitante personalizada. No establezca este campo como un valor estático.

## s.visitorID en el editor de código personalizado de AppMeasurement y Launch

La variable `s.visitorID` es una cadena que contiene un identificador único personalizado para el visitante. Los valores válidos incluyen caracteres alfanuméricos de hasta 100 bytes. Evite utilizar guiones, espacios, guiones bajos o símbolos en esta variable.

>[!WARNING] Si establece la variable `visitorID` en mitad de una visita, los datos generarán dos visitantes únicos independientes.

```js
s.visitorID = "abc123";
```

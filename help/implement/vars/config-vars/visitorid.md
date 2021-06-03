---
title: visitorID
description: Utilice un ID de visitante personalizado.
exl-id: cb336042-01a1-4a66-a947-a221a7919c1b
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '255'
ht-degree: 97%

---

# visitorID

Adobe utiliza diferentes métodos para identificar a los visitantes del sitio. La variable `visitorID` anula todos los demás métodos de identificación del visitante.

>[!IMPORTANT]
>
>Adobe recomienda evitar esta variable. En su lugar, utilice el [servicio de identidad de Adobe Experience Cloud](https://experienceleague.adobe.com/docs/id-service/using/home.html).

## ID de visitante en Adobe Experience Platform Launch

[!UICONTROL ID de visitante] es un campo en el acordeón de [!UICONTROL Cookies] al configurar la extensión de Adobe Analytics.

1. Inicie sesión en [launch.adobe.com](https://launch.adobe.com) con sus credenciales de Adobe ID.
2. Haga clic en la propiedad deseada.
3. Vaya a la pestaña [!UICONTROL Extensiones] y, a continuación, haga clic en el botón [!UICONTROL Configurar] en Adobe Analytics.
4. Expanda el acordeón [!UICONTROL Cookies], que muestra el campo [!UICONTROL ID de visitante].

Asigne este campo al elemento de datos que contenga su ID de visitante personalizada. No establezca este campo como un valor estático.

## s.visitorID en el editor de código personalizado de AppMeasurement y Launch

La variable `s.visitorID` es una cadena que contiene un identificador único personalizado para el visitante. Los valores válidos incluyen caracteres alfanuméricos de hasta 100 bytes. Evite utilizar guiones, espacios, guiones bajos o símbolos en esta variable.

>[!WARNING]
>
>Si establece la variable `visitorID` en mitad de una visita, los datos generarán dos visitantes únicos independientes.

```js
s.visitorID = "abc123";
```

>[!CAUTION]
>
>Una implementación no válida de los ID de visitante personalizados puede generar datos incorrectos y un rendimiento de sistema de informes deficiente. Si esta variable contiene un valor predeterminado (como `"0"` o `"NULL"`), Adobe trata estas visitas como si fueran el mismo visitante. Esta situación da como resultado datos incorrectos, con recuentos de visitantes bajos y segmentos de nivel de visitante que no funcionan según lo esperado. Los ID de visitante personalizados implementados incorrectamente también introducen una carga pesada en los servidores de procesamiento, lo que aumenta la [latencia](/help/technotes/latency.md) y disminuye el rendimiento del informe.

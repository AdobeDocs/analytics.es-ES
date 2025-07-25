---
title: visitorID
description: Utilice un ID de visitante personalizado.
feature: Appmeasurement Implementation
exl-id: cb336042-01a1-4a66-a947-a221a7919c1b
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '334'
ht-degree: 71%

---

# visitorID

Adobe utiliza diferentes métodos para identificar a los visitantes del sitio. La variable `visitorID` anula todos los demás métodos de identificación del visitante.

>[!IMPORTANT]
>
>Adobe recomienda evitar esta variable. En su lugar, utilice el [servicio de identidad de Adobe Experience Cloud](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=es).

## ID de visitante con la extensión Adobe Analytics

[!UICONTROL ID de visitante] es un campo en el acordeón de [!UICONTROL Cookies] al configurar la extensión de Adobe Analytics.

1. Inicie sesión en la [Recopilación de datos de Adobe Experience Platform](https://experience.adobe.com/data-collection) con sus credenciales de Adobe ID.
2. Haga clic en la propiedad de etiquetas deseada.
3. Vaya a la pestaña [!UICONTROL Extensiones] y, a continuación, haga clic en el botón **[!UICONTROL Configurar]** en Adobe Analytics.
4. Expanda el acordeón [!UICONTROL Cookies], que muestra el campo [!UICONTROL ID de visitante].

Asigne este campo al elemento de datos que contenga su ID de visitante personalizada. No establezca este campo como un valor estático.

## s.visitorID en AppMeasurement y el editor de código personalizado de la extensión de Analytics

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

## ID de visitante con Web SDK

Adobe Experience Platform Edge Network le permite proporcionar varios identificadores utilizando el [mapa de identidad](https://experienceleague.adobe.com/docs/experience-platform/edge/identity/overview.html?lang=es#using-identitymap) de XDM. Cada identidad de un mapa de identidad tiene un área de nombres diferente. Puede especificar qué área de nombres debe usarse para el ID de visitante como parte de [configuración de secuencia de datos](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=es#analytics). Una vez configurado, cuando envíe un evento con un valor especificado para esta área de nombres, se utilizará automáticamente como ID de visitante en Analytics.

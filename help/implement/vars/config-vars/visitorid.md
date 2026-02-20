---
title: visitorID
description: Utilice un ID de visitante personalizado.
feature: Appmeasurement Implementation
exl-id: cb336042-01a1-4a66-a947-a221a7919c1b
role: Admin, Developer
source-git-commit: de98bf68c57f5453b6662f6e6e57312d8fd3e642
workflow-type: tm+mt
source-wordcount: '484'
ht-degree: 19%

---

# visitorID

Adobe usa diferentes métodos para [identificar visitantes](../../id/overview.md) en el sitio. **La variable `visitorID` anula todos los demás métodos de identificación de visitantes.**

>[!IMPORTANT]
>
>Adobe recomienda evitar esta variable. En su lugar, utilice el [servicio de identidad de Adobe Experience Cloud](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=es).

## Cómo usa Analytics `visitorID`

Esta variable es una anulación manual del ID de visitante que reemplaza todas las demás formas de identificación del visitante. Para ser contabilizado como un solo visitante, cada visita individual para una persona debe usar el mismo valor `visitorID`.

* Las visitas que omiten `visitorID` vuelven a otro método de identificación de visitante y se tratan como un visitante independiente.
* Las visitas que utilizan más de un valor `visitorID` se tratan como visitantes independientes.
* Adobe no vincula las visitas que utilizan distintos ID de visitante.

Consulte [Identificación de visitantes en Adobe Analytics](../../id/overview.md) para obtener detalles sobre la prioridad de identificación y por qué la mezcla de identificadores puede aumentar los recuentos de visitantes.

>[!WARNING]
>
>Establezca `visitorID` solo si puede garantizar que se establece en cada visita para esa persona y que el valor nunca cambia. Si se configura solo en algunas visitas, se introduce en parte a través de una visita (por ejemplo, al autenticarse) o se cambia entre visitas, la actividad de un visitante se divide en varios visitantes.

>[!CAUTION]
>
>Los valores no válidos de ID de visitante personalizado pueden generar datos incorrectos y un rendimiento de sistema de informes deficiente. Si esta variable contiene un valor predeterminado o de marcador de posición (como `"0"` o `"NULL"`), Adobe trata estas visitas como si fueran el mismo visitante. Esta situación da como resultado datos incorrectos, con recuentos de visitantes artificialmente bajos y segmentos de nivel de visitante que no funcionan según lo esperado. Los ID de visitante personalizados implementados incorrectamente también pueden introducir una carga pesada en los servidores de procesamiento, lo que aumenta la [latencia](/help/technotes/latency.md) y disminuye el rendimiento del informe.

## ID de visitante con la extensión Adobe Analytics

[!UICONTROL ID de visitante] es un campo en el acordeón de [!UICONTROL Cookies] al configurar la extensión de Adobe Analytics.

1. Inicie sesión en la [Recopilación de datos de Adobe Experience Platform](https://experience.adobe.com/data-collection) con sus credenciales de Adobe ID.
2. Seleccione la propiedad de etiquetas que desee.
3. Vaya a la pestaña [!UICONTROL Extensions] y, a continuación, seleccione el botón **[!UICONTROL Configure]** en Adobe Analytics.
4. Expanda el acordeón [!UICONTROL Cookies], que muestra el campo [!UICONTROL ID de visitante].

Asigne este campo al elemento de datos que contenga su ID de visitante personalizada. **No establezca este campo en un solo valor estático para todos los visitantes.**: utilice un elemento de datos que se resuelva por visitante y que permanezca constante en todas las visitas.

## s.visitorID en AppMeasurement y el editor de código personalizado de la extensión de Analytics

La variable `s.visitorID` es una cadena que contiene un identificador único personalizado para el visitante. Los valores válidos incluyen caracteres alfanuméricos de hasta 100 bytes. Evite utilizar guiones, espacios, guiones bajos o símbolos en esta variable.

```js
s.visitorID = "abc123";
```

## ID de visitante con Web SDK

Adobe Experience Platform Edge Network le permite proporcionar varios identificadores utilizando el [mapa de identidad](https://experienceleague.adobe.com/docs/experience-platform/edge/identity/overview.html?lang=es#using-identitymap) de XDM. Cada identidad de un mapa de identidad tiene un área de nombres diferente. Puede especificar qué área de nombres debe usarse para el ID de visitante como parte de [configuración de secuencia de datos](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=es#analytics). Una vez configurado este campo, cuando se envía un evento con un valor especificado para esta área de nombres, se utiliza automáticamente como ID de visitante en Analytics.

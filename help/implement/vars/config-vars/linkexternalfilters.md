---
title: linkExternalFilters
description: Utilice la variable linkExternalFilters para ayudar al seguimiento automático de vínculos de salida.
feature: Appmeasurement Implementation
exl-id: 7d4e8d96-17ee-4a04-9a57-37d2056ee9a7
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '388'
ht-degree: 91%

---

# linkExternalFilters

AppMeasurement ofrece la capacidad de rastrear automáticamente los vínculos que redirigen fuera del sitio. Si [`trackExternalLinks`](trackexternallinks.md) (AppMeasurement) o [`clickCollectionEnabled`](trackexternallinks.md) (SDK web) está habilitada, se envía una solicitud de imagen a Adobe justo cuando un visitante hace clic en un vínculo para abandonar el sitio. Las variables `linkExternalFilters` y [`linkInternalFilters`](linkinternalfilters.md) determinan qué vínculos se consideran internos/externos.

Si esta variable contiene un valor, el seguimiento automático de vínculos de salida se comporta como una lista de permitidos. Si un clic en un vínculo no coincide con ningún valor de `linkExternalFilters`, no se considera un vínculo de salida. La dirección URL completa se examina con esta variable. Si [`linkLeaveQueryString`](linkleavequerystring.md) está habilitada, también se examina la cadena de consulta.

>[!TIP]
>
>Utilice esta variable solo si sabe exactamente qué dominios desea considerar como vínculos de salida. Muchas organizaciones consideran que el uso de `linkInternalFilters` es suficiente para sus necesidades de seguimiento de vínculos de salida y no utilizan `linkExternalFilters`.

Si utiliza `linkInternalFilters` y `linkExternalFilters` simultáneamente, el vínculo en el que se hizo clic debe coincidir con `linkExternalFilters` **y no** con `linkInternalFilters` para considerarse como un vínculo de salida. Si un vínculo en el que se hizo clic coincide con los criterios de vínculo de salida y de descarga, el tipo de vínculo de descarga tiene prioridad.

## Vínculos de salida en el SDK web

Los vínculos se califican automáticamente como vínculos de salida si el dominio de destino del vínculo es distinto del actual `window.location.hostname`. El SDK web no ofrece ninguna variable de configuración para modificar la detección automática de vínculos de salida. Si necesita personalizar los dominios que cumplen los requisitos como vínculo de salida, puede utilizar la lógica personalizada en la llamada de retorno `onBeforeEventSend`.

Consulte [Seguimiento automático de vínculos](https://experienceleague.adobe.com/docs/experience-platform/edge/data-collection/track-links.html?lang=es#automaticLinkTracking) en la documentación del SDK web para obtener más información.

## Vínculos de salida: Rastrear mediante la extensión de Adobe Analytics

El campo Rastrear es una lista de filtros separados por comas (generalmente dominios) en el acordeón de [!UICONTROL Seguimiento de vínculos] al configurar la extensión de Adobe Analytics.

1. Inicie sesión en la [Recopilación de datos de Adobe Experience Platform](https://experience.adobe.com/data-collection) con sus credenciales de Adobe ID.
2. Haga clic en la propiedad de etiquetas deseada.
3. Vaya a la pestaña [!UICONTROL Extensiones] y, a continuación, haga clic en el botón **[!UICONTROL Configurar]** en Adobe Analytics.
4. Expanda el acordeón de [!UICONTROL Seguimiento de vínculos], que muestra el campo [!UICONTROL Seguimiento de vínculos de salida].

Coloque los filtros que desee considerar siempre externos en este campo. Separe varios dominios con una coma sin espacios.

## s.linkExternalFilters en AppMeasurement y el editor de código personalizado de la extensión de Analytics

La variable `s.linkExternalFilters` es una cadena que contiene filtros (como dominios) que se consideran vínculos de salida. Separe varios dominios con una coma sin espacios.

```js
s.linkExternalFilters = "example.com,example.net,example.org";
```

Considere el siguiente ejemplo de implementación como si estuviera en `adobe.com`:

```html
<script>
  s.trackExternalLinks = true;
  s.linkExternalFilters = "example.com,example.net";
</script>

<!-- The following link is NOT considered an exit link, even though the link is outside adobe.com -->
<a href = "example.org">Example link 1</a>

<!-- The following link is an exit link because it matches the linkExternalFilters allowlist -->
<a href = "example.com">Example link 2</a>
```

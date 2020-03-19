---
title: linkExternalFilters
description: Utilice la variable linkExternalFilters para ayudar al seguimiento automático de vínculos de salida.
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# linkExternalFilters

AppMeasurement ofrece la capacidad de rastrear automáticamente los vínculos que apuntan fuera del sitio. Si [`trackExternalLinks`](trackexternallinks.md) está habilitada, se envía una solicitud de imagen a Adobe directamente cuando un visitante hace clic en un vínculo para abandonar el sitio. Las `linkExternalFilters` variables y [`linkInternalFilters`](linkinternalfilters.md) determinan qué vínculos se consideran internos/externos.

Si esta variable contiene un valor, el seguimiento automático de vínculos de salida se comporta de una manera similar a la lista de direcciones permitidas. Si un clic en un vínculo no coincide con ningún `linkExternalFilters` valor, no se considera un vínculo de salida. La dirección URL completa se examina con esta variable. Si [`linkLeaveQueryString`](linkleavequerystring.md) está habilitada, también se examina la cadena de consulta.

> [!TIP] Utilice esta variable sólo si sabe exactamente qué dominios desea considerar como vínculos de salida. Muchas organizaciones consideran que el uso `linkInternalFilters` es suficiente para sus necesidades de seguimiento de vínculos de salida y no lo utilizan `linkExternalFilters`.

Si utiliza `linkInternalFilters` y `linkExternalFilters` simultáneamente, el vínculo en el que se hizo clic debe coincidir `linkExternalFilters` y no coincidir **para** `linkInternalFilters` ser considerado un vínculo de salida. Si un vínculo en el que se hizo clic coincide con los criterios de vínculo de salida y de descarga, el tipo de vínculo de descarga tiene prioridad.

## Vínculos salientes: Seguimiento en Adobe Experience Platform Launch

El campo Rastrear es una lista de filtros separados por comas (generalmente dominios) bajo el acordeón [!UICONTROL Link Tracking] al configurar la extensión de Adobe Analytics.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. Haga clic en la propiedad que desee.
3. Vaya a la [!UICONTROL Extensions] ficha y, a continuación, haga clic en el [!UICONTROL Configure] botón situado debajo de Adobe Analytics.
4. Expanda el [!UICONTROL Link Tracking] acordeón, que muestra el [!UICONTROL Outbound Links - Track] campo.

Coloque los filtros que desee considerar siempre externos en este campo. Separe varios dominios con una coma sin espacio.

## s.linkExternalFilters en AppMeasurement e inicie el editor de código personalizado

La `s.linkExternalFilters` variable es una cadena que contiene filtros (como dominios) que se consideran vínculos de salida. Separe varios dominios con una coma sin espacios.

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

<!-- The following link is an exit link because it matches the linkExternalFilters whitelist -->
<a href = "example.com">Example link 2</a>
```

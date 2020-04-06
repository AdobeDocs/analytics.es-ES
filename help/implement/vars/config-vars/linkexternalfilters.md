---
title: linkExternalFilters
description: Utilice la variable linkExternalFilters para ayudar al seguimiento automático de vínculos de salida.
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# linkExternalFilters

AppMeasurement ofrece la capacidad de rastrear automáticamente los vínculos que redirigen fuera del sitio. If [`trackExternalLinks`](trackexternallinks.md) is enabled, an image request is sent to Adobe right as a visitor clicks a link to leave your site. Las variables `linkExternalFilters` y [`linkInternalFilters`](linkinternalfilters.md) determinan qué vínculos se consideran internos/externos.

Si esta variable contiene un valor, el seguimiento automático de vínculos de salida se comporta de una manera similar a la lista de elementos permitidos. Si un clic en un vínculo no coincide con ningún valor de `linkExternalFilters`, no se considera un vínculo de salida. La dirección URL completa se examina con esta variable. If [`linkLeaveQueryString`](linkleavequerystring.md) is enabled, the query string is also examined.

>[!TIP] Utilice esta variable solo si sabe exactamente qué dominios desea considerar como vínculos de salida. Muchas organizaciones consideran que el uso de `linkInternalFilters` es suficiente para sus necesidades de seguimiento de vínculos de salida y no utilizan `linkExternalFilters`.

Si utiliza `linkInternalFilters` y `linkExternalFilters` simultáneamente, el vínculo en el que se hizo clic debe coincidir con `linkExternalFilters` **y no** con `linkInternalFilters` para considerarse como un vínculo de salida. Si un vínculo en el que se hizo clic coincide con los criterios de vínculo de salida y de descarga, el tipo de vínculo de descarga tiene prioridad.

## Vínculos de salida: Rastrear en Adobe Experience Platform Launch

The Track field is a comma-separated list of filters (usually domains) under the [!UICONTROL Link Tracking] accordion when configuring the Adobe Analytics extension.

1. Inicie sesión en [launch.adobe.com](https://launch.adobe.com) con sus credenciales de Adobe ID.
2. Haga clic en la propiedad deseada.
3. Go to the [!UICONTROL Extensions] tab, then click the [!UICONTROL Configure] button under Adobe Analytics.
4. Expanda el [!UICONTROL Link Tracking] acordeón, que muestra el [!UICONTROL Outbound Links - Track] campo.

Coloque los filtros que desee considerar siempre externos en este campo. Separe varios dominios con una coma sin espacios.

## s.linkExternalFilters en el editor de código personalizado de AppMeasurement y Launch

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

<!-- The following link is an exit link because it matches the linkExternalFilters whitelist -->
<a href = "example.com">Example link 2</a>
```

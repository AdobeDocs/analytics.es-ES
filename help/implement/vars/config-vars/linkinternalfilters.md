---
title: linkInternalFilters
description: Utilice la variable linkInternalFilters para ayudar al seguimiento automático de vínculos de salida.
translation-type: tm+mt
source-git-commit: 8f7baa770f800ffe800e760f1eca59911d3db348

---


# linkInternalFilters

AppMeasurement ofrece la capacidad de rastrear automáticamente los vínculos que apuntan fuera del sitio. Si `trackExternalLinks` es así, `true`se envía una solicitud de imagen a Adobe justo cuando un visitante hace clic en un vínculo para abandonar el sitio. Las `linkTrackExternalFilters` variables y `linkTrackInternalFilters` determinan qué vínculos se consideran internos/externos.

Si esta variable contiene un valor, el seguimiento automático de vínculos de salida se comporta de manera similar a una lista negra. Si un clic en un vínculo no coincide con ningún `linkInternalFilters` valor, se considera un vínculo de salida. La dirección URL completa se examina con esta variable. Si `linkLeaveQueryString` lo es `true`, también se examina la cadena de consulta.

Si utiliza `linkInternalFilters` y `linkExternalFilters` simultáneamente, el vínculo en el que se hizo clic debe coincidir `linkExternalFilters` y no coincidir **para** `linkInternalFilters` ser considerado un vínculo de salida. Si un vínculo en el que se hizo clic coincide con los criterios de vínculo de salida y de descarga, el tipo de vínculo de descarga tiene prioridad.

> [!NOTE] `linkInternalFilters` y los filtros de URL internos son funciones independientes que cumplen distintos propósitos. La `linkInternalFilters` variable funciona específicamente para el seguimiento de vínculos de salida. Los filtros URL internos son una configuración de administración que ayuda con las dimensiones de fuentes de tráfico como Dominio de referencia. See [Internal URL filters](/help/admin/admin/internal-url-filter-admin.md) in the Admin user guide.

## Vínculos salientes: nunca rastrear en el lanzamiento de la plataforma Adobe Experience Platform

El campo Nunca rastrear es una lista de filtros separados por comas (generalmente dominios) bajo el [!UICONTROL acordeón Seguimiento] de vínculos al configurar la extensión de Adobe Analytics.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. Haga clic en la propiedad que desee.
3. Vaya a la ficha [!UICONTROL Extensiones] y, a continuación, haga clic en el botón [!UICONTROL Configurar] en Adobe Analytics.
4. Expanda el [!UICONTROL acordeón Seguimiento] de vínculos, que muestra el campo Vínculos [!UICONTROL salientes - Nunca rastrear] .

Coloque filtros que no desee que nunca se rastreen como vínculos de salida en este campo. Separe varios dominios con una coma sin espacio.

## s.linkInternalFilters en AppMeasurement e inicie el editor de código personalizado

La `s.linkInternalFilters` variable es una cadena que contiene filtros (como dominios) que considera internos al sitio. Separe varios filtros con una coma sin espacios.

```js
s.linkInternalFilters = "example.com,example.net,example.org";
```

Considere el siguiente ejemplo de implementación como si estuviera en `adobe.com`:

```html
<script>
  s.trackExternalLinks = true;
  s.linkInternalFilters = "adobe.com";
</script>

<!-- The following link is an exit link because it does not match the anything under linkInternalFilters -->
<a href = "example.com">Example link 2</a>
```

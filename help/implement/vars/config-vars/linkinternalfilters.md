---
title: linkInternalFilters
description: Utilice la variable linkInternalFilters para ayudar al seguimiento automático de vínculos de salida.
exl-id: eaa6e64a-ebd5-4e6b-913f-1a6c315579c8
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '340'
ht-degree: 100%

---

# linkInternalFilters

AppMeasurement ofrece la capacidad de rastrear automáticamente los vínculos que redirigen fuera del sitio. Si [`trackExternalLinks`](trackexternallinks.md) está habilitada, se envía una solicitud de imagen a Adobe justo cuando un visitante hace clic en un vínculo para abandonar el sitio. Las variables [`linkExternalFilters`](linkexternalfilters.md) y `linkInternalFilters` determinan qué vínculos se consideran internos/externos.

Si esta variable contiene un valor, el seguimiento automático de vínculos de salida se comporta de una manera similar a una lista de elementos bloqueados. Si un clic en un vínculo no coincide con ningún valor `linkInternalFilters`, se considera un vínculo de salida. La dirección URL completa se examina con esta variable. Si [`linkLeaveQueryString`](linkleavequerystring.md) está habilitada, también se examina la cadena de consulta.

Si utiliza `linkInternalFilters` y `linkExternalFilters` simultáneamente, el vínculo en el que se hizo clic debe coincidir con `linkExternalFilters` **y no** con `linkInternalFilters` para considerarse como un vínculo de salida. Si un vínculo en el que se hizo clic coincide con los criterios de vínculo de salida y de descarga, el tipo de vínculo de descarga tiene prioridad.

Activity Map utiliza esta variable para determinar qué vínculos son internos del sitio. Adobe recomienda configurar esta variable para implementaciones que utilizan Activity Map.

>[!NOTE]
>
>`linkInternalFilters` y los [filtros de URL](/help/admin/admin/internal-url-filter-admin.md) internos son funciones independientes que cumplen distintos propósitos. La variable `linkInternalFilters` funciona específicamente para el seguimiento de vínculos de salida. Los filtros URL internos son una configuración de administración que ayuda con las dimensiones de fuentes de tráfico como Dominio de referencia.

## Vínculos de salida: No rastrear Adobe Experience Platform Launch

El campo No rastrear nunca es una lista de filtros separados por comas (generalmente dominios) bajo el acordeón de [!UICONTROL Seguimiento de vínculos] al configurar la extensión de Adobe Analytics.

1. Inicie sesión en [launch.adobe.com](https://launch.adobe.com) con sus credenciales de Adobe ID.
2. Haga clic en la propiedad deseada.
3. Vaya a la pestaña [!UICONTROL Extensiones] y, a continuación, haga clic en el botón [!UICONTROL Configurar] en Adobe Analytics.
4. Expanda el acordeón de [!UICONTROL Seguimiento de vínculos], que muestra el campo [!UICONTROL Vínculos de salida: No rastrear].

Coloque filtros que no desee que se rastreen como vínculos de salida en este campo. Separe varios dominios con una coma sin espacios.

## s.linkInternalFilters en el editor de código personalizado de AppMeasurement y Launch

La variable `s.linkInternalFilters` es una cadena que contiene filtros (como dominios) que el usuario considera internos al sitio. Separe varios filtros con una coma sin espacios.

```js
s.linkInternalFilters = "example.com,example.net";
```

Considere el siguiente ejemplo de implementación como si estuviera en `adobe.com`:

```html
<script>
  s.trackExternalLinks = true;
  s.linkInternalFilters = "adobe.com";
</script>

<!-- The following link is an exit link because it does not match the anything under linkInternalFilters -->
<a href = "example.org">Example link 2</a>
```

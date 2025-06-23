---
title: ActivityMap.regionIDAttribute
description: Cambie el atributo que Activity Map busca para determinar la región.
feature: Appmeasurement Implementation
role: Admin, Developer
exl-id: 4aec045e-1a86-412f-bd37-777ac49ccc7d
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '227'
ht-degree: 11%

---

# ActivityMap.regionIDAttribute

La variable `ActivityMap.regionIDAttribute` le permite cambiar el atributo que Activity Map busca al determinar la dimensión [Región de Activity Map](/help/components/dimensions/activity-map-region.md). Si el sitio está estructurado de manera que el atributo `id` sea menos útil para la región de Activity Map, puede configurar esta variable para que observe un atributo diferente.

## Atributo ID de región en la extensión Web SDK

Cuando **[!UICONTROL Habilitar la recopilación de datos de clics]** esté habilitada, use el bloque de código de devolución de llamada **[!UICONTROL Propiedades de clic en filtros]**. Dentro de este bloque de código, puede comprobar el valor de `content.clickedElement` y cambiar el valor o abandonar la recopilación de datos de seguimiento de vínculos.

## Atributo de ID de región en la biblioteca JavaScript de Web SDK

Cuando [`clickCollectionEnabled`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/clickcollectionenabled) esté habilitado, usar la devolución de llamada `filterClickDetails` en el objeto `clickCollection`. Dentro de esta llamada de retorno, puede comprobar el valor de `clickedElement` y personalizar la lógica de la región recopilada.

```js
alloy("configure", {
  clickCollectionEnabled: true,
  clickCollection: {
    filterClickDetails: function(content) {
      // If the clicked element was in a table, set the region to the contents of the data-custom attribute
      // If the clicked element was not in a table, or if the data-custom attribute doesn't exist, leave region as-is
      content.region = content.clickedElement.closest('table')?.getAttribute('data-custom') || content.region;
    }
  }
});
```

## Atributo de ID de región con la extensión Adobe Analytics

No hay ningún campo dedicado en la extensión de Adobe Analytics para utilizar esta variable. Utilice el editor de código personalizado siguiendo la sintaxis de AppMeasurement.

## s.ActivityMap.regionIDAttribute mediante AppMeasurement

La variable `s.ActivityMap.regionIDAttribute` es una cadena que representa el atributo para determinar la dimensión [Región de Activity Map](/help/components/dimensions/activity-map-region.md). Esta variable está configurada como `id` de manera predeterminada. Si cambia esta variable, Activity Map ya no busca el atributo `id`, pero sigue buscando otros criterios para determinar la región (como elementos semánticos).

```html
<script>
  var s = s_gi("examplersid");
  s.ActivityMap.regionIDAttribute = "data-custom";
</script>

<!-- Clicking any of these links populates the region dimension with 'left-nav' -->
<div id="676967617A656C6C65" data-custom="left-nav">
  <a href="index.html">Home</a>
  <a href="products.html">View our products</a>
  <a href="contact.html">Contact us</a>
</div>
```

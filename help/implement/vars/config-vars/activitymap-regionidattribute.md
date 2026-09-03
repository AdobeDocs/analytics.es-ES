---
title: ActivityMap.regionIDAttribute
description: Cambie el atributo que Activity Map busca para determinar la región.
feature: Appmeasurement Implementation
role: Admin, Developer
exl-id: 4aec045e-1a86-412f-bd37-777ac49ccc7d
TQID: 'https://experienceleague.adobe.com/DJj1qmoYB0iMxDszdGKYTeczkjv0OvxXAYlg2irpKb0'
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 237
ht-degree: 15%

---

# ActivityMap.regionIDAttribute

La variable `ActivityMap.regionIDAttribute` le permite cambiar el atributo que Activity Map busca al determinar la dimensión [Región de Activity Map](/help/components/dimensions/activity-map-region.md). Si el sitio está estructurado de manera que el atributo `id` sea menos útil para la región de Activity Map, puede configurar esta variable para que observe un atributo diferente.

## Atributo ID de región en la extensión Web SDK

Cuando **[!UICONTROL Habilitar la recopilación de datos de clics]** esté habilitada, use el bloque de código de devolución de llamada **[!UICONTROL Propiedades de clic en filtros]**. Dentro de este bloque de código, puede comprobar el valor de `content.clickedElement` y cambiar el valor o abandonar la recopilación de datos de seguimiento de vínculos.

## Atributo de ID de región en la biblioteca JavaScript de Web SDK

Cuando [`clickCollectionEnabled`](https://experienceleague.adobe.com/es/docs/experience-platform/web-sdk/commands/configure/clickcollectionenabled) esté habilitado, usar la devolución de llamada `filterClickDetails` en el objeto `clickCollection`. Dentro de esta llamada de retorno, puede comprobar el valor de `clickedElement` y personalizar la lógica de la región recopilada.

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

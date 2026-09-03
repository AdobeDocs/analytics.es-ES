---
title: ActivityMap.linkExclusions
description: Filtre los datos de Activity Map por nombre de vínculo.
role: Admin, Developer
feature: Appmeasurement Implementation
exl-id: 9fc95016-362d-4c21-806e-e23adce9b6f7
TQID: 'https://experienceleague.adobe.com/m4ovqFSZBZ88KFm8lnKRI7z5wbbTNZygEj8koL6HC6E'
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 206
ht-degree: 17%

---

# ActivityMap.linkExclusions

La variable `ActivityMap.linkExclusions` le permite filtrar o excluir selectivamente datos de Activity Map basados en el texto de la dimensión [Vínculo de Activity Map](/help/components/dimensions/activity-map-link.md).

## Exclusiones de vínculos en la extensión web de SDK

Cuando **[!UICONTROL Habilitar la recopilación de datos de clics]** esté habilitada, use el bloque de código de devolución de llamada **[!UICONTROL Propiedades de clic en filtros]**. Dentro de este bloque de código, puede comprobar el valor de `content.linkName` y cambiar el valor o abandonar la recopilación de datos de seguimiento de vínculos.

## Exclusiones de vínculos en la biblioteca JavaScript de Web SDK

Cuando [`clickCollectionEnabled`](https://experienceleague.adobe.com/es/docs/experience-platform/web-sdk/commands/configure/clickcollectionenabled) esté habilitado, usar la devolución de llamada `filterClickDetails` en el objeto `clickCollection`. Dentro de esta llamada de retorno, puede comprobar el valor de `linkName` y cambiar el valor o abandonar la recopilación de datos de seguimiento de vínculos.

```js
alloy("configure", {
  clickCollectionEnabled: true,
  clickCollection: {
    filterClickDetails: function(content) {
      // If the link is a clickable telephone number, anonymize it
      if(content.linkUrl.includes("tel:")) {
        content.linkName = content.linkUrl = "Phone number";
      }
      // If the link is an email address, anonymize it
      if(content.linkUrl.includes("mailto:")) {
        content.linkName = content.linkUrl = "Email address";
      }
    }
  }
});
```

## Exclusiones de vínculos que utilizan la extensión Adobe Analytics

No hay ningún campo dedicado en la extensión de Adobe Analytics para utilizar esta variable. Utilice el editor de código personalizado siguiendo la sintaxis de AppMeasurement.

## s.ActivityMap.linkExclusions mediante AppMeasurement

La variable `s.ActivityMap.linkExclusions` es una cadena que contiene valores de frases delimitados por comas que se deben excluir del seguimiento de Activity Map. Si alguna de las frases coincide con el valor recopilado en la dimensión [Vínculo de Activity Map](/help/components/dimensions/activity-map-link.md), se eliminarán todos los datos de Activity Map de la visita. Tenga en cuenta que esta variable busca `linkName`, no `linkUrl`.

```html
<script>
  var s = s_gi("examplersid");
  s.ActivityMap.linkExclusions = "Contact";
</script>

<!-- Clicking this link tracks normally -->
<a href="products.html">View our products</a>

<!-- Activity Map data is not tracked for this link -->
<a href="mailto:user@example.com">Contact this user</a>
```

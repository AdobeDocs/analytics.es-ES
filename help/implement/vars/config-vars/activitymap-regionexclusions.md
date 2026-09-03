---
title: ActivityMap.regionExclusions
description: Filtre los datos de Activity Map por región.
role: Admin, Developer
feature: Appmeasurement Implementation
exl-id: 353282aa-860c-45dc-a6b0-8d9f1fa09f13
TQID: 'https://experienceleague.adobe.com/YWC5bRG0JSZBk-iJbBLAv2HjjbtOC2IYkUPXid-EsTM'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 198
ht-degree: 18%

---

# ActivityMap.regionExclusions

La variable `ActivityMap.regionExclusions` le permite filtrar o excluir selectivamente los datos de Activity Map en función de los elementos de dimensión recopilados en la dimensión [Región de Activity Map](/help/components/dimensions/activity-map-region.md).

## Exclusiones de región en la extensión web de SDK

Cuando **[!UICONTROL Habilitar la recopilación de datos de clics]** esté habilitada, use el bloque de código de devolución de llamada **[!UICONTROL Propiedades de clic en filtros]**. Dentro de este bloque de código, puede comprobar el valor de `content.linkRegion` y cambiar el valor o abandonar la recopilación de datos de seguimiento de vínculos.

## Exclusiones de región en la biblioteca JavaScript de Web SDK

Cuando [`clickCollectionEnabled`](https://experienceleague.adobe.com/es/docs/experience-platform/web-sdk/commands/configure/clickcollectionenabled) esté habilitado, usar la devolución de llamada `filterClickDetails` en el objeto `clickCollection`. Dentro de esta llamada de retorno, puede comprobar el valor de `linkRegion` y cambiar el valor o abandonar la recopilación de datos de seguimiento de vínculos.

```js
alloy("configure", {
  clickCollectionEnabled: true,
  clickCollection: {
    filterClickDetails: function(content) {
      // If the clicked region has personal links in it, don't send click data
      if(content.linkRegion.includes("personal")) {
        return false;
      }
    }
  }
});
```

## Exclusiones de región mediante la extensión de Adobe Analytics

No hay ningún campo dedicado en la extensión de Adobe Analytics para utilizar esta variable. Utilice el editor de código personalizado siguiendo la sintaxis de AppMeasurement.

## s.ActivityMap.regionExclusions mediante AppMeasurement

La variable `s.ActivityMap.regionExclusions` es una cadena que contiene frases delimitadas por comas que se excluirán del seguimiento de Activity Map. Si alguna de las frases coincide con el valor recopilado en la dimensión [Región de Activity Map](/help/components/dimensions/activity-map-region.md), se eliminarán todos los datos de Activity Map de la visita.

```html
<script>
  var s = s_gi("examplersid");
  s.ActivityMap.regionExclusions = "contact";
</script>

<!-- Clicking any of these links tracks normally. -->
<!-- While "contact" is present, it is not tracked in region. The region is "nav" -->
<nav>
  <a href="index.html">Home</a>
  <a href="products.html">View our products</a>
  <a href="contact.html">Contact us</a>
</nav>

<!-- Activity Map data is not tracked for any of these links. -->
<!-- All these links belong to the region "Personal contact information" -->
<div id="personal-contact-information">
 <a href="mailto:user@example.com">Example user</a>
 <a href="mailto:user2@example.com">Example user 2</a>
 <a href="mailto:user3@example.com">Example user 3</a>
</div>
```

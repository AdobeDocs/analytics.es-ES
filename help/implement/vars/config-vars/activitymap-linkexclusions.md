---
title: ActivityMap.linkExclusions
description: Filtre los datos de Activity Map por nombre de vínculo.
role: Admin, Developer
feature: Appmeasurement Implementation
exl-id: 9fc95016-362d-4c21-806e-e23adce9b6f7
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '195'
ht-degree: 12%

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

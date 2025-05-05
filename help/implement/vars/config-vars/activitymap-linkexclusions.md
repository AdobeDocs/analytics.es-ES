---
title: ActivityMap.linkExclusions
description: Filtrar los datos del Activity Map por nombre de vínculo.
role: Admin, Developer
feature: Variables
source-git-commit: 05010d58ba2a3376473097e9d4543ee4415e83e1
workflow-type: tm+mt
source-wordcount: '195'
ht-degree: 11%

---

# ActivityMap.linkExclusions

La variable `ActivityMap.linkExclusions` le permite filtrar o excluir selectivamente datos de Activity Map basados en el texto de la dimensión [Vínculo de Activity Map](/help/components/dimensions/activity-map-link.md).

## Exclusiones de vínculos en la extensión del SDK web

Cuando **[!UICONTROL Habilitar la recopilación de datos de clics]** esté habilitada, use el bloque de código de devolución de llamada **[!UICONTROL Propiedades de clic en filtros]**. Dentro de este bloque de código, puede comprobar el valor de `content.linkName` y cambiar el valor o abandonar la recopilación de datos de seguimiento de vínculos.

## Exclusiones de vínculos en la biblioteca JavaScript del SDK web

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

## s.ActivityMap.linkExclusions mediante el AppMeasurement

La variable `s.ActivityMap.linkExclusions` es una cadena que contiene valores de frases delimitados por comas que se deben excluir del seguimiento de Activity Map. Si alguna de las frases coincide con el valor recopilado en la dimensión [Vínculo de Activity Map](/help/components/dimensions/activity-map-link.md), se quitarán todos los datos del Activity Map de la visita. Tenga en cuenta que esta variable busca `linkName`, no `linkUrl`.

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

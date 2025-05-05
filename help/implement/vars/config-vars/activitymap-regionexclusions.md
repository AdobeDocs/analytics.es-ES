---
title: ActivityMap.regionExclusions
description: Filtrar los datos del Activity Map por región.
role: Admin, Developer
feature: Variables
source-git-commit: 05010d58ba2a3376473097e9d4543ee4415e83e1
workflow-type: tm+mt
source-wordcount: '187'
ht-degree: 12%

---

# ActivityMap.regionExclusions

La variable `ActivityMap.regionExclusions` le permite filtrar o excluir selectivamente los datos del Activity Map en función de los elementos de dimensión recopilados en la dimensión [Región del Activity Map](/help/components/dimensions/activity-map-region.md).

## Exclusiones de región en la extensión del SDK web

Cuando **[!UICONTROL Habilitar la recopilación de datos de clics]** esté habilitada, use el bloque de código de devolución de llamada **[!UICONTROL Propiedades de clic en filtros]**. Dentro de este bloque de código, puede comprobar el valor de `content.linkRegion` y cambiar el valor o abandonar la recopilación de datos de seguimiento de vínculos.

## Exclusiones de región en la biblioteca JavaScript del SDK web

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

## s.ActivityMap.regionExclusions mediante el AppMeasurement

La variable `s.ActivityMap.regionExclusions` es una cadena que contiene frases delimitadas por comas que se excluirán del seguimiento del Activity Map. Si alguna de las frases coincide con el valor recopilado en la dimensión [Región del Activity Map](/help/components/dimensions/activity-map-region.md), se eliminarán todos los datos del Activity Map de la visita.

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

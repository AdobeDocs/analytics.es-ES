---
description: Los vínculos se pueden diferenciar personalizando bien el ID del vínculo con la variable s_objectID, bien la región, o bien el archivo del módulo ActivityMap AppMeasurement.
title: Diferenciación entre varios vínculos que hacen referencia al mismo ID y la misma región de vínculo
uuid: f2da0cda-a33b-4a12-8d99-1f58386d6d30
feature: Activity Map
role: User, Admin
exl-id: 43fe4eb9-08fe-4e20-bc02-3f712c3dec1d
source-git-commit: 25eccb2b9fe3827e62b0ae98d9bebf7a97b239f5
workflow-type: ht
source-wordcount: '363'
ht-degree: 100%

---

# Diferenciación entre varios vínculos que hacen referencia al mismo ID y la misma región de vínculo

Los vínculos se pueden diferenciar personalizando bien el ID del vínculo con la variable s_objectID, bien la región, o bien el archivo del módulo ActivityMap AppMeasurement.

Como ejemplo, supongamos que tenemos varios vínculos “Buy” (comprar) identificados en Activity Map con el mismo ID y la misma región de vínculo:

<table id="table_3020E2C0175D455C84E794CF51BE5A93">
 <thead>
  <tr>
   <th colname="col1" class="entry"> Ejemplo de código </th>
   <th colname="col2" class="entry"> ID del vínculo </th>
   <th colname="col3" class="entry"> Región </th>
  </tr>
 </thead>
  <tbody>
  <tr>
   <td colname="col1">
    <code>&lt;div&nbsp;id="recommendation&nbsp;panel"&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;div&gt;</code><br/>
    <code>&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;href="product1.html"&gt;Buy&lt;/a&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;/div&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;div&gt;</code><br/>
    <code>&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;href="product2.html"&gt;Buy&lt;/a&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;/div&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;div&gt;</code><br/>
    <code>&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;href="product3.html"&gt;Buy&lt;/a&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;/div&gt;</code><br/>
    <code>&lt;/div&gt;</code>
   </td>
   <td colname="col2">
     <br/>
     <br/>
    Buy<br/>
     <br/>
     <br/>
    Buy<br/>
     <br/>
     <br/>
    Buy<br/>
     <br/>
     <br/>
   </td> 
   <td colname="col3">
     <br/>
     <br/>
    recommendation panel<br/>
     <br/>
     <br/>
    recommendation panel<br/>
     <br/>
     <br/>
    recommendation panel<br/>
     <br/>
     <br/>
   </td>
  </tr>
 </tbody>
</table>

¿Cómo se personalizan la página web y las etiquetas para diferenciar los valores de estos vínculos? Hay tres opciones: se puede personalizar el ID del vínculo, la región o el archivo del módulo ActivityMap AppMeasurement.

## Personalizar el ID del vínculo con s_objectID {#section_01B0D463397B4837B2D46F087A6E5937}

Si crea un ID de objeto único, `s_objectID`, para un vínculo o una ubicación de vínculo en una página, se puede mejorar el seguimiento de Activity Map, o bien utilizar Activity Map para informar sobre un tipo o una ubicación de vínculo en lugar de la URL del vínculo. Haga clic [aquí](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/page-variables.html?lang=es) para obtener más información sobre la variable `s_objectID`

>[!IMPORTANT]
>
>Tenga en cuenta que es obligatorio el uso de un punto y coma de cierre (`;`) al usar `s_objectID` en Activity Map.

<table id="table_9439A5F320304E439A19842CF3EBA456">
 <thead>
  <tr>
   <th colname="col02" class="entry"> Ejemplo de código </th>
   <th colname="col2" class="entry"> ID del vínculo </th>
   <th colname="col3" class="entry"> Región </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col02">
    <code>&lt;div&nbsp;id="recommendation&nbsp;panel"&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;div&gt;</code><br/>
    <code>&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;onClick="s_objectID='Product1';"&nbsp;href="product1.html"&gt;Buy&lt;/a&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;/div&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;div&gt; </code><br/>
    <code>&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;onClick="s_objectID='Product2';"&nbsp;href="product2.html"&gt;Buy&lt;/a&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;/div&gt; </code><br/>
    <code>&nbsp;&lt;div&gt; </code><br/>
    <code>&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;onClick="s_objectID='Product3';"&nbsp;href="product3.html"&gt;Buy&lt;/a&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;/div&gt;</code><br/>
    <code>&lt;/div&gt;</code>
   </td> 
   <td colname="col2">
     <br/>
     <br/>
    Product1<br/>
     <br/>
     <br/>
    Product2<br/>
     <br/>
     <br/>
    Product3<br/>
     <br/>
     <br/>
   </td> 
   <td colname="col3">
     <br/>
     <br/>
    recommendation panel<br/>
     <br/>
     <br/>
    recommendation panel<br/>
     <br/>
     <br/>
    recommendation panel<br/>
     <br/>
     <br/>
   </td>
  </tr>
 </tbody>
</table>

## Personalizar la región {#section_6B1EF302573B445DBAF44176D0A12DB9}

Puede personalizar la región asegurándose de que cada vínculo “Buy” tenga definida su propia región. Para hacerlo, agregue un parámetro `"id"` a uno de los elementos primarios de cada etiqueta de anclaje “Buy”.

>[!NOTE]
>
>Se pueden usar otros parámetros como identificadores de región aparte de `"id"`. También puede definir su propio identificador con la variable de JavaScript `"s.ActivityMap.regionIDAttribute"`.

<table id="table_250DB52A869C466B942517BABA1C287B">
 <thead>
  <tr>
   <th colname="col02" class="entry"> Ejemplo de código </th>
   <th colname="col2" class="entry"> ID del vínculo </th>
   <th colname="col3" class="entry"> Región </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col02">
    <code>&lt;div&nbsp;id="recommendation&nbsp;panel"&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;div&nbsp;id="region&nbsp;a"&gt;</code><br/>
    <code>&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;href="product1.html"&gt;Buy&lt;/a&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;/div&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;div&nbsp;id="region&nbsp;b"&gt;</code><br/>
    <code>&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;href="product2.html"&gt;Buy&lt;/a&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;/div&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;div&nbsp;id="region&nbsp;c"&gt;</code><br/>
    <code>&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;href="product3.html"&gt;Buy&lt;/a&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;/div&gt;</code><br/>
    <code>&lt;/div&gt;</code>
   </td> 
   <td colname="col2">
     <br/>
     <br/>
    Buy<br/>
     <br/>
     <br/>
    Buy<br/>
     <br/>
     <br/>
    Buy<br/>
     <br/>
     <br/>
   </td> 
   <td colname="col3">
     <br/>
     <br/>
    region a<br/>
     <br/>
     <br/>
    region b<br/>
     <br/>
     <br/>
    region c<br/>
     <br/>
     <br/>
   </td>
  </tr>
 </tbody>
</table>

## Personalizar el archivo del módulo ActivityMap AppMeasurement {#section_B933BB9F944E4D5389002908A5A881F8}

>[!CAUTION]
>
>No se olvide de probar el código modificado para asegurarse de que funciona correctamente. Adobe no se responsabiliza por el comportamiento del código modificado.

A continuación, presentamos un par de ejemplos de funciones de vínculo y región **genéricas** que se pueden incluir (modificadas) en el archivo AppMeasurement.js.

```js
s.ActivityMap.link = function(ele, linkName) {
  if (linkName) {
    return linkName;
  }
  if (ele) {
    if (ele.tagName == 'A' && ele.href) {
      return ele.href;
    }
  }
}
```

El `linkName` se pasa durante las llamadas a `s.tl()`.

```js
s.ActivityMap.region = function(ele) {
  var className,
  classNames = {
    'header': 1,
    'navbar': 1,
    'left-content': 1,
    'main-content': 1,
    'footer': 1,
  }; 
  while ((ele && (ele = ele.parentNode))) {
    if ((className=ele.className) && classNames[className]) {
      return className;
    }
  }
  return "BODY";
}
```

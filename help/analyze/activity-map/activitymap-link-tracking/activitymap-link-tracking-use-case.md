---
description: Los vínculos se pueden diferenciar personalizando bien el ID del vínculo con la variable s_objectID, bien la región, o bien el archivo del módulo Activity Map AppMeasurement.
title: Diferenciación entre varios vínculos que hacen referencia al mismo ID y la misma región de vínculo
uuid: f2da0cda-a33b-4a12-8d99-1f58386d6d30
feature: Activity Map
role: Profesional empresarial, administrador
translation-type: tm+mt
source-git-commit: f9d9c7dbaf5fde5bd51c929d927d4cd3f61cb63b
workflow-type: tm+mt
source-wordcount: '369'
ht-degree: 61%

---


# Diferenciación entre varios vínculos que hacen referencia al mismo ID y la misma región de vínculo

Los vínculos se pueden diferenciar personalizando bien el ID del vínculo con la variable s_objectID, bien la región, o bien el archivo del módulo Activity Map AppMeasurement.

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
    panel de recomendaciones<br/>
     <br/>
     <br/>
    panel de recomendaciones<br/>
     <br/>
     <br/>
    panel de recomendaciones<br/>
     <br/>
     <br/>
   </td>
  </tr>
 </tbody>
</table>

¿Cómo se personalizan la página web y las etiquetas para diferenciar los valores de estos vínculos? Hay tres opciones: se puede personalizar el ID del vínculo, la región o el archivo del módulo Activity Map AppMeasurement.

## Personalizar el ID del vínculo con s_objectID {#section_01B0D463397B4837B2D46F087A6E5937}

Al crear un ID de objeto único, `s_objectID`, para un vínculo o una ubicación de vínculo en una página, se puede mejorar el seguimiento del Activity Map o utilizar el Activity Map para informar sobre un tipo o ubicación de vínculo, en lugar de la URL del vínculo. Haga clic [aquí](https://docs.adobe.com/content/help/es-ES/analytics/implementation/vars/page-vars/page-variables.html) para obtener más información sobre la variable `s_objectID`

>[!IMPORTANT]
>
>Tenga en cuenta que se requiere un punto y coma de cierre (`;`) al utilizar `s_objectID` en el Activity Map.
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
    panel de recomendaciones<br/>
     <br/>
     <br/>
    panel de recomendaciones<br/>
     <br/>
     <br/>
    panel de recomendaciones<br/>
     <br/>
     <br/>
   </td>
  </tr>
 </tbody>
</table>

## Personalizar la región  {#section_6B1EF302573B445DBAF44176D0A12DB9}

Puede personalizar la región asegurándose de que cada vínculo &quot;Buy&quot; tenga definida su propia región. Para ello, agregue un parámetro `"id"` a uno de los elementos primarios de cada etiqueta de anclaje &quot;Buy&quot;.

>[!NOTE]
>Se pueden usar otros parámetros como identificadores de región aparte de `"id"`. También puede establecer su propio identificador con la variable `"s.ActivityMap.regionIDAttribute"` de JavaScript.
>
>
><table id="table_250DB52A869C466B942517BABA1C287B">
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
    región a<br/>
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

## Personalizar el archivo del módulo Activity Map AppMeasurement  {#section_B933BB9F944E4D5389002908A5A881F8}

>[!CAUTION]
No se olvide de probar el código modificado para asegurarse de que funciona correctamente. Adobe no se responsabiliza por el comportamiento del código modificado.

A continuación, presentamos un par de ejemplos de funciones de vínculo y región **genéricas** que se pueden incluir (modificadas) en el archivo AppMeasurement.js.

```
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

```
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

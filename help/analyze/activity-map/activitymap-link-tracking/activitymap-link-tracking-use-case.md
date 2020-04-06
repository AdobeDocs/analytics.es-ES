---
description: Los vínculos se pueden diferenciar personalizando bien el ID del vínculo con la variable s_objectID, bien la región, o bien el archivo del módulo Activity Map AppMeasurement.
title: Diferenciación entre varios vínculos que hacen referencia al mismo ID y la misma región de vínculo
topic: Activity map
uuid: f2da0cda-a33b-4a12-8d99-1f58386d6d30
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Diferenciación entre varios vínculos que hacen referencia al mismo ID y la misma región de vínculo

Los vínculos se pueden diferenciar personalizando bien el ID del vínculo con la variable s_objectID, bien la región, o bien el archivo del módulo Activity Map AppMeasurement.

Por ejemplo: supongamos que tiene varios vínculos &quot;Comprar&quot; identificados por el mapa de Actividad en el mismo ID de vínculo y región:

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
    <code>
      &lt;div&nbsp;id="recommendation&nbsp;panel"&gt; 
     &nbsp;&nbsp;&lt;div&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;href="product1.html"&gt;Buy&lt;/a&gt; 
     &nbsp;&nbsp;&nbsp;&lt;/div&gt; 
     &nbsp;&nbsp;&lt;div&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;href="product2.html"&gt;Buy&lt;/a&gt; 
     &nbsp;&nbsp;&nbsp;&lt;/div&gt; 
     &nbsp;&lt;div&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;href="product3.html"&gt;Buy&lt;/a&gt; 
     &nbsp;&nbsp;&nbsp;&lt;/div&gt; 
    </code> </td> 
   <td colname="col2"> <p> </p> <p> </p> <p> </p> <p> </p>Comprar <p> </p> <p> </p> <p>Comprar </p> <p> </p> <p> </p> <p>Comprar </p> </td> 
   <td colname="col3"> <p> </p> <p> </p> <p> </p> <p> </p>panel de recomendaciones <p> </p> <p> </p> <p>panel de recomendaciones </p> <p> </p> <p> </p> <p>panel de recomendaciones </p> </td> 
  </tr> 
 </tbody> 
</table>

¿Cómo puede personalizar la página web y el etiquetado para diferenciar los valores de estos vínculos? Tiene tres opciones: Puede personalizar el ID del vínculo, la región o el archivo del módulo Activity Map de AppMeasurement.

## Personalizar el ID del vínculo con s_objectID {#section_01B0D463397B4837B2D46F087A6E5937}

Al crear una ID de objeto única para un vínculo o una ubicación de vínculo en una página, puede mejorar el seguimiento del mapa de Actividad o utilizar el mapa de Actividad para informar sobre un tipo o ubicación de vínculo, en lugar de la dirección URL del vínculo. Haga clic [aquí](https://marketing.adobe.com/resources/help/es_ES/sc/implement/s_objectID.html) para obtener más información sobre la variable s_objectID.

>[!IMPORTANT]
>
>Tenga en cuenta que es obligatorio el uso de un punto y coma de cierre (;) al usar s_objectID en Activity Map.

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
    <code>
      &lt;div&nbsp;id="recommendation&nbsp;panel"&gt; 
     &nbsp;&nbsp;&lt;div&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;onClick="s_objectID='Product1';"&nbsp;href="product1.html"&gt;Buy&lt;/a&gt; 
     &nbsp;&nbsp;&nbsp;&lt;/div&gt; 
     &nbsp;&nbsp;&lt;div&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;onClick="s_objectID='Product2';"&nbsp;href="product2.html"&gt;Buy&lt;/a&gt; 
     &nbsp;&nbsp;&nbsp;&lt;/div&gt; 
     &nbsp;&lt;div&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;onClick="s_objectID='Product3';"&nbsp;href="product3.html"&gt;Buy&lt;/a&gt; 
     &nbsp;&nbsp;&nbsp;&lt;/div&gt;&nbsp;&nbsp;&nbsp; 
    </code> </td> 
   <td colname="col2"> <p> </p> <p> </p> <p> </p>Product 1 <p> </p> <p> </p> <p>Product 2 </p> <p> </p> <p> </p> <p>Product 3 </p> <p> </p> </td> 
   <td colname="col3"> <p> </p> <p> </p> <p> </p> <p>panel de recomendaciones </p> <p> </p> <p> </p> <p>panel de recomendaciones </p> <p> </p> <p> </p> <p>panel de recomendaciones </p> <p> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Personalizar la región {#section_6B1EF302573B445DBAF44176D0A12DB9}

Puede personalizar la región asegurándose de que cada vínculo de &quot;compra&quot; tenga su propia región definida. Para ello, agregue un parámetro &quot;id&quot; a uno de los elementos principales de cada etiqueta de anclaje &quot;Buy&quot;.

>[!NOTE] Se pueden usar otros parámetros como identificadores de región aparte de “id”. También puede definir su propio identificador con la variable de JavaScript “s.ActivityMap.regionIDAttribute”.

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
    <code>
      &lt;div&nbsp;id="recommendation&nbsp;panel"&gt; 
     &nbsp;&nbsp;&lt;div&nbsp;id="region&nbsp;a"&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;href="product1.html"&gt;Buy&lt;/a&gt; 
     &nbsp;&nbsp;&nbsp;&lt;/div&gt; 
     &nbsp;&nbsp;&lt;div&nbsp;id="region&nbsp;b"&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;href="product2.html"&gt;Buy&lt;/a&gt; 
     &nbsp;&nbsp;&nbsp;&lt;/div&gt; 
     &nbsp;&lt;div&nbsp;id="region&nbsp;c"&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;href="product3.html"&gt;Buy&lt;/a&gt; 
     &nbsp;&nbsp;&nbsp;&lt;/div&gt; 
    </code> </td> 
   <td colname="col2"> <p> </p> <p> </p> <p> </p> <p>Comprar </p> <p> </p> <p> </p> <p>Comprar </p> <p> </p> <p> </p> <p>Comprar </p> </td> 
   <td colname="col3"> <p> </p> <p> </p> <p> </p>región a <p> </p> <p> </p> <p>región b </p> <p> </p> <p> </p> <p>Región c </p> </td> 
  </tr> 
 </tbody> 
</table>

## Personalizar el archivo del módulo Activity Map AppMeasurement {#section_B933BB9F944E4D5389002908A5A881F8}

>[!CAUTION]
>
>No se olvide de probar el código modificado para asegurarse de que funciona correctamente. Adobe no se responsabiliza por el comportamiento del código modificado.

A continuación, presentamos un par de ejemplos de funciones de vínculo y región** genéricas** que se pueden incluir (modificadas) en el archivo AppMeasurement.js.

```
s.ActivityMap.link = function(ele,linkName){ 
if(linkName){ 
return linkName; 
} 
if(ele){ 
if(ele.tagName == 'A' && ele.href){ 
return ele.href; 
} 
} 
} 
```

El linkName se pasa durante las llamadas a s.tl.

```
s.ActivityMap.region = function(ele){ 
var className, 
classNames = { 
'header': 1, 
'navbar': 1, 
'left-content': 1, 
'main-content': 1, 
'footer': 1, 
}; 
  while( (ele && (ele = ele.parentNode))){ 
if( (className=ele.className) && classNames[className]){ 
return className; 
} 
} 
return "BODY"; 
} 
```


---
description: Los vínculos se pueden diferenciar personalizando bien el ID del vínculo con la variable s_objectID, bien la región, o bien el archivo del módulo Activity Map AppMeasurement.
seo-description: Los vínculos se pueden diferenciar personalizando bien el ID del vínculo con la variable s_objectID, bien la región, o bien el archivo del módulo Activity Map AppMeasurement.
seo-title: Diferenciar vínculos que hacen referencia al mismo ID y región de vínculo
solution: Analytics
title: Diferenciar vínculos que hacen referencia al mismo ID y región de vínculo
topic: Activity Map
uuid: f 2 da 0 cda-a 33 b -4 a 12-8 d 99-1 f 58386 d 6 d 30
translation-type: tm+mt
source-git-commit: 4f313ae50c4d5a0f3bfec493c2d554bc8614aeef

---


# Diferenciar vínculos que hacen referencia al mismo ID y región de vínculo

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
    <code>&lt; div id = "panel de recomendaciones" &gt; 
 &lt; div &gt; 
 &lt; a href = "product1.html" &gt; Comprar &lt;/a &gt; 
 &lt;/div &gt; 
 &lt; div &gt; 
 &lt; a href = "product2.html" &gt; Comprar &lt;/a &gt; 
 &lt;/div &gt; 
 &lt; div &gt; 
 &lt; a href = "product3.html" &gt; Comprar &lt;/a &gt; 
 &lt;/div &gt; </code>
  </td> 
   <td colname="col2"> <p> </p> <p> </p> <p> </p> <p> </p>Buy <p> </p> <p> </p> <p>Buy </p> <p> </p> <p> </p> <p>Buy </p> </td> 
   <td colname="col3"> <p> </p> <p> </p> <p> </p> <p> </p>Panel de recomendaciones <p> </p> <p> </p> <p>Panel de recomendaciones </p> <p> </p> <p> </p> <p>Panel de recomendaciones </p> </td> 
  </tr> 
 </tbody> 
</table>

¿Cómo se personalizan la página web y las etiquetas para diferenciar los valores de estos vínculos? Hay tres opciones: se puede personalizar el ID del vínculo, la región o el archivo del módulo Activity Map AppMeasurement.

## Personalizar el ID del vínculo con s_objectID {#section_01B0D463397B4837B2D46F087A6E5937}

Si crea un ID de objeto único para un vínculo o una ubicación de vínculo en una página, se puede mejorar el seguimiento de Activity Map, o bien utilizar Activity Map para informar sobre un tipo o una ubicación de vínculo en lugar de la URL del vínculo. Haga clic [aquí](https://marketing.adobe.com/resources/help/en_US/sc/implement/s_objectID.html) para obtener más información sobre la variable s_objectID.

>[!IMPORTANT]
>
>Tenga en cuenta que se requiere un punto y coma (;) final al usar s_ objectid en Activity Map.

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
    <code>&lt; div id = "panel de recomendaciones" &gt; 
 &lt; div &gt; 
 &lt; a onclick = "s_ objectid =' Product 1 '; " href = "product1.html" &gt; Comprar &lt;/a &gt; 
 &lt;/div &gt; 
 &lt; div &gt; 
 &lt; a onclick = "s_ objectid =' Product 2 '; " href = "product2.html" &gt; Comprar &lt;/a &gt; 
 &lt;/div &gt; 
 &lt; div &gt; 
 &lt; a onclick = "s_ objectid =' Product 3 '; " href = "product3.html" &gt; Comprar &lt;/a &gt; 
 &lt;/div &gt; </code>
  </td> 
   <td colname="col2"> <p> </p> <p> </p> <p> </p>Product1 <p> </p> <p> </p> <p>Product2 </p> <p> </p> <p> </p> <p>Product3 </p> <p> </p> </td> 
   <td colname="col3"> <p> </p> <p> </p> <p> </p> <p>Panel de recomendaciones </p> <p> </p> <p> </p> <p>Panel de recomendaciones </p> <p> </p> <p> </p> <p>Panel de recomendaciones </p> <p> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Personalizar la región {#section_6B1EF302573B445DBAF44176D0A12DB9}

Puede personalizar la región asegurándose de que cada vínculo “buy” tenga definida su propia región. Para hacerlo, agregue un parámetro “id” a uno de los elementos primarios de cada etiqueta de anclaje “Buy”.

>[!NOTE]
>
>No se limita exclusivamente al parámetro "id" como identificador de región. También puede establecer su propio identificador utilizando la variable JavaScript "s. activitymap. regionidattribute".

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
    <code>&lt; div id = "panel de recomendaciones" &gt; 
 &lt; div id = "region a" &gt; 
 &lt; a href = "product1.html" &gt; Comprar &lt;/a &gt; 
 &lt;/div &gt; 
 &lt; div id = "region b" &gt; 
 &lt; a href = "product2.html" &gt; Comprar &lt;/a &gt; 
 &lt;/div &gt; 
 &lt; div id = "region c" &gt; 
 &lt; a href = "product3.html" &gt; Comprar &lt;/a &gt; 
 &lt;/div &gt; </code>
  </td> 
   <td colname="col2"> <p> </p> <p> </p> <p> </p> <p>Buy </p> <p> </p> <p> </p> <p>Buy </p> <p> </p> <p> </p> <p>Buy </p> </td> 
   <td colname="col3"> <p> </p> <p> </p> <p> </p>Región a <p> </p> <p> </p> <p>Región b </p> <p> </p> <p> </p> <p>Región c </p> </td> 
  </tr> 
 </tbody> 
</table>

## Personalizar el archivo del módulo Activity Map AppMeasurement {#section_B933BB9F944E4D5389002908A5A881F8}

>[!CAUTION]
>
>Asegúrese de probar el código modificado para asegurarse de que funciona correctamente. Adobe no se responsabiliza por el comportamiento del código modificado.

A continuación, presentamos un par de ejemplos de funciones de vínculo/región genéricas** que puede incluir (en forma modificada) en su archivo appmeasurement. js.

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


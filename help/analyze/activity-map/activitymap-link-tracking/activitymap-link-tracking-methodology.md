---
description: Esta sección está dirigida a los administradores de Adobe Analytics. Explora los nuevos parámetros de seguimiento de vínculos. Explica cómo garantizan la exclusividad y coherencia de los vínculos en distintos exploradores y dispositivos, y de qué modo facilitar el cambio de posición de los vínculos en una página.
seo-description: Esta sección está dirigida a los administradores de Adobe Analytics. Explora los nuevos parámetros de seguimiento de vínculos. Explica cómo garantizan la exclusividad y coherencia de los vínculos en distintos exploradores y dispositivos, y de qué modo facilitar el cambio de posición de los vínculos en una página.
seo-title: Metodología de seguimiento de vínculos
solution: Analytics
title: Metodología de seguimiento de vínculos
topic: Activity Map
uuid: 67864 bf 9-33 cd -46 fa -89 a 8-4 d 83 d 3 b 81152
translation-type: tm+mt
source-git-commit: 4f313ae50c4d5a0f3bfec493c2d554bc8614aeef

---


# Metodología de seguimiento de vínculos

Esta sección está dirigida a los administradores de Adobe Analytics. Explora los nuevos parámetros de seguimiento de vínculos. Explica cómo garantizan la exclusividad y coherencia de los vínculos en distintos exploradores y dispositivos, y de qué modo facilitar el cambio de posición de los vínculos en una página.

>[!IMPORTANT]
>
>Any link where the text (not the href) may contain PII (Personally Identifiable Information) should be implemented explicitly using [s_objectID](https://marketing.adobe.com/resources/help/en_US/sc/implement/s_objectID.html) or by excluding ActivityMap link collection with [s.ActivityMap.linkExclusions or s.ActivityMap.regionExclusions](../../../analyze/activity-map/activitymap-link-tracking/activitymap-link-tracking-methodology.md#section_634197EACD404AC086DF9A03B813C8C3). Para obtener más información sobre cómo Activity Map recopila datos PII, acceda [aquí](../../../analyze/activity-map/lnk-tracking-overview.md#section_A9F016E64F33446F8916855D8C69A7C6).

Activity Map basa el seguimiento de vínculos en estos dos ID:

* ID principal: se trata del parámetro reconocible del vínculo.
* Región del vínculo: es un parámetro secundario que permite a los usuarios indicar una cadena que representa el área global del vínculo en la página o región. Este parámetro se puede generar automáticamente si el usuario no lo proporciona.

## ID principal {#section_E8705CC1BDBC47FB8A4FE02293BACFE6}

Si el HTML tiene un s_objectid, el ID principal predeterminado pasará a ser s_objectid. Si no, se usarán los parámetros siguientes como ID principal (en este orden de prioridad):

* Innertext (texto interior)
* Alttext (texto alternativo)
* Title (título)
* Src (origen)
* Action (acción)

## Utilización de Innertext y de Acción de vínculo (URL) {#section_70C3573E22274522A8CC035BF18EC468}

Acción de vínculo es la acción que efectúa la página web cuando se hace clic en el vínculo. Normalmente es la URL que se visita tras hacer clic en el vínculo. Al usar Acción de vínculo, pueden surgir los problemas siguientes:

* Tener dos o más vínculos distintos con el mismo ID
* Legibilidad del vínculo
* Un vínculo con varias acciones (según el dispositivo donde se vea el vínculo)

Por eso, usamos Innertext, que aporta las ventajas siguientes respecto a Acción de vínculo (URL):

* Es una buena presentación de la identidad del vínculo. La duplicación de ID principal se reduce significativamente, ya que no es habitual que haya varios vínculos con el mismo texto.
* Garantiza la coherencia de los ID principales en los distintos dispositivos y tipos de exploradores.
* No se ve afectado por el cambio de posición de un vínculo en la página.
* Mejora la legibilidad, de modo que los usuarios pueden empezar a analizar los informes de seguimiento fuera de Activity Map.

## Link region {#section_75BF9B9E3CE94B59ACC3D9AF63E04535}

Este nuevo atributo permite a los usuarios especificar una cadena que representa la región de la página donde se encuentra el vínculo.

Por ejemplo, para el vínculo “Contacto” que se encuentra en la sección de menús de la página web, el usuario puede querer enviar el parámetro de región “Menú”. De igual modo, para un vínculo “Contacto” que aparece en el pie de la página web, el parámetro de región se puede establecer en “pie de página”.

El valor de la región del vínculo no se define en el propio vínculo, sino en un elemento HTML superior del árbol DOM HTML que engloba esa región.
La utilización de la región del vínculo ofrece las siguientes ventajas:

* Ayuda a distinguir los vínculos que tienen el mismo ID principal.
* La tendencia de una región se ve menos afectada por el aspecto dinámico de la página web.
* Los usuarios pueden ver los vínculos de mayor rendimiento que hay en una región. Si tenemos Región como anclaje, podemos mostrar superposiciones de vínculos que no estén visibles en ese momento en la página (Ajax, targeting).
* Una región puede reemplazar páginas, ya que una región determinada se puede usar en muchas páginas web. Ayuda a responder a preguntas como: “¿La región 'Oferta de productos' ofrece mejores resultados en la página de aterrizaje de mujeres o de hombres?
* La dimensión de región es importante para analizar páginas web muy dinámicas. Esto se debe a que elimina el ruido provocado por los cambios continuos en los vínculos: la región “Últimas noticias” de la página de aterrizaje de la CNN puede tener muchos vínculos que cambian. Pero la región siempre estará ahí. Por eso puede ser interesante definir tendencias en el nivel de región a lo largo de varios días.

**Seguimiento de regiones personalizado**

Puede personalizar el parámetro de región para un vínculo (el predeterminado es el ID del vínculo): una etiqueta definida en “ID” usará todos los elementos HTML con un parámetro “id” como región. Por este motivo, al definir la etiqueta Región en “id”, lo más probable es que se devuelvan muchas regiones diferentes (tantas como “ID” distintos haya en la página). Asimismo, si quiere una implementación más personalizada, puede establecer la etiqueta de región en otro valor más específico, como “region_id”.

A continuación, puede ver un fragmento de HTML de muestra donde se usa el atributo de ID de región predeterminado: “id”.

```
<div id="content"> 
  <div id="breaking_news"> 
      <a href="breaking-news.html">...</a> 
   </div> 
 <div id="todays_top_headlines"> 
      <a href="breaking-news.html">...</a> 
   </div> 
```

Si lo desea, puede etiquetar elementos con un identificador de cadena al azar, en este caso “lpos”, y luego agregar atributos con el nombre “lpos”.

```
s.ActivityMap.regionIDAttribute="lpos"; 
   
<div id="nav" lpos="navbar"> 
  <ul> 
     <li> Menu Category A 
    <ul> 
      <li><a href="">Menu Item A 1</a> 
      <li><a href="">Menu Item A 2</a> 
     </ul> 
    </li> 
     <li> Menu Category B 
     <ul> 
      <li><a href="">Menu Item B 1</a>  
      <li><a href="">Menu Item B 2</a> 
  
   </ul> 
</ul> 
</div> 
  
<div id="content" > 
  <div id="breaking_news" lpos="breaking_news> 
      <a href="breaking-news.html">...</a> 
   </div> 
 <div id="todays_top_headlines"> 
      <a href="breaking-news.html">...</a> 
   </div> 
</div>
```

## Configuration variables {#section_634197EACD404AC086DF9A03B813C8C3}

Estas variables se indican únicamente como referencia. Activity Map viene configurado de fábrica, pero se puede personalizar la implementación usando estas variables.

<table id="table_7BC8DC3F35CF49288D94BA707F06B283"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Nombre de variable </th> 
   <th colname="col2" class="entry"> Ejemplo </th> 
   <th colname="col3" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> s. activitymap. regionidattribute </td> 
   <td colname="col2"> El parámetro predeterminado es “id”. Puede establecerla en otro parámetro. </td> 
   <td colname="col3"> Cadena que identifica el atributo de etiqueta que se usará como ID de región de algún elemento antecesor (parent, parent.parent...) de s.linkObject, es decir, <b>el elemento donde se hizo clic</b>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> s. activitymap. link </td> 
   <td colname="col2"> 
    <code>// only ever use "title" attributes from A tag function function (clickedelement) {var linkid; if (clickedelement &amp; &amp; clickedelement. tagname. touppercase () = = =' A ') {linkid = clickedelement. getattribute (' title '); } return linkid; } </code>
  </td> 
   <td colname="col3"> Función que recibe el elemento HTML donde se hizo clic y que devuelve un valor de cadena que representa <b>el vínculo en el que se hizo clic</b>. <p>Si el valor devuelto es falso (nulo, indefinido, cadena vacía, 0), no se realiza el seguimiento de ningún vínculo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> s. activitymap. region </td> 
   <td colname="col2"> 
    <code>// only ever a minúscula version of tag name concatenated with first classname as the region function (clickedelement) {var regionid, classname; while (clickedelement &amp; &amp; (clickedelement = clickedelement. parentnode)) {regionid = clickedelement. tagname; if (regionid) {return regionid. tolowercase (); }}}} </code>
  </td> 
   <td colname="col3"> Función que recibe el elemento HTML donde se hizo clic y que devuelve un valor de cadena que representa <b>la región donde estaba el vínculo cuando se hizo clic en él</b>. <p>Si el valor devuelto es falso (nulo, indefinido, cadena vacía, 0), no se realiza el seguimiento de ningún vínculo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> s.ActivityMap.linkExclusions </td> 
   <td colname="col2"> 
    <code>// Excluir vínculos etiquetados con una clase de linkexclucss especial &lt; style &gt;. linkived {display: block; height: 1 px; left: -9999 px; desbordamiento: hidden; position: absolute; width: 1 px; } &lt;/style &gt; &lt; a href = "next-page.html" &gt; Vínculo es rastreado porque el vínculo no tiene texto oculto que coincida con el filtro.&lt;/a &gt; &lt; a href = "next-page.html" &gt; Vínculo no rastreado porque s. activitymap. linkexclusions está establecido y este vínculo tiene texto oculto que coincide con el filtro. &lt; span class = "linkexclude" &gt; exclude-link 1 &lt;/span &gt; &lt;/a &gt; &lt; a href = "next-page.html" &gt; Vínculo no rastreado porque s. activitymap. linkexclusions está establecido y este vínculo tiene texto oculto que coincide con el filtro.  &lt;span class="linkExcluded"&gt;exclude-link2&lt;/span&gt; &lt;/a&gt; &lt;script&gt;   var s = s_gi('samplersid');   s.ActivityMap.linkExclusions = 'exclude-link1,exclude-link2'; &lt;/script&gt; 
    </code> </td> 
   <td colname="col3"> <p>Cadena que recibe una lista de cadenas separadas por comas para buscar texto en un vínculo. Si se encuentra, se excluye el vínculo del seguimiento realizado por Activity Map. Si no se configura, no se intenta detener el seguimiento del vínculo realizado por Activity Map. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> s.ActivityMap.regionExclusions </td> 
   <td colname="col2"> 
    <code>// Excluir regiones en la página de sus vínculos siendo rastreables por activitymap &lt; div id = "links-included" &gt; &lt; a href = "next-page.html" &gt; El vínculo se rastrea porque s. activitymap. regionexclusions está establecido pero no coincide con el filtro.&lt;/a &gt; &lt;/div &gt; &lt; div id = "links-exclude" &gt; &lt; a href = "next-page.html" &gt; Vínculo no rastreado porque s. activitymap. regionexclusions está establecido y este vínculo coincide con el filtro.&lt;/a&gt; &lt;/div&gt; &lt;script&gt;   var s = s_gi('samplersid');   s.ActivityMap.regionExclusions = 'links-excluded'; &lt;/script&gt;
    </code> </td> 
   <td colname="col3"> <p>Cadena que recibe una lista de cadenas separadas por comas para buscar texto en una región. Si se encuentra, se excluye el vínculo del seguimiento realizado por Activity Map. Si no se configura, no se intenta detener el seguimiento del vínculo realizado por Activity Map. </p> </td> 
  </tr> 
 </tbody> 
</table>

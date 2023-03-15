---
description: Esta sección está dirigida a los administradores de Adobe Analytics. Explora los nuevos parámetros de seguimiento de vínculos. Explica cómo garantizan la exclusividad y coherencia de los vínculos en distintos exploradores y dispositivos, y de qué modo facilitar el cambio de posición de los vínculos en una página.
title: Método de seguimiento de vínculos
uuid: 67864bf9-33cd-46fa-89a8-4d83d3b81152
feature: Activity Map
role: User, Admin
exl-id: 6aef3a0f-d0dd-4c84-ad44-07b286edbe18
source-git-commit: a6b38c6e7a34c876524ebe15514ac205898549d0
workflow-type: tm+mt
source-wordcount: '992'
ht-degree: 100%

---

# Método de seguimiento de vínculos

Esta sección está dirigida a los administradores de Adobe Analytics. Explora los nuevos parámetros de seguimiento de vínculos. Explica cómo garantizan la exclusividad y coherencia de los vínculos en distintos exploradores y dispositivos, y de qué modo facilitar el cambio de posición de los vínculos en una página.

>[!IMPORTANT]
>
>Cualquier vínculo en el que el texto (no el href) pueda contener información de identificación personal (PII) debe implementarse de forma explícita mediante [s_objectID](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/page-variables.html?lang=es) o excluyendo la recopilación de vínculos de Activity Map con [s.ActivityMap.linkExclusions o s.ActivityMap.regionExclusions](/help/analyze/activity-map/activitymap-link-tracking/activitymap-link-tracking-methodology.md#configuration-vars). Para obtener más información sobre cómo Activity Map recopila datos PII, acceda [aquí](/help/analyze/activity-map/lnk-tracking-overview.md).

Activity Map basa el seguimiento de vínculos en estos dos ID:

* ID principal: se trata del parámetro reconocible del vínculo.
* Región del vínculo: es un parámetro secundario que permite a los usuarios indicar una cadena que representa el área global del vínculo en la página o región. Este parámetro se puede generar automáticamente si el usuario no lo proporciona.

## ID principal {#section_E8705CC1BDBC47FB8A4FE02293BACFE6}

Si el HTML tiene un s_objectid, el ID principal predeterminado pasará a ser s_objectid. Si no, se usarán los parámetros siguientes como ID principal (en este orden de prioridad):

* Innertext (texto interior)
* Alttext (texto alternativo)
* Título
* Src (origen)
* Acción

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

## Región del vínculo {#section_75BF9B9E3CE94B59ACC3D9AF63E04535}

Este nuevo atributo permite a los usuarios especificar una cadena que representa la región de la página donde se encuentra el vínculo.

Por ejemplo, para el vínculo “Contacto” que se encuentra en la sección de menús de la página web, el usuario puede querer enviar el parámetro de región “Menú”. De igual modo, para un vínculo “Contacto” que aparece en el pie de la página web, el parámetro de región se puede establecer en “pie de página”.

El valor de la región del vínculo no se define en el propio vínculo, sino en un elemento HTML superior del árbol DOM HTML que engloba esa región.
La utilización de la región del vínculo ofrece las siguientes ventajas:

* Ayuda a distinguir los vínculos que tienen el mismo ID principal.
* La tendencia de una región se ve menos afectada por el aspecto dinámico de la página web.
* Los usuarios pueden ver los vínculos de mayor rendimiento que hay en una región. Si tenemos Región como anclaje, podemos mostrar superposiciones de vínculos que no estén visibles en ese momento en la página (Ajax, targeting).
* Una región puede reemplazar páginas, ya que una región determinada se puede usar en muchas páginas web. Ayuda a responder a preguntas como: ¿La región “Oferta de productos” ofrece mejores resultados en la página de aterrizaje de mujeres o de hombres?
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

Si lo desea, puede etiquetar elementos con un identificador de cadena al azar, en este caso “lpos”, y luego añadir atributos con el nombre “lpos”.

```
<script language="JavaScript" type="text/javascript">
s.ActivityMap.regionIDAttribute = "lpos";
</script>
<div id="nav" lpos="navbar">
  <ul>
    <li>Menu Category A
      <ul>
        <li><a href="">Menu Item A 1</a>
        <li><a href="">Menu Item A 2</a>
      </ul>
    </li>
    <li>Menu Category B
      <ul>
        <li><a href="">Menu Item B 1</a>
        <li><a href="">Menu Item B 2</a>
      </ul>
    </li>
  </ul>
</div> 
  
<div id="content">
  <div id="breaking_news" lpos="breaking_news>
    <a href="breaking-news.html">...</a>
  </div>
  <div id="todays_top_headlines">
    <a href="breaking-news.html">...</a>
  </div>
```

## Variables de configuración {#configuration-vars}

Estas variables se indican únicamente como referencia. Activity Map viene configurado de fábrica, pero se puede personalizar la implementación usando estas variables.

### `s.ActivityMap.regionIDAttribute`

Cadena que identifica el atributo de etiqueta que se usará como ID de región de algún elemento antecesor (parent, parent.parent...) de `s.linkObject`, es decir, **el elemento donde se hizo clic**.

**Ejemplo**

El parámetro predeterminado es “id”. Puede establecerla en otro parámetro.

### `s.ActivityMap.link`

Función que recibe el `HTMLElement` en el que se hizo clic y que devuelve un valor de cadena que representa el vínculo en el que se hizo clic. Si el valor devuelto es falso (nulo, indefinido, cadena vacía, 0), no se realiza el seguimiento del vínculo.

**Ejemplo**

```
// only ever use "title" attributes from A tags
function(clickedElement) {
  var linkId;
  if (clickedElement && clickedElement.tagName.toUpperCase() === 'A') {
    linkId = clickedElement.getAttribute('title');
  }
  return linkId;
}
```

### `s.ActivityMap.region`

Función que recibe el elemento HTML donde se hizo clic y que devuelve un valor de cadena que representa **la región donde estaba el vínculo cuando se hizo clic en él.** Si el valor devuelto es falso (nulo, indefinido, cadena vacía, 0), no se realiza el seguimiento del vínculo.

**Ejemplo**

```
// only ever use lowercase version of tag name concatenated with first className as the region
function(clickedElement) {
  var regionId, className;
  while (clickedElement && (clickedElement = clickedElement.parentNode)) {
    regionId = clickedElement.tagName;
    if (regionId) {
      return regionId.toLowerCase();
    }
  }
}
```

### `s.ActivityMap.linkExclusions`

Cadena que recibe una lista de cadenas separadas por comas para buscar texto en un vínculo. Si se encuentra, se excluye el vínculo del seguimiento realizado por Activity Map. Si no se configura, no se intenta detener el seguimiento del vínculo realizado por Activity Map.

**Ejemplo**

```
// Exclude links tagged with a special linkExcluded CSS class
<style>
.linkExcluded {
  display: block;
  height: 1px;
  left: -9999px;
  overflow: hidden;
  position: absolute;
  width: 1px;
}
</style>
<a href="next-page.html">
  Link is tracked because link does not have hidden text matching the filter. 
</a>
<a href="next-page.html">
  Link not tracked because s.ActivityMap.linkExclusions is set and this link has hidden text matching the filter.
  <span class="linkExcluded">exclude-link1</span>
</a>
<a href="next-page.html">
  Link not tracked because s.ActivityMap.linkExclusions is set and this link has hidden text matching the filter.
  <span class="linkExcluded">exclude-link2</span>
</a>
<script>
  var s = s_gi('samplersid');
  s.ActivityMap.linkExclusions = 'exclude-link1,exclude-link2';
</script>
```

### `s.ActivityMap.regionExclusions`

Cadena que recibe una lista de cadenas separadas por comas para buscar texto en una región. Si se encuentra, se excluye el vínculo del seguimiento realizado por Activity Map. Si no se configura, no se intenta detener el seguimiento del vínculo realizado por Activity Map.

**Ejemplo**

```
// Exclude regions on the page from its links being trackable by ActivityMap
<div id="links-included">
  <a href="next-page.html">
    Link is tracked because s.ActivityMap.regionExclusions is set but does not match the filter.
  </a>
</div>
<div id="links-excluded"> 
  <a href="next-page.html">
    Link not tracked because s.ActivityMap.regionExclusions is set and this link matches the filter.
  </a>
</div>
<script>
  var s = s_gi('samplersid');
  s.ActivityMap.regionExclusions = 'links-excluded';
</script>
```

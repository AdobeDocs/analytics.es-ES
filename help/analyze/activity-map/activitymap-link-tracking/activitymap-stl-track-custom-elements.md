---
description: Puede utilizar el método s.tl() para rastrear elementos personalizados y configurar la representación de superposiciones para el contenido dinámico.
title: Utilizar el método s.tl()
topic: Activity map
uuid: 59e062af-6a1c-46ff-9c3b-6cf7a0453711
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# Utilizar el `tl()` método

You can use the `tl()` method to track custom elements and to configure overlay rendering for dynamic content.

## Seguimiento de elementos personalizados {#section_5D6688DFFFC241718249A9A0C632E465}

Using the [`tl()` method](/help/implement/vars/functions/tl-method.md) as part of the Activity Map AppMeasurement module lets you track any object that is clicked on, even objects that are not anchor tags or image elements. Con s.tl, se puede hacer un seguimiento de cualquier elemento personalizado que no resulte en una carga de página.

In the `tl()` method, the `linkName` parameter that is currently used to identify the exit links, custom links, etc. ahora se utiliza también para identificar el ID del vínculo que corresponde a la variable de Activity Map.

```js
s.tl(this,linkType,linkName,variableOverrides)
```

In other words, if you use `s.tl()` to track your custom elements, the link ID is pulled from the value passed as the third parameter (linkName) in the `s.tl()` method. No se extrae del algoritmo de seguimiento estándar de vínculos que se utiliza para el [seguimiento predeterminado](/help/analyze/activity-map/activitymap-link-tracking/activitymap-link-tracking-methodology.md) en Activity Map.

## Representación de superposiciones en el contenido dinámico {#section_FD24B61A732149C7B58BA957DD84A5E7}

Cuando se llama a la función s.tl() directamente desde el evento en el que se hace clic del elemento HTML, Activity Map puede mostrar una superposición para ese elemento al cargar la página web. Ejemplo:

```html
<div onclick="s.tl(this,'o','Example custom link')">Example link text</a>
```

Whenever any web page content is added to the page after the initial page load, the `tl()` method is called indirectly and we cannot display overlays for that new content unless it is expressly activated/clicked. Luego se desencadena un proceso de recopilación de nuevos vínculos desde Activity Map.

When the `tl()` method is not called directly from the HTML element&#39;s on-click event, Activity Map can only display overlay once that element has been clicked by the user. Here is an example where the `tl()` method is called indirectly:

```html
<div onclick="someFn(event)"></div>
<script>function someFn (event)
{
  s.tl(event.srcElement,'o','Example custom link');
}
</script>
```

La mejor manera de que Activity Map superponga vínculos de contenido dinámico es tener configurada una función ActivityMap.link personalizada para llamar a la misma función cuyo valor devuelto se pase a `s.tl`. Por ejemplo:

```js
var originalLinkFunction = s.ActivityMap.link;
s.ActivityMap.link = function(element,linkName) {
    return linkName ||      // if this is a s.tl call, just return string passed
        makeLinkName(element) || // this is ActivityMap reporting time
        originalLinkFunction(element,linkName); // our custom function didn't return anything, so just return the default ActivityMap Link
};
```

```html
<button type="button" onclick="s.tl(this,'o',makeLinkName(this)">Add To Cart</button>
```

Aquí, hemos sobrescrito la función ActivityMap.link para que realice una de estas tres acciones cuando se llame:

1. Si se pasa linkName, s.tl() la llama para que se devuelva únicamente el contenido que s.tl ha pasado como linkName.
2. Activity Map la llama en el momento de generar los informes para que linkName nunca se pase y se llame a makeLinkName() con el elemento del vínculo. Este es el paso clave: la llamada de “makeLinkName(element)” debe ser la misma en el tercer argumento de la llamada de s.tl en la etiqueta `<button>`. Esto significa que, cuando se llama a s.tl, realizamos un seguimiento de la cadena devuelta por makeLinkName. Cuando Activity Map realiza un informe sobre los vínculos de la página, usa la misma llamada para generar un vínculo.
3. La solución definitiva es devolver el valor devuelto original de la función predeterminada de vínculo de Activity Map. Esta referencia solo le será útil en casos predeterminados, ya que en ella solo encontrará ayuda para sobrescribir o escribir código predeterminado para makeLinkName, y no para presentar un valor devuelto de vínculo para todos los vínculos de la página.

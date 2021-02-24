---
title: Uso del método tl() con el Activity Map
description: Puede utilizar el método tl() para realizar el seguimiento de elementos personalizados y configurar la representación de superposiciones para el contenido dinámico.
topic: Activity Map
translation-type: tm+mt
source-git-commit: 65cb0a49ef74156f0b8adf4a11c6fec6394d306f
workflow-type: tm+mt
source-wordcount: '483'
ht-degree: 43%

---


# Usar el método `tl()` con el Activity Map

El método `tl()` se puede usar para hacer un seguimiento de elementos personalizados y configurar la representación de las superposiciones en el contenido dinámico.

## Seguimiento de elementos personalizados

Al usar [`tl()` el método](/help/implement/vars/functions/tl-method.md) en el módulo AppMeasurement de Activity Map se puede realizar un seguimiento de cualquier objeto en el que se haga clic, incluso objetos que no sean etiquetas de anclaje ni elementos de imagen. Mediante `tl()`, puede rastrear cualquier elemento personalizado que no resulte en una carga de página.

En el método `tl()`, el parámetro `linkName` que se usa actualmente para identificar los vínculos de salida, los vínculos personalizados, etc. ahora se utiliza también para identificar el ID del vínculo que corresponde a la variable de Activity Map.

```js
s.tl([Link object],[Link type],[Link name],[Override variable]);
```

En otras palabras, si utiliza `tl()` para rastrear los elementos personalizados, la ID del vínculo se extrae del valor pasado como el tercer parámetro (nombre del vínculo) en el método `tl()`. No se extrae del algoritmo de seguimiento estándar de vínculos que se utiliza para el [seguimiento predeterminado](activitymap-link-tracking-methodology.md) en Activity Map.

## Representación de superposiciones en el contenido dinámico

Cuando se llama al método `tl()` directamente desde el evento en el que se hace clic del elemento HTML, el Activity Map puede mostrar una superposición para ese elemento cuando se carga la página web. Ejemplo:

```html
<a href="javascript:" onclick="s.tl(this,'o','Example custom link');">Example link text</a>
```

Cuando se añade contenido de página web a la página tras su carga inicial, se llama indirectamente el método `tl()` y no se pueden mostrar superposiciones para ese nuevo contenido si no se activa expresamente o se hace clic en él. Luego se desencadena un proceso de recopilación de nuevos vínculos desde Activity Map.

Cuando no se llama directamente a el método `tl()` desde el evento en el que se hace clic del elemento HTML, Activity Map solo puede mostrar la superposición cuando el usuario ha hecho clic en el elemento. A continuación, vemos un ejemplo en el que se llama el método `tl()` de manera indirecta:

```html
<a href="javascript:" onclick="someFn(event);">Example link text</a>
<script>function someFn (event)
{
  s.tl(event.srcElement,'o','Example custom link');
}
</script>
```

La mejor manera para que el Activity Map superponga vínculos de contenido dinámico es tener una función `ActivityMap.link` personalizada configurada para llamar a la misma función cuyo valor devuelto se pasa a `tl()`. Por ejemplo:

```js
var originalLinkFunction = s.ActivityMap.link;
s.ActivityMap.link = function(element,linkName)
{
    // if this is a s.tl call, just return string passed
    return linkName ||      
    // this is ActivityMap reporting time
    makeLinkName(element) ||
    // our custom function didn't return anything, so just return the default ActivityMap Link
    originalLinkFunction(element,linkName);
};
```

```html
<button type="button" onclick="s.tl(this,'o',makeLinkName(this)">Add To Cart</button>
```

Aquí, hemos anulado la función `ActivityMap.link` para hacer una de las tres cosas cuando se llama:

1. Si se pasa `linkName`, `tl()` lo llamó, sólo tiene que devolver lo que `tl()` pasó como `linkName`.
2. Cuando el Activity Map llama en tiempo de sistema de informes, nunca se pasa un `linkName` y, por lo tanto, llama a `makeLinkName()` con el elemento link. Este es el paso crucial: la llamada `makeLinkName(element)` debe ser el mismo que el tercer argumento de la llamada `tl()` en la etiqueta `<button>`. Esto significa que cuando se llama a `tl()`, rastreamos la cadena devuelta por `makeLinkName()`. Cuando el Activity Map informa de los vínculos de la página, utiliza la misma llamada para crear un vínculo.
3. La solución definitiva es devolver el valor devuelto original de la función predeterminada de vínculo de Activity Map. Mantener esta referencia para llamar en el caso predeterminado sólo le ayuda a tener que sobrescribir o escribir código personalizado para `makeLinkName()` y a no tener que obtener un valor de devolución de vínculo para todos los vínculos de la página.

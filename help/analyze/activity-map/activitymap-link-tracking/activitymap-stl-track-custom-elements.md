---
title: Utilice el método tl() con el Activity Map
description: El método tl() se puede usar para hacer un seguimiento de elementos personalizados y configurar la representación de las superposiciones en el contenido dinámico.
feature: Activity Map
role: User, Admin
exl-id: e4e32de7-0e46-413a-abc9-9707e273903d
source-git-commit: 7226b4c77371b486006671d72efa9e0f0d9eb1ea
workflow-type: tm+mt
source-wordcount: '481'
ht-degree: 43%

---

# Utilice el `tl()` método con Activity Map

El método `tl()` se puede usar para hacer un seguimiento de elementos personalizados y configurar la representación de las superposiciones en el contenido dinámico.

## Seguimiento de elementos personalizados

Al usar [`tl()` el método](/help/implement/vars/functions/tl-method.md) en el módulo AppMeasurement de Activity Map se puede realizar un seguimiento de cualquier objeto en el que se haga clic, incluso objetos que no sean etiquetas de anclaje ni elementos de imagen. Uso de `tl()`, puede realizar un seguimiento de cualquier elemento personalizado que no resulte en una carga de página.

En el método `tl()`, el parámetro `linkName` que se usa actualmente para identificar los vínculos de salida, los vínculos personalizados, etc. ahora se utiliza también para identificar el ID del vínculo que corresponde a la variable de Activity Map.

```js
s.tl([Link object],[Link type],[Link name],[Override variable]);
```

En otras palabras, si utiliza `tl()` para realizar un seguimiento de los elementos personalizados, el ID del vínculo se extrae del valor pasado como tercer parámetro (Nombre del vínculo) en `tl()` método. No se extrae del algoritmo de seguimiento estándar de vínculos que se utiliza para el [seguimiento predeterminado](activitymap-link-tracking-methodology.md) en Activity Map.

## Representación de superposiciones en el contenido dinámico

Si la variable `tl()` se llama directamente desde el evento en el que se hace clic del elemento HTML, Activity Map puede mostrar una superposición para ese elemento cuando se carga la página web. Ejemplo:

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

La mejor manera de que el Activity Map superponga vínculos de contenido dinámico es tener un personalizado `ActivityMap.link` función configurada para llamar a la misma función cuyo valor devuelto se pasa a `tl()`. Por ejemplo:

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

Aquí, hemos anulado el `ActivityMap.link` para hacer una de las tres cosas cuando se llama a:

1. If `linkName` se pasa, entonces fue invocado por `tl()`, así que devuelva lo que `tl()` pasado como `linkName`.
2. Cuando el Activity Map la llama en el momento de generar el informe, `linkName` nunca se pasa, así que llame a `makeLinkName()` con el elemento de vínculo. Este es el paso crucial aquí: la `makeLinkName(element)` la llamada debe ser la misma que la `tl()` tercer argumento de la llamada en el `<button>` etiqueta. Esto significa que cuando `tl()` se llama, realizamos un seguimiento de la cadena devuelta por `makeLinkName()`. Cuando el Activity Map informa sobre los vínculos de la página, utiliza la misma llamada para crear un vínculo.
3. La solución definitiva es devolver el valor devuelto original de la función predeterminada de vínculo de Activity Map. Esta referencia solo le será útil en casos predeterminados, ya que en ella solo encontrará ayuda para sobrescribir o escribir código personalizado para `makeLinkName()` y no tener que crear un valor devuelto de vínculo para todos los vínculos de la página.

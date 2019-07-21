---
description: La función s.tl() se puede usar para hacer un seguimiento de elementos personalizados y configurar la representación de las superposiciones en el contenido dinámico.
seo-description: La función s.tl() se puede usar para hacer un seguimiento de elementos personalizados y configurar la representación de las superposiciones en el contenido dinámico.
seo-title: Utilizar la función s. tl ()
solution: Analytics
title: Utilizar la función s. tl ()
topic: Activity Map
uuid: 59 e 062 af -6 a 1 c -46 ff -9 c 3 b -6 cf 7 a 0453711
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Utilizar la función s. tl ()

La función s.tl() se puede usar para hacer un seguimiento de elementos personalizados y configurar la representación de las superposiciones en el contenido dinámico.

## Tracking custom elements {#section_5D6688DFFFC241718249A9A0C632E465}

Al usar la [función s.tl()](https://marketing.adobe.com/resources/help/en_US/sc/implement/function_tl.html) en el módulo AppMeasurement de Activity Map se puede realizar un seguimiento de cualquier objeto en el que se haga clic, incluso objetos que no sean etiquetas de anclaje ni elementos de imagen. Con s.tl, se puede hacer un seguimiento de cualquier elemento personalizado que no resulte en una carga de página.

En la función s.tl, el parámetro linkName que se usa actualmente para identificar los vínculos de salida, los vínculos personalizados, etc., ahora se utiliza también para identificar el ID del vínculo que corresponde a la variable de Activity Map.

```
s.tl(this,linkType, 
<b>linkName</b>,variableOverrides,doneAction)
```

En otras palabras, si se usa s.tl para hacer un seguimiento de los elementos personalizados, el ID del vínculo se extrae del valor pasado como tercer parámetro (linkName) en la función s.tl. No se extrae del algoritmo de seguimiento estándar de vínculos que se utiliza para el [seguimiento predeterminado](/help/analyze/activity-map/activitymap-link-tracking/activitymap-link-tracking-methodology.md) en Activity Map.

## Overlay rendering for dynamic content {#section_FD24B61A732149C7B58BA957DD84A5E7}

Cuando se llama a la función s.tl() directamente desde el evento en el que se hace clic del elemento HTML, Activity Map puede mostrar una superposición para ese elemento al cargar la página web. Ejemplo:

```
<div onclick="s.tl(this,'o','some link name')">Text to click on</a>
```

Cuando se añade contenido de página web a la página tras su carga inicial, se llama indirectamente a la función s.tl y no se pueden mostrar superposiciones para ese nuevo contenido si no se activa expresamente o se hace clic en él. Luego se desencadena un proceso de recopilación de nuevos vínculos desde Activity Map.

Cuando no se llama directamente a la función s.tl() desde el evento en el que se hace clic del elemento HTML, Activity Map solo puede mostrar la superposición cuando el usuario ha hecho clic en el elemento. A continuación, vemos un ejemplo en el que se llama indirectamente a la función s.tl():

```
<div onclick="someFn(event)"></div> 
 <script>function someFn (event) 
 {    
 s.tl(event.srcElement,'o','some link name'); 
 } 
 </script>
```

La mejor manera de que Activity Map superponga vínculos de contenido dinámico es tener configurada una función ActivityMap.link personalizada para llamar a la misma función cuyo valor devuelto se pase a s.tl. Veamos un ejemplo:

```
var originalLinkFunction = s.ActivityMap.link; 
s.ActivityMap.link = function(element,linkName){ 
    return linkName ||      // if this is a s.tl call, just return string passed 
        makeLinkName(element) || // this is ActivityMap reporting time 
        originalLinkFunction(element,linkName); // our custom function didn't return anything, so just return the default ActivityMap Link 
};
```

```
<button type=”button” onclick=”s.tl(this,’o’,makeLinkName(this)”>Add To Cart</button>
```

Aquí, hemos sobrescrito la función ActivityMap.link para que realice una de estas tres acciones cuando se llame:

1. Si se pasa linkName, s.tl() la llama para que se devuelva únicamente el contenido que s.tl ha pasado como linkName.
1. Activity Map la llama en el momento de generar los informes para que linkName nunca se pase y se llame a makeLinkName() con el elemento del vínculo. This is the crucial step here - the “makeLinkName(element)” call should be the same at the s.tl call’s 3rd argument in the `<button>` tag. Esto significa que, cuando se llama a s.tl, realizamos un seguimiento de la cadena devuelta por makeLinkName. Cuando Activity Map realiza un informe sobre los vínculos de la página, usa la misma llamada para generar un vínculo.
1. La solución definitiva es devolver el valor devuelto original de la función predeterminada de vínculo de Activity Map. Esta referencia solo le será útil en casos predeterminados, ya que en ella solo encontrará ayuda para sobrescribir o escribir código predeterminado para makeLinkName, y no para presentar un valor devuelto de vínculo para todos los vínculos de la página.

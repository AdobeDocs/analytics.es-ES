---
title: Implementación con AJAX
description: Obtenga más información sobre cómo implementar Adobe Analytics en un sitio mediante AJAX.
translation-type: ht
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: ht
source-wordcount: '373'
ht-degree: 100%

---


# Implementación con AJAX

AJAX es una práctica para utilizar JavaScript y HTML para borrar y generar contenido sin cargar una nueva página.

Adobe Analytics normalmente depende de la recarga de páginas para restablecer el objeto de seguimiento de Analytics. Cada vez que se desplaza a una dirección URL diferente, se restauran todas las variables de Analytics y se pueden definir de nuevo. Al utilizar AJAX en el sitio, ajuste la implementación en función de la falta de actualizaciones de página para asegurarse de que los datos no persistan incorrectamente entre las visitas.

Una vez que haya implementado medidas para borrar los valores de las variables, la implementación de Adobe Analytics en sitios que usan AJAX es mayormente la misma que otros métodos de implementación.

## Determinación de interacciones y tipos de visitas

Dado que las páginas que utilizan AJAX generalmente no se recargan, hay varias interacciones que un usuario puede realizar en el sitio. Al implementar Adobe Analytics, asegúrese de diferenciar las vistas de página de las llamadas de seguimiento de vínculos. Tenga en cuenta la siguiente pregunta para cada interacción que un usuario pueda realizar en el sitio:

*Cuando un usuario interactúa con mi sitio, ¿cambia lo suficiente el contenido de la página como para calificarse como una página nueva?*

* Si la respuesta es **sí**, considere la posibilidad de utilizar una llamada de seguimiento de vista de página (`s.t()`).
* Si la respuesta es **no**, considere rastrear esa interacción usando una llamada de seguimiento de vínculos (`s.tl()`).

>[!NOTE]
>
>No es necesario registrar todas las interacciones o clics. Tenga en cuenta qué acciones son más importantes de rastrear y envíe datos a Adobe en consecuencia.

## Borrado de variables en cada página

Los valores de las variables persisten en las páginas que utilizan AJAX, ya que la página no se vuelve a cargar. Por lo tanto, se requiere un ajuste especial para borrar los valores de las variables de modo que no persistan incorrectamente entre las visitas. Adobe ofrece la función [`clearVars`](../vars/functions/clearvars.md) para borrar fácilmente los valores de las variables. Asegúrese de utilizar esta función después de enviar cada visita a Adobe y antes de establecer los valores de las variables para la siguiente visita.

>[!TIP]
>
>La función `clearVars()` no está disponible en el código H. Si no ha actualizado a AppMeasurement, establezca cada valor de variable de Analytics en una cadena vacía.

## Ejemplos

El ejemplo siguiente utiliza JavaScript simple para borrar los valores de variables existentes, definir nuevos valores y enviar una solicitud de imagen a Adobe:

```js
s.clearVars();
s.pageName = "Example AJAX page";
s.eVar1="Example value";
void(s.t());
```

En el ejemplo siguiente se muestra una llamada de seguimiento de la llamada de retorno `done` de la función `.ajax` de JQuery:

```js
$.ajax({
  url: "example.html",
  dataType: "html"
})
  .done(function( response ) {
    $( "#content" ).html( response );
  s.clearVars();
  s.pageName = $( "h1:first" ).text();
  s.t();
  });
```

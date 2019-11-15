---
description: Describe cómo se cuentan las instancias en las variables de comercialización.
keywords: Analytics Implementation
solution: Analytics
title: Las instancias en las variables de comercialización
topic: Developer and implementation
uuid: 4cdfd53e-88aa-48cf-a135-98f7fc8dcece
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Las instancias en las variables de comercialización

Describe cómo se cuentan las instancias en las variables de comercialización.

Actualmente no se admiten instancias para variables de comercialización. Si observa instancias en un informe que contiene una variable de comercialización, indica que la eVar se está estableciendo en algunas ubicaciones fuera de la cadena de productos y no debería considerarse como un auténtico recuento de instancias para la variable de comercialización seleccionada.

Si usa Sintaxis de la variable de conversión, se contará una instancia cada vez que se establezca la variable. No obstante, siempre que se establezca esta instancia se le asignará el atributo "Ninguno" si no se cumple ninguna de las condiciones siguientes:

* Se establece un evento de enlace.
* Se establece la variable de productos.
* La eVar de comercialización cuenta con un valor.

Por ejemplo, la instancia de eVar1 siguiente se ha asignado a "Aire libre:gafas protectoras de esquí":

```js
s.eVar1="Outdoors:Ski Goggles" 
s.events="prodView" 
s.products=";Fernie Snow Goggles"
```

No obstante, en el ejemplo siguiente, la instancia de eVar1 se ha asignado a "Ninguno" porque no se ha cumplido ninguna de las condiciones en el momento de establecer la eVar (no existe ningún evento de enlace y no se ha establecido la variable de productos):

Página 1 de la visita:

```js
s.eVar1="Outdoors:Ski Goggles"
```

Página 2 de la visita:

```js
s.events="prodView" 
s.products=";Fernie Snow Goggles"
```

La asignación a "Ninguno" se produce cuando se establece un valor para una eVar en una página sin eventos de enlace, o si se establece el valor de la eVar en la cadena de productos sin uno de estos eventos.

> [!NOTE] La funcionalidad actual para contar instancias en variables de comercialización se está revisando y está programado que cambie en una próxima versión.


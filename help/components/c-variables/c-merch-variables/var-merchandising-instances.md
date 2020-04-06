---
description: Describe cómo se cuentan las instancias en las variables de comercialización.
keywords: Analytics Implementation
title: Las instancias en las variables de comercialización
topic: Developer and implementation
uuid: 4cdfd53e-88aa-48cf-a135-98f7fc8dcece
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Las instancias en las variables de comercialización

Describe cómo se cuentan las instancias en las variables de comercialización.

Actualmente no se admiten instancias para variables de comercialización. Si observa instancias en un informe que contiene una variable de comercialización, indica que la eVar se está configurando en algunas ubicaciones fuera de la cadena de productos y no debe considerarse como un verdadero recuento de instancias para la variable de comercialización seleccionada.

Si utiliza Sintaxis de la variable de conversión, se cuenta una instancia cada vez que se configura la variable. Sin embargo, la instancia se atribuye a &quot;Ninguno&quot; a menos que se produzca lo siguiente cada vez que se establezca la variable:

* Se establece un evento de enlace.
* Se establece la variable products.
* La eVar de comercialización tiene un valor.

Por ejemplo, la siguiente instancia de eVar1 se asigna a &quot;Aire libre:gafas de esquí&quot;:

```js
s.eVar1="Outdoors:Ski Goggles" 
s.events="prodView" 
s.products=";Fernie Snow Goggles"
```

Sin embargo, en el siguiente ejemplo, la instancia de eVar1 se asigna a &quot;Ninguno&quot;, ya que no se cumplen todas las condiciones cuando se establece la eVar (no hay ningún evento de enlace y la variable products no está configurada):

Página 1 de la visita:

```js
s.eVar1="Outdoors:Ski Goggles"
```

Página 2 de la visita:

```js
s.events="prodView" 
s.products=";Fernie Snow Goggles"
```

La asignación a &quot;Ninguno&quot; se produce si se establece un valor para una eVar en una página en la que no se produce ningún evento de enlace, o si se establece el valor de la eVar en la cadena de productos sin un evento de enlace.

>[!NOTE] La funcionalidad actual de recuento de instancias en las variables de comercialización se está revisando y su modificación se ha programado para una versión próxima.


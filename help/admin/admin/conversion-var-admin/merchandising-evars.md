---
title: eVars de comercialización y métodos de búsqueda de productos
description: Una profundización en los conceptos subyacentes a las eVars de comercialización y en cómo procesan y asignan los datos.
source-git-commit: 746c2cfd3236df7ec7498749015ddf75c1e558f5
workflow-type: tm+mt
source-wordcount: '246'
ht-degree: 0%

---

# eVars de comercialización y métodos de búsqueda de productos

En este documento se explican los conceptos subyacentes a las eVars de comercialización, que procesan y asignan los datos de forma diferente a las eVars estándar. También explica cómo se relacionan las eVars de comercialización con los métodos de búsqueda de productos.

Aunque la mayoría de los sitios web comerciales tienen muchas formas de encontrar productos, Adobe considera que los siguientes son los métodos fundamentales de búsqueda de productos que todos los clientes minoristas deben rastrear en Adobe Analytics:

* Palabras clave de búsqueda interna
* Códigos de seguimiento de campaña internos
* Categorías de comercialización y exploración
* Vínculos de venta cruzada

A los efectos de este documento, asignemos algunas eVars a las soluciones de la siguiente manera:

* eVar2: Palabras clave de búsqueda interna
* eVar3: Códigos de seguimiento de campaña internos
* eVar4: Categorías de comercialización y exploración
* eVar5: Vínculos de venta cruzada

Podemos usar un eVar adicional para medir el rendimiento de todos los métodos de búsqueda de productos en relación mutua. Además de los métodos de búsqueda descritos anteriormente, el eVar incluirá otros métodos de búsqueda, como vínculos a páginas de detalles de productos de sitios web externos, en su comparación.

* eVar1: Métodos de búsqueda de productos

No debe configurar ninguna de estas variables para que sean eVars estándar, sino que debe configurarlas para que sean eVars de comercialización.  El uso de eVars de comercialización permite asignar cualquier actividad exitosa a los valores capturados por las eVars en un nivel *por producto* en lugar de en un nivel *por visita/por pedido*. Aclararé la diferencia entre la asignación por producto y por pedido durante el resto de este documento.


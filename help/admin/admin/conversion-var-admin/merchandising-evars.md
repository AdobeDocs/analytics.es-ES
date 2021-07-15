---
title: eVars de comercialización y métodos de búsqueda de productos
description: Una profundización en los conceptos subyacentes a las eVars de comercialización y en cómo procesan y asignan los datos.
source-git-commit: e7bfb56b63a9134728360c91f3c835da1952fa5a
workflow-type: tm+mt
source-wordcount: '549'
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

Para demostrar cómo se van a configurar estas variables, empezaré con un ejemplo en el que un visitante decide que utilizará las palabras clave internas de búsqueda &quot;sandals&quot; para encontrar un producto en el sitio.  En la página de resultados de búsqueda de palabras clave, debe capturar datos en al menos dos eVars:

* `eVar2` será igual a la palabra clave utilizada en la búsqueda (&quot;sandals&quot;)
* `eVar1` será igual al método de búsqueda de productos utilizado (&quot;búsqueda de palabras clave interna&quot;).

Cuando configura estas dos variables en función de estos valores específicos, sabe que el visitante está usando el término de búsqueda de palabras clave internas &quot;sandals&quot; para encontrar un producto.
Al mismo tiempo, sabe que el visitante no está usando los otros métodos de búsqueda de productos para encontrar productos (por ejemplo, el visitante no está navegando por categorías de productos exactamente al mismo tiempo que realiza una búsqueda de palabras clave). Para garantizar que se realice la asignación adecuada por producto, estos métodos no utilizados no deben acreditar la búsqueda de un producto que se haya encontrado mediante una búsqueda de palabras clave interna.  Por lo tanto, debe insertar lógica en el código (por ejemplo, AppMeasurement, SDK web de AEP, etc.) que establecerá automáticamente las eVars asociadas con estos otros métodos de búsqueda en el valor &quot;método de no búsqueda&quot;.

Por ejemplo, cuando un usuario busca productos utilizando la palabra clave &quot;sandals&quot;, la lógica del código de Analytics debe establecer las variables iguales a las siguientes en la página de resultados de búsqueda de palabras clave internas:

* eVar2=&quot;sandals&quot;: la palabra clave &quot;sandals&quot; se utilizó en la búsqueda de palabras clave interna
* eVar1=&quot;búsqueda de palabras clave interna&quot;: se utilizó el método de búsqueda &quot;búsqueda de palabras clave internas&quot;
* eVar3=&quot;campaña no interna&quot;: no se utilizó una campaña interna para acceder a la página de resultados de la búsqueda
* eVar4=&quot;non-browse&quot;: no se accedió a una categoría Examinar en la página de resultados de búsqueda
* eVar5=&quot;non-cross-sell&quot;: no se hizo clic en un vínculo de venta cruzada en la página de resultados de búsqueda


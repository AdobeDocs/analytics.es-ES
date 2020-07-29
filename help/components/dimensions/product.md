---
title: Product
description: El nombre del producto.
translation-type: tm+mt
source-git-commit: 6778dd290424651dc959224daa0eef8ebd8196e5
workflow-type: tm+mt
source-wordcount: '142'
ht-degree: 1%

---


# Product

La dimensión &#39;Producto&#39; informa el nombre del producto en la visita. Resulta útil para implementaciones que utilizan la `products` variable y desean ver métricas en torno a productos, como los principales vendedores o los más visitados. Esta dimensión puede estar en blanco si no tiene ningún producto en el sitio.

## Rellenar esta dimensión con datos

Esta dimensión hace referencia a la segunda parte de la cadena en la [`products`](/help/implement/vars/page-vars/products.md) variable. Los caracteres entre el primer y el segundo punto y coma (`;`) rellenan esta dimensión.

## Elementos de Dimension

Dado que esta variable se basa en una cadena personalizada en la implementación, su organización determina cuáles son los elementos de dimensión. Adobe recomienda que establezca una convención de nombres uniforme para los productos. [Las clasificaciones](../classifications/c-classifications.md) están disponibles si desea agrupar los productos de forma diferente o proporcionar un nombre más sencillo. Adobe recomienda utilizar las dimensiones &quot;Producto&quot; y &quot;Categoría&quot;.

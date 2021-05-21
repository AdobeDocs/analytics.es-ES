---
title: Product
description: Nombre del producto.
exl-id: 2649c200-4b0a-49a9-8592-9b9af72b91cf
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '142'
ht-degree: 100%

---

# Product

La dimensión “Producto” informa del nombre del producto en la visita. Resulta útil para implementaciones que utilizan la variable `products` y desean ver métricas en torno a los productos, como los principales vendedores o los más visitados. Esta dimensión puede estar en blanco si no tiene ningún producto en el sitio.

## Rellene esta dimensión con datos

Esta dimensión hace referencia a la segunda parte de la cadena en la variable [`products`](/help/implement/vars/page-vars/products.md). Los caracteres entre el primer y el segundo punto y coma (`;`) rellenan esta dimensión.

## Elementos de dimensión

Dado que esta variable se basa en una cadena personalizada en la implementación, su organización determina cuáles son los elementos de dimensión. Adobe recomienda que establezca una convención de nombres uniforme para los productos. Las [clasificaciones](../classifications/c-classifications.md) están disponibles si desea agrupar los productos de forma diferente o proporcionar un nombre más descriptivo. Adobe recomienda utilizar las dimensiones “Producto” y “Categoría”.

---
title: Categoría
description: La categoría del producto de la visita.
feature: Dimensions
exl-id: 3517b417-1a44-4d3e-ac16-93fdc5f36404
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: tm+mt
source-wordcount: '155'
ht-degree: 100%

---

# Categoría

La dimensión “Categoría” informa la categoría del producto de la visita. Resulta útil para implementaciones que utilizan la variable `products` y desean ver métricas en torno a la categoría del producto, como los principales vendedores o los más visitados. Esta dimensión puede estar en blanco si no tiene ningún producto en el sitio.

## Rellene esta dimensión con datos

Esta dimensión hace referencia a la primera parte de la cadena en la variable [`products`](/help/implement/vars/page-vars/products.md). Todo lo anterior al primer punto y coma (`;`) rellena esta dimensión.

## Elementos de dimensión

Dado que esta variable se basa en una cadena personalizada en la implementación, su organización determina cuáles son los elementos de dimensión. Adobe recomienda agrupar productos individuales en categorías significativas, utilizando las dimensiones “Producto” y “Categoría”.

>[!TIP]
>
>En versiones anteriores de Adobe Analytics, algunas limitaciones a la dimensión “Categoría” se impusieron debido a su arquitectura de procesamiento. Estas limitaciones se han eliminado desde entonces, lo que le permite utilizar cualquier métrica y desglose.

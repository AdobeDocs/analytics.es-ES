---
title: Categoría
description: La categoría del producto de la visita.
translation-type: tm+mt
source-git-commit: bddfc52d460e87a70e7cff149f197570f405037a
workflow-type: tm+mt
source-wordcount: '155'
ht-degree: 1%

---


# Categoría

La dimensión &#39;Categoría&#39; informa la categoría del producto de la visita. Resulta útil para implementaciones que utilizan la `products` variable y desean ver métricas en torno a la categoría del producto, como los principales vendedores o los más visitados. Esta dimensión puede estar en blanco si no tiene ningún producto en el sitio.

## Rellenar esta dimensión con datos

Esta dimensión hace referencia a la primera parte de la cadena en la [`products`](/help/implement/vars/page-vars/products.md) variable. Todo lo anterior al primer punto y coma (`;`) rellena esta dimensión.

## Valores de dimensión

Dado que esta variable se basa en una cadena personalizada en la implementación, su organización determina cuáles son los valores de dimensión. Adobe recomienda agrupar productos individuales en categorías significativas, utilizando las dimensiones &quot;Producto&quot; y &quot;Categoría&quot;.

> [!TIP] En versiones anteriores de Adobe Analytics, se impusieron algunas limitaciones a la dimensión &#39;Categoría&#39; debido a su arquitectura de procesamiento. Estas limitaciones se han eliminado desde entonces, lo que le permite utilizar cualquier métrica y desglose.

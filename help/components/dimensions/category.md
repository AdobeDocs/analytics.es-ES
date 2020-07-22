---
title: Categoría
description: La categoría del producto de la visita.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '155'
ht-degree: 1%

---


# Categoría

La dimensión &#39;Categoría&#39; informa la categoría del producto de la visita. Resulta útil para implementaciones que utilizan la `products` variable y desean ver métricas en torno a la categoría del producto, como los principales vendedores o los más visitados. Esta dimensión puede estar en blanco si no tiene ningún producto en el sitio.

## Rellenar esta dimensión con datos

Esta dimensión hace referencia a la primera parte de la cadena en la [`products`](/help/implement/vars/page-vars/products.md) variable. Todo lo anterior al primer punto y coma (`;`) rellena esta dimensión.

## Elementos de dimensión

Dado que esta variable se basa en una cadena personalizada en la implementación, su organización determina cuáles son los elementos de dimensión. Adobe recomienda agrupar productos individuales en categorías significativas, utilizando las dimensiones &quot;Producto&quot; y &quot;Categoría&quot;.

>[!TIP]
>
>En versiones anteriores de Adobe Analytics, algunas limitaciones a la dimensión &#39;Categoría&#39; se impusieron debido a su arquitectura de procesamiento. Estas limitaciones se han eliminado desde entonces, lo que le permite utilizar cualquier métrica y desglose.

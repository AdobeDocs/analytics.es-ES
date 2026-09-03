---
title: Categoría
description: La categoría del producto de la visita.
feature: Dimensions
exl-id: 3517b417-1a44-4d3e-ac16-93fdc5f36404
TQID: 'https://experienceleague.adobe.com/3G1qDbtVnRj8At-FU1fNaI8KLboMQvo8NKktinrTbs8'
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7aid: b8734a57-d5fb-44a8-8ee1-65225cecaeae
subfeature_v2: id: b22bc0f7-b089-4966-95a1-31e7b3b69b79
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 155
ht-degree: 93%

---

# Categoría

La &quot;Categoría&quot; [dimensión](overview.md) informa de la categoría del producto de la visita. Resulta útil para implementaciones que utilizan la variable `products` y desean ver métricas en torno a la categoría del producto, como los principales vendedores o los más visitados. Esta dimensión puede estar en blanco si no tiene ningún producto en el sitio.

## Rellene esta dimensión con datos

Esta dimensión hace referencia a la primera parte de la cadena en la variable [`products`](/help/implement/vars/page-vars/products.md). Todo lo anterior al primer punto y coma (`;`) rellena esta dimensión.

## Elementos de dimensión

Dado que esta variable se basa en una cadena personalizada en la implementación, su organización determina cuáles son los elementos de dimensión. Adobe recomienda agrupar productos individuales en categorías significativas, utilizando las dimensiones “Producto” y “Categoría”.

>[!TIP]
>
>En versiones anteriores de Adobe Analytics, algunas limitaciones a la dimensión “Categoría” se impusieron debido a su arquitectura de procesamiento. Estas limitaciones se han eliminado desde entonces, lo que le permite utilizar cualquier métrica y desglose.

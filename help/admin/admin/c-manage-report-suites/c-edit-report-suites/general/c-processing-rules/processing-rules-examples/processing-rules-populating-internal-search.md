---
description: Si utiliza una variable común, como "q", para rellenar términos de búsqueda, puede utilizar reglas de procesamiento para rellenar las eVar de los términos de búsqueda internos con esos valores.
subtopic: Processing rules
title: Rellenar términos de búsqueda internos utilizando un parámetro de cadena de consulta
feature: Admin Tools
uuid: 05ae2b0a-8797-468c-8f59-643beac614c5
exl-id: bc7cc712-0f2a-4260-a82c-ad0e48149e73
source-git-commit: 71ff81a0ae67c6f4cc9a8df567e27223cc63f18c
workflow-type: tm+mt
source-wordcount: '115'
ht-degree: 100%

---

# Rellenar términos de búsqueda internos utilizando un parámetro de cadena de consulta

Si utiliza una variable común, como &quot;q&quot;, para rellenar términos de búsqueda, puede utilizar reglas de procesamiento para rellenar las eVar de los términos de búsqueda internos con esos valores.

Los valores de las cadenas de consulta deben estar codificados en Unicode o UTF-8 para que puedan leerlos las reglas de procesamiento.

| Conjunto de reglas | Valor |
|---|---|
| Condición | Si está definido el parámetro de cadena de consulta q |
| Acción | Sobrescribir el valor de los términos de búsqueda internos con el parámetro de cadena de consulta q |

Por ejemplo:

![](assets/populate-internal-search-terms.png)

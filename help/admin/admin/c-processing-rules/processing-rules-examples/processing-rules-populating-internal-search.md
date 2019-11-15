---
description: Si utiliza una variable común, como q, para rellenar términos de búsqueda, puede utilizar reglas de procesamiento para rellenar las eVar de los términos de búsqueda internos con esos valores.
solution: Analytics
subtopic: Processing rules
title: Rellenar términos de búsqueda internos utilizando un parámetro de cadena de consulta
topic: Admin tools
uuid: 05ae2b0a-8797-468c-8f59-643beac614c5
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Rellenar términos de búsqueda internos utilizando un parámetro de cadena de consulta

Si utiliza una variable común, como q, para rellenar términos de búsqueda, puede utilizar reglas de procesamiento para rellenar las eVar de los términos de búsqueda internos con esos valores.

Los valores de las cadenas de consulta deben estar codificados en Unicode o UTF-8 para que puedan leerlos las reglas de procesamiento.

| Conjunto de reglas | Valor |
|---|---|
| Condición | Si está definido el parámetro de cadena de consulta q |
| Acción | Sobrescribir el valor de los términos de búsqueda internos con el parámetro de cadena de consulta q |

Por ejemplo:

![](assets/populate-internal-search-terms.png)


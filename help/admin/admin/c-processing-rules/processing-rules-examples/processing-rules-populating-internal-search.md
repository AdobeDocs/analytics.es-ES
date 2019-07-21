---
description: Si utiliza una variable común, como q, para rellenar términos de búsqueda, puede utilizar reglas de procesamiento para rellenar las eVar de los términos de búsqueda internos con esos valores.
seo-description: Si utiliza una variable común, como q, para rellenar términos de búsqueda, puede utilizar reglas de procesamiento para rellenar las eVar de los términos de búsqueda internos con esos valores.
seo-title: Rellene los términos de búsqueda interna utilizando un parámetro de cadena de consulta
solution: Analytics
subtopic: Reglas de procesamiento
title: Rellene los términos de búsqueda interna utilizando un parámetro de cadena de consulta
topic: Herramientas de administración
uuid: 05 ae 2 b 0 a -8797-468 c -8 f 59-643 beac 614 c 5
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Rellene los términos de búsqueda interna utilizando un parámetro de cadena de consulta

Si utiliza una variable común, como q, para rellenar términos de búsqueda, puede utilizar reglas de procesamiento para rellenar las eVar de los términos de búsqueda internos con esos valores.

Los valores de las cadenas de consulta deben estar codificados en Unicode o UTF-8 para que puedan leerlos las reglas de procesamiento.

| Conjunto de reglas | Valor |
|---|---|
| Condición | Si está definido el parámetro de cadena de consulta q |
| Acción | Sobrescribir el valor de los términos de búsqueda internos con el parámetro de cadena de consulta q |

Por ejemplo:

![](assets/populate-internal-search-terms.png)


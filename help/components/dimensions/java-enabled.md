---
title: Habilitado para Java
description: Determina si Java está habilitado en el explorador.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '216'
ht-degree: 1%

---


# Habilitado para Java

La dimensión &#39;Java habilitado&#39; determina si el explorador en ese momento tiene Java habilitado. Resulta útil en los casos en los que desea introducir la funcionalidad basada en Java en el sitio y desea saber cuántos visitantes ya tienen Java habilitado. Para aquellos que tienen Java deshabilitado, puede proporcionar una alternativa o instrucciones sobre cómo habilitarlo.

## Rellenar esta dimensión con datos

Esta dimensión recupera datos de la cadena [`v` de](/help/implement/validate/query-parameters.md) consulta en solicitudes de imagen. AppMeasurement recopila estos datos detectando si Java está habilitado en el explorador. Si utiliza una biblioteca de AppMeasurement (por ejemplo, mediante Adobe Experience Platform Launch), esta dimensión funciona de forma predeterminada. Si utiliza un método de recopilación de datos fuera de AppMeasurement (por ejemplo, a través de la API), asegúrese de incluir el parámetro de cadena de `v` consulta que contiene &quot;Y&quot; o &quot;N&quot; si desea utilizar esta dimensión.

## Elementos de dimensión

Los elementos de dimensión incluyen &quot;Habilitado&quot;, &quot;Deshabilitado&quot; y &quot;Desconocido&quot;.

* **Habilitado**: Java está habilitado en el explorador. La cadena de `v` consulta contenía el valor &quot;Y&quot;.
* **Deshabilitado**: Java está deshabilitado en el explorador o no admite Java. La cadena de `v` consulta contenía el valor &quot;N&quot;.
* **Desconocido**: AppMeasurement no pudo determinar la compatibilidad con Java. La cadena de `v` consulta no estaba presente en la solicitud de imagen.

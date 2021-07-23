---
title: Habilitado para Java
description: Determina si Java está habilitado en el explorador.
exl-id: 2d4b4ea2-65ba-4d39-a040-f989b5eddc6e
source-git-commit: e6f3beadfba340cea07f5fd2694105ad31de9751
workflow-type: tm+mt
source-wordcount: '217'
ht-degree: 90%

---

# Habilitado para Java

La dimensión “Java habilitado” determina si el explorador tiene Java habilitado en ese momento. Resulta útil en los casos en los que desea introducir la funcionalidad basada en Java en el sitio y desea saber cuántos visitantes ya tienen Java habilitado. Para aquellos que tienen Java deshabilitado, puede proporcionar una alternativa o instrucciones sobre cómo habilitarlo.

## Rellene esta dimensión con datos

Esta dimensión recupera datos de la [`v`cadena de consulta](/help/implement/validate/query-parameters.md) en solicitudes de imagen. AppMeasurement recopila estos datos detectando si Java está habilitado en el explorador. Si utiliza una biblioteca de AppMeasurement (por ejemplo, mediante etiquetas en Adobe Experience Platform), esta dimensión funciona de forma predeterminada. Si utiliza un método de recopilación de datos fuera de AppMeasurement (por ejemplo, a través de la API), asegúrese de incluir el parámetro de cadena de consulta `v` que contiene “Y” o “N” si desea utilizar esta dimensión.

## Elementos de dimensión

Los elementos de dimensión incluyen “Habilitado”, “Deshabilitado” y “Desconocido”.

* **Habilitado**: Java está habilitado en el explorador. La cadena de consulta `v` contenía el valor “Y”.
* **Deshabilitado**: Java está deshabilitado en el explorador o no admite Java. La cadena de consulta `v` contenía el valor “N”.
* **Desconocido**: AppMeasurement no pudo determinar la compatibilidad con Java. La cadena de consulta `v` no estaba presente en la solicitud de imagen.

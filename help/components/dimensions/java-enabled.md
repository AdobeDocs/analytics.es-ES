---
title: Habilitado para Java
description: Determina si Java está habilitado en el explorador.
feature: Dimensions
exl-id: 2d4b4ea2-65ba-4d39-a040-f989b5eddc6e
TQID: https://experienceleague.adobe.com/EjiqmqpByH-q9AL-934s5HXAv78JTXpEJZ1Bwk-y5MI
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 218
ht-degree: 93%

---

# Habilitado para Java

La [dimensión](overview.md) &quot;Java habilitado&quot; determina si el explorador tiene Java habilitado en ese momento. Resulta útil en los casos en los que desea introducir la funcionalidad basada en Java en el sitio y desea saber cuántos visitantes ya tienen Java habilitado. Para aquellos que tienen Java deshabilitado, puede proporcionar una alternativa o instrucciones sobre cómo habilitarlo.

## Rellene esta dimensión con datos

Esta dimensión recupera datos de la [`v`cadena de consulta](/help/implement/validate/query-parameters.md) en solicitudes de imagen. AppMeasurement recopila estos datos detectando si Java está habilitado en el explorador. Si utiliza una biblioteca de AppMeasurement (por ejemplo, mediante etiquetas en Adobe Experience Platform), esta dimensión funciona de forma predeterminada. Si utiliza un método de recopilación de datos fuera de AppMeasurement (por ejemplo, a través de la API), asegúrese de incluir el parámetro de cadena de consulta `v` que contiene “Y” o “N” si desea utilizar esta dimensión.

## Elementos de dimensión

Los elementos de dimensión incluyen “Habilitado”, “Deshabilitado” y “Desconocido”.

* **Habilitado**: Java está habilitado en el explorador. La cadena de consulta `v` contenía el valor “Y”.
* **Deshabilitado**: Java está deshabilitado en el explorador o no admite Java. La cadena de consulta `v` contenía el valor “N”.
* **Desconocido**: AppMeasurement no pudo determinar la compatibilidad con Java. La cadena de consultas `v` no estaba presente en la solicitud de imagen.

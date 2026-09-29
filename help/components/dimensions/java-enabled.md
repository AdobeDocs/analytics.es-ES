---
title: Habilitado para Java
description: Determina si Java está habilitado en el explorador.
feature: Dimensions
exl-id: 2d4b4ea2-65ba-4d39-a040-f989b5eddc6e
TQID: 'https://experienceleague.adobe.com/EjiqmqpByH-q9AL-934s5HXAv78JTXpEJZ1Bwk-y5MI'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
    internal-label: API
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
    internal-label: Data configuration and collection
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
  - id: b22bc0f7-b089-4966-95a1-31e7b3b69b79
    internal-label: Dimensions
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: 9a50beeb0aa51cf9f4baf212566947c14029ce8e
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 51%
---
# Habilitado para Java

La [dimensión](overview.md) &quot;Java habilitado&quot; determina si el explorador tiene Java habilitado en ese momento. Resulta útil en los casos en los que desea introducir la funcionalidad basada en Java en el sitio y desea saber cuántos visitantes ya tienen Java habilitado. Para aquellos que tienen Java deshabilitado, puede proporcionar una alternativa o instrucciones sobre cómo habilitarlo.

## Rellene esta dimensión con datos

Java habilitado se recopila automáticamente en el lado del cliente: AppMeasurement detecta si Java está habilitado en el explorador e informa de &quot;Y&quot; o &quot;N&quot;. Funciona de forma predeterminada en cualquier implementación de AppMeasurement o Web SDK (etiquetas); no hay ninguna variable que establecer. Si recopila datos fuera de AppMeasurement o de la SDK web (por ejemplo, a través de la API), envíe &quot;Y&quot; o &quot;N&quot; para utilizar esta dimensión.

| Propiedad | Valor |
| --- | --- |
| **variable de AppMeasurement** | Ninguno (recopilado automáticamente) |
| **Campo Web SDK / XDM** | Ninguno (recopilado automáticamente) |
| **Parámetro de consulta** | [`v`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **etiqueta XML** | [`<javaEnabled>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Límite de bytes** | 1 byte |
| **Persistencia** | N/A |

## Elementos de dimensión

Los elementos de dimensión incluyen “Habilitado”, “Deshabilitado” y “Desconocido”.

* **Habilitado**: Java está habilitado en el explorador. La cadena de consulta `v` contenía el valor “Y”.
* **Deshabilitado**: Java está deshabilitado en el explorador o no admite Java. La cadena de consulta `v` contenía el valor “N”.
* **Desconocido**: AppMeasurement no pudo determinar la compatibilidad con Java. La cadena de consultas `v` no estaba presente en la solicitud de imagen.

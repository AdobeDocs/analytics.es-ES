---
title: API de inserción de datos en lotes
description: La API de inserción masiva de datos (BDIA) es una función de Adobe Analytics que permite cargar datos de llamadas al servidor en lotes de archivos en lugar de utilizar bibliotecas del lado del cliente como AppMeasurement.
solution: Analytics
feature: API
exl-id: c9d23fae-2800-42bb-8f8d-adf915cadc62
role: Admin
TQID: https://experienceleague.adobe.com/TVa-LtTWKi6lQKGQKhH2bu5UcKsSJ2-KVqlfU5tQROQ
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 201
ht-degree: 85%

---

# API de inserción de datos en lotes

La inserción masiva de datos resuelve varios casos de uso, como:

* Ingesta de datos históricos de un sistema de análisis anterior

* Un sistema de recopilación de análisis interno que impide utilizar AppMeasurement. Puede utilizar procesos de extracción, transformación y carga (ETL) para colocar datos en archivos por lotes y, a continuación, utilizar BDIA para cargarlos en Adobe Analytics.

* Recopilación de datos de dispositivos que solo tienen conectividad intermitente con Internet. Estos dispositivos almacenan las interacciones hasta que reciben una conexión. A continuación, el dispositivo puede cargar los datos a la vez a través de BDIA.

Tanto la API de inserción de datos como [la API de inserción masiva de datos](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md) son métodos para enviar datos de colección del lado del servidor a Adobe Analytics. Las llamadas a la API de inserción de datos se realizan a razón de un evento a la vez. La API de inserción masiva de datos acepta archivos con formato CSV que contienen datos de evento, un evento por fila. Si está trabajando en una nueva implementación de la colección del lado del servidor, le recomendamos utilizar la API de inserción masiva de datos.

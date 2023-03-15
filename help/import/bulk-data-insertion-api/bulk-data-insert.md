---
title: API de inserción de datos en lotes
description: La API de inserción masiva de datos (BDIA) es una función de Adobe Analytics que permite cargar datos de llamadas al servidor en lotes de archivos en lugar de usar bibliotecas del lado del cliente como AppMeasurement. Las llamadas al servidor en estos archivos por lotes pueden ser datos actuales (activos) o datos históricos. Es un sucesor más escalable de la API de inserción de datos en versiones anteriores de la API de Adobe Analytics.
solution: Analytics
feature: API
exl-id: c9d23fae-2800-42bb-8f8d-adf915cadc62
source-git-commit: b1ebf6e3548ef73217ffff1cbfb66af82e38fb8f
workflow-type: tm+mt
source-wordcount: '231'
ht-degree: 100%

---

# API de inserción de datos en lotes

La inserción masiva de datos resuelve varios casos de uso, como:

* Ingesta de datos históricos de un sistema de análisis anterior

* Un sistema de recopilación de análisis interno que impide utilizar AppMeasurement. Puede utilizar procesos de extracción, transformación y carga (ETL) para colocar datos en archivos por lotes y, a continuación, utilizar BDIA para cargarlos en Adobe Analytics.

* Recopilación de datos de dispositivos que solo tienen conectividad intermitente con Internet. Estos dispositivos almacenan las interacciones hasta que reciben una conexión. A continuación, el dispositivo puede cargar los datos a la vez a través de BDIA.

Tanto la API de inserción de datos como [la API de inserción masiva de datos](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md) son métodos para enviar datos de colección del lado del servidor a Adobe Analytics. Las llamadas a la API de inserción de datos se realizan a razón de un evento a la vez. La API de inserción masiva de datos acepta archivos con formato CSV que contienen datos de evento, un evento por fila. Si está trabajando en una nueva implementación de la colección del lado del servidor, le recomendamos utilizar la API de inserción masiva de datos.

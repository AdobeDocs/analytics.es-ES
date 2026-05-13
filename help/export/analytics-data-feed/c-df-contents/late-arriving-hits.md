---
title: Visitas que llegan tarde
description: Descubra cómo las fuentes de datos tratan las visitas que llegan tarde.
feature: Data Feeds
exl-id: c99a702b-2aaa-47a6-958a-1e5ab66961ba
TQID: https://experienceleague.adobe.com/eNLHiK8xI-O-E7UDfIkxEfFB0oAQoum6lTXH7OFQJ3c
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 317
ht-degree: 48%

---

# Visitas que llegan tarde {#late-arriving-hits}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa_datafeed_late_hits"
>title="Permitir visitas que llegan tarde."
>abstract="Seleccione esta opción para incluir datos que llegaron después de que el trabajo de feed de datos terminara de procesar los datos dentro de la frecuencia de creación de informes establecida (normal o diariamente o cada hora). Con esta opción habilitada, cada vez que un feed de datos procesa la información, examina las visitas que han llegado y las procesa por lotes con el siguiente archivo de feed de datos que se envía."

<!-- markdownlint-enable MD034 -->

## Comprender las visitas que llegan tarde

Los datos históricos pueden llegar después de que un trabajo de fuente de datos termine de procesarse durante una hora o un día determinados, por ejemplo, mediante visitas con marca de tiempo u origen de datos.

Cuando una fuente de datos procesa la información con normalidad, solo utiliza los datos dentro de su intervalo de informes (generalmente la hora o el día más recientes). Si los datos llegan después de que una fuente procese ese intervalo de informes, nunca se incluirán en ninguna fuente de datos.

Cuando las visitas que llegan tarde se encuentran habilitadas, el método de procesamiento cambia para incluir estos datos. Cada vez que una fuente de datos procesa la información, observa las visitas que llegan tarde y las procesa en el siguiente archivo de fuente de datos que se envía.

## Habilitar las visitas que llegan tarde

Antes de activar la opción para permitir las visitas que llegan tarde para una fuente de datos, tenga en cuenta lo siguiente:

* Los datos de diferentes días aparecen con frecuencia en las fuentes de datos cuando las visitas que llegan tarde están habilitadas. Compruebe que la plataforma que utiliza para la ingesta de fuentes de datos puede admitir datos de diferentes días dentro del mismo archivo.
* Si se vuelve a procesar un archivo de fuente de datos, las visitas que llegan tarde y que se incluyeron en el archivo original se incluirán en el archivo reprocesado cuando el reprocesamiento se produzca en los primeros 5 días. Después de 5 días, las visitas que llegan tarde no se incluyen en el archivo reprocesado.

Puede habilitar las visitas que llegan tarde al crear o editar una fuente de datos habilitando la opción **[!UICONTROL Permitir visitas que llegan tarde]**, tal como se describe en [Crear una fuente de datos](/help/export/analytics-data-feed/create-feed.md).

---
description: La tabla de búsqueda para determinar el tipo de visita basándose en los eventos de página.
keywords: page;event;page_event;post_page_event
title: Búsqueda de eventos de página
feature: Data Feeds
exl-id: ef0467df-b94b-4cec-b312-96d8f42c23b0
TQID: 'https://experienceleague.adobe.com/VaSk-h0AVXNcL-YoxuFu2XJwzING-08-GX2Pgt6dj4s'
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
subfeature_v2: id: ede9f3ba-4ee4-4497-9d8e-e9da5848bda0
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 226
ht-degree: 100%

---

# Búsqueda de eventos de página

La tabla de búsqueda para determinar el tipo de visita basándose en el valor `page_event`. Como se menciona en la [referencia de columna de datos](datafeeds-reference.md), las columnas `page_event` y `post_page_event` son tinyint sin firmar.

* Consulte [`t()`](/help/implement/vars/functions/t-method.md) para comprender la implementación de las llamadas de vista de página para AppMeasurement y SDK web.
* Consulte [`tl()`](/help/implement/vars/functions/tl-method.md) para comprender la implementación de las llamadas de seguimiento de vínculos para AppMeasurement y SDK Web.
* Consulte [Implementar Adobe Analytics con Adobe Experience Platform Edge Network](/help/implement/aep-edge/overview.md) para comprender cómo Adobe Analytics traduce las cargas útiles XDM a tipos de eventos de página.

| `page_event` valor | `post_page_event` valor | Descripción |
| --- | --- | --- |
| `0` | `0` | Todas las llamadas de vista de páginas estándar. Es el valor predeterminado para la mayoría de las visitas. |
| `10` | `100` | Vínculos personalizados. Establezca el tipo de vínculo en `o` (AppMeasurement) o `xdm.web.webInteraction.type` en `other` (SDK web o SDK móvil). |
| `11` | `101` | Vínculos de descarga. Establezca el tipo de vínculo en `d` (AppMeasurement) o `xdm.web.webInteraction.type` en `download` (SDK web o SDK móvil). |
| `12` | `102` | Vínculos de salida. Establezca el tipo de vínculo en `e` (AppMeasurement) o `xdm.web.webInteraction.type` en `exit` (Web SDK o Mobile SDK). |
| `31` | `76` | Inicio de medios |
| `32` | `77` | Actualizaciones de medios (sin otro procesamiento de variables) |
| `33` | `78` | Actualizaciones de medios (con otro procesamiento de variables) |
| `40` | `80` | Encuesta |
| `50` | `50` | Inicio de medios de streaming |
| `51` | `51` | Cierre de medios de streaming |
| `52` | `52` | Borrado de medios de streaming |
| `53` | `53` | Visitas persistentes de medios de streaming |
| `54` | `54` | Inicio de anuncios de medios de streaming |
| `55` | `55` | Cierre de anuncios de medios de streaming |
| `56` | `56` | Borrado de anuncios de medios de streaming |
| `60` | `60` | Inicio de medios de Primetime |
| `61` | `61` | Cierre de medios de Primetime |
| `62` | `62` | Borrado de medios de Primetime |
| `63` | `63` | Visitas persistentes de medios de Primetime |
| `64` | `64` | Inicio de anuncios de medios de Primetime |
| `65` | `65` | Cierre de anuncios de medios de Primetime |
| `66` | `66` | Borrado de anuncios de medios de Primetime |
| `70` | `70` | Incluye datos de actividad de Target |

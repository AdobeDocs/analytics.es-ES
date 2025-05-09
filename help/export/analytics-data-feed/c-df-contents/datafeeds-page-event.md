---
description: La tabla de búsqueda para determinar el tipo de visita en función del evento de la página.
keywords: página;evento;page_event;post_page_event
title: Búsqueda de eventos de página
feature: Data Feeds
exl-id: ef0467df-b94b-4cec-b312-96d8f42c23b0
source-git-commit: e16b0d7b3fe585dc8e9274a77833ad5af3c63124
workflow-type: tm+mt
source-wordcount: '226'
ht-degree: 4%

---

# Búsqueda de eventos de página

Tabla de búsqueda para determinar el tipo de visita basándose en el valor `page_event`. Como se menciona en la [referencia de columna de datos](datafeeds-reference.md), las columnas `page_event` y `post_page_event` son tinyint sin firmar.

* Consulte [`t()`](/help/implement/vars/functions/t-method.md) para comprender la implementación de las llamadas de vista de página para AppMeasurement y Web SDK.
* Consulte [`tl()`](/help/implement/vars/functions/tl-method.md) para comprender la implementación de las llamadas de seguimiento de vínculos para AppMeasurement y Web SDK.
* Consulte [Implementar Adobe Analytics con Adobe Experience Platform Edge Network](/help/implement/aep-edge/overview.md) para comprender cómo Adobe Analytics traduce las cargas XDM a tipos de eventos de página.

| `page_event` valor | `post_page_event` valor | Descripción |
| --- | --- | --- |
| `0` | `0` | Todas las llamadas de vista de página estándar. Es el valor predeterminado para la mayoría de las visitas. |
| `10` | `100` | Vínculos personalizados. Establezca el tipo de vínculo en `o` (AppMeasurement) o `xdm.web.webInteraction.type` en `other` (Web SDK o Mobile SDK). |
| `11` | `101` | Vínculos de descarga. Establezca el tipo de vínculo en `d` (AppMeasurement) o `xdm.web.webInteraction.type` en `download` (Web SDK o Mobile SDK). |
| `12` | `102` | Vínculos de salida. Establezca el tipo de vínculo en `e` (AppMeasurement) o `xdm.web.webInteraction.type` en `exit` (Web SDK o Mobile SDK). |
| `31` | `76` | Inicio de contenidos |
| `32` | `77` | Actualizaciones de medios (sin otro procesamiento de variables) |
| `33` | `78` | Actualizaciones de medios (con otro procesamiento de variables) |
| `40` | `80` | Encuesta |
| `50` | `50` | Inicio de medios de streaming |
| `51` | `51` | Cierre de medios de streaming |
| `52` | `52` | Eliminación de medios de streaming |
| `53` | `53` | Los medios de streaming se mantienen activos |
| `54` | `54` | Inicio del anuncio de medios de streaming |
| `55` | `55` | Cierre de anuncio de medios de streaming |
| `56` | `56` | Medios de streaming y eliminación |
| `60` | `60` | Inicio de medios de Primetime |
| `61` | `61` | Cierre de medios de Primetime |
| `62` | `62` | Eliminación de medios de Primetime |
| `63` | `63` | Mantener activos los medios de Primetime |
| `64` | `64` | Inicio del anuncio multimedia de Primetime |
| `65` | `65` | Cierre de anuncio multimedia de Primetime |
| `66` | `66` | Eliminación de medios y publicidad de Primetime |
| `70` | `70` | Incluye datos de actividad de Target |

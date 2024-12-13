---
title: Métricas de publicidad de medios de streaming
description: Métricas disponibles cuando se habilita [!UICONTROL Anuncios multimedia] para un grupo de informes.
feature: Metrics
exl-id: f0ddf3e0-ab55-4a05-a8ae-f040ba26e704
source-git-commit: fdd66c9558f070cd760f37a39e5911f0dac22612
workflow-type: tm+mt
source-wordcount: '152'
ht-degree: 5%

---

# Métricas de publicidad de medios de streaming

*Esta página describe las métricas disponibles al habilitar [!UICONTROL Anuncios multimedia] para un grupo de informes. Consulte [Dimensiones de anuncios de medios de streaming](../dimensions/sm-ads.md) para ver las dimensiones disponibles.*

Las métricas de anuncios de medios de streaming proporcionan una funcionalidad de creación de informes suplementaria para la recopilación de datos mediante bibliotecas de recopilación de medios de streaming. El uso de estas métricas requiere la **[!UICONTROL recopilación de medios de streaming de Adobe]**. Póngase en contacto con el equipo de cuenta de Adobe para obtener más información.

Cuando habilita **[!UICONTROL Anuncios multimedia]** en [Informes multimedia](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/media-management.md), están disponibles las siguientes métricas:

| Nombre de la métrica | Descripción | Enviado con | Variable de datos de contexto |
| --- | --- | --- | --- |
| El anuncio finaliza | Se activa cuando se completa un anuncio de vídeo. | Cierre de publicidad | `a.media.ad.complete` |
| El anuncio comienza | Se activa cuando se inicia un anuncio de vídeo. | Inicio del anuncio | `a.media.ad.view` |
| Tiempo invertido en publicidad | Cantidad total de tiempo invertido en ver el anuncio, en segundos. | Cierre de publicidad | `a.media.ad.timePlayed` |
| Tiempo invertido en contenido | Suma la duración del evento para todos los eventos de REPRODUCCIÓN (contenido principal y de publicidad), en segundos. | Cierre de medios | `a.media.totalTimePlayed` |

{style="table-layout:auto"}

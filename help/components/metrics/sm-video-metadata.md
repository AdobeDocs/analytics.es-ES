---
title: Métricas de metadatos de vídeo de medios de streaming
description: Métricas disponibles cuando se habilita [!UICONTROL Metadatos de vídeo] para un grupo de informes.
feature: Metrics
source-git-commit: 26c131a37fa1f30c83fd99b290523a97d3c954db
workflow-type: tm+mt
source-wordcount: '118'
ht-degree: 5%

---

# Métricas de metadatos de vídeo de medios de streaming

*Esta página describe las métricas disponibles al habilitar [!UICONTROL Metadatos de vídeo] para un grupo de informes. Consulte [Dimensiones de metadatos de vídeo de medios de streaming](../dimensions/sm-video-metadata.md) para ver las dimensiones disponibles.*

Las métricas de metadatos de vídeo de medios de streaming proporcionan una funcionalidad de creación de informes suplementaria para la recopilación de datos a través de bibliotecas de recopilación de medios de streaming. El uso de estas métricas requiere el **[!UICONTROL Complemento de recopilación de medios de streaming de Adobe]**. Póngase en contacto con el equipo de cuenta de Adobe para obtener más información.

Cuando habilita **[!UICONTROL Metadatos de vídeo]** en [Informes de contenidos](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/media-management.md), está disponible la siguiente métrica:

| Nombre de la métrica | Descripción | Enviado con | Variable de datos de contexto |
| --- | --- | --- | --- |
| Con autorización | Un booleano que establece un déclencheur cuando el usuario está autorizado mediante la autenticación de Adobe. | Inicio de contenidos, Cierre de contenidos | `a.media.pass.auth` |

{style="table-layout:auto"}

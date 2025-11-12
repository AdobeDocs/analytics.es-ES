---
title: Métricas de metadatos de vídeo de los servicios de medios de streaming
description: Métricas disponibles cuando se habilita [!UICONTROL Metadatos de vídeo] para un grupo de informes.
feature: Metrics
exl-id: b2f60a34-e139-4498-bf71-74d291759ef2
source-git-commit: 936644c719f46a1327c8a5aa247ed69a14d3da1e
workflow-type: tm+mt
source-wordcount: '125'
ht-degree: 4%

---

# Métricas de metadatos de vídeo de los servicios de medios de streaming

*Esta página describe las métricas disponibles al habilitar [!UICONTROL Metadatos de vídeo] para un grupo de informes. Consulte [Dimensiones de metadatos de vídeo de los servicios de medios de streaming](../dimensions/sm-video-metadata.md) para ver las dimensiones disponibles.*

Las métricas de metadatos de vídeo de los servicios de medios de streaming proporcionan una funcionalidad de creación de informes suplementaria para la recopilación de datos a través de las bibliotecas de los servicios de medios de streaming. El uso de estas métricas requiere el **[!UICONTROL complemento de Adobe Analytics para medios de streaming]**. Póngase en contacto con el equipo de su cuenta de Adobe para obtener más información.

Cuando habilita **[!UICONTROL Metadatos de vídeo]** en [Informes de contenidos](/help/admin/tools/manage-rs/edit-settings/media-management.md), está disponible la siguiente métrica:

| Nombre de la métrica | Descripción | Enviado con | Variable de datos de contexto | Campo XDM |
| --- | --- | --- | --- | --- |
| **[!UICONTROL Autorizado]** | Un booleano que establece un déclencheur cuando el usuario está autorizado a través de la autenticación de Adobe. | Inicio de contenidos, Cierre de contenidos | `a.media.pass.auth` | `xdm.mediaCollection.`<br>`sessionDetails.authorized`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.authorized` |

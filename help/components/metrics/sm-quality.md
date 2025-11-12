---
title: Métricas de calidad de servicios de medios de streaming
description: Métricas disponibles cuando se habilita [!UICONTROL Calidad de los medios] para un grupo de informes.
feature: Metrics
exl-id: a64829b5-d45b-44c6-80c3-5acf1a6d9919
source-git-commit: 936644c719f46a1327c8a5aa247ed69a14d3da1e
workflow-type: tm+mt
source-wordcount: '333'
ht-degree: 1%

---

# Métricas de calidad de servicios de medios de streaming

*Esta página describe las métricas disponibles cuando se habilita [!UICONTROL Calidad de los medios] para un grupo de informes. Consulte [Dimensiones de calidad de servicios de medios de streaming](../dimensions/sm-quality.md) para ver las dimensiones disponibles.*

Las métricas de calidad de los servicios de medios de streaming proporcionan una funcionalidad de sistema de informes suplementaria a la recopilación de datos a través de las bibliotecas de los servicios de medios de streaming. El uso de estas métricas requiere el **[!UICONTROL complemento de Adobe Analytics para medios de streaming]**. Póngase en contacto con el equipo de su cuenta de Adobe para obtener más información.

Cuando habilita **[!UICONTROL Calidad multimedia]** en [Informes multimedia](/help/admin/tools/manage-rs/edit-settings/media-management.md), están disponibles las siguientes métricas:

| Nombre de la métrica | Descripción | Enviado con | Variable de datos de contexto | Campo XDM |
| --- | --- | --- | --- | --- |
| **[!UICONTROL Velocidad de bits media]** | Una media ponderada de todos los valores de velocidad de bits durante la duración de reproducción de una sesión de reproducción. | Cierre de medios | `a.media.qoe.`<br>`bitrateAverage` | `xdm.mediaReporting.`<br>`qoeDataDetails.bitrateAverage` |
| **[!UICONTROL Flujos afectados por cambio de velocidad de bits]** | Un booleano que indica en déclencheur si la velocidad de bits cambia al menos una vez durante una sesión de reproducción. | Cierre de medios | `a.media.qoe.`<br>`bitrateChange` | `xdm.mediaReporting.`<br>`qoeDataDetails.`<br>`hasBitrateChangeImpactedStreams` |
| **[!UICONTROL Cambios de velocidad de bits]** | El número de veces que cambió la velocidad de bits. | Cierre de medios | `a.media.qoe.`<br>`bitrateChangeCount` | `xdm.mediaCollection.`<br>`qoeDataDetails.`<br>`bitrateChangeCount`<br><br>`xdm.mediaReporting.`<br>`qoeDataDetails.`<br>`bitrateChangeCount` |
| **[!UICONTROL Flujos afectados por búfer]** | Un booleano que indica en déclencheur si el vídeo entra en estado de búfer al menos una vez. | Cierre de medios | `a.media.qoe.`<br>`buffer` | `xdm.mediaReporting.`<br>`qoeDataDetails.`<br>`hasBufferImpactedStreams` |
| **[!UICONTROL Eventos de búfer]** | El número de veces que el vídeo se almacena en búfer durante una sesión de reproducción. | Cierre de medios | `a.media.qoe.`<br>`bufferCount` | `xdm.mediaReporting.`<br>`qoeDataDetails.bufferCount` |
| **[!UICONTROL Duración total del búfer]** | La cantidad de tiempo que un vídeo ha invertido en almacenar en búfer todos los eventos de búfer, en segundos. | Cierre de medios | `a.media.qoe.`<br>`bufferTime` | `xdm.mediaReporting.`<br>`qoeDataDetails.bufferTime` |
| **[!UICONTROL Pérdidas antes del inicio]** | Un booleano que establece un déclencheur si un usuario sale antes de que comience el contenido principal de un vídeo. | Cierre de medios | `a.media.qoe.`<br>`dropBeforeStart` | `xdm.mediaReporting.`<br>`qoeDataDetails.`<br>`isDroppedBeforeStart` |
| **[!UICONTROL Fotogramas perdidos]** | Un entero que representa el número total de fotogramas perdidos durante una sesión de reproducción. | Cierre de medios | `a.media.qoe.`<br>`droppedFrameCount` | `xdm.mediaCollection.`<br>`qoeDataDetails.droppedFrames`<br><br>`xdm.mediaReporting.`<br>`qoeDataDetails.droppedFrames` |
| **[!UICONTROL Flujos afectados por fotogramas rechazados]** | Un booleano que déclencheur cuando se pierden fotogramas durante una sesión de reproducción. | Cierre de medios | `a.media.qoe.`<br>`droppedFrames` | `xdm.mediaReporting.`<br>`qoeDataDetails.`<br>`hasDroppedFrameImpactedStreams` |
| **[!UICONTROL Flujos afectados por error]** | Un booleano que déclencheur cuando un vídeo experimenta un error en cualquier momento durante una sesión de reproducción. | Cierre de medios | `a.media.qoe.`<br>`error` | `xdm.mediaReporting.`<br>`qoeDataDetails.`<br>`hasErrorImpactedStreams` |
| **[!UICONTROL Eventos de error]** | Un entero que representa el número total de errores encontrados durante una sesión de reproducción. | Cierre de medios | `a.media.qoe.`<br>`errorCount` | `xdm.mediaReporting.`<br>`qoeDataDetails.errorCount` |
| **[!UICONTROL Tiempo para el inicio]** | La cantidad de tiempo que se tarda en iniciar un vídeo, en milisegundos. Adobe convierte y almacena este valor en segundos. | Cierre de medios | `a.media.qoe.`<br>`timeToStart` | `xdm.mediaCollection.`<br>`qoeDataDetails.timeToStart`<br><br>`xdm.mediaReporting.`<br>`qoeDataDetails.timeToStart` |

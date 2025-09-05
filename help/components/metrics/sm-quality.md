---
title: Métricas de calidad de servicios de medios de streaming
description: Métricas disponibles cuando se habilita [!UICONTROL Calidad de los medios] para un grupo de informes.
feature: Metrics
exl-id: a64829b5-d45b-44c6-80c3-5acf1a6d9919
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '331'
ht-degree: 1%

---

# Métricas de calidad de servicios de medios de streaming

*Esta página describe las métricas disponibles cuando se habilita [!UICONTROL Calidad de los medios] para un grupo de informes. Consulte [Dimensiones de calidad de servicios de medios de streaming](../dimensions/sm-quality.md) para ver las dimensiones disponibles.*

Las métricas de calidad de los servicios de medios de streaming proporcionan una funcionalidad de sistema de informes suplementaria a la recopilación de datos a través de las bibliotecas de los servicios de medios de streaming. El uso de estas métricas requiere el **[!UICONTROL complemento de Adobe Analytics para medios de streaming]**. Póngase en contacto con el equipo de su cuenta de Adobe para obtener más información.

Cuando habilita **[!UICONTROL Calidad multimedia]** en [Informes multimedia](/help/admin/tools/manage-rs/edit-settings/media-management.md), están disponibles las siguientes métricas:

| Nombre de la métrica | Descripción | Enviado con | Variable de datos de contexto |
| --- | --- | --- | --- |
| Velocidad de bits media | Una media ponderada de todos los valores de velocidad de bits durante la duración de reproducción de una sesión de reproducción. | Cierre de medios | `a.media.qoe.bitrateAverage` |
| Flujos afectados por cambio de velocidad | Un booleano que indica en déclencheur si la velocidad de bits cambia al menos una vez durante una sesión de reproducción. | Cierre de medios | `a.media.qoe.bitrateChange` |
| Cambios de velocidad de bits | El número de veces que cambió la velocidad de bits. | Cierre de medios | `a.media.qoe.bitrateChangeCount` |
| Flujos afectados por búfer | Un booleano que indica en déclencheur si el vídeo entra en estado de búfer al menos una vez. | Cierre de medios | `a.media.qoe.buffer` |
| Eventos de búfer | El número de veces que el vídeo se almacena en búfer durante una sesión de reproducción. | Cierre de medios | `a.media.qoe.bufferCount` |
| Duración total del búfer | La cantidad de tiempo que un vídeo ha invertido en almacenar en búfer todos los eventos de búfer, en segundos. | Cierre de medios | `a.media.qoe.bufferTime` |
| Pérdidas antes del inicio | Un booleano que establece un déclencheur si un usuario sale antes de que comience el contenido principal de un vídeo. | Cierre de medios | `a.media.qoe.dropBeforeStart` |
| Fotogramas perdidos | Un entero que representa el número total de fotogramas perdidos durante una sesión de reproducción. | Cierre de medios | `a.media.qoe.droppedFrameCount` |
| Flujos afectados por fotogramas rechazados | Un booleano que déclencheur cuando se pierden fotogramas durante una sesión de reproducción. | Cierre de medios | `a.media.qoe.droppedFrames` |
| Flujos afectados por error | Un booleano que déclencheur cuando un vídeo experimenta un error en cualquier momento durante una sesión de reproducción. | Cierre de medios | `a.media.qoe.error` |
| Eventos de error | Un entero que representa el número total de errores encontrados durante una sesión de reproducción. | Cierre de medios | `a.media.qoe.errorCount` |
| Tiempo para el inicio | La cantidad de tiempo que se tarda en iniciar un vídeo, en milisegundos. Adobe convierte y almacena este valor en segundos. | Cierre de medios | `a.media.qoe.timeToStart` |

---
title: Métricas principales de los servicios de medios de streaming
description: Métricas disponibles cuando habilitas [!UICONTROL Media Core] para un grupo de informes.
feature: Metrics
exl-id: f4ff5f84-18b6-4e67-b808-133faeaf8605
source-git-commit: 936644c719f46a1327c8a5aa247ed69a14d3da1e
workflow-type: tm+mt
source-wordcount: '412'
ht-degree: 2%

---

# Métricas principales de los servicios de medios de streaming

*Esta página describe las métricas disponibles cuando se habilita [!UICONTROL Media Core] para un grupo de informes. Consulte [Dimensiones principales de los servicios de medios de streaming](../dimensions/sm-core.md) para ver las dimensiones disponibles.*

Las métricas principales de los servicios de medios de streaming proporcionan una funcionalidad básica de creación de informes a los datos recopilados a través de las bibliotecas de recopilación de servicios de medios de streaming. El uso de estas métricas requiere el **[!UICONTROL complemento de Adobe Analytics para medios de streaming]**. Póngase en contacto con el equipo de su cuenta de Adobe para obtener más información.

Cuando habilita **[!UICONTROL Componentes básicos de medios]** en [Informes de medios](/help/admin/tools/manage-rs/edit-settings/media-management.md), están disponibles las siguientes métricas:

| Nombre de la métrica | Descripción | Enviado con | Variable de datos de contexto | Campo XDM |
| --- | --- | --- | --- | --- |
| **[!UICONTROL Público medio por minuto]** | Cantidad total de tiempo invertido en un contenido determinado, dividido por su duración para todas las sesiones de reproducción.<br>`[Time spent] / [Media length]` | Cierre de medios | `a.media.`<br>`averageMinuteAudience` | `xdm.mediaReporting.`<br>`sessionDetails.`<br>`averageMinuteAudience` |
| **[!UICONTROL Contenido finalizado]** | Déclencheur cuando se completa un fragmento de contenido. Esta métrica no significa necesariamente que hayan visto todo el contenido; podrían haberse saltado partes. Solo significa que han llegado al final del contenido. | | `a.media.complete` | `xdm.mediaReporting.`<br>`sessionDetails.isCompleted` |
| **[!UICONTROL Flujos afectados por la pausa]** | Un booleano que indica en déclencheur si se produjeron una o más pausas durante la reproducción del contenido. | Cierre de medios | `a.media.pause` | `xdm.mediaReporting.`<br>`sessionDetails.`<br>`hasPauseImpactedStreams` |
| **[!UICONTROL Pausar eventos]** | El recuento de pausas que se produjeron durante una sesión de reproducción. | Cierre de medios | `a.media.pauseCount` | `xdm.mediaReporting.`<br>`sessionDetails.pauseCount` |
| **[!UICONTROL Duración total de la pausa]** | Duración total de todos los eventos de pausa, en segundos. | Cierre de medios | `a.media.pauseTime` | `xdm.mediaReporting.`<br>`sessionDetails.pauseTime` |
| **[!UICONTROL El contenido comienza]** | Se consume el primer fotograma del contenido. Si un usuario lo cierra durante un anuncio o el almacenamiento en búfer, este evento no se almacena en déclencheur. | Cierre de medios | `a.media.play` | `xdm.mediaReporting.`<br>`sessionDetails.isPlayed` |
| **[!UICONTROL Marcador de progreso al 10%]**<br>**[!UICONTROL Marcador de progreso al 25%]**<br>**[!UICONTROL Marcador de progreso al 50%]**<br>**[!UICONTROL Marcador de progreso al 75%]**<br>**[!UICONTROL Marcador de progreso al 95%]** | El cabezal de reproducción pasa el marcador de contenido indicado en función de la longitud. Cada marcador se cuenta solo una vez, incluso hacia atrás. Si se salta hacia adelante, los marcadores omitidos no se cuentan. | Cierre de medios | `a.media.progress10`<br>`a.media.progress25`<br>`a.media.progress50`<br>`a.media.progress75`<br>`a.media.progress95` | `xdm.mediaReporting.`<br>`sessionDetails.hasProgress10`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.hasProgress25`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.hasProgress50`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.hasProgress75`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.hasProgress95` |
| **[!UICONTROL Reanudación del contenido]** | Un booleano que entra en déclencheur cuando el contenido se reanuda después de más de 30 minutos de búfer, pausa o bloqueo. También déclencheur si lo establece el reproductor en VideoInfo trackPlay. | Cierre de medios | `a.media.resume` | `xdm.mediaCollection.`<br>`sessionDetails.hasResume`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.hasResume` |
| **[!UICONTROL Vistas de segmentos de contenido]** | Un booleano que entra en déclencheur en el primer fotograma del segmento visualizado. | Cierre de medios | `a.media.segmentView` | `xdm.mediaReporting.`<br>`sessionDetails.`<br>`hasSegmentView` |
| **[!UICONTROL Comienzos de medios]** | Un booleano que entra en déclencheur cuando el medio se carga inicialmente. Este evento incluye anuncios, almacenamiento en búfer y errores. | Inicio de medios | `a.media.view` | `xdm.mediaReporting.`<br>`sessionDetails.isViewed` |
| **[!UICONTROL Tiempo invertido en contenido]** | Duración total del evento para todos los eventos de tipo REPRODUCIR en el contenido principal, en segundos. | Cierre de medios | `a.media.timePlayed` | `xdm.mediaReporting.`<br>`sessionDetails.timePlayed` |
| **[!UICONTROL Tiempo único reproducido]** | Cantidad total de tiempo que se reproduce el contenido único, en segundos. Esta métrica excluye el tiempo de reproducción cuando se visualiza contenido repetido, como la búsqueda hacia atrás. | Cierre de medios | `a.media.`<br>`uniqueTimePlayed` | `xdm.mediaReporting.`<br>`sessionDetails.`<br>`uniqueTimePlayed` |

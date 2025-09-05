---
title: Dimensiones de calidad de servicios de medios de streaming
description: Dimensiones disponibles al habilitar [!UICONTROL Calidad de los medios] para un grupo de informes.
feature: Dimensions
exl-id: e3794d8c-3c03-425d-850c-a735b579324b
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '309'
ht-degree: 1%

---

# Dimensiones de calidad de servicios de medios de streaming

*Esta página describe las dimensiones disponibles cuando se habilita [!UICONTROL Calidad multimedia] para un grupo de informes. Consulte [Métricas de calidad de servicios de medios de streaming](../metrics/sm-quality.md) para ver las métricas disponibles.*

Las dimensiones de calidad de los servicios de medios de streaming proporcionan informes relacionados con la calidad del contenido que consume el visitante. El uso de estas dimensiones requiere el [!UICONTROL complemento de Adobe Analytics para medios de streaming]. Póngase en contacto con el equipo de su cuenta de Adobe para obtener más información.

Cuando habilita **[!UICONTROL Calidad multimedia]** en [Informes multimedia](/help/admin/tools/manage-rs/edit-settings/media-management.md), están disponibles las siguientes dimensiones:

| Nombre de dimensiones | Descripción | Enviado con | Variable de datos de contexto |
| --- | --- | --- | --- |
| Velocidad de bits media | La velocidad de bits media en intervalos de bloque de 100 KBPS. Se calcula como una media ponderada de todos los valores de velocidad de bits en relación con la duración de reproducción de una sesión determinada. | Cierre de medios | `a.media.qoe.bitrateAverageBucket` |
| Cambios de velocidad de bits | El número de cambios de velocidad de bits que se produjeron durante una sesión de reproducción. | Cierre de medios | `a.media.qoe.bitrateChangeCount` |
| Eventos de búfer | El número de veces que el reproductor de contenido ha entrado en un estado de búfer durante una sesión de reproducción. | Cierre de medios | `a.media.qoe.bufferCount` |
| Duración total del búfer | Cantidad total de tiempo en búfer, en segundos. | Cierre de medios | `a.media.qoe.bufferTime` |
| Fotogramas perdidos | El número total de fotogramas perdidos que se produjeron durante una sesión de reproducción. | Cierre de medios | `a.media.qoe.droppedFrameCount` |
| Errores | El número total de errores que se produjeron durante una sesión de reproducción. | Cierre de medios | `a.media.qoe.errorCount` |
| ID de error externo | Todos los ID de error únicos de cualquier fuente externa, como errores de CDN. Debe proporcionar los códigos de error o ID deseados. Se permiten varios ID de error. | Cierre de medios | `a.media.qoe.externalErrors` |
| ID de error del reproductor SDK | Todos los ID de error únicos generados por el SDK del reproductor de contenido. Debe proporcionar los códigos de error o ID deseados. Se permiten varios ID de error. | Cierre de medios | `a.media.qoe.playerSdkErrors` |
| Tiempo para el inicio | El valor predeterminado es `0` si no se establece mediante QoSObject. Establezca el valor en milisegundos. Analysis Workspace informa de esta dimensión en segundos. | Inicio de contenidos, Cierre de contenidos | `a.media.qoe.timeToStart` |

{style="table-layout:auto"}

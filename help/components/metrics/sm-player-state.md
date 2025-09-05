---
title: Métricas de seguimiento del estado del reproductor de servicios de medios de streaming
description: Métricas disponibles cuando habilitas [!UICONTROL Seguimiento de estado del reproductor] para un grupo de informes.
feature: Metrics
exl-id: 324936cc-0c7a-4710-a618-b24cc6a2c2cf
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '376'
ht-degree: 1%

---

# Métricas de seguimiento del estado del reproductor de servicios de medios de streaming

Las métricas de seguimiento de estado del reproductor de servicios de streaming de medios proporcionan una funcionalidad de sistema de informes suplementaria para la recopilación de datos a través de las bibliotecas de los servicios de streaming de medios. El uso de estas métricas requiere el **[!UICONTROL complemento de Adobe Analytics para medios de streaming]**. Póngase en contacto con el equipo de su cuenta de Adobe para obtener más información.

Cuando habilita **[!UICONTROL Seguimiento de estado del reproductor]** en [Informes de medios](/help/admin/tools/manage-rs/edit-settings/media-management.md), están disponibles las siguientes métricas:

| Nombre de la métrica | Descripción | Enviado con | Variable de datos de contexto |
| --- | --- | --- | --- |
| Transmisiones afectadas por los subtítulos | Se activa si tuvo lugar al menos un estado de Subtítulos durante una sesión de reproducción. | Cierre de medios | `a.media.states.closedcaptioning.set` |
| Recuentos de subtítulos | El número de veces que el vídeo entró en estado de Subtítulos. | Cierre de medios | `a.media.states.closedcaptioning.count` |
| Duración total de los subtítulos | La cantidad de tiempo que el vídeo estuvo en estado de Subtítulos, en segundos. | Cierre de medios | `a.media.states.closedcaptioning.time` |
| Transmisiones afectadas por pantalla completa | Se activa si tuvo lugar al menos un estado de pantalla completa durante una sesión de reproducción. | Cierre de medios | `a.media.states.fullscreen.set` |
| Recuento de pantalla completa | El número de veces que el vídeo entró en estado de pantalla completa. | Cierre de medios | `a.media.states.fullscreen.count` |
| Duración total de pantalla completa | La cantidad de tiempo que el vídeo estuvo en estado de pantalla completa, en segundos. | Cierre de medios | `a.media.states.fullscreen.time` |
| Transmisiones afectadas por el enfoque | Se activa si tuvo lugar al menos un estado de Enfocado durante una sesión de reproducción. | Cierre de medios | `a.media.states.infocus.set` |
| Recuentos de Enfocado | El número de veces que el vídeo entró en un estado Enfocado. | Cierre de medios | `a.media.states.infocus.count` |
| Duración total de Enfocado | La cantidad de tiempo que el vídeo estuvo en estado Enfocado, en segundos. | Cierre de medios | `a.media.states.infocus.time` |
| Transmisiones afectadas por silenciar | Se activa si se produce al menos un estado de Silenciar durante una sesión de reproducción. | Cierre de medios | `a.media.states.mute.set` |
| Recuentos de Silenciar | El número de veces que el vídeo entró en estado Silenciar. | Cierre de medios | `a.media.states.mute.count` |
| Duración total de Silenciar | La cantidad de tiempo que el vídeo estuvo en estado Silenciar, en segundos. | Cierre de medios | `a.media.states.mute.time` |
| Transmisiones afectadas por imagen en imagen | Se activa si tuvo lugar al menos un estado de Imagen en imagen durante una sesión de reproducción. | Cierre de medios | `a.media.states.pictureinpicture.set` |
| Recuentos de Imagen en imagen | El número de veces que el vídeo ha entrado en el estado Imagen en imagen. | Cierre de medios | `a.media.states.pictureinpicture.count` |
| Duración total de Imagen en imagen | La cantidad de tiempo que el vídeo estuvo en estado Imagen en imagen, en segundos. | Cierre de medios | `a.media.states.pictureinpicture.time` |

{style="table-layout:auto"}

---
title: Métricas principales de los servicios de medios de streaming
description: Métricas disponibles cuando habilitas [!UICONTROL Media Core] para un grupo de informes.
feature: Metrics
exl-id: f4ff5f84-18b6-4e67-b808-133faeaf8605
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '534'
ht-degree: 1%

---

# Métricas principales de los servicios de medios de streaming

*Esta página describe las métricas disponibles cuando se habilita [!UICONTROL Media Core] para un grupo de informes. Consulte [Dimensiones principales de los servicios de medios de streaming](../dimensions/sm-core.md) para ver las dimensiones disponibles.*

Las métricas principales de los servicios de medios de streaming proporcionan una funcionalidad básica de creación de informes a los datos recopilados a través de las bibliotecas de recopilación de servicios de medios de streaming. El uso de estas métricas requiere el **[!UICONTROL complemento de Adobe Analytics para medios de streaming]**. Póngase en contacto con el equipo de su cuenta de Adobe para obtener más información.

Cuando habilita **[!UICONTROL Componentes básicos de medios]** en [Informes de medios](/help/admin/tools/manage-rs/edit-settings/media-management.md), están disponibles las siguientes métricas:

| Nombre de la métrica | Descripción | Enviado con | Variable de datos de contexto |
| --- | --- | --- | --- |
| Público medio por minuto | Cantidad total de tiempo invertido en un contenido determinado, dividido por su duración para todas las sesiones de reproducción.<br>`[Time spent] / [Media length]` | Cierre de medios | `a.media.averageMinuteAudience` |
| El contenido finaliza | Déclencheur cuando se completa un fragmento de contenido. Esta métrica no significa necesariamente que hayan visto todo el contenido; podrían haberse saltado partes. Solo significa que han llegado al final del contenido. | `a.media.complete` |
| Flujos afectados por la pausa | Un booleano que indica en déclencheur si se produjeron una o más pausas durante la reproducción del contenido. | Cierre de medios | `a.media.pause` |
| Pausar eventos | El recuento de pausas que se produjeron durante una sesión de reproducción. | Cierre de medios | `a.media.pauseCount` |
| Duración total de la pausa | Duración total de todos los eventos de pausa, en segundos. | Cierre de medios | `a.media.pauseTime` |
| El contenido comienza | Se consume el primer fotograma del contenido. Si un usuario lo cierra durante un anuncio o el almacenamiento en búfer, este evento no se almacena en déclencheur. | Cierre de medios | `a.media.play` |
| Marcador de progreso al 10 % | El cabezal de reproducción sobrepasa el marcador del 10% del contenido en función de la longitud. Este marcador se cuenta solo una vez, incluso hacia atrás. Si se salta hacia adelante, los marcadores omitidos no se cuentan. | Cierre de medios | `a.media.progress10` |
| Marcador de progreso del 25 % | El cabezal de reproducción sobrepasa el marcador del 25% del contenido en función de la longitud. Este marcador se cuenta solo una vez, incluso hacia atrás. Si se salta hacia adelante, los marcadores omitidos no se cuentan. | Cierre de medios | `a.media.progress25` |
| Marcador de progreso al 50 % | El cabezal de reproducción sobrepasa el marcador del 50% del contenido en función de la longitud. Este marcador se cuenta solo una vez, incluso hacia atrás. Si se salta hacia adelante, los marcadores omitidos no se cuentan. | Cierre de medios | `a.media.progress50` |
| Marcador de progreso al 75 % | El cabezal de reproducción sobrepasa el marcador del 75% del contenido en función de la longitud. Este marcador se cuenta solo una vez, incluso hacia atrás. Si se salta hacia adelante, los marcadores omitidos no se cuentan. | Cierre de medios | `a.media.progress75` |
| Marcador de progreso al 95 % | El cabezal de reproducción sobrepasa el marcador del 95% del contenido en función de la longitud. Este marcador se cuenta solo una vez, incluso hacia atrás. Si se salta hacia adelante, los marcadores omitidos no se cuentan. | Cierre de medios | `a.media.progress95` |
| Currículos de contenido | Un booleano que entra en déclencheur cuando el contenido se reanuda después de más de 30 minutos de búfer, pausa o bloqueo. También déclencheur si lo establece el reproductor en VideoInfo trackPlay. | Cierre de medios | `a.media.resume` |
| Vistas de segmentos de contenido | Un booleano que entra en déclencheur en el primer fotograma del segmento visualizado. | Cierre de medios | `a.media.segmentView` |
| Inicio de medios | Un booleano que entra en déclencheur cuando el medio se carga inicialmente. Este evento incluye anuncios, almacenamiento en búfer y errores. | Inicio de medios | `a.media.view` |
| Tiempo invertido en contenido | Duración total del evento para todos los eventos de tipo REPRODUCIR en el contenido principal, en segundos. | Cierre de medios | `a.media.timePlayed` |
| Tiempo de reproducción única | Cantidad total de tiempo que se reproduce el contenido único, en segundos. Esta métrica excluye el tiempo de reproducción cuando se visualiza contenido repetido, como la búsqueda hacia atrás. | Cierre de medios | `a.media.uniqueTimePlayed` |

{style="table-layout:auto"}

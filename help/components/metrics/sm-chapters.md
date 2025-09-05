---
title: Métricas del capítulo de servicios de medios de streaming
description: Métricas disponibles cuando habilitas [!UICONTROL Capítulos multimedia] para un grupo de informes.
feature: Metrics
exl-id: bef379d5-9dc9-404f-8197-1ba66d11299d
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '142'
ht-degree: 5%

---

# Métricas del capítulo de servicios de medios de streaming

*Esta página describe las métricas disponibles cuando se habilitan [!UICONTROL Capítulos multimedia] para un grupo de informes. Consulte [Dimensiones del capítulo de servicios de medios de streaming](../dimensions/sm-chapters.md) para ver las dimensiones disponibles.*

Las métricas de capítulo de los servicios de medios de streaming proporcionan una funcionalidad de sistema de informes suplementaria a la recopilación de datos mediante bibliotecas de recopilación de servicios de medios de streaming. El uso de estas métricas requiere el **[!UICONTROL complemento de Adobe Analytics para medios de streaming]**. Póngase en contacto con el equipo de su cuenta de Adobe para obtener más información.

Cuando habilita **[!UICONTROL Capítulos multimedia]** en [Informes multimedia](/help/admin/tools/manage-rs/edit-settings/media-management.md), están disponibles las siguientes métricas:

| Nombre de la métrica | Descripción | Enviado con | Variable de datos de contexto |
| --- | --- | --- | --- |
| El capítulo finaliza | Un booleano que entra en déclencheur cuando se completa un capítulo. | Cierre de capítulo | `a.media.chapter.complete` |
| El capítulo comienza | Un booleano que entra en déclencheur cuando comienza un capítulo. | Inicio del capítulo. | `a.media.chapter.view` |
| Tiempo dedicado al capítulo | Cantidad de tiempo empleado en el capítulo, en segundos. | Cierre de capítulo | `a.media.chapter.timePlayed` |

{style="table-layout:auto"}

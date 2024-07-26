---
title: Métricas del capítulo de medios de streaming
description: Métricas disponibles cuando habilitas [!UICONTROL Capítulos multimedia] para un grupo de informes.
feature: Metrics
source-git-commit: 26c131a37fa1f30c83fd99b290523a97d3c954db
workflow-type: tm+mt
source-wordcount: '136'
ht-degree: 5%

---

# Métricas del capítulo de medios de streaming

*Esta página describe las métricas disponibles cuando se habilitan [!UICONTROL Capítulos multimedia] para un grupo de informes. Consulte [Dimensiones del capítulo de medios de streaming](../dimensions/sm-chapters.md) para ver las dimensiones disponibles.*

Las métricas de capítulo de medios de streaming proporcionan una funcionalidad de creación de informes suplementaria para la recopilación de datos mediante bibliotecas de recopilación de medios de streaming. El uso de estas métricas requiere el **[!UICONTROL Complemento de recopilación de medios de streaming de Adobe]**. Póngase en contacto con el equipo de cuenta de Adobe para obtener más información.

Cuando habilita **[!UICONTROL Capítulos multimedia]** en [Informes multimedia](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/media-management.md), están disponibles las siguientes métricas:

| Nombre de la métrica | Descripción | Enviado con | Variable de datos de contexto |
| --- | --- | --- | --- |
| El capítulo finaliza | Un booleano que entra en déclencheur cuando se completa un capítulo. | Cierre de capítulo | `a.media.chapter.complete` |
| El capítulo comienza | Un booleano que entra en déclencheur cuando comienza un capítulo. | Inicio del capítulo. | `a.media.chapter.view` |
| Tiempo dedicado al capítulo | Cantidad de tiempo empleado en el capítulo, en segundos. | Cierre de capítulo | `a.media.chapter.timePlayed` |

{style="table-layout:auto"}

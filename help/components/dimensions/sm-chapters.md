---
title: Dimensiones del capítulo de medios de streaming
description: Dimensiones disponibles al habilitar [!UICONTROL Capítulos multimedia] para un grupo de informes.
feature: Dimensions
exl-id: cac66a0b-3f83-46a9-b35c-ba08e0eafb92
source-git-commit: fdd66c9558f070cd760f37a39e5911f0dac22612
workflow-type: tm+mt
source-wordcount: '188'
ht-degree: 14%

---

# Dimensiones del capítulo de medios de streaming

*Esta página describe las dimensiones disponibles cuando se habilitan [!UICONTROL Capítulos multimedia] para un grupo de informes. Consulte [Métricas del capítulo de medios de streaming](../metrics/sm-chapters.md) para ver las métricas disponibles*.

Las dimensiones del capítulo medios de streaming proporcionan una funcionalidad de creación de informes suplementaria para la recopilación de datos a través de las bibliotecas de recopilación de medios de streaming. El uso de estas dimensiones requiere la **[!UICONTROL recopilación de medios de streaming de Adobe]**. Póngase en contacto con el equipo de cuenta de Adobe para obtener más información.

Cuando habilita **[!UICONTROL Capítulos multimedia]** en [Informes multimedia](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/media-management.md), está disponible la siguiente dimensión:

| Nombre de la dimensión | Descripción | Enviado con | Variable de datos de contexto |
| --- | --- | --- | --- |
| Capítulo | El ID de capítulo generado automáticamente. | Cierre de capítulo | `a.media.chapter.name` |

{style="table-layout:auto"}

Además de las dimensiones anteriores, Adobe crea automáticamente las siguientes dimensiones de clasificación. Debe cargar datos de clasificación para ver los informes que utilizan estas dimensiones.

| Nombre de clasificación | Dimensión principal | Descripción |
| --- | --- | --- |
| Creador | [Contenido](sm-core.md) | El creador del contenido. |
| Duración del capítulo | Capítulo | Duración del capítulo, expresada en segundos. |
| Nombre del capítulo | Capítulo | Nombre descriptivo del capítulo. |
| Desplazamiento de capítulo | Capítulo | El desplazamiento del capítulo dentro del contenido desde el inicio, en segundos. |
| Posición del capítulo | Capítulo | La posición del índice del capítulo en el contenido. |

{style="table-layout:auto"}

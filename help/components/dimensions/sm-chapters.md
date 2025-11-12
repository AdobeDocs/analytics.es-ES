---
title: Dimensiones del capítulo de medios de streaming
description: Dimensiones disponibles al habilitar [!UICONTROL Capítulos multimedia] para un grupo de informes.
feature: Dimensions
exl-id: cac66a0b-3f83-46a9-b35c-ba08e0eafb92
source-git-commit: 936644c719f46a1327c8a5aa247ed69a14d3da1e
workflow-type: tm+mt
source-wordcount: '195'
ht-degree: 4%

---

# Dimensiones del capítulo de servicios de medios de streaming

*Esta página describe las dimensiones disponibles cuando se habilitan [!UICONTROL Capítulos multimedia] para un grupo de informes. Consulte [Métricas del capítulo de servicios de medios de streaming](../metrics/sm-chapters.md) para ver las métricas disponibles.*

Las dimensiones del capítulo de los servicios de medios de streaming proporcionan una funcionalidad de creación de informes suplementaria para la recopilación de datos a través de las bibliotecas de los servicios de medios de streaming. El uso de estas dimensiones requiere el **[!UICONTROL complemento de Adobe Analytics para medios de streaming]**. Póngase en contacto con el equipo de su cuenta de Adobe para obtener más información.

Cuando habilita **[!UICONTROL Capítulos multimedia]** en [Informes multimedia](/help/admin/tools/manage-rs/edit-settings/media-management.md), está disponible la siguiente dimensión:

| Nombre de la dimensión | Descripción | Enviado con | Variable de datos de contexto | Campo XDM |
| --- | --- | --- | --- | --- |
| **[!UICONTROL Capítulo]** | El ID de capítulo generado automáticamente. | Cierre de capítulo | `a.media.chapter.name` | `xdm.mediaReporting.`<br>`chapterDetails.ID` |

Además de las dimensiones anteriores, Adobe crea automáticamente las siguientes dimensiones de clasificación. Debe cargar datos de clasificación para ver los informes que utilizan estas dimensiones.

| Nombre de clasificación | Dimensión principal | Descripción |
| --- | --- | --- |
| **[!UICONTROL Creador]** | [[!UICONTROL Contenido]](sm-core.md) | El creador del contenido. |
| **[!UICONTROL Longitud del capítulo]** | [!UICONTROL Capítulo] | La duración del capítulo en segundos. |
| **[!UICONTROL Nombre de capítulo]** | [!UICONTROL Capítulo] | Nombre descriptivo del capítulo. |
| **[!UICONTROL Desplazamiento de capítulo]** | [!UICONTROL Capítulo] | El desplazamiento del capítulo dentro del contenido desde el inicio, en segundos. |
| **[!UICONTROL Posición del capítulo]** | [!UICONTROL Capítulo] | La posición del índice del capítulo en el contenido. |

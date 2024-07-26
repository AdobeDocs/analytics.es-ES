---
title: Dimensiones de metadatos de vídeo de medios de streaming
description: Dimensiones disponibles al habilitar [!UICONTROL Metadatos de vídeo] para un grupo de informes.
feature: Dimensions
source-git-commit: 26c131a37fa1f30c83fd99b290523a97d3c954db
workflow-type: tm+mt
source-wordcount: '241'
ht-degree: 7%

---

# Dimensiones de metadatos de vídeo de medios de streaming

*Esta página describe las dimensiones disponibles al habilitar [!UICONTROL Metadatos de vídeo] para un grupo de informes. Consulte [Métricas de metadatos de vídeo de medios de streaming](../metrics/sm-video-metadata.md) para ver las métricas disponibles*.

Las dimensiones de anuncios de medios de streaming proporcionan una funcionalidad de creación de informes suplementaria para la recopilación de datos mediante bibliotecas de recopilación de medios de streaming. El uso de estas dimensiones requiere el **[!UICONTROL complemento de recopilación de medios de streaming de Adobe]**. Póngase en contacto con el equipo de cuenta de Adobe para obtener más información.

Cuando habilita **[!UICONTROL Metadatos de vídeo]** en [Informes de contenidos](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/media-management.md), están disponibles las siguientes dimensiones:

| Nombre de la dimensión | Descripción | Enviado con | Variable de datos de contexto |
| --- | --- | --- | --- |
| Cargas publicitarias | Tipo de anuncio cargado. | Por determinar | `a.media.adLoad` |
| Parte del día | Hora del día a la que se emitió o reprodujo el contenido. Se admite cualquier valor de cadena. | Inicio de contenidos, Cierre de contenidos | `a.media.dayPart` |
| Episodio | El número del episodio. | Inicio de contenidos, Cierre de contenidos | `a.media.episode` |
| Tipo de fuente de medios | El tipo de fuente. | Inicio de contenidos, Cierre de contenidos | `a.media.feed` |
| Género | El tipo o agrupación de contenido según lo definido por el productor de contenido. Esta dimensión admite varios valores, delimitados por comas. | Inicio de contenidos, Cierre de contenidos | `a.media.genre` |
| MVPD | La MVPD proporcionada por la autenticación de Adobe. | Inicio de contenidos, Cierre de contenidos | `a.media.pass.mvpd` |
| Red | El nombre de la red o del canal | Inicio de contenidos, Cierre de contenidos | `a.media.network` |
| Temporada | Número de temporada al que pertenece el programa. | Inicio de contenidos, Cierre de contenidos | `a.media.season` |
| Show | El nombre del programa o serie. | Inicio de contenidos, Cierre de contenidos | `a.media.show` |
| Tipo de programa | Un entero que representa el tipo de contenido.<br>`0`: episodio completo<br>`1`: vista previa o trailer<br>`2`: Clip<br>`3`: Otro | Inicio de contenidos, Cierre de contenidos | `a.media.type` |

{style="table-layout:auto"}

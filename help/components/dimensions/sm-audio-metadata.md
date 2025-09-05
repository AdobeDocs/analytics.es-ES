---
title: Dimensiones de metadatos de audio de los servicios de medios de streaming
description: Dimensiones disponibles al habilitar [!UICONTROL Metadatos de audio] para un grupo de informes.
feature: Dimensions
exl-id: 2e4dc1e9-267b-47a2-b791-23d1e754a2c1
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 8%

---

# Dimensiones de metadatos de audio de los servicios de medios de streaming

Las dimensiones y los servicios de medios de streaming proporcionan una funcionalidad de creación de informes suplementaria para la recopilación de datos a través de las bibliotecas de los servicios de medios de streaming. El uso de estas dimensiones requiere el **[!UICONTROL complemento de Adobe Analytics para medios de streaming]**. Póngase en contacto con el equipo de su cuenta de Adobe para obtener más información.

Cuando habilita **[!UICONTROL Metadatos de audio]** en [Informes de medios](/help/admin/tools/manage-rs/edit-settings/media-management.md), están disponibles las siguientes dimensiones:

| Nombre de la dimensión | Descripción | Enviado con | Variable de datos de contexto |
| --- | --- | --- | --- |
| Álbum | El nombre del álbum. | Inicio de contenidos, Cierre de contenidos | `a.media.album` |
| Artista | El nombre del artista. | Inicio de contenidos, Cierre de contenidos | `a.media.artist` |
| Autor | El nombre del autor del libro de audio. | Inicio de contenidos, Cierre de contenidos | `a.media.author` |
| Etiqueta | El nombre de la discográfica. | Inicio de contenidos, Cierre de contenidos | `a.media.label` |
| Editor | Nombre del editor del contenido de audio. | Inicio de contenidos, Cierre de contenidos | `a.media.publisher` |
| Emisora | El nombre o ID de la emisora de radio. | Inicio de contenidos, Cierre de contenidos | `a.media.station` |

{style="table-layout:auto"}

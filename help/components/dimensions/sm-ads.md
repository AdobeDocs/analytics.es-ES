---
title: Dimensiones y servicios de medios de streaming
description: Dimensiones disponibles al habilitar [!UICONTROL Anuncios multimedia] para un grupo de informes.
feature: Dimensions
exl-id: 3f17bacc-8c36-499a-a863-9298e2d54370
source-git-commit: 936644c719f46a1327c8a5aa247ed69a14d3da1e
workflow-type: tm+mt
source-wordcount: '466'
ht-degree: 4%

---

# Dimensiones y servicios de medios de streaming

*Esta página describe las dimensiones disponibles cuando se habilita [!UICONTROL Anuncios multimedia] para un grupo de informes. Consulte [Métricas de anuncios de medios de streaming](../metrics/sm-ads.md) para ver las métricas disponibles*.

Las dimensiones y los servicios de medios de streaming proporcionan una funcionalidad de creación de informes suplementaria para la recopilación de datos a través de las bibliotecas de los servicios de medios de streaming. El uso de estas dimensiones requiere el **[!UICONTROL complemento de Adobe Analytics para medios de streaming]**. Póngase en contacto con el equipo de su cuenta de Adobe para obtener más información.

Cuando habilita **[!UICONTROL Anuncios multimedia]** en [Informes multimedia](/help/admin/tools/manage-rs/edit-settings/media-management.md), están disponibles las siguientes dimensiones:

| Nombre de la dimensión | Descripción | Enviado con | Variable de datos de contexto | Campo XDM |
| --- | --- | --- | --- | --- |
| **[!UICONTROL Anuncio]** | El identificador único del anuncio. | Inicio del anuncio, Cierre del anuncio | `a.media.ad.`<br>`name` | `xdm.mediaCollection.`<br>`advertisingDetails.name`<br><br>`xdm.mediaReporting.`<br>`advertisingDetails.name` |
| **[!UICONTROL Nombre del anuncio (variable)]** | Nombre descriptivo del anuncio. También hay disponible una dimensión de clasificación denominada &#39;[!UICONTROL Nombre del anuncio]&#39;, que proporciona un propósito similar. Esta dimensión y la clasificación se tratan como dos dimensiones distintas. | Inicio del anuncio, Cierre del anuncio | `a.media.ad.`<br>`friendlyName` | `xdm.mediaCollection.`<br>`advertisingDetails.friendlyName`<br><br>`xdm.mediaReporting.`<br>`advertisingDetails.friendlyName` |
| **[!UICONTROL Nombre del reproductor del anuncio]** | Nombre del reproductor que procesa el anuncio. | Inicio del anuncio, Cierre del anuncio | `a.media.ad.`<br>`playerName` | `xdm.mediaCollection.`<br>`advertisingDetails.playerName`<br><br>`xdm.mediaReporting.`<br>`advertisingDetails.playerName` |
| **[!UICONTROL Longitud del anuncio (variable)]** | Duración del anuncio de vídeo, en segundos. | Inicio del anuncio, Cierre del anuncio | `a.media.ad.`<br>`length` | `xdm.mediaCollection.`<br>`advertisingDetails.length`<br><br>`xdm.mediaReporting.`<br>`advertisingDetails.length` |
| **[!UICONTROL pod de anuncios]** | El identificador único del pod de anuncios. | Inicio del anuncio, Cierre del anuncio | `a.media.ad.`<br>`pod` | |
| **[!UICONTROL Posición del anuncio en la secuencia]** | La posición de índice del anuncio dentro de la pausa para anuncios principal (indexado por 0). | Inicio del anuncio, Cierre del anuncio | `a.media.ad.`<br>`podPosition` | `xdm.mediaCollection.`<br>`advertisingDetails.podPosition`<br><br>`xdm.mediaReporting.`<br>`advertisingDetails.podPosition` |
| **[!UICONTROL Anunciante]** | La empresa o marca que aparece en el anuncio. | Inicio del anuncio, Cierre del anuncio | `a.media.ad.`<br>`advertiser` | `xdm.mediaCollection.`<br>`advertisingDetails.advertiser`<br><br>`xdm.mediaReporting.`<br>`advertisingDetails.advertiser` |
| **[!UICONTROL ID de campaña]** | ID de la campaña de publicidad | Inicio del anuncio, Cierre del anuncio | `a.media.ad.`<br>`campaign` | `xdm.mediaCollection.`<br>`advertisingDetails.campaignID`<br><br>`xdm.mediaReporting.`<br>`advertisingDetails.campaignID` |

Además de las dimensiones anteriores, Adobe crea automáticamente las siguientes dimensiones de clasificación. Debe cargar datos de clasificación para ver los informes que utilizan estas dimensiones.

| Nombre de clasificación | Dimensión principal | Descripción |
| --- | --- | --- |
| **[!UICONTROL ID de recurso]** | [[!UICONTROL Contenido]](sm-core.md) | El identificador único del contenido del recurso de medios. Algunos ejemplos son el identificador de episodio de series de TV, el identificador de recursos de una película o el identificador de eventos en directo. Estos ID generalmente se derivan de autoridades de metadatos como EIDR, TMS/Gracenote, Rovi o de otros sistemas propietarios o internos. |
| **[!UICONTROL Clasificación del contenido]** | [[!UICONTROL Contenido]](sm-core.md) | La calificación definida por las pautas parentales de TV. |
| **[!UICONTROL Primera fecha de emisión]** | [[!UICONTROL Contenido]](sm-core.md) | La fecha en la que el contenido se emitió por primera vez en televisión. Dado que esta dimensión de clasificación es una cadena, se permite cualquier formato de fecha. Adobe recomienda usar un formato de fecha coherente, como `YYYY-MM-DD`. |
| **[!UICONTROL Primera fecha digital]** | [[!UICONTROL Contenido]](sm-core.md) | La fecha en la que el contenido se emitió por primera vez en cualquier canal o plataforma digital. Dado que esta dimensión de clasificación es una cadena, se permite cualquier formato de fecha. Adobe recomienda usar un formato de fecha coherente, como `YYYY-MM-DD`. |
| **[!UICONTROL Longitud del anuncio]** | [!UICONTROL Anuncio] | Duración del anuncio de vídeo, en segundos. |
| **[!UICONTROL Nombre del anuncio]** | [!UICONTROL Anuncio] | Nombre descriptivo del anuncio. Es el equivalente de clasificación de &#39;[!UICONTROL Ad name (variable)]&#39;. |
| **[!UICONTROL ID. DE Creative]** | [!UICONTROL Anuncio] | El ID del creador de la publicidad. |
| **[!UICONTROL Nombre de la secuencia]** | [!UICONTROL pod de anuncios] | Nombre descriptivo del pod de anuncios. |
| **[!UICONTROL Posición de la secuencia]** | [!UICONTROL pod de anuncios] | El desplazamiento del desglose de anuncios dentro del contenido, en segundos. |

---
title: Dimensiones y servicios de medios de streaming
description: Dimensiones disponibles al habilitar [!UICONTROL Anuncios multimedia] para un grupo de informes.
feature: Dimensions
exl-id: 3f17bacc-8c36-499a-a863-9298e2d54370
source-git-commit: 7609ecb3c34fb0bc8293fc1ecd409cfabb327295
workflow-type: tm+mt
source-wordcount: '464'
ht-degree: 15%

---

# Dimensiones y servicios de medios de streaming

*Esta página describe las dimensiones disponibles cuando se habilita [!UICONTROL Anuncios multimedia] para un grupo de informes. Consulte [Métricas de anuncios de medios de streaming](../metrics/sm-ads.md) para ver las métricas disponibles*.

Las dimensiones y los servicios de medios de streaming proporcionan una funcionalidad de creación de informes suplementaria para la recopilación de datos a través de las bibliotecas de los servicios de medios de streaming. El uso de estas dimensiones requiere el **[!UICONTROL complemento de Adobe Analytics para medios de streaming]**. Póngase en contacto con el equipo de su cuenta de Adobe para obtener más información.

Cuando habilita **[!UICONTROL Anuncios multimedia]** en [Informes multimedia](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/media-management.md), están disponibles las siguientes dimensiones:

| Nombre de la dimensión | Descripción | Enviado con | Variable de datos de contexto |
| --- | --- | --- | --- |
| Publicidad | El identificador único del anuncio. | Inicio del anuncio, Cierre del anuncio | `a.media.ad.name` |
| Nombre del anuncio (variable) | Nombre descriptivo del anuncio. También está disponible una dimensión de clasificación denominada &quot;Nombre del anuncio&quot;, que proporciona un propósito similar. Esta dimensión y la clasificación se tratan como dos dimensiones distintas. | Inicio del anuncio, Cierre del anuncio | `a.media.ad.friendlyName` |
| Nombre del reproductor del anuncio | Nombre del reproductor que procesa el anuncio. | Inicio del anuncio, Cierre del anuncio | `a.media.ad.playerName` |
| Duración del anuncio (variable) | Duración del anuncio de vídeo, en segundos. | Inicio del anuncio, Cierre del anuncio | `a.media.ad.length` |
| Pod de anuncios | El identificador único del pod de anuncios. | Inicio del anuncio, Cierre del anuncio | `a.media.ad.pod` |
| Posición del anuncio en la secuencia | La posición de índice del anuncio dentro de la pausa para anuncios principal (indexado por 0). | Inicio del anuncio, Cierre del anuncio | `a.media.ad.podPosition` |
| Anunciante | La empresa o marca que aparece en el anuncio. | Inicio del anuncio, Cierre del anuncio | `a.media.ad.advertiser` |
| ID de campaña | ID de la campaña de publicidad | Inicio del anuncio, Cierre del anuncio | `a.media.ad.campaign` |

{style="table-layout:auto"}

Además de las dimensiones anteriores, Adobe crea automáticamente las siguientes dimensiones de clasificación. Debe cargar datos de clasificación para ver los informes que utilizan estas dimensiones.

| Nombre de clasificación | Dimensión principal | Descripción |
| --- | --- | --- |
| ID del recurso | [Contenido](sm-core.md) | El identificador único del contenido del recurso de medios. Algunos ejemplos son el identificador de episodio de series de TV, el identificador de recursos de una película o el identificador de eventos en directo. Estos ID generalmente se derivan de autoridades de metadatos como EIDR, TMS/Gracenote, Rovi o de otros sistemas propietarios o internos. |
| Calificación de contenido | [Contenido](sm-core.md) | La calificación definida por las pautas parentales de TV. |
| Fecha de la primera emisión | [Contenido](sm-core.md) | La fecha en la que se emitió por primera vez el contenido en televisión. Dado que esta dimensión de clasificación es una cadena, se permite cualquier formato de fecha. Adobe recomienda usar un formato de fecha coherente, como `YYYY-MM-DD`. |
| Fecha de la primera emisión digital | [Contenido](sm-core.md) | La fecha en la que se emitió por primera vez el contenido en cualquier canal o plataforma digital. Dado que esta dimensión de clasificación es una cadena, se permite cualquier formato de fecha. Adobe recomienda usar un formato de fecha coherente, como `YYYY-MM-DD`. |
| Duración del anuncio | Publicidad | Duración del anuncio de vídeo, en segundos. |
| Nombre del anuncio | Publicidad | Nombre descriptivo del anuncio. Es el equivalente de clasificación de &quot;Nombre del anuncio (variable)&quot;. |
| ID del creativo | Publicidad | El ID del creador de la publicidad. |
| Nombre de pod | Pod de anuncios | Nombre descriptivo del pod de anuncios. |
| Posición del pod | Pod de anuncios | El desplazamiento del desglose de anuncios dentro del contenido, en segundos. |

{style="table-layout:auto"}

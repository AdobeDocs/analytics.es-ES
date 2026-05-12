---
title: Dimensiones y servicios de medios de streaming
description: Dimensiones disponibles al habilitar [!UICONTROL Anuncios multimedia] para un grupo de informes.
feature: Dimensions
exl-id: 3f17bacc-8c36-499a-a863-9298e2d54370
TQID: https://experienceleague.adobe.com/5d5RQ-2dkRD-R5U0iVyApP7WdCH2O1Rsk-qlPLYJm9c
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dcid: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 1be0f3577403db7cf9bd40ef9e7c4bfcfa6c0b17
workflow-type: tm+mt
source-wordcount: 353
ht-degree: 2%

---

# Dimensiones y servicios de medios de streaming

Las dimensiones y los servicios de medios de streaming proporcionan una funcionalidad adicional de creación de informes para los datos recopilados a través de las bibliotecas de recopilación de medios de streaming. Estas dimensiones requieren el **[!UICONTROL complemento de Adobe Analytics para medios de streaming]**. Póngase en contacto con el equipo de su cuenta de Adobe para obtener más información.

Para usar estas dimensiones, habilite **[!UICONTROL Anuncios multimedia]** en [[!UICONTROL Informes multimedia]](/help/admin/tools/manage-rs/edit-settings/media-management.md) para el grupo de informes.

Las dimensiones disponibles son las siguientes:

* [[!UICONTROL Anuncio]](https://experienceleague.adobe.com/en/docs/media-analytics/using/reporting/dimensions/ad)
* [[!UICONTROL Posición del anuncio en la secuencia]](https://experienceleague.adobe.com/en/docs/media-analytics/using/reporting/dimensions/ad-in-pod-position)
* [[!UICONTROL Longitud del anuncio (variable)]](https://experienceleague.adobe.com/en/docs/media-analytics/using/reporting/dimensions/ad-length)
* [[!UICONTROL Nombre del anuncio (variable)]](https://experienceleague.adobe.com/en/docs/media-analytics/using/reporting/dimensions/ad-name)
* [[!UICONTROL Nombre del reproductor del anuncio]](https://experienceleague.adobe.com/en/docs/media-analytics/using/reporting/dimensions/ad-player-name)
* [[!UICONTROL pod de anuncios]](https://experienceleague.adobe.com/en/docs/media-analytics/using/reporting/dimensions/ad-pod)
* [[!UICONTROL Anunciante]](https://experienceleague.adobe.com/en/docs/media-analytics/using/reporting/dimensions/advertiser)
* [[!UICONTROL ID de campaña]](https://experienceleague.adobe.com/en/docs/media-analytics/using/reporting/dimensions/campaign-id)

Además de las dimensiones anteriores, Adobe crea automáticamente las siguientes dimensiones de clasificación. Debe cargar datos de clasificación para ver los informes que utilizan estas dimensiones.

| Nombre de clasificación | Dimensión principal |
| --- | --- |
| [[!UICONTROL ID de recurso]](https://experienceleague.adobe.com/en/docs/media-analytics/using/reporting/dimensions/asset-id) | [[!UICONTROL Contenido]](sm-core.md) |
| [[!UICONTROL Clasificación del contenido]](https://experienceleague.adobe.com/en/docs/media-analytics/using/reporting/dimensions/content-rating) | [[!UICONTROL Contenido]](sm-core.md) |
| [[!UICONTROL Primera fecha de emisión]](https://experienceleague.adobe.com/en/docs/media-analytics/using/reporting/dimensions/first-air-date) | [[!UICONTROL Contenido]](sm-core.md) |
| [[!UICONTROL Primera fecha digital]](https://experienceleague.adobe.com/en/docs/media-analytics/using/reporting/dimensions/first-digital-date) | [[!UICONTROL Contenido]](sm-core.md) |
| [[!UICONTROL Longitud del anuncio]](https://experienceleague.adobe.com/en/docs/media-analytics/using/reporting/dimensions/ad-length) | [!UICONTROL Anuncio] |
| [[!UICONTROL Nombre del anuncio]](https://experienceleague.adobe.com/en/docs/media-analytics/using/reporting/dimensions/ad-name) | [!UICONTROL Anuncio] |
| [[!UICONTROL ID. de Creative]](https://experienceleague.adobe.com/en/docs/media-analytics/using/reporting/dimensions/creative-id) | [!UICONTROL Anuncio] |
| [[!UICONTROL Nombre de la secuencia]](https://experienceleague.adobe.com/en/docs/media-analytics/using/reporting/dimensions/pod-name) | [!UICONTROL pod de anuncios] |
| [[!UICONTROL Posición de la secuencia]](https://experienceleague.adobe.com/en/docs/media-analytics/using/reporting/dimensions/pod-position) | [!UICONTROL pod de anuncios] |

Consulte [Métricas y servicios de medios de streaming](../metrics/sm-ads.md) para ver las métricas correspondientes.

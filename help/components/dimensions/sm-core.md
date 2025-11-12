---
title: Dimensiones principales de los servicios de medios de streaming
description: Dimensiones disponibles al habilitar [!UICONTROL Media Core] para un grupo de informes.
feature: Dimensions
exl-id: 1316a646-a31a-49a4-a670-d56d90dd462b
source-git-commit: 936644c719f46a1327c8a5aa247ed69a14d3da1e
workflow-type: tm+mt
source-wordcount: '418'
ht-degree: 7%

---

# Dimensiones principales de los servicios de medios de streaming

*Esta página describe las dimensiones disponibles cuando se habilita [!UICONTROL Media Core] para un grupo de informes. Consulte [Métricas principales de servicios de medios de streaming](../metrics/sm-core.md) para ver las métricas disponibles*.

Las dimensiones principales de los servicios de medios de streaming proporcionan una funcionalidad básica de creación de informes a los datos recopilados a través de las bibliotecas de los servicios de medios de streaming. El uso de estas dimensiones requiere el **[!UICONTROL complemento de Adobe Analytics para medios de streaming]**. Póngase en contacto con el equipo de su cuenta de Adobe para obtener más información.

Cuando habilita **[!UICONTROL Componentes básicos de medios]** en [Informes de medios](/help/admin/tools/manage-rs/edit-settings/media-management.md), están disponibles las siguientes dimensiones:

| Nombre de la dimensión | Descripción | Enviado con | Variable de datos de contexto | Campo XDM |
| --- | --- | --- | --- | --- |
| **[!UICONTROL Contenido]** | ID del contenido. | Inicio de contenidos, Cierre de contenidos | `a.media.`<br>`name` | `xdm.mediaCollection.`<br>`sessionDetails.name`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.name` |
| **[!UICONTROL Canal de contenido]** | Estación o canal de distribución donde se reproduce el contenido. Cualquier valor de cadena es válido. | Inicio de contenidos, Cierre de contenidos | `a.media.`<br>`channel` | `xdm.mediaCollection.`<br>`sessionDetails.channel`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.channel` |
| **[!UICONTROL Longitud del contenido (variable)]** | Longitud máxima (o duración) del contenido consumido, en segundos. Esta dimensión es necesaria para varias métricas, incluida &#39;[!UICONTROL Audiencia media por minuto]&#39;. Si no se establece esta dimensión, las métricas dependientes no estarán disponibles.<br><br>También hay disponible una dimensión de clasificación denominada &#39;[!UICONTROL Longitud del vídeo]&#39;, que proporciona un propósito similar. Esta dimensión y la clasificación se tratan como dos dimensiones distintas. | Inicio de contenidos, Cierre de contenidos | `a.media.`<br>`length` | `xdm.mediaCollection.`<br>`sessionDetails.length`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.length` |
| **[!UICONTROL Nombre de contenido (variable)]** | Nombre descriptivo del contenido. También hay disponible una clasificación con el nombre &#39;[!UICONTROL Video name]&#39;, que proporciona un propósito similar. Esta dimensión y la clasificación se tratan como dos dimensiones distintas. | Inicio de contenidos, Cierre de contenidos | `a.media.`<br>`friendlyName` | `xdm.mediaCollection.`<br>`sessionDetails.friendlyName`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.friendlyName` |
| **[!UICONTROL Nombre del reproductor de contenido]** | Nombre del reproductor de contenido. | Inicio de contenidos, Cierre de contenidos | `a.media.`<br>`playerName` | `xdm.mediaCollection.`<br>`sessionDetails.playerName`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.playerName` |
| **[!UICONTROL Segmento de contenido]** | Intervalo que describe la parte del contenido que se ha visto, en minutos. El segmento se calcula como un mínimo y un máximo de los valores del cabezal de reproducción durante una sesión de reproducción. | Cierre de medios | `a.media.`<br>`segment` | `xdm.mediaReporting.`<br>`sessionDetails.segment` |
| **[!UICONTROL Tipo de contenido]** | El tipo de contenido. Los valores válidos incluyen `song`, `podcast`, `audiobook`, `radio`, `VoD`, `Live`, `Linear`, `UGC`, `DVoD` o un valor personalizado. | Inicio de contenidos, Cierre de contenidos | `a.contentType` | `xdm.mediaCollection.`<br>`sessionDetails.contentType`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.contentType` |
| **[!UICONTROL Ruta de medios]** | La ruta que tomó el visitante para llegar al contenido. | Inicio de medios | `a.media.path` | |
| **[!UICONTROL Tipo de emisión]** | El tipo de flujo. Los valores válidos incluyen `audio` y `video`. | Inicio de contenidos, Cierre de contenidos | `a.media.`<br>`streamType` | `xdm.mediaCollection.`<br>`sessionDetails.streamType`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.streamType` |

Además de las dimensiones anteriores, Adobe crea automáticamente las siguientes dimensiones de clasificación. Debe cargar datos de clasificación para ver los informes que utilizan estas dimensiones.

| Nombre de clasificación | Dimensión principal | Descripción |
| --- | --- | --- |
| **[!UICONTROL Longitud del vídeo]** | [!UICONTROL Contenido] | Longitud máxima (o duración) del contenido consumido, en segundos. Las métricas que dependen de la longitud del contenido no pueden utilizar esta clasificación; debe crear una métrica calculada para obtener métricas como &#39;[!UICONTROL Audiencia media por minuto]&#39; mediante esta clasificación. |
| **[!UICONTROL Nombre del vídeo]** | [!UICONTROL Contenido] | Nombre descriptivo del contenido. Es el equivalente de clasificación de &#39;[!UICONTROL Content name (variable)]&#39;. |

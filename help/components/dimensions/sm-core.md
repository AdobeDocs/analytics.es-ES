---
title: Dimensiones principales de medios de streaming
description: Dimensiones disponibles al habilitar [!UICONTROL Media Core] para un grupo de informes.
feature: Dimensions
exl-id: 1316a646-a31a-49a4-a670-d56d90dd462b
source-git-commit: fdd66c9558f070cd760f37a39e5911f0dac22612
workflow-type: tm+mt
source-wordcount: '410'
ht-degree: 10%

---

# Dimensiones principales de medios de streaming

*Esta página describe las dimensiones disponibles cuando se habilita [!UICONTROL Media Core] para un grupo de informes. Consulte [Métricas principales de medios de streaming](../metrics/sm-core.md) para ver las métricas disponibles*.

Las dimensiones principales de los medios de streaming proporcionan funcionalidad básica de creación de informes a los datos recopilados mediante bibliotecas de recopilación de medios de streaming. El uso de estas dimensiones requiere la **[!UICONTROL recopilación de medios de streaming de Adobe]**. Póngase en contacto con el equipo de cuenta de Adobe para obtener más información.

Cuando habilita **[!UICONTROL Componentes básicos de medios]** en [Informes de medios](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/media-management.md), están disponibles las siguientes dimensiones:

| Nombre de la dimensión | Descripción | Enviado con | Variable de datos de contexto |
| --- | --- | --- | --- |
| Contenido | ID del contenido. | Inicio de contenidos, Cierre de contenidos | `a.media.name` |
| Canal de contenido | Estación o canal de distribución donde se reproduce el contenido. Cualquier valor de cadena es válido. | Inicio de contenidos, Cierre de contenidos | `a.media.channel` |
| Longitud del contenido (variable) | Longitud máxima (o duración) del contenido consumido, en segundos. Esta dimensión es necesaria para varias métricas, incluida la &quot;Audiencia media por minuto&quot;. Si no se establece esta dimensión, las métricas dependientes no estarán disponibles.<br><br>También hay disponible una dimensión de clasificación denominada &#39;Longitud del vídeo&#39;, que proporciona un propósito similar. Esta dimensión y la clasificación se tratan como dos dimensiones distintas. | Inicio de contenidos, Cierre de contenidos | `a.media.length` |
| Nombre del contenido (variable) | Nombre descriptivo del contenido. También está disponible una clasificación denominada &quot;Nombre del vídeo&quot;, que tiene un propósito similar. Esta dimensión y la clasificación se tratan como dos dimensiones distintas. | Inicio de contenidos, Cierre de contenidos | `a.media.friendlyName` |
| Nombre del reproductor de contenido | Nombre del reproductor de contenido. | Inicio de contenidos, Cierre de contenidos | `a.media.playerName` |
| Segmento de contenido | Intervalo que describe la parte del contenido que se ha visto, en minutos. El segmento se calcula como un mínimo y un máximo de los valores del cabezal de reproducción durante una sesión de reproducción. | Cierre de medios | `a.media.segment` |
| Tipo de contenido | El tipo de contenido. Los valores válidos incluyen `song`, `podcast`, `audiobook`, `radio`, `VoD`, `Live`, `Linear`, `UGC`, `DVoD` o un valor personalizado. | Inicio de contenidos, Cierre de contenidos | `a.contentType` |
| Ruta de medios | La ruta que tomó el visitante para llegar al contenido. | Inicio de medios | `a.media.path` |
| Tipo de emisión | Tipo de flujo. Los valores válidos incluyen `audio` y `video`. | Inicio de contenidos, Cierre de contenidos | `a.media.streamType` |

{style="table-layout:auto"}

Además de las dimensiones anteriores, Adobe crea automáticamente las siguientes dimensiones de clasificación. Debe cargar datos de clasificación para ver los informes que utilizan estas dimensiones.

| Nombre de clasificación | Dimensión principal | Descripción |
| --- | --- | --- |
| Duración del vídeo | Contenido | Longitud máxima (o duración) del contenido consumido, en segundos. Las métricas que dependen de la longitud del contenido no pueden utilizar esta clasificación; debe crear una métrica calculada para obtener métricas como &quot;Audiencia media por minuto&quot; mediante esta clasificación. |
| Nombre del vídeo | Contenido | Nombre descriptivo del contenido. Es el equivalente de clasificación de Nombre del contenido (variable). |

{style="table-layout:auto"}

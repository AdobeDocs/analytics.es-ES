---
description: 'null'
keywords: Fuente de datos;trabajo;visitantes;ID de Experience Cloud;ID de visitante de Analytics;identificar
seo-description: 'null'
seo-title: Identificar visitantes
solution: Analytics
title: Identificar visitantes
topic: Reports and Analytics
uuid: 2490b67e-a333-422d-82fa-cb0670ef2e0c
translation-type: tm+mt
source-git-commit: 0dbc8ac9b416ce50f197a884bb71c6cd389cd0bb

---


# Identificar visitantes

Analytics proporciona varios métodos que permiten identificar a los visitantes (enumerados en [Identificación de visitantes](../../../export/analytics-data-feed/c-df-contents/datafeeds-visid.md#concept_BE966BABA7D0475BB706BC6676B8FA11)). Regardless of the method used to identify a visitor, in data feeds the final visitor ID used by Analytics is split across the `post_visid_high` and `post_visid_low` columns, even when using the Identity Service.

**Para identificar visitantes únicos:**

1. Exclude all rows where `exclude_hit > 0`.
1. Exclude all rows with `hit_source = 5,7,8,9`. 5, 8, y 9 son filas de resumen cargadas mediante fuentes de datos. 7 representa las cargas de fuentes de datos del ID de transacción que no se deben incluir en los recuentos de visitas y de visitantes. Consulte [Búsqueda de la fuente de visitas](../../../export/analytics-data-feed/c-df-contents/datafeeds-hit-source.md#concept_FE4C114F6A524F7593D5CAC944C36C42)
1. Combinar `post_visid_high` con `post_visid_low`. All hits across all dates that contain this combination of `post_visid_high` and `post_visid_low` can be considered as coming from same visitor.

Si desea determinar qué mecanismo se utilizó para determinar el valor de ID de visitante (por ejemplo, para calcular la aceptación de cookies), `post_visid_type` contiene un clave de búsqueda que indica qué método de ID se utilizó. Las claves de búsqueda se enumeran junto a los mecanismos de ID de visitante en la [tabla siguiente](../../../export/analytics-data-feed/c-df-contents/datafeeds-visid.md#table_D267D36451F643D1BB68AF6FEAA6AD1A).

## Experience Cloud ID {#section_1628ED37D31E4B0EB75632E397A06B29}

El Experience Cloud ID se informa en una columna separada, `mcvisid`. Debido a que este ID se incluye en su propia columna, puede no quedar claro si Analytics utiliza este ID o un ID diferente para identificar a un visitante.

If the Experience Cloud ID was used to identify the visitor, the ID will be contained in the `post_visid_high` and `post_visid_low` columns and the `post_visid_type` will be set to 5. When calculating metrics, you should use the value from the `post_visid_high` and `post_visid_low` columns since these columns will always contain the final visitor ID.

>[!TIP]
>
> When using the Adobe Analytics visitor ID as a key for other systems, always use `post_visid_high` and `post_visid_low`. Estos campos son los únicos campos de ID de visitante garantizados que tienen un valor con cada fila en la fuente de datos.

## ID del visitante de Analytics {#section_DE1DC9FC9B6D4388995B70E35B8BCDDF}

Existen muchas maneras mediante las que se puede identificar un visitante en Analytics (enumeradas en la tabla siguiente en orden de preferencia):

| Orden utilizado | Parámetro de consulta (método de colección) | valor de columna post_visid_type | Presente si |
|---|---|---|---|
| ![](assets/step1_icon.png) | [vid (s.visitorID)](https://marketing.adobe.com/resources/help/en_US/sc/implement/visid_custom.html) | 0 | s.visitorID está establecido. |
| ![](assets/step2_icon.png) | [aid (s_vi cookie)](https://marketing.adobe.com/resources/help/en_US/sc/implement/visid_analytics.html) | 3 | El visitante tenía una cookie existente s_vi antes de que implementara el servicio de ID del visitante, o haya configurado un [período de gracia](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_grace_period.html) del ID del visitante. |
| ![](assets/step3_icon.png) | [mid (cookie AMCV_ establecida por Identity Service)](https://marketing.adobe.com/resources/help/en_US/mcvid/) | 5 | El explorador del visitante acepta cookies (de origen) y se implementa el servicio de identidad. |
| ![](assets/step4_icon.png) | [fid (cookie de respaldo en H.25.3 o superior, o AppMeasurement para JavaScript)](https://marketing.adobe.com/resources/help/en_US/sc/implement/visid_fallback.html) | 4 | El navegador del visitante acepta cookies (personales). |
| ![](assets/step5_icon.png) | [Cabecera de suscriptor móvil HTTP](https://marketing.adobe.com/resources/help/en_US/sc/implement/visid_mobile.html) | 2 | El dispositivo se ha reconocido como un dispositivo móvil. |
| ![](assets/step6_icon.png) | [Dirección IP, agente de usuario y dirección IP de puerta de enlace](https://marketing.adobe.com/resources/help/en_US/sc/implement/visid_fallback.html) | 1 | El navegador del visitante no acepta cookies. |

En muchos escenarios puede que vea 2 o 3 ID diferentes en una llamada, pero Analytics utilizará el primer ID presente de la lista como ID de visitante oficial, y dividirá el valor en las columnas `post_visid_high` y `post_visid_low`. Por ejemplo, si configura un ID de visitante personalizado (incluido en el parámetro de consulta "vid"), ese ID se utilizará antes que otros ID que puedan existir en la misma visita.

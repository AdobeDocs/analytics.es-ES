---
description: En la versión 14, "visitante único" hace referencia a un visitante que visita un sitio por primera vez durante un período de tiempo especificado. Por ejemplo, el visitante único puede visitar un sitio diez veces en una semana pero, si el período de tiempo es una semana, cada visitante único se contará solamente una vez en esa semana. Cuando termine esa semana, ese visitante único se podrá contar de nuevo en otro período de tiempo.
title: Visitantes únicos
topic: Metrics
uuid: ae210698-99f9-485e-a640-c7520807adc7
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Visitantes únicos

En la versión 14, "visitante único" hace referencia a un visitante que visita un sitio por primera vez durante un período de tiempo especificado. Por ejemplo, el visitante único puede visitar un sitio diez veces en una semana pero, si el período de tiempo es una semana, cada visitante único se contará solamente una vez en esa semana. Cuando termine esa semana, ese visitante único se podrá contar de nuevo en otro período de tiempo.

## Diferencias entre la versión 14 y la versión 15

La versión 14 no elimina las métricas duplicadas de [!UICONTROL Visitas] y [!UICONTROL Visitantes únicos] de los informes basados en clasificaciones. Por ejemplo, si dos clips de vídeo compartían la misma clasificación, un visitante único que viera ambos clips generaría dos [!UICONTROL visitas] y [!UICONTROL visitantes únicos] en el informe basado en clasificaciones.

La versión 15 elimina las [!UICONTROL visitas] y los [!UICONTROL visitantes únicos] del informe basado en clasificaciones. Esta medida de las [!UICONTROL visitas] y los [!UICONTROL visitantes] es más fiel a la realidad, pero suele provocar un descenso en la métrica de [!UICONTROL visitas] y [!UICONTROL visitantes únicos] en los informes de clasificación, si se compara con los datos que se recopilaron antes de la actualización.

| Usos | Descripción |
|---|---|
| Tráfico | Un visitante es una persona que llega al sitio web. No requiere de una cookie persistente. |
| Conversión | Un visitante es una persona que llega al sitio web. Se contabiliza cuando se produce una acción o un evento relacionado con la conversión. |
| Ad Hoc Analysis  | Un visitante es una persona que llega al sitio web. No requiere de una cookie persistente. |

Consulte [Informe Visitantes únicos - Versión 15 y Ad Hoc Analysis](/help/components/c-variables/dimensionslist/reports-unique-visitors-v15-dsc.md).

>[!MORELIKETHIS]
>
>* [Visitantes únicos diarios](/help/components/c-variables/c-metrics/metrics-daily-unique-visitors.md)


---
title: Analizar datos afectados por eventos
description: Comprender cómo los datos afectados por un evento contribuyen a la calidad general de los datos.
translation-type: tm+mt
source-git-commit: 09c7c1f4b4a6f67243cc72c642fd83a75406fb76

---


# Analizar datos afectados por eventos

A veces, un evento puede afectar a la calidad de los datos de la organización. Algunos ejemplos son:

* Un bot que envía datos externos, como millones de dólares en ingresos
* Su organización insertó una actualización en el sitio web que afectó negativamente a la implementación de Analytics
* Otros problemas que afectan a la calidad o integridad de los datos

Si el sitio ha experimentado problemas de calidad de los datos, problemas de implementación u otros vacíos en los datos, es posible que desee excluirlos del sistema de informes para evitar tomar decisiones sobre los datos parciales. Utilice estas secciones para medir el impacto del evento en los datos y determinar cómo desea continuar.

## Analizar y excluir datos mediante la segmentación

Adobe Analytics oferta una forma sencilla y sólida de centrarse en los datos o excluirlos mediante la segmentación. Puede utilizar dimensiones de intervalo de fechas dentro de segmentos para filtrar o centrarse en esas fechas específicas. Consulte [Excluir fechas específicas en la análisis](/help/components/c-segmentation/use-cases/exclude-date-range.md) en la guía del usuario Componentes.

## Comparar un evento con intervalos de fechas anteriores

Si desea obtener más información sobre el impacto que un evento ha tenido en los datos a lo largo del tiempo, puede usar la comparación de fechas en el área de Análisis. Esta función le permite comparar datos día a día, semana a semana o mes a mes para ver cómo se compara con intervalos anteriores. A continuación, puede utilizar esta comparación para determinar en qué medida un evento afecta a las tendencias. Consulte [Comparación de fechas afectadas por un evento con rangos](/help/analyze/analysis-workspace/components/calendar-date-ranges/compare-event.md) anteriores en la guía del usuario Analizar.

## Usar un evento de calendario en Informes y análisis

Si utiliza Informes y análisis, puede utilizar un evento [de](/help/components/t-calendar-event.md) calendario para resaltar los días afectados en cualquier informe de tendencias. Este método no se aplica a Análisis Workspace.

1. Vaya a **[!UICONTROL Components]** > **[!UICONTROL Calendar events]**.
2. Introduzca el título, el intervalo de fechas y el texto de la nota que desee.
3. Haga clic en **[!UICONTROL Save]**.

![evento de calendario](assets/exclude_calendar_event.jpg)

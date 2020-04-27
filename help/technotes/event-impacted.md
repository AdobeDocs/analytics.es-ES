---
title: Analizar datos afectados por eventos
description: Comprender cómo los datos afectados por un evento contribuyen a la calidad general de los datos.
translation-type: tm+mt
source-git-commit: 65f5fad547558cc9dc481f0eca72873815c9d13a

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

## Obtener datos mediante métricas calculadas

Una vez que haya creado segmentos y utilizado la comparación de fechas, puede combinar ambos conceptos para corregir los datos de tendencias mediante métricas calculadas. Incluya los segmentos dentro de una métrica calculada y luego multiplique los días afectados por el desplazamiento encontrado al comparar fechas. Consulte [Derivar datos afectados por eventos](/help/components/c-calcmetrics/cm-events.md) en la guía del usuario Componentes.

## Comunicar el impacto a los usuarios de su organización

Una vez que esté preparado para manejar un evento, puede [comunicarse con los usuarios de su organización](event/event-communicate.md). Adobe oferta varios lugares dentro de Analytics en los que puede colocar texto para comunicar a los usuarios qué ha sucedido y qué componentes pueden utilizar.

## Vídeo

Este vídeo recorre cada uno de los pasos anteriores.

>[!VIDEO](https://video.tv.adobe.com/v/33316?quality=12)

* **0:27**: Excluir datos mediante segmentación
* **2:55**: Comparar un evento con rangos anteriores
* **8:42**: Obtener datos mediante métricas calculadas
* **11:46**: Comunicar el impacto a los usuarios

---
title: Analizar datos afectados por eventos
description: Comprender cómo los datos afectados por un evento contribuyen a la calidad general de los datos.
translation-type: ht
source-git-commit: 178e372e63c436268a1f7028d986504983430b2f
workflow-type: ht
source-wordcount: '390'
ht-degree: 100%

---


# Analizar datos afectados por eventos

A veces, un evento puede afectar a la calidad de los datos de la organización. Algunos ejemplos son:

* Un bot que envía datos periféricos, como millones de dólares en ingresos
* Su organización insertó una actualización en el sitio web que afectó negativamente a la implementación de Analytics
* Otros problemas que afectan a la calidad o integridad de los datos

Si el sitio ha experimentado algún tipo de problema de calidad de los datos, es posible que desee excluirlo de la creación de informes para evitar que se tomen decisiones comerciales al respecto. Utilice estas secciones para medir el impacto del evento en los datos y determinar cómo desea continuar.

## Determinar la causa de un evento

Si no está seguro de por qué se ve un pico o una caída en los datos, consulte [Solución de problemas de picos o caídas en los datos](spikes-drops.md).

## Analizar y excluir datos mediante la segmentación

Adobe Analytics ofrece una forma sencilla y sólida de centrarse en los datos o excluirlos mediante la segmentación. Puede utilizar dimensiones de intervalo de fechas dentro de segmentos para filtrar o centrarse en esas fechas específicas. Consulte [Excluir fechas específicas en el análisis](segments.md).

## Comparar un evento con intervalos de fechas anteriores

Si desea obtener más información sobre el impacto que un evento ha tenido en los datos a lo largo del tiempo, puede usar la comparación de fechas en Analysis Workspace. Esta función le permite comparar datos día a día, semana a semana o mes a mes para ver cómo se compara con intervalos anteriores. A continuación, puede utilizar esta comparación para determinar en qué medida un evento afecta a las tendencias. Consulte [Comparar fechas afectadas por un evento con intervalos anteriores](compare-dates.md).

## Obtener datos mediante métricas calculadas

Una vez que haya creado segmentos y utilizado la comparación de fechas, puede combinar ambos conceptos para corregir los datos de tendencias mediante métricas calculadas. Incluya los segmentos dentro de una métrica calculada y luego multiplique los días afectados por el desajuste encontrado al comparar fechas. Consulte [Derivar datos afectados por eventos](calcmetrics.md).

## Comunicar el impacto a los usuarios de su organización

Una vez que esté preparado para gestionar un evento, puede [comunicarse con los usuarios de su organización](communicate.md). Adobe ofrece varios lugares dentro de Analytics en los que puede colocar texto para comunicar a los usuarios qué ha sucedido y qué componentes pueden utilizar.

## Vídeo

Este vídeo muestra cada uno de los pasos anteriores.

>[!VIDEO](https://video.tv.adobe.com/v/33316?quality=12&captions=spa)

* **0:27**: Excluir datos mediante la segmentación
* **2:55**: Comparar un evento con intervalos anteriores
* **8:42**: Obtener datos mediante métricas calculadas
* **11:46**: Comunicar el impacto a los usuarios

---
title: Obtener datos afectados por eventos
description: Utilice las métricas calculadas para corregir los datos de tendencias afectados por un evento.
translation-type: tm+mt
source-git-commit: 1ffbd728aba893d7f7a4ecf027c479fc753e371a

---


# Obtener datos afectados por eventos

Si los datos [se ven afectados por un evento](/help/technotes/event-impacted.md), puede utilizar métricas calculadas para derivar valores de tendencias durante el evento. Por ejemplo, si tuvo un evento que causó una caída del 25 % en los datos, puede utilizarlo como multiplicador en una métrica calculada. Este método resulta útil si no tiene tiempo o recursos para insertar datos en Adobe Analytics mediante fuentes [](/help/import/c-data-sources/datasrc-home.md) de datos o la API [](/help/import/c-data-insertion-api/c-data-insertion-api.md)de inserción de datos.

>[!NOTE] Estos pasos funcionan mejor cuando se comprende el impacto de un evento, tanto desde una perspectiva de segmentación como de comparación de fechas. Asegúrese de seguir [Comparar fechas afectadas por un evento con intervalos](/help/analyze/analysis-workspace/components/calendar-date-ranges/compare-event.md) anteriores y [Excluir fechas específicas en análisis](../c-segmentation/use-cases/exclude-date-range.md) antes de seguir esta página.

1. Cree dos segmentos para &#39;Días afectados&#39; y &#39;Excluir días afectados&#39;, tal como se describe en [Excluir fechas específicas en la análisis](../c-segmentation/use-cases/exclude-date-range.md).
2. Vaya a **[!UICONTROL Components]** > **[!UICONTROL Calculated metrics]**.
3. Haga clic en **[!UICONTROL Add]**.
4. Arrastre los dos segmentos anteriores al lienzo de definición. Cambie el operador entre ellos a un `+` para sumarlos.
5. Añada la métrica deseada dentro de ambos segmentos. Por ejemplo, puede utilizar la métrica &quot;Visitas&quot;.

   ![Generador de segmentos](assets/event_segment_builder.png)

6. Haga clic **[!UICONTROL Add]** en en la parte superior derecha del contenedor &#39;Días afectados&#39; y luego haga clic en **[!UICONTROL Static number]**. Establezca el número estático en el porcentaje que desea desplazar los datos, como se describe en [Comparar fechas afectadas por un evento con intervalos](/help/analyze/analysis-workspace/components/calendar-date-ranges/compare-event.md)anteriores. En este ejemplo, el desplazamiento es 25 % o 1,25.

   ![Número estático](assets/event_static_number.png)

7. Aplique la métrica &quot;corregida&quot; de forma paralela en una tabla improvisada de tendencias. Todos los días fuera del evento reflejan su recuento de métricas normal, mientras que todos los días afectados utilizan el desplazamiento del multiplicador.

   ![Métrica corregida](assets/event_corrected.png)

8. Vista los datos en una visualización de línea para ver el efecto de la métrica corregida.

   ![Línea corregida](assets/event_line.png)

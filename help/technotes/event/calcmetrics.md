---
title: Derivar datos afectados por eventos
description: Utilice las métricas calculadas para corregir los datos de tendencias afectados por un evento.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '270'
ht-degree: 4%

---


# Derivar datos afectados por eventos

Si los datos [se ven afectados por un evento](overview.md), puede utilizar métricas calculadas para derivar valores de tendencias durante el evento. Por ejemplo, si tuvo un evento que causó una caída del 25 % en los datos, puede utilizarlo como multiplicador en una métrica calculada.

>[!NOTE]
>
>Estos pasos funcionan mejor cuando se comprende el impacto de un evento, tanto desde una perspectiva de segmentación como de comparación de fechas. Asegúrese de seguir [Comparar fechas afectadas por un evento con intervalos](compare-dates.md) anteriores y [Excluir fechas específicas en análisis](segments.md) antes de seguir esta página.

1. Cree dos segmentos para &#39;Días afectados&#39; y &#39;Excluir días afectados&#39;, tal como se describe en [Excluir fechas específicas en la análisis](segments.md).
2. Vaya a **[!UICONTROL Componentes]** > Métricas **** calculadas.
3. Haga clic en **[!UICONTROL Agregar]**.
4. Arrastre los dos segmentos anteriores al lienzo de definición. Cambie el operador entre ellos a un `+` para sumarlos.
5. Añada la métrica deseada dentro de ambos segmentos. Por ejemplo, puede utilizar la métrica &quot;Visitas&quot;.

   ![Generador de segmentos](assets/event_segment_builder.png)

6. Haga clic en **[!UICONTROL Añadir]** en la parte superior derecha del contenedor &#39;Días afectados&#39; y, a continuación, haga clic en Número **** estático. Establezca el número estático en el porcentaje que desea desplazar los datos, como se describe en [Comparar fechas afectadas por un evento con intervalos](compare-dates.md)anteriores. En este ejemplo, el desplazamiento es 25 % o 1,25.

   ![Número estático](assets/event_static_number.png)

7. Aplique la métrica &quot;corregida&quot; de forma paralela en una tabla improvisada de tendencias. Todos los días fuera del evento reflejan su recuento de métricas normal, mientras que todos los días afectados utilizan el desplazamiento del multiplicador.

   ![Métrica corregida](assets/event_corrected.png)

8. Vista los datos en una visualización de línea para ver el efecto de la métrica corregida.

   ![Línea corregida](assets/event_line.png)

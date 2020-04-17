---
title: Excluir fechas específicas en la análisis
description: Sugerencias para excluir fechas o intervalos de fechas si no desea incluirlos en los informes.
translation-type: tm+mt
source-git-commit: e2ddfc7fb7ced2d7f480bec3b50cb2657d779646

---


# Excluir fechas específicas en la análisis

Si tiene datos [afectados por un evento](/help/technotes/event-impacted.md), puede utilizar un segmento para excluir cualquier intervalo de fechas que no desee incluir en los informes. La segmentación de las fechas afectadas por el evento puede ayudar a evitar que su organización tome decisiones sobre los datos parciales.

## Aísle los días afectados

Cree un segmento que aísle el día o intervalo de fechas afectados. Este segmento es útil si solo desea centrarse en los días problemáticos para ver más información sobre su impacto.

1. Para abrir el generador de segmentos, vaya a **[!UICONTROL Components]** > **[!UICONTROL Segments]** y haga clic en **[!UICONTROL Add]**.
2. Arrastre la dimensión &#39;Día&#39; al lienzo de definición y configúrela en el día que desee aislar.
3. Repita el paso anterior para cada día que desee aislar en el informe.

![Segmento de días afectados](../assets/affected_days.jpg)

Adobe recomienda utilizar los componentes de dimensión naranja y no los componentes de intervalo de fechas púrpura. Si utiliza componentes de intervalo de fechas púrpura, anulan el intervalo de calendario del proyecto:

![Excluir tipo de día del segmento](../assets/exclude_segment_day_type.jpg)

## Excluir días afectados

Cree un segmento que excluya el día o intervalo de fechas afectados. Este segmento es útil si desea excluir los días en los que se produjeron problemas para minimizar el impacto en el sistema de informes general.

1. Para abrir el generador de segmentos, vaya a **[!UICONTROL Components]** > **[!UICONTROL Segments]** y haga clic en **[!UICONTROL Add]**.
2. En la parte superior derecha del lienzo de definición de segmento, haga clic en **[!UICONTROL Options]** > **[!UICONTROL Exclude]**.
3. Arrastre la dimensión &#39;Día&#39; al lienzo de definición y configúrela en el día que desee eliminar.
4. Repita el paso anterior para cada día que desee eliminar en el informe.

![Excluir días afectados](../assets/exclude_affected_days.jpg)

## Utilizar estos segmentos en los informes

Una vez creado el segmento de exclusión, puede utilizarlo exactamente como lo haría con otros segmentos.

### Comparar segmentos en un informe de tendencias

Puede aplicar tanto el segmento &#39;Días afectados&#39; como el segmento &#39;Excluir días afectados&#39; en un informe para compararlos en paralelo. Arrastre ambos segmentos por encima o por debajo de una métrica para compararlos:

![Ambos segmentos](../assets/affected_and_exclude.png)

### Aplicar el segmento de exclusión a un proyecto

Puede aplicar el segmento &#39;Excluir días afectados&#39; a un proyecto de Workspace. Arrastre el segmento de exclusión a la sección del lienzo de Workspace rotulada *Colocar un segmento aquí*.

>[!TIP] Incluya una nota alrededor de los datos excluidos en la descripción del panel para ayudar a los que ven el informe. Haga clic con el botón secundario en el título de un panel y, a continuación, haga clic en **[!UICONTROL Edit description]**.

![Segmento aplicado a un panel](../assets/exclude_segment_panel.jpg)

### Utilizar el segmento de exclusión en un grupo de informes virtuales

Puede utilizar el segmento en un grupo [de informes](../../vrs/vrs-about.md) virtuales para excluir los datos de forma más cómoda. Esta opción es ideal en el sentido de que no tiene que recordar aplicar el segmento para cada informe que incluya el intervalo de fechas afectado. Si ya utiliza grupos de informes virtuales como fuente principal de datos, puede agregar el segmento a un VRS existente.

1. Vaya a **[!UICONTROL Components]** > **[!UICONTROL Virtual report suites]**.
2. Haga clic en **[!UICONTROL Add]**.
3. Escriba el nombre y la descripción que desee para el grupo de informes virtuales.
4. Arrastre el segmento de exclusión al área rotulada **[!UICONTROL Add segment]**.
5. Haga clic **[!UICONTROL Continue]** en en la esquina superior derecha y luego haga clic en **[!UICONTROL Save]**.

![Segmento aplicado al VRS](../assets/exclude_segment_vrs.png)

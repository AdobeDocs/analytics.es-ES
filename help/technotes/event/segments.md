---
title: Excluir fechas específicas en el análisis
description: Sugerencias para excluir fechas o intervalos de fechas si no desea incluirlos en informes.
exl-id: 744666c0-17f3-443b-9760-9c8568bec600
source-git-commit: d03206b127e16cbb98d1318b0acc6c304f91ca48
workflow-type: tm+mt
source-wordcount: '590'
ht-degree: 2%

---

# Excluir fechas específicas en el análisis

Si tiene datos [afectado por un evento](overview.md), puede utilizar un segmento para excluir cualquier intervalo de fechas que no desee incluir en los informes. Segmentar las fechas afectadas por el evento puede ayudar a evitar que su organización tome decisiones sobre los datos parciales.

## Aislar los días afectados {#isolate}

Cree un segmento que aísle el día o el intervalo de fechas afectados. Este segmento es útil si solo desea centrarse en los días del problema para ver más información sobre su impacto.

1. Abra el Generador de segmentos en **[!UICONTROL Componentes]** > **[!UICONTROL Segmentos]** y haga clic en **[!UICONTROL Agregar]**.
2. Arrastre la dimensión &quot;Día&quot; al lienzo de definición y configúrela en el día que desee aislar.
3. Repita el paso anterior para cada día que desee aislar en el informe.

![Segmento de días afectados](assets/affected_days.jpg)

>[!TIP]
>
>Para cambiar la instrucción OR a una instrucción AND, haga clic en la flecha abajo situada junto a OR y seleccione AND.

Adobe recomienda utilizar los componentes de dimensión de dimensión naranja y no los componentes de intervalo de fechas morados. Si utiliza componentes de intervalo de fechas morados, estos anulan el intervalo de calendario del proyecto:

![Excluir tipo de día del segmento](assets/exclude_segment_day_type.jpg)

## Excluir días afectados {#exclude}

Cree un segmento que excluya el día o el intervalo de fechas afectados. Este segmento es útil si desea excluir los días en los que se produjeron problemas para minimizar el impacto en los informes generales.

1. Abra el Generador de segmentos en **[!UICONTROL Componentes]** > **[!UICONTROL Segmentos]** y haga clic en **[!UICONTROL Agregar]**.
2. En la parte superior derecha del lienzo de definición de segmento, haga clic en **[!UICONTROL Opciones]** > **[!UICONTROL Excluir]**.
3. Arrastre la dimensión &quot;Día&quot; al lienzo de definición y configúrela en el día que desee eliminar.
4. Repita el paso anterior para cada día que desee eliminar en el informe.

![Excluir días afectados](assets/exclude_affected_days.jpg)

## Usar estos segmentos en informes

Una vez creado el segmento de exclusión, puede utilizarlo exactamente como haría con otros segmentos.

### Comparar segmentos en un informe de tendencias {#compare}

Puede aplicar el segmento &quot;Días afectados&quot; y el segmento &quot;Excluir días afectados&quot; en un informe para compararlos en paralelo. Arrastre ambos segmentos por encima o por debajo de una métrica para compararlos:

![Ambos segmentos](assets/affected_and_exclude.png)

Si no desea mostrar ceros en la tabla o en las visualizaciones (lo que provoca caídas), habilite **[!UICONTROL La interpretación de cero no tiene valor]** en la configuración de columna.

![Interpretar cero](assets/interpret_zero.png)

Si no desea mostrar ceros en la tabla o en las visualizaciones (lo que provoca caídas), habilite **[!UICONTROL La interpretación de cero no tiene valor]** en la configuración de columna.

![Interpretar cero](assets/interpret_zero.png)

### Aplicar el segmento de exclusión a un proyecto {#apply}

Puede aplicar el segmento &quot;Excluir días afectados&quot; a un proyecto de Workspace. Arrastre el segmento de exclusión a la sección del lienzo de Workspace etiquetada *Colocar un segmento aquí*.

>[!TIP]
>
>Incluya una nota alrededor de los datos excluidos en la descripción del panel para ayudar a quienes visualizan el informe. Haga clic con el botón derecho en el título de un panel y, a continuación, haga clic en **[!UICONTROL Editar descripción]**.

![Segmento aplicado a un panel](assets/exclude_segment_panel.jpg)

### Uso del segmento de exclusión en un grupo de informes virtuales {#use-vrs}

Puede utilizar el segmento en un [grupo de informes virtuales](/help/components/vrs/vrs-about.md) para excluir los datos de forma más conveniente. Esta opción es ideal, ya que no tiene que recordar aplicar el segmento a cada informe que incluya el intervalo de fechas afectado. Si ya usa grupos de informes virtuales como fuente principal de datos, puede agregar el segmento a un VRS existente.

1. Vaya a **[!UICONTROL Componentes]** > **[!UICONTROL Grupos de informes virtuales]**.
2. Haga clic en **[!UICONTROL Agregar]**.
3. Introduzca el nombre y la descripción deseados para el grupo de informes virtuales.
4. Arrastre el segmento de exclusión al área etiquetada **[!UICONTROL Añadir segmento]**.
5. Haga clic en **[!UICONTROL Continuar]** en la parte superior derecha, haga clic en **[!UICONTROL Guardar]**.

![Segmento aplicado a VRS](assets/exclude_segment_vrs.png)

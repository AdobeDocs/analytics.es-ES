---
description: Obtenga información sobre cómo desglosar dimensiones y elementos de dimensión en Analysis Workspace.
keywords: Analysis Workspace
title: Desglose de dimensiones
feature: Dimensions
role: User, Admin
exl-id: 0d26c920-d0d9-4650-9cf0-b67dbc4629e1
source-git-commit: ff38740116ac6f12033ebdc17cffa3250a30f3f7
workflow-type: tm+mt
source-wordcount: '554'
ht-degree: 56%

---

# Desglose de dimensiones

Puede desglosar los datos en Analysis Workspace de formas ilimitadas para sus necesidades específicas; crear consultas con métricas, dimensiones, segmentos, líneas de tiempo y otros valores de desglose de análisis relevantes.

1. En una [tabla de forma libre](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.md), en el menú contextual de una o más filas seleccionadas, seleccione **[!UICONTROL Desglose]** ![ChevronRight](/help/assets/icons/ChevronRight.svg).

   ![Resultado del paso que muestra la selección de Crear alerta a partir de la selección.](assets/breakdown.png)

1. En el submenú, seleccione **[!UICONTROL Dimensiones]**, **[!UICONTROL Métricas]**, **[!UICONTROL Segmentos]** o **[!UICONTROL Intervalos de fechas]** y, a continuación, seleccione un elemento. O simplemente busque un componente en el campo **[!UICONTROL *Buscar *]**.

Puede desglosar métricas por elementos de dimensión o segmentos de audiencia entre periodos de tiempo seleccionados. También puede continuar desglosando hasta un nivel más granular.

>[!NOTE]
>
>El número de desgloses de la tabla está limitado a 200 desgloses. Este límite aumenta para la exportación de desgloses.

## Desglose por posición

De forma predeterminada, los desgloses se corrigen a elementos de fila estáticos. Por ejemplo, supongamos que desglosa los 3 elementos de dimensión de página principales (página principal, resultados de búsqueda, cierre de compra) por canal de marketing. Después abandona el proyecto y regresa dos semanas más tarde. Al volver a abrir el proyecto, las 3 páginas principales han cambiado, y ahora la página principal, los resultados de búsqueda y el cierre de compra son las 4 o 6 páginas principales. De forma predeterminada, los desgloses del canal de marketing siguen apareciendo en la página principal, los resultados de búsqueda y el cierre de compra, aunque ahora se encuentren en las filas 4-6.

Por el contrario, **Desglose por posición**, siempre desglosa los 3 elementos principales, independientemente de cuáles sean. En referencia al ejemplo anterior, cuando vuelva a abrir el proyecto, los desgloses de canal de marketing se vinculan a las 3 páginas principales de la tabla. Y no a la página principal, los resultados de búsqueda y el cierre de compra, que ahora están en las filas 4-6. Consulte [Configuración de fila](/help/analyze/analysis-workspace/visualizations/freeform-table/column-row-settings/table-settings.md) para obtener información sobre cómo configurar esta opción.



## Aplicar modelos de atribución a desgloses

Cualquier desglose dentro de una tabla también puede tener aplicado cualquier modelo de atribución. Este modelo de atribución puede ser el mismo o diferente de la columna principal. Por ejemplo, puede analizar Pedidos lineales en su dimensión de Canales de marketing pero aplicar Pedidos en forma de U a los códigos de seguimiento específicos dentro de un Canal. Para editar el modelo de atribución aplicado a un desglose, pase el ratón sobre el modelo de desglose y seleccione **[!UICONTROL Editar]**.

![Comparación de atribución de pedidos que muestra la configuración de desglose](assets/breakdown-attribution.png)

Este es el comportamiento esperado al aplicar modelos de atribución a desgloses o editarlos:

* Si aplica una atribución cuando no existen otras atribuciones, esta se aplica a todo el árbol de columnas.

* Si añade un desglose después de aplicar una atribución, utilizará el valor predeterminado para el desglose dado que se añadió (si esa dimensión tiene un valor predeterminado). De lo contrario, se utiliza el desglose de la columna principal. Algunas dimensiones tienen una asignación predeterminada. Por ejemplo, las dimensiones temporales y el remitente del reenvío utilizan el mismo contacto. La dimensión Producto utiliza Último contacto. Otras dimensiones no tienen un valor predeterminado y utilizarán la asignación de columna principal.

* Si ya hay atribuciones en el árbol de columnas, cambiar la atribución solo afecta al que esté editando.

>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Dimension en Analysis Workspace](https://video.tv.adobe.com/v/23971?quality=12&learn=on){target="_blank"} para ver un vídeo de demostración.


>[!ENDSHADEBOX]


>[!BEGINSHADEBOX]

Vea ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [desgloses de Dimension](https://video.tv.adobe.com/v/23969?quality=12&learn=on){target="_blank"} para ver un vídeo de demostración.


>[!ENDSHADEBOX]


>[!BEGINSHADEBOX]

Vea ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Agregar dimensiones y métricas](https://video.tv.adobe.com/v/30606?quality=12&learn=on){target="_blank"} para ver un vídeo de demostración.


>[!ENDSHADEBOX]


>[!BEGINSHADEBOX]

Vea ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Trabajo con dimensiones en una tabla de forma libre](https://video.tv.adobe.com/v/40179?quality=12&learn=on){target="_blank"} para ver un vídeo de demostración.


>[!ENDSHADEBOX]


>[!BEGINSHADEBOX]

Vea ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Desglose de Dimension por posición](https://video.tv.adobe.com/v/24033){target="_blank"} para ver un vídeo de demostración.


>[!ENDSHADEBOX]



<!--
# Break down dimensions

Break down dimensions and dimension items in Analysis Workspace.

Break down your data in unlimited ways for your specific needs; build queries using relevant metrics, dimensions, segments, time lines, and other analysis breakdown values.

1. [Create a project](/help/analyze/analysis-workspace/home.md) with a data table.
1. In the data table, right-click a line item and select **[!UICONTROL Breakdown]** > *`<item>`*.

   ![Step Result](assets/fa_data_table_actions.png)

   You can break down metrics by dimension items or audience segments across selected time periods. You can also drill down further to a more granular level.

   >[!NOTE]
   >
   >The number of breakdowns to show in the table is limited to 200. This limit will increase for exporting breakdowns.

## Apply attribution models to breakdowns

Any breakdown within a table can also have any attribution model applied to it. This attribution model can be the same or different from the parent column. For example, you can analyze linear Orders on your Marketing Channels dimension but apply U-Shaped Orders to the specific tracking codes within a Channel. To edit the attribution model applied to a breakdown, hover over the breakdown model and click **[!UICONTROL Edit]**:

![Breakdown settings](assets/breakdown_settings.png)

This is the expected behavior when applying attribution models to breakdowns or editing them:

* If you apply an attribution when no other attributions exist, then the attribution applies to the entire column tree.

* If you add a breakdown after an attribution has been applied, it will use the default for the given breakdown that was added, if that dimension has a default. Otherwise it will use the breakdown from the parent column. Some dimensions have a default allocation.  For example, [!UICONTROL Time] dimensions and [!UICONTROL Referrer] use [!UICONTROL Same Touch]. The [!UICONTROL Product] dimension uses [!UICONTROL Last Touch]. Other dimensions don't have a default, and will use the parent column allocation.

* If there are already attributions in the column tree, changing the attribution only impacts the one you are editing.

## Videos


>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Adding dimensions and metrics to your project in Analysis Workspace](https://video.tv.adobe.com/v/30606?quality=12&learn=on){target="_blank"} for a demo video.

>[!ENDSHADEBOX]



>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Working with dimensions in a Freeform Table](https://video.tv.adobe.com/v/40179?quality=12&learn=on){target="_blank"} for a demo video.

>[!ENDSHADEBOX]


>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [dimension breakdowns by position](https://video.tv.adobe.com/v/24033?quality=12&learn=on){target="_blank"} for a demo video.

>[!ENDSHADEBOX]


-->
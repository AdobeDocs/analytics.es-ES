---
description: Utilice la visualización de resumen de métricas clave para comparar el rendimiento de las métricas en dos cronologías.
title: Resumen de métricas clave
feature: Visualizations
role: User, Admin
exl-id: c74e77ff-15d6-48f1-a845-85bdf3444c3a
source-git-commit: c0855c6bed6a9762c0440e1a8e004ee11020808e
workflow-type: tm+mt
source-wordcount: '839'
ht-degree: 56%

---

# Resumen de métricas clave {#key-metric-summary}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_keymetricsummary_button"
>title="Resumen de métricas clave"
>abstract="Cree una visualización que sea una combinación de los gráficos de líneas, resumen de cambios y resumen de números. Utilice esta visualización para comparar la tendencia de las métricas importantes entre dos períodos de tiempo."

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

*Este artículo describe la visualización Resumen de métricas clave en **Adobe Analytics**.<br/>Consulte [Resumen de métricas clave](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/visualizations/key-metric) para la versión de **Customer Journey Analytics**de este artículo.*

>[!ENDSHADEBOX]

La visualización [!UICONTROL Resumen de métricas clave] permite ver las tendencias de una métrica importante dentro de un solo periodo de tiempo. También le permite comparar el rendimiento de las métricas en dos intervalos de tiempo. Proporciona las ventajas de varias visualizaciones combinadas en una sola:

* **[!UICONTROL Visualizaciones de línea]** que muestran la tendencia de la métrica para los intervalos de fechas principales y de comparación

* **[!UICONTROL Cambio de porcentaje de resumen]** que muestra el aumento o la disminución de la métrica entre los intervalos de fechas principal y de comparación

* Valor total actual ([!UICONTROL **número de resumen**]) para la métrica

## Casos prácticos

Esta visualización aborda varios casos de uso comunes, incluidos los siguientes:

* Un analista que trata de entender qué aspecto tenía la creación de oportunidades este mes en comparación con el mismo periodo de tiempo del año pasado.

* Un experto en marketing que explora cómo la generación de posibles clientes para un tipo de posible cliente específico ha cambiado de este mes al último.

* Un ejecutivo que quiere entender cómo han variado las nuevas reservas de este trimestre al último.

## Configuración del resumen de métricas clave

1. Arrastre la visualización **[!UICONTROL Resumen de métricas clave]** desde el menú **[!UICONTROL Visualizaciones]** del carril izquierdo a un panel.

   ![](assets/key-metric-config.png)

1. Configure la visualización con las siguientes opciones:

   | Ajuste de configuración | Definición |
   | --- | --- |
   | **[!UICONTROL Métrica]** | Seleccione la métrica que desea examinar. Todas las métricas son compatibles. |
   | **[!UICONTROL Intervalo de fechas principal]** | El intervalo de fechas actual para la tabla de forma libre.<p>Elija entre cualquier intervalo de fechas disponible en el grupo de informes.</p> <p>Elija [!UICONTROL **Intervalo de fechas del panel**] si desea utilizar el mismo intervalo de fechas que se está utilizando en el panel en el que se encuentra la visualización.</p> |
   | **[!UICONTROL Intervalo de fechas de comparación]** | El intervalo de fechas que desea comparar con el intervalo de fechas principal. |
   | **[!UICONTROL Segmento (opcional)]** | Cualquier segmento que le interese para este resumen. |

   {style="table-layout:auto"}

   >[!NOTE]
   >
   >Cuando el campo [!UICONTROL **Intervalo de fechas principal**] se establece en [!UICONTROL **Intervalo de fechas del panel**], el **[!UICONTROL Intervalo de fechas de comparación]** se puede actualizar automáticamente, dependiendo de si la opción **[!UICONTROL Intervalo de fechas de comparación]** que elija es relativa al intervalo de fechas principal o fija.
   >
   >* **Relativo:** Si el campo **[!UICONTROL Intervalo de fechas de comparación]** se establece en una opción relativa al intervalo de fechas principal (como [!UICONTROL **Día anterior**], [!UICONTROL **Mismo día la semana pasada**], [!UICONTROL **Mismo día cuatro semanas antes**], etc.), cualquier actualización del campo [!UICONTROL **Intervalo de fechas principal**] hará que el **[!UICONTROL Intervalo de fechas de comparación]** se actualice automáticamente al período que sigue inmediatamente al intervalo de fechas del panel.
   >* **Fijo:** Si el campo [!UICONTROL **Intervalo de fechas de comparación**] está establecido en un intervalo de fechas fijo (como **3 de febrero de 2023**), los cambios realizados en el campo [!UICONTROL **Intervalo de fechas principal**] o en el intervalo de fechas del panel no tendrán ningún efecto en el [!UICONTROL **Intervalo de fechas de comparación**]. Sin embargo, cualquier actualización del intervalo de fechas del panel hace que [!UICONTROL **Intervalo de fechas principal**] se actualice automáticamente.

1. Seleccione **[!UICONTROL Generar]**.

## Visualización del resultado

El resultado debería tener un aspecto similar al siguiente:

![](assets/key-metric-output.png)

Tenga en cuenta lo siguiente al ver el resultado:

* El gráfico de líneas **[!UICONTROL Periodo anterior]** (siempre mostrado en gris) corresponde al **[!UICONTROL Intervalo de fechas de comparación]** en el paso de configuración.

* Si no se especifica un intervalo de fechas de comparación durante la configuración o está oculto en los ajustes de visualización, solo se muestra el gráfico de líneas del intervalo de fechas principal. El cambio de resumen está oculto.

* Desde aquí, puede pasar el ratón por encima de los gráficos de líneas para ver las estadísticas de los días individuales:

![](assets/key-metric-output2.png)

## Configuración de visualización

El resumen de métricas clave ofrece varias configuraciones flexibles para mejorar la creación de informes y la comunicación de métricas importantes. Se puede acceder a la configuración a través del icono de engranaje en la esquina superior derecha de la visualización.

![](assets/key-metric-settings.png)

| Configuración | Descripción |
| --- | --- |
| **[!UICONTROL Enfatizar el cambio porcentual]** | Mostrar el cambio de resumen en negrita destacado en el centro de la visualización |
| **[!UICONTROL Enfatización del valor numérico]** | Mostrar el número de resumen en negrita destacado en el centro de la visualización |
| **[!UICONTROL Leyenda visible]** | Mostrar u ocultar la leyenda en la parte inferior de la visualización |
| **[!UICONTROL Mostrar anotaciones]** | Mostrar u ocultar anotaciones añadidas por un administrador |
| **[!UICONTROL Mostrar minigráficos]** | Muestre u oculte gráficos de líneas en la parte inferior del gráfico. Cuando está oculta, la leyenda cambia para no hacer referencia visual a las líneas |
| **[!UICONTROL Mostrar mínimo y máximo en reflectores]** | Mostrar u ocultar valores mínimos y máximos en gráficos de líneas principales y de comparación |
| **[!UICONTROL Mostrar comparación]** | Muestre u oculte los datos de comparación. Cuando están ocultos, el gráfico de líneas de comparación y los objetos de cambio de resumen no se ven. |
| **[!UICONTROL Mostrar número total]** | Mostrar u ocultar el número de resumen |
| **[!UICONTROL Mostrar diferencia en bruto]** | Mostrar u ocultar la diferencia en bruto entre el valor total de la métrica en el intervalo de fechas principal y el secundario |
| **[!UICONTROL Valor abreviado]** | Abreviar los valores numéricos para simplificar las perspectivas comunicadas (por ejemplo, 20 000 -> 20K) |

## Edición de la visualización

Después de crear la visualización, aún puede editar la configuración original.

1. Haga clic en el icono de lápiz en la esquina superior derecha de la visualización (junto al icono de engranaje de configuración).

   ![](assets/edit-icon.png)

   Ahora volverá a la vista de configuración original.

1. Cambie la métrica, el intervalo de fechas principal, el intervalo de fechas de comparación o el segmento como prefiera.

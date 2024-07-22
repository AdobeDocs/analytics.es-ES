---
description: La comparación de fechas de Analysis Workspace le permite tomar cualquier columna que contenga un intervalo de fechas y crear una comparación de fechas comunes, por ejemplo, año tras año, trimestre tras trimestre, mes tras mes, etc.
title: Comparación de fechas
feature: Calendar
role: User, Admin
exl-id: ea7a42ef-89de-4f70-b468-8a5cf69fea05
source-git-commit: 8405c36b3e19a54385011ea80fc06363a02bc07a
workflow-type: tm+mt
source-wordcount: '746'
ht-degree: 57%

---

# Comparación de fechas

La comparación de fechas de Analysis Workspace le permite tomar cualquier columna que contenga un intervalo de fechas y crear una comparación de fechas comunes, por ejemplo, año tras año, trimestre tras trimestre, mes tras mes, etc.

A continuación, se muestra un vídeo sobre este tema:

>[!VIDEO](https://video.tv.adobe.com/v/30753/?quality=12)

## Comparar periodos de tiempo {#section_C4E36BFE0F5C4378A74E705747C9DEE4}

>[!NOTE]
>[!UICONTROL Comparar periodos de tiempo] aprovecha las métricas calculadas avanzadas. Como resultado, solo está disponible para clientes con las SKU Select, Prime y Ultimate de Analytics.

El análisis requiere contexto, y este lo proporciona a menudo un periodo de tiempo previo. Por ejemplo, la pregunta &quot;¿Cuánto mejor o peor estamos haciendo que en esta época del año pasado?&quot; es fundamental para comprender su negocio. Las comparaciones de fechas incluyen automáticamente una columna “diferencia” que muestra el porcentaje de cambio en comparación con un periodo de tiempo concreto.

1. Cree una tabla de forma libre con cualquier dimensión y métrica que quiera comprobar a lo largo de un periodo de tiempo.
1. Haga clic con el botón derecho en una fila de la tabla y seleccione **[!UICONTROL Comparar periodos de tiempo]**.

   ![](assets/compare-time.png)

   >[!NOTE]
   >
   >Esta opción del botón secundario está deshabilitada para filas de métricas, filas de intervalos de fechas y filas de dimensiones de tiempo.

1. Dependiendo de cómo haya establecido el intervalo de fechas de la tabla, dispone de estas opciones para la comparación:

   | Opción | Descripción |
   |---|---|
   | **[!UICONTROL Semana/mes/trimestre/año anterior a este intervalo de fechas]** | Compara la semana/mes/etc. inmediatamente anterior a este intervalo de fechas. |
   | **[!UICONTROL Esta semana/mes/trimestre/año del año pasado hasta este intervalo de fechas]** | Lo compara con el mismo intervalo de fechas hace un año. |
   | **[!UICONTROL Intervalo de fechas personalizado a este intervalo de fechas]** | Le permite seleccionar un intervalo de fechas personalizado. |

   >[!NOTE]
   >
   >Al seleccionar una cantidad personalizada de días, por ejemplo, del 7 de octubre al 20 de octubre (un intervalo de 14 días), solo obtendrá dos opciones: **[!UICONTROL 14 días anteriores a este intervalo de fechas]** e **[!UICONTROL Intervalo de fechas personalizado a este intervalo de fechas]**.

1. La comparación resultante tiene este aspecto:

   ![](assets/compare-time-result.png)

   Las filas en la columna Cambio porcentual aparecen en rojo para los valores negativos y en verde para los positivos.

1. (Opcional) Como en cualquier otro proyecto de Workspace, puede crear visualizaciones basadas en estas comparaciones de tiempo. Por ejemplo, aquí tiene un gráfico de barras:

   ![](assets/compare-time-barchart.png)

   Fíjese en que, para mostrar el cambio porcentual en el gráfico de barras, debe tener marcado el ajuste [!UICONTROL Porcentajes] en la [!UICONTROL Configuración de visualización].

## Agregar una columna Periodo de tiempo para comparar {#section_93CC2B4F48504125BEC104046A32EB93}

Ahora puede agregar un periodo de tiempo a cada columna en una tabla, lo que permite agregar un periodo diferente al periodo en que está establecido el calendario. Esta es otra manera de comparar fechas.

1. Haga clic con el botón derecho en una columna de la tabla y seleccione **[!UICONTROL Agregar columna de período de tiempo]**.

   ![](assets/add-time-period-column.png)

1. Dependiendo de cómo haya establecido el intervalo de fechas de la tabla, dispone de estas opciones para la comparación:

   | Opción | Descripción |
   |---|---|
   | **[!UICONTROL Semana/mes/trimestre/año anterior a este intervalo de fechas]** | Agrega una columna con la semana/mes/etc. inmediatamente anterior a este intervalo de fechas. |
   | **[!UICONTROL Esta semana/mes/trimestre/año del año pasado hasta este intervalo de fechas]** | Agrega el mismo intervalo de fechas hace un año. |
   | **[!UICONTROL Intervalo de fechas personalizado a este intervalo de fechas]** | Le permite seleccionar un intervalo de fechas personalizado. |

   >[!NOTE]
   >
   >Al seleccionar una cantidad personalizada de días, por ejemplo, del 7 de octubre al 20 de octubre (un intervalo de 14 días), solo obtendrá dos opciones: **[!UICONTROL 14 días anteriores a este intervalo de fechas]** e **[!UICONTROL Intervalo de fechas personalizado a este intervalo de fechas]**.

1. El periodo de tiempo se insertará en la parte superior de la columna seleccionada:

   ![](assets/add-time-period-column2.png)

1. Puede agregar todas las columnas de tiempo que desee, así como combinar a voluntad distintos intervalos de fechas:

   ![](assets/add-time-period-column4.png)

1. Además, puede ordenar en función de cualquier columna, lo que cambiará el orden de los días, dependiendo de la columna elegida.

## Alinear fechas de columnas para que comiencen en la misma fila {#section_5085E200082048CB899C3F355062A733}

Puede alinear las fechas de cada columna con todas a partir de la misma fila.

Por ejemplo, cuando alinea las fechas, si realiza una comparación mes a mes entre octubre y septiembre de 2016, la columna de la izquierda comenzará el 1 de octubre y la de la derecha, el 1 de septiembre:

![](assets/add-time-period-column3.png)

>[!NOTE]
>
>Tenga en cuenta lo siguiente al utilizar esta opción:
>
>* Esta configuración está habilitada de forma predeterminada para todos los proyectos nuevos.
>
>* Esta configuración se aplica a toda la tabla. Por ejemplo, si cambia esta configuración para un desglose dentro de la tabla, cambiará la configuración de toda la tabla.
>

Para habilitar esta configuración, si aún no está habilitada:

1. En la tabla en la que desee alinear las fechas de la columna, seleccione el icono **Configuración** en el encabezado de la tabla.

1. En la ficha [!UICONTROL **Configuración**], seleccione **[!UICONTROL Alinear fechas de cada columna para que todas empiecen en la misma fila (se aplica a toda la tabla)]**.

![](assets/date-comparison-setting.png)



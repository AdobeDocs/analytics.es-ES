---
description: Permite visualizar fácilmente datos de comparación en Analysis Workspace, como comparaciones con el mes pasado, el año pasado, etc.
title: Visualización de gráficos combinados
feature: Visualizations
role: User, Admin
source-git-commit: e2cd08ae4109e037f8b54edf21239fa6fa659896
workflow-type: tm+mt
source-wordcount: '644'
ht-degree: 32%

---


# Gráfico combinado

>[!NOTE]
>
>Actualmente, esta funcionalidad está en [prueba limitada](/help/release-notes/releases.md).

La variable [!UICONTROL Gráfico combinado] la visualización facilita la creación rápida de una visualización de comparación sin tener que crear primero una tabla. Puede ver fácilmente las tendencias de sus datos en una combinación de líneas/barras.

Utilice un [!UICONTROL Gráfico combinado] a

* Compare los pedidos de esta semana con los pedidos de al mismo tiempo el mes pasado (y el año pasado), todo en pocos clics.

* Analice y compare rápidamente varias métricas (por ejemplo, [!UICONTROL Visitantes únicos] y [!UICONTROL Ingresos]) en el mismo gráfico.

* Analizar una métrica con una función (como [!UICONTROL Media acumulada]) en un horizonte temporal.

Tenga en cuenta que puede

* Agregar varias comparaciones en una sola [!UICONTROL Gráfico combinado].
* Si agrega una o más comparaciones, deben ser del mismo tipo, como Periodo de tiempo.
* Se pueden agregar hasta 5 comparaciones.
* Puede aplicar un filtro a una métrica.

## Crear un gráfico combinado

1. En la lista desplegable Visualizaciones del carril izquierdo, arrastre el [!UICONTROL Gráfico combinado] visualización en un panel en blanco.

   ![](assets/combo-chart-build.png)

1. En las listas desplegables, seleccione una dimensión para el eje X y una métrica para el eje Y.

1. Seleccione el tipo de [!UICONTROL Comparación de líneas] desea utilizar.

   | Tipo de comparación de líneas | Definición |
   | --- | --- |
   | Período de tiempo | El tipo de comparación más común: comparar este período de tiempo con hace 4 semanas, por ejemplo. Si ha seleccionado Periodo de tiempo, realice una selección secundaria de qué periodo de tiempo desea comparar.<p>![](assets/combo-time-period.png) |
   | Métrica adicional | Por ejemplo, podría comparar [!UICONTROL Ingresos] a otra métrica.<p>![](assets/combo-2metrics.png) |
   | Función | Puede introducir una función como [!UICONTROL Promedio] en la comparación. Consulte la lista de funciones admitidas a continuación.<p>![](assets/combo-functions.png) |

   {style=&quot;table-layout:auto&quot;}

1. Haga clic en **[!UICONTROL Generar]**.

   El resultado será similar al siguiente:

   ![](assets/combo-output.png)

   El período actual se muestra en el gráfico de barras y el período de comparación se representa mediante el gráfico de líneas. Los puntos en el gráfico de líneas se conocen como &quot;barras&quot;.

## Funciones compatibles

Si elige **[!UICONTROL Función]** como el [!UICONTROL Tipo de comparación de líneas], se devolverá una función de la métrica que haya elegido.

| Función | Definición |
| --- | --- |
| **[!UICONTROL Media acumulada]** | Devuelve la media de las últimas N filas. |
| **[!UICONTROL Suma]** | Suma todos los valores numéricos de una métrica dentro de una columna (entre los elementos de una dimensión) |
| **[!UICONTROL Exponente]** | Devuelve *e* elevado a la potencia de un número determinado. |
| **[!UICONTROL Media]** | Devuelve la media aritmética o el promedio de una métrica. |
| **[!UICONTROL Cuartil]** | Devuelve el cuartil de los valores de una métrica. Por ejemplo, los cuartiles se pueden utilizar para encontrar el primer 25 % de los productos que generan los mayores ingresos. |

{style=&quot;table-layout:auto&quot;}

Este es un ejemplo del promedio acumulativo de la métrica Ingresos:

![](assets/combo-cumul-avg.png)

Este es un ejemplo de gráfico combinado con las funciones Cumulative average y Mean :

![](assets/combo-two-functions.png)

## Configuración de gráficos combinados

Haga clic en el icono de engranaje en la parte superior derecha de un gráfico combinado para cambiar su configuración.

![](assets/combo-settings.png)

| Configuración | Definición |
| --- | --- |
| **[!UICONTROL General]** |  |
| **[!UICONTROL Porcentajes]** | Muestra valores en porcentajes. |
| **[!UICONTROL Leyenda visible]** | Permite ocultar el texto de leyenda detallado para la visualización de gráficos combinados. |
| **[!UICONTROL Granularidad]** | En las visualizaciones de tendencias, puede cambiar la granularidad de tiempo (día, semana, mes, etc.) de esta lista desplegable. |
| **[!UICONTROL Superposiciones]** | Muestre u oculte los barriles en líneas. |
| **[!UICONTROL Eje]** |  |
| **[!UICONTROL Mostrar eje doble]** | Solo es aplicable si cuenta con dos métricas: puede tener un eje Y a la izquierda (para una métrica) y a la derecha (para otra métrica). Esto resulta útil cuando las métricas trazadas son de magnitudes muy diferentes. |
| **[!UICONTROL Normalización]** | Fuerza métricas para igualar proporciones. Esto resulta útil cuando las métricas trazadas son de magnitudes muy diferentes. |
| **[!UICONTROL Mostrar eje x]** | Muestre el eje x u oculte. |
| **[!UICONTROL Mostrar eje Y]** | Muestre el eje y u oculte el elemento. |
| **[!UICONTROL Eje Y delimitador a cero]** | Si todos los valores marcados en el gráfico están considerablemente por encima de cero, el gráfico mostrará el valor base del eje Y distinto a cero. Si marca esta casilla, el eje Y se forzará a ser cero (y se redibujará el gráfico). |

{style=&quot;table-layout:auto&quot;}



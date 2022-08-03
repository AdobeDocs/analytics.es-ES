---
description: Permite visualizar fácilmente datos de comparación en Analysis Workspace, como comparaciones con el mes pasado, el año pasado, etc.
title: Visualización de gráficos combinados
feature: Visualizations
role: User, Admin
source-git-commit: 04a314e93a77ecf5687e771e143bf68ba911b32b
workflow-type: tm+mt
source-wordcount: '241'
ht-degree: 7%

---


# Gráfico combinado

>[!NOTE]
>
>Actualmente, esta funcionalidad está en [prueba limitada](/help/release-notes/releases.md).

La variable [!UICONTROL Gráfico combinado] la visualización facilita la creación rápida de una visualización de comparación sin tener que crear primero una tabla. Puede ver fácilmente las tendencias de sus datos en una combinación de líneas/barras.

Uso de un gráfico combinado para

* Compare los pedidos de esta semana con los pedidos de al mismo tiempo el mes pasado (y el año pasado), todo en pocos clics.

* Analice y compare rápidamente varias métricas (por ejemplo, [!UICONTROL Visitantes únicos] y [!UICONTROL Ingresos]) en el mismo gráfico.

* Analizar una métrica con una función (como [!UICONTROL Media acumulada]) en un horizonte temporal.

## Crear un gráfico combinado

1. En la lista desplegable Visualizaciones del carril izquierdo, arrastre el [!UICONTROL Gráfico combinado] visualización en un panel en blanco.

   ![](assets/combo-chart-build.png)

1. En las listas desplegables, seleccione una dimensión para el eje X y una métrica para el eje Y.

1. Seleccione el tipo de [!UICONTROL Comparación de líneas] desea utilizar.

   | Tipo de comparación de líneas | Definición |
   | --- | --- |
   | Período de tiempo | El tipo de comparación más común: comparar este período de tiempo con hace 4 semanas, por ejemplo. Si ha seleccionado Periodo de tiempo, realice una selección secundaria de qué periodo de tiempo desea comparar.<p>![](assets/combo-time-period.png) |
   | Métrica adicional | Por ejemplo, podría comparar [!UICONTROL Ingresos] a otra métrica. |
   | Función | Puede introducir una función como [!UICONTROL Promedio] en la comparación. |

1. Haga clic en **[!UICONTROL Generar]**.

   El resultado será similar al siguiente:

   ![](assets/combo-output.png)






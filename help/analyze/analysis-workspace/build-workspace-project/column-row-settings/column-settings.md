---
description: La configuración de columna le permite configurar el formato de la columna, aunque algunas opciones de formato pueden ser condicionales.
seo-description: La configuración de columna le permite configurar el formato de la columna, aunque algunas opciones de formato pueden ser condicionales.
seo-title: Configuración de columna
title: Configuración de columna
uuid: 151d66da-04f7-4d0f-985c-4fdd92bc1308
translation-type: tm+mt
source-git-commit: ed22e0520bf1c7427ead039fb1d0391f2f1e567f

---


# Configuración de columna

La configuración de columna le permite configurar el formato de la columna, aunque algunas opciones de formato pueden ser condicionales.

## Configuración de columna {#section_C5A9C13553BF4BFDAD7FACE0139AECA3}

Para acceder a la [!UICONTROL Configuración de columna], arrastre una tabla improvisada al proyecto y, a continuación, haga clic en el icono de engranaje en el encabezado de la columna.

![](assets/column_settings.png)

Puede editar la configuración **de varias columnas a la vez**. Basta con seleccionar varias columnas y hacer clic en el icono de configuración de cualquiera de ellas. Los cambios realizados se aplicarán a todas las columnas que tengan celdas seleccionadas.

| Elemento | Descripción |
|--- |--- |
| Número | Determina si una celda muestra u oculta el valor numérico de la métrica. Por ejemplo, si la métrica es Visualizaciones de la página, el valor numérico es el número de visualizaciones de la página para el elemento de fila. |
| Porcentaje | Determina si una celda muestra u oculta el valor porcentual de la métrica. Por ejemplo, si la métrica es Visualizaciones de la página, el valor porcentual es el número de visualizaciones de la página para el elemento de fila dividido por el total de visualizaciones de la página para la columna.  Nota: Se pueden mostrar porcentajes superiores al 100 % para mejorar la precisión. También se ha he incrementado el límite superior hasta el 1000 % para garantizar que la anchura de las columnas se pueda ampliar. |
| Anomalías | Determina si se ha ejecutado una detección de anomalías en los valores de esta columna. |
| Justificar el texto del encabezado | Permite justificar el texto del encabezado en las tablas improvisadas para que los encabezados sean más legibles y las tablas se puedan compartir con mayor facilidad. Esto resulta útil en el procesamiento de archivos .pdf y en las métricas con nombres largos. Está activada de forma predeterminada. |
| La interpretación de cero no tiene valor | Para las celdas con un valor de 0, determina si se va a mostrar un 0 o una celda en blanco. Esto resulta útil cuando se ven los datos de cada día de un mes y algunos días aún no han ocurrido.  En vez de mostrar 0 para las fechas futuras, se pueden mostrar celdas en blanco. Los gráficos también respetan estas opciones de configuración (por ejemplo, si esta opción de configuración está marcada, no muestran ninguna línea ni ninguna barra con el valor 0). |
| Contexto | Determina si una celda muestra u oculta todo el formato de la celda, que incluye la gráfico de barras y el formato condicional. |
| Gráfico de barras | Muestra un gráfico de barras horizontales que representa el valor de la celda en relación con el total de la columna. |
| Formato condicional | Consulte la siguiente sección. |
| Vista previa de celdas de tabla | Muestra una vista previa del aspecto de cada una de las celdas con las opciones de formato seleccionadas actualmente aplicadas. |


## Conditional formatting {#section_3DD847151DA14914888A70FC4FD7BDFB}

El formato condicional aplica formato que puede definir a los límites superior, medio e inferior. La aplicación de formato condicional (colores, etc.) en tablas improvisadas también se activa automáticamente en los desgloses, a menos que se seleccionen los límites "Personalizados".

![](assets/conditional-formatting.png)

| Elemento | Descripción |
|--- |--- |
| Formato condicional | Aplica los colores siguientes a las celdas, en función de los valores de los datos: <ul><li>Verde: valores altos</li><li>Amarillo: valores medios</li><li>Rojo: valores bajos</li></ul><br>Sustituir una dimensión en la tabla restablece los límites de formato condicional. Cuando se sustituye una métrica se vuelven a calcular los límites de dicha columna (donde las métricas se encuentran en el eje X y las dimensiones se encuentran en el eje Y). |
| Usar límites porcentuales | Le permite utilizar los límites superior, medio e inferior basándose en valores porcentuales para cada métrica. Esto sirve para métricas que solo se basan en porcentajes (como el porcentaje de rebote), así como para métricas que tienen un recuento y un porcentaje (como las vistas de la página). |
| Generación automática | Genera automáticamente límites para el formato condicional. El límite superior es el valor máximo de esta columna. El límite inferior es el valor más bajo y el punto medio es la media entre los límites superior e inferior. |
| Personalizado | Puede asignar de forma manual los valores de los campos Superior, Punto medio y Límite inferior para el formato condicional. Esto le proporciona la flexibilidad para determinar si el valor de una columna es bueno, medio o malo. |
| Vista previa de celdas de tabla | Muestra una vista previa del aspecto de cada una de las celdas con las opciones de formato seleccionadas actualmente aplicadas. |

>[!MORELIKETHIS]
>
>* [Administración de fuentes de datos](/help/analyze/analysis-workspace/visualizations/t-sync-visualization.md)


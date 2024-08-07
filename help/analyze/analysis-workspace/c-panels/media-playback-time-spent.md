---
title: Panel Tiempo invertido en la reproducción de contenido
description: Cómo utilizar e interpretar el panel Tiempo invertido en la reproducción de contenido en Analysis Workspace.
feature: Panels
role: User, Admin
exl-id: 9268baf7-b50b-4c09-a722-7bfcd4172f15
source-git-commit: 4633225cc35658a7de39a40cd77df00137a54461
workflow-type: tm+mt
source-wordcount: '928'
ht-degree: 73%

---

# Panel Tiempo invertido en la reproducción de contenido

En Analysis Workspace, Tiempo invertido en la reproducción de contenido es la cantidad de tiempo que se emplea para ver flujos de medios en un momento específico. Incluye pausa, búfer y tiempo para el inicio.

El panel Tiempo invertido en la reproducción de contenido permite analizar la reproducción a lo largo del tiempo, con detalles sobre los picos de concurrencia y la capacidad de realizar desgloses y comparaciones.

Los clientes que hayan adquirido el complemento de recopilación de medios de streaming pueden analizar el tiempo invertido en la reproducción para obtener un valioso conocimiento de la calidad del contenido y la participación del visualizador, así como para ayudar a solucionar problemas o a planificar el volumen y la escala.

El tiempo invertido en la reproducción puede ayudarle a comprender lo siguiente:

* Donde se produjo la concurrencia máxima

* Dónde se produjeron los descensos

A continuación se muestra un vídeo introductorio de este panel:

>[!VIDEO](https://video.tv.adobe.com/v/338699)

## Uso del panel Tiempo invertido en la reproducción de medios

1. Vaya a un grupo de informes con los componentes de medios de streaming habilitados.
1. Seleccione el icono del panel en el extremo izquierdo y, a continuación, arrastre el panel a su proyecto de Analysis Workspace.
1. Continúe con las secciones siguientes para personalizar el panel Tiempo invertido en la reproducción de medios

   * [Entradas de panel](#panel-inputs)
   * [Salida de panel](#panel-output)

## Entradas de panel {#Input}

Puede configurar el panel Tiempo invertido en la reproducción de contenido con esta configuración de entrada:

| Configuración | Descripción |
|---|---|
| Intervalo de fecha del panel | El intervalo de fechas predeterminado del panel es Hoy. Puede editarlo para ver un solo día o varios meses a la vez.<br>Esta visualización está limitada a 1440 filas de datos (por ejemplo, 24 horas con una granularidad por minuto). Si la combinación de intervalo de fechas y granularidad genera más de 1440 filas, la granularidad se actualiza automáticamente para dar cabida al intervalo de fechas completo. |
| Granularidad | El valor predeterminado de granularidad es Minuto.<br>Esta visualización está limitada a 1440 filas de datos (por ejemplo, 24 horas con una granularidad por minuto). Si la combinación de intervalo de fechas y granularidad genera más de 1440 filas, la granularidad se actualiza automáticamente para dar cabida al intervalo de fechas completo. |
| Números de resumen del panel | Para ver los detalles de fecha y hora del tiempo invertido en la reproducción, hay disponible un número de resumen. El Máximo muestra detalles para la concurrencia máxima. El Mínimo muestra los detalles de la emisión. Suma recoge el tiempo total de reproducción invertido para la selección. El panel predeterminado muestra Máximo solamente, pero puede cambiarlo para mostrar Mínimo, Suma o cualquier combinación de los tres.<br>Si utiliza desgloses, se muestra un número de resumen para cada uno. |
| Desglose de serie | De forma opcional, puede desglosar la visualización por segmentos, dimensiones, elementos de dimensión o intervalos de fechas.<p>: Puede ver hasta 10 líneas a la vez. Los desgloses están limitados a un solo nivel.</p><p>: Al arrastrar una dimensión, los elementos de dimensión principales se seleccionarán automáticamente en función del intervalo de fechas del panel seleccionado.</p>: Para comparar intervalos de fechas, arrastre 2 o más intervalos de fechas al filtro de desglose de series. |
| Formato de hora | Puede ver el tiempo de reproducción transcurrido en `Hours:Minutes:Seconds` (predeterminado) o en `Minutes` (que se muestra en números enteros redondeados a 0,5). |
| Visualización de la secuencia de fechas | Si ha colocado al menos dos segmentos de intervalo de fechas como desgloses de serie, verá la opción para seleccionar superposición (predeterminada) o secuencial. La superposición mostrará las líneas con un inicio común del eje x para que se ejecuten en paralelo, mientras que la secuencial mostrará las líneas con su inicio específico del eje x. Si los datos se alinean (por ejemplo, el segmento 1 termina a las 8:44 p. m. y el segmento 2 comienza a las 8:45 p. m.), las líneas se mostrarán en secuencia. |

## Vista predeterminada

![Vista predeterminada](assets/mpts_default_view.png)

## Salida de panel {#Output}

El panel Tiempo invertido en la reproducción de contenido devuelve un gráfico de líneas y números de resumen para incluir detalles sobre el tiempo de reproducción máximo, mínimo o total. En la parte superior del panel, se proporciona una línea de resumen para recordarle la configuración del panel seleccionada.

En cualquier momento, puede editar y rediseñar el panel haciendo clic en el lápiz de edición en la parte superior derecha.

Si seleccionó el desglose de series, se mostrará una línea en el gráfico de líneas y un número de resumen para cada uno:

![salida de tiempo invertido en la reproducción de contenido](assets/mpts_outputs1.png)

### Fuente de datos

La única métrica que se puede usar en este panel es Tiempo invertido en la reproducción.

| Métrica | Descripción |
|---|---|
| Tiempo invertido en la reproducción | Total `hours:minutes:seconds` (o `minutes`) de contenido visualizado durante la granularidad seleccionada, incluyendo pausa, búfer y tiempo para el inicio. |

## Preguntas frecuentes

| Pregunta | Respuesta |
|---|---|
| ¿Dónde está la tabla de forma libre? ¿Cómo puedo ver la fuente de datos? | La tabla de forma libre no está disponible en esta vista. Puede descargar la fuente de datos haciendo clic con el botón derecho en el gráfico de líneas y descargando el archivo CSV. |
| ¿Por qué ha cambiado la granularidad? | Esta visualización está limitada a 1440 filas de datos (por ejemplo, 24 horas con una granularidad por minuto). Si la combinación de intervalo de fechas y granularidad genera más de 1440 filas, la granularidad se actualizará automáticamente para dar cabida al intervalo de fechas completo. <p>Al cambiar de un intervalo de fechas más grande a uno más pequeño, la granularidad se actualiza con el detalle más bajo permitido una vez que se cambia el intervalo de fechas. Para ver una granularidad más alta, edite el panel y vuelva a generar.</p> |
| ¿Cómo comparo nombres de vídeo, segmentos, tipos de contenido, etc.? | Para compararlos en una sola visualización, arrastre segmentos, dimensiones o elementos de dimensión específicos en el filtro de desglose de series. La vista está limitada a 10 desgloses. Para ver más de 10, debe usar varios paneles. |
| ¿Cómo comparo intervalos de fechas? | Para comparar intervalos de fechas en una sola visualización, utilice los desgloses de series arrastrando 2 o más intervalos de fechas. Estos intervalos de fechas anularán el intervalo de fechas del panel. |
| ¿Cómo cambio el tipo de visualización? | Este panel solo permite la visualización de líneas de la serie temporal. |
| ¿Puedo ejecutar la detección de anomalías? | No. La detección de anomalías no está disponible para este panel. |

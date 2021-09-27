---
title: Panel de tiempo invertido en la reproducción de contenido
description: Cómo usar e interpretar el panel Tiempo invertido en la reproducción de contenido en Analysis Workspace.
feature: Panels
role: User, Admin
exl-id: null
source-git-commit: c799efba2ddffc3f419fdac4187355d33e78a9ca
workflow-type: tm+mt
source-wordcount: '981'
ht-degree: 49%

---

# Panel de tiempo invertido en la reproducción de contenido

Los clientes de Media Analytics pueden analizar el tiempo invertido en la reproducción para comprender dónde se produjo la concurrencia máxima o dónde se produjeron los descensos y proporcionar una valiosa perspectiva de la calidad del contenido y la participación del visor, así como ayudar a solucionar problemas o a planificar el volumen o la escala.

En Analysis Workspace, Tiempo de reproducción transcurrido es la cantidad de tiempo que se pasa viendo los flujos de medios en un momento específico, e incluye la pausa, el búfer y el tiempo para el inicio.

El panel Tiempo invertido en reproducción de contenido permite analizar la reproducción a lo largo del tiempo, con detalles sobre la concurrencia máxima y la capacidad de realizar desgloses y comparaciones. Para acceder al panel Tiempo invertido en la reproducción de contenido, vaya a un grupo de informes con los componentes de Media Analytics activados. A continuación, haga clic en el icono del panel situado en el extremo izquierdo y arrastre el panel a su proyecto de Analysis Workspace.

Este panel también incluye nueva funcionalidad en el calendario que le permite seleccionar y mostrar menos de 24 horas. Puede hacerlo para todo el panel o puede crear segmentos utilizando periodos de tiempo consecutivos para poder rastrear el ingreso/salida de audiencia en programas o secciones de programas. Una vez que haya colocado al menos dos de esos segmentos de fecha, verá una opción de botón de opción para Visualización de secuencia de fecha que superpondrá las líneas con un inicio de eje x común o las mostrará en secuencia con su inicio específico del eje x.

## Entradas de panel {#Input}

Puede configurar el panel Tiempo invertido en la reproducción de contenido con esta configuración de entrada:

| Configuración | Descripción |
|---|---|
| Intervalo de fecha del panel | El intervalo de fechas predeterminado del panel es Hoy. Puede editarlo para ver un solo día o varios meses a la vez.<br>Esta visualización está limitada a 1440 filas de datos (por ejemplo, 24 horas con una granularidad por minuto). Si la combinación de intervalo de fechas y granularidad genera más de 1440 filas, la granularidad se actualiza automáticamente para dar cabida al intervalo de fechas completo. |
| Granularidad | El valor predeterminado de granularidad es Minuto.<br>Esta visualización está limitada a 1440 filas de datos (por ejemplo, 24 horas con una granularidad por minuto). Si la combinación de intervalo de fechas y granularidad genera más de 1440 filas, la granularidad se actualiza automáticamente para dar cabida al intervalo de fechas completo. |
| Números de resumen del panel | Para ver los detalles de fecha y hora del tiempo de reproducción transcurrido, hay disponible un número de resumen. El Máximo muestra detalles para la concurrencia máxima. El Mínimo muestra los detalles de la emisión. Sum suma el tiempo total de reproducción empleado para la selección. El panel predeterminado muestra Máximo solamente, pero puede cambiarlo para mostrar Mínimo, Suma o cualquier combinación de los tres.<br>Si utiliza desgloses, se muestra un número de resumen para cada uno. |
| Desglose de serie | De forma opcional, puede desglosar la visualización por segmentos, dimensiones, elementos de dimensión o intervalos de fechas.<p>: Puede ver hasta 10 líneas a la vez. Los desgloses están limitados a un solo nivel.</p><p>: Al arrastrar una dimensión, los elementos de dimensión principales se seleccionarán automáticamente en función del intervalo de fechas del panel seleccionado.</p>: Para comparar intervalos de fechas, arrastre 2 o más intervalos de fechas al filtro de desglose de series. |
| Formato de hora | Puede ver el tiempo de reproducción transcurrido en horas:Minutes:segundos (predeterminado) o en minutos (que se muestra en números enteros redondeados a 0,5). |
| Visualización de la secuencia de fechas | Si ha colocado al menos dos segmentos de intervalo de fechas como desgloses de serie, verá la opción para seleccionar superposición (predeterminada) o secuencial. La superposición mostrará las líneas con un inicio común del eje x para que se ejecuten en paralelo, mientras que la secuencial mostrará las líneas con su inicio específico del eje x. Si los datos se alinean (por ejemplo, el segmento 1 termina a las 8:44 pm y el segmento 2 comienza a las 8:45 pm), entonces las líneas se mostrarán en secuencia. |

### Vista predeterminada

![Vista predeterminada](assets/mpts_default_view.png)

## Salida de panel {#Output}

El panel Tiempo invertido en la reproducción de contenido devuelve un gráfico de líneas y números de resumen para incluir detalles sobre el tiempo de reproducción máximo, mínimo o total. En la parte superior del panel, se proporciona una línea de resumen para recordarle la configuración del panel seleccionada.

En cualquier momento, puede editar y rediseñar el panel haciendo clic en el lápiz de edición en la parte superior derecha.

Si seleccionó el desglose de series, se mostrará una línea en el gráfico de líneas y un número de resumen para cada uno:

![salida de tiempo empleado de reproducción de contenido](assets/mpts_outputs1.png)

### Fuente de datos

La única métrica que se puede usar en este panel es Tiempo de reproducción transcurrido.

| Métrica | Descripción |
|---|---|
| Tiempo de reproducción transcurrido | Total de horas:minutes:segundos (o minutos) de contenido visualizado durante la granularidad seleccionada, incluida la pausa, el búfer y el tiempo para el inicio. |

## Preguntas frecuentes {#FAQ}

| Pregunta | Respuesta |
|---|---|
| ¿Dónde está la tabla improvisada? ¿Cómo puedo ver la fuente de datos? | <p></p><p>La tabla improvisada no está disponible en esta vista. Puede descargar la fuente de datos haciendo clic con el botón derecho en el gráfico de líneas y descargando el archivo CSV.</p> |
| <p>¿Por qué ha cambiado la granularidad?</p> | <p>Esta visualización está limitada a 1440 filas de datos (por ejemplo, 24 horas con una granularidad por minuto). Si la combinación de intervalo de fechas y granularidad genera más de 1440 filas, la granularidad se actualizará automáticamente para dar cabida al intervalo de fechas completo.</p><p></p><p>Al cambiar de un intervalo de fechas más grande a uno más pequeño, la granularidad se actualiza con el detalle más bajo permitido una vez que se cambia el intervalo de fechas. Para ver una granularidad más alta, edite el panel y vuelva a generar.</p> |
| <p></p><p>¿Cómo comparo nombres de vídeo, segmentos, tipos de contenido, etc.?</p> | <p>Para compararlos en una sola visualización, arrastre segmentos, dimensiones o elementos de dimensión específicos en el filtro de desglose de series.</p><p></p><p>La vista está limitada a 10 desgloses. Para ver más de 10, debe usar varios paneles.</p> |
| ¿Cómo comparo intervalos de fechas? | Para comparar intervalos de fechas en una sola visualización, utilice los desgloses de series arrastrando 2 o más intervalos de fechas. Estos intervalos de fechas anularán el intervalo de fechas del panel. |
| ¿Cómo cambio el tipo de visualización? | <p></p><p>Este panel solo permite la visualización de líneas de la serie temporal.</p> |
| ¿Puedo ejecutar la detección de anomalías? | <p></p><p>No. La detección de anomalías no está disponible para este panel.</p> |

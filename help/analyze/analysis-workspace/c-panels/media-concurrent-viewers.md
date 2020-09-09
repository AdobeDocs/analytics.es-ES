---
title: Panel de visores simultáneos de medios
description: Cómo utilizar e interpretar el panel Visores simultáneos de medios en Analysis Workspace.
translation-type: tm+mt
source-git-commit: b55faba0298dffa9df9e45c13c2770fe7ffcdce4
workflow-type: tm+mt
source-wordcount: '1068'
ht-degree: 9%

---


# Panel de visores simultáneos de medios

>[!IMPORTANT]
>
>Esta función está en Prueba limitada para clientes de análisis de medios. [Más información...](https://docs.adobe.com/content/help/es-ES/analytics/landing/an-releases.html)

Los clientes de Media Analytics pueden analizar los visores simultáneos para comprender dónde se produjo el pico de concurrencia o dónde se produjeron los descensos y proporcionar una valiosa perspectiva de la calidad del contenido y la participación del visor, así como para ayudar a solucionar problemas o a planificar el volumen o la escala.

En Analysis Workspace, los visores simultáneos es el número de visitantes únicos que visualizan sus flujos de medios en un momento específico, independientemente del número de sesiones.

El panel Visores simultáneos de medios permite la análisis de visores simultáneos con el paso del tiempo, con detalles sobre la concurrencia máxima y la capacidad de desglosar y comparar.  Para acceder al panel Visores simultáneos de medios, vaya a un grupo de informes con los componentes de Media Analytics activados. A continuación, haga clic en el icono del panel situado en el extremo izquierdo y arrastre el panel al proyecto de Analysis Workspace.

## Entradas de panel {#Input}

Puede configurar el panel Visores simultáneos de medios con esta configuración de entrada:

| Configuración | Descripción |
|---|---|
| Intervalo de fechas del panel | El intervalo de fechas predeterminado del panel es Hoy.  Puede editarlo para la vista de un solo día o de varios meses a la vez. <br> <br> Esta visualización está limitada a 1440 filas de datos (por ejemplo, 24 horas con una granularidad por minuto).  Si una combinación de intervalo de fechas y granularidad da como resultado más de 1440 filas, la granularidad se actualiza automáticamente para dar cabida al intervalo de fechas completo. |
| Granularidad | El valor predeterminado de granularidad es Minuto. <br> <br>Esta visualización está limitada a 1440 filas de datos (por ejemplo, 24 horas con una granularidad por minuto).  Si una combinación de intervalo de fechas y granularidad da como resultado más de 1440 filas, la granularidad se actualiza automáticamente para dar cabida al intervalo de fechas completo. |
| Números de resumen del panel | Para ver los detalles de fecha y hora de los visores simultáneos, hay disponible un número de resumen. El valor Máximo muestra los detalles de la concurrencia máxima. El Mínimo muestra los detalles del valle.  El panel predeterminado muestra Máximo solamente, pero puede cambiarlo para mostrar Mínimo o Máximo y Mínimo.<br><br>Si utiliza desgloses, se muestra un número de resumen para cada uno. |
| Desglose de serie | Si lo desea, puede desglosar la visualización por segmentos, dimensiones, elementos de dimensión o intervalos de fechas. <br><br>- Puede vista de hasta 10 líneas a la vez. Los desgloses están limitados a un solo nivel.<br><br>- Al arrastrar una dimensión, los elementos de dimensión principales se seleccionarán automáticamente en función del intervalo de fechas del panel seleccionado.<br><br>- Para comparar intervalos de fechas, arrastre 2 o más intervalos de fechas al filtro de desglose de series. |

### Vista predeterminada

![Vista predeterminada](assets/concurrent-viewers-default.png)


### Vista de desglose de serie

![vista de desglose de serie](assets/concurrent-viewers-series-breakdown.png)

## Salida de panel {#Output}

El panel Visores simultáneos de medios devuelve un gráfico de líneas y números de resumen para incluir detalles de los visores simultáneos máximos y/o mínimos.  En la parte superior del panel, se proporciona una línea de resumen para recordarle la configuración del panel seleccionada.

En cualquier momento, puede editar y reconstruir el panel haciendo clic en el lápiz de edición en la parte superior derecha.

Si seleccionó el desglose de series, se mostrará una línea en el gráfico de líneas y un número de resumen para cada una de ellas:

![salida de visores simultáneos](assets/concurrent-viewers-output.png)

### Fuente de datos

La única métrica que se puede utilizar en este panel son los visores simultáneos:

| Métrica | Descripción |
|---|---|
| Visualizadores simultáneos | Número de visitantes únicos que ven los flujos de medios en un momento específico, independientemente del número de sesiones.<br><br>Esto es diferente al sistema de informes del visor simultáneo en la sección Informes, que utiliza Sesiones activas simultáneos.  El uso de cuentas de visitantes únicas para eliminar los &quot;picos&quot; no deseados en los límites del programa (donde las sesiones finalizan y comienzan al mismo tiempo). |

No hay una tabla improvisada disponible en esta vista.  Para realizar la vista del origen de datos, puede hacer clic con el botón derecho en el gráfico de líneas y descargarlo como archivo .csv.  Se incluirán desgloses de serie.


![salida de visores simultáneos](assets/concurrent-viewers-download-csv.png)

## Preguntas frecuentes {#FAQ}

| Pregunta | Respuesta |
|---|---|
| ¿Dónde está la tabla improvisada? ¿Cómo puedo ver la fuente de datos? | La tabla improvisada no está disponible en esta vista.  Puede descargar la fuente de datos haciendo clic con el botón derecho en el gráfico de líneas y descargando el archivo CSV. |
| ¿Por qué cambió mi granularidad? | Esta visualización está limitada a 1440 filas de datos (por ejemplo, 24 horas con una granularidad por minuto).  Si una combinación de intervalo de fechas y granularidad da como resultado más de 1440 filas, la granularidad se actualizará automáticamente para dar cabida al intervalo de fechas completo.<br><br>Cuando se cambia de un intervalo de fechas más grande a uno más pequeño, la granularidad se actualiza al detalle más bajo permitido una vez que se cambia el intervalo de fechas. Para vista de una granularidad mayor, edite el panel y vuelva a compilarlo. |
| ¿Cómo comparo nombres de vídeo, segmentos, tipos de contenido, etc.? | Para compararlas en una sola visualización, arrastre segmentos, dimensiones o elementos de dimensión específicos en el filtro de desglose de serie.<br><br>La vista está limitada a 10 desgloses.  Para vista de más de 10, debe utilizar varios paneles. |
| ¿Cómo comparo intervalos de fechas? | Para comparar intervalos de fechas en una sola visualización, utilice los desgloses de series arrastrando 2 o más intervalos de fechas.  Estos intervalos de fechas anularán el intervalo de fechas del panel. |
| ¿Cómo cambio el tipo de visualización? | Este panel solo permite la visualización de líneas para la serie temporal. |
| ¿Puedo ejecutar la detección de anomalías? | No.  La detección de anomalías no está disponible para este panel. |
| ¿Por qué utilizar visitantes únicos en lugar de sesiones activas? | El uso de visitantes únicos permite eliminar los picos no deseados en los límites del programa (donde las sesiones finalizan y comienzan al mismo tiempo). |
| ¿Qué significa tener visores simultáneos con una granularidad mayor que el minuto? | Con una granularidad de más de un minuto, los visores simultáneos son la suma de visores simultáneos únicos para todos los minutos dentro de ese intervalo de tiempo.  Por ejemplo, en la granularidad de nivel de hora, los visores concurrentes es la suma de los visores concurrentes únicos para todos los minutos dentro de la hora. |
| ¿Qué sucede si deseo ver más de un día en la granularidad de nivel de minuto? | Para acceder a los datos en granularidad de nivel de minuto durante un mes como máximo, puede utilizar las API de Analytics 2.0. Para obtener más información, consulte API [de Analytics 2.0](https://www.adobe.io/apis/experiencecloud/analytics/docs.html). |
| ¿Muestra el panel del área de trabajo la misma información que el informe Visores simultáneos? | No.  En Analysis Workspace, los visores simultáneos se definen como el número de visitantes únicos que visualizan el flujo de medios en un momento determinado, independientemente del número de sesiones.<br></br>Esto es diferente al sistema de informes del visor simultáneo en la sección Informes, que utiliza Sesiones activas simultáneos.  El uso de cuentas de visitantes únicas para eliminar picos no deseados en los límites del programa, donde las sesiones finalizan y comienzan al mismo tiempo. |

<!-- For more information about Media Concurrent Viewers, visit [MA doc page]( https://url). -->

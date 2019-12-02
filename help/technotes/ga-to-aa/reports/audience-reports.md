---
title: Informes de audiencia en Adobe Analytics
description: Obtenga información sobre cómo crear informes basados en audiencias mediante Analysis Workspace.
translation-type: tm+mt
source-git-commit: 6217430bf0ae9c0f9c6426e4bb2a8101257068e7

---


# Informes de audiencia

Los informes de audiencia muestran información sobre los tipos de personas que visitan el sitio.

Esta página supone que el usuario tiene conocimientos básicos sobre el uso de Analysis Workspace. Consulte [Creación de un informe básico en Analysis Workspace para usuarios](create-report.md) de Google Analytics si todavía no está familiarizado con la herramienta en Adobe Analytics.

## Usuarios activos

Los usuarios activos muestran el número acumulado de usuarios en el sitio en los 1, 7, 14 o 28 días anteriores. Aunque Adobe no tiene el cálculo exacto utilizado en Google Analytics, puede utilizar la métrica Visitantes únicos para ver un recuento deduplicado de usuarios en su sitio en función del intervalo de fechas seleccionado.

Para obtener un gráfico de líneas de visitantes únicos:

1. Haga clic en el icono Visualizaciones de la izquierda y arrastre la visualización Línea al espacio de trabajo sobre la tabla improvisada vacía.
2. Haga clic en el icono Componentes de la izquierda y, a continuación, arrastre la métrica Visitantes **** únicos al espacio más pequeño rotulado 'Colocar una métrica aquí'.
3. Si desea una granularidad diferente, arrastre el intervalo de fechas deseado (por ejemplo, **Día**, **Semana**, **Mes**, etc.) encima del encabezado de dimensión de fecha existente.

Consulte Visitantes [](/help/components/c-variables/c-metrics/metrics-unique-visitors.md) únicos en la guía del usuario Componentes para obtener más información sobre cómo calcula Adobe los visitantes únicos.

## Valor de duración

El valor de duración es una característica que requiere una implementación especializada adicional en ambas plataformas. Adobe recomienda trabajar con un consultor de implementación para obtener estos datos.

## Análisis de cohorte

El análisis de cohorte muestra la frecuencia con la que los mismos usuarios regresan al sitio.

Para crear una tabla de cohorte:

1. Haga clic en el icono Visualización de la izquierda y arrastre la visualización Tabla de cohorte al espacio de trabajo.
2. Haga clic en el icono Componentes de la izquierda y, a continuación, arrastre la métrica **Visitas** a los criterios de inclusión y de retorno.
3. Haga clic en Crear.

Consulte Análisis [de](/help/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) cohorte en la guía del usuario de Analysis Workspace para obtener más información sobre las personalizaciones adicionales de la visualización de cohorte.

## Audiencias

El informe Audiencias de Google Analytics requiere la configuración de audiencias. Las audiencias también requieren configuración en Adobe a través de Adobe Audience Manager. Consulte la guía del usuario de Adobe Audience Manager para obtener más información.

## Explorador de usuarios

El informe Explorador de usuarios permite a un analista ver visitas individuales mediante identificadores anónimos. Adobe no saca a la superficie los identificadores back-end fuera de las fuentes de datos, que son exportaciones de datos sin procesar en el nivel de visita individual.

* Si estos datos se desean en Analysis Workspace, es posible trabajar con un consultor de implementación para pasar el valor de cookie de identificador único anónima a una eVar. Tenga en cuenta que esto solo funciona con implementaciones más pequeñas que consisten en menos de 1 millón de visitantes únicos por mes.
* Si estos datos se desean dentro de las fuentes de datos, las columnas concatenadas `visid_high` y `visid_low` son la forma más común de identificar visitantes únicos. Obtenga más información sobre las fuentes [de datos](/help/export/analytics-data-feed/data-feed-overview.md) en la Guía del usuario de exportación.

## Informes demográficos e intereses

Los datos demográficos y de intereses proporcionan información sobre la edad, el sexo y los intereses de los usuarios del sitio. Google recopila esos datos mediante sus capacidades de seguimiento entre sitios.

Adobe no recopila automáticamente los datos demográficos y de intereses. Sin embargo, si su organización obtiene estos datos, puede utilizar Atributos del cliente, una función de la plataforma de Adobe Experience Cloud. Permite un control total de la organización de los datos por atributos, y no se limita sólo a la demografía o a los intereses.

Consulte la Ayuda de Atributos del cliente para obtener más información.

## Geografía - Idioma

El informe de idioma geográfico muestra el tráfico del sitio según la configuración de idioma del explorador del visitante.

Para crear un informe de idioma:

1. En el menú Componentes, busque la dimensión **Idioma** y arrástrela hasta el área grande de la tabla improvisada con la etiqueta 'Colocar una dimensión aquí'.
2. Arrastre las métricas deseadas al espacio de trabajo junto con la métrica **Ocurrencias** creada automáticamente. Consulte la guía [de traducción de](common-metrics.md) métricas para obtener detalles sobre cómo obtener cada métrica respectiva.

Consulte la dimensión [Idioma](/help/components/c-variables/dimensionslist/reports-languages.md) en la guía del usuario Componentes para obtener más información.

## Geografía - Ubicación

El informe de ubicación geográfica proporciona una vista de mapa mundial, desglosando los datos por país.

Para crear un informe de ubicación geográfica:

1. Haga clic en el icono Visualizaciones de la izquierda y arrastre la visualización Mapa al espacio de trabajo sobre la tabla improvisada vacía.
2. Haga clic en el icono Componentes de la izquierda y, a continuación, arrastre la métrica Visitantes **** únicos al espacio rotulado 'Agregar métrica'.
3. Haga clic en Crear.

Si la tabla también se desea además del mapa:

1. En el menú Componentes, busque la dimensión **Países** y arrástrela al área grande de la tabla improvisada con la etiqueta 'Colocar una dimensión aquí'.
2. Arrastre las métricas deseadas al espacio de trabajo junto con la métrica **Ocurrencias** creada automáticamente. Consulte la guía [de traducción de](common-metrics.md) métricas para obtener detalles sobre cómo obtener cada métrica respectiva.

Consulte [Dimensiones de segmentación](/help/components/c-variables/dimensionslist/reports-geosegmentation.md) geográfica en la guía del usuario Componentes para obtener más información.

## Comportamiento: nuevo vs. recurrente

El informe nuevo vs. recurrente proporciona una vista simplificada de las primeras sesiones (nuevas visitas) vs. las sesiones subsiguientes (visitas de retorno).

Para crear un informe de visitas nuevas vs. recurrentes:

1. En el menú de componentes, busque el segmento **Visitas** por primera vez y arrástrelo al área grande de la tabla improvisada denominada 'Colocar una dimensión aquí'. Tenga en cuenta que las **primeras visitas** son un segmento, mientras que Workspace suele utilizar dimensiones para representar filas.
2. Busque el segmento **Visitas** de retorno y arrástrelo sobre el encabezado de fila Segmentos. Esto agrega el segmento como una dimensión debajo de Visitas por primera vez, lo que permite una comparación sencilla.
3. Arrastre las métricas deseadas al espacio de trabajo junto con la métrica **Ocurrencias** creada automáticamente. Consulte la guía [de traducción de](common-metrics.md) métricas para obtener detalles sobre cómo obtener cada métrica respectiva.

Si también se desea un gráfico de líneas:

1. Haga clic en el icono de visualizaciones de la izquierda y arrastre una visualización Línea al espacio de trabajo sobre la tabla improvisada
2. Utilice ctrl+clic (Windows) o cmd+clic (Mac) en cada fila de la tabla improvisada para resaltarlos. Esto permite que ambas tendencias aparezcan en la visualización de líneas.
3. Haga clic en el pequeño punto redondeado de color en la esquina superior izquierda de la visualización de línea y, a continuación, haga clic en la casilla de verificación 'Bloquear selección'.

## Comportamiento: frecuencia y actualización

El informe de frecuencia y actualización es aproximadamente igual a la dimensión Número **de** visita en Analysis Workspace.

1. En el menú de componentes, localice la dimensión Número **de** visita y arrástrela hasta el área grande de la tabla improvisada con la etiqueta 'Colocar una dimensión aquí'.
2. Arrastre las métricas deseadas al espacio de trabajo junto con la métrica **Ocurrencias** creada automáticamente. Consulte la guía [de traducción de](common-metrics.md) métricas para obtener detalles sobre cómo obtener cada métrica respectiva.

Consulte la dimensión Número [de](/help/components/c-variables/dimensionslist/reports-visitor-number.md) visita en la guía del usuario Componentes para obtener más información.

## Comportamiento - Participación

El informe de participación es aproximadamente igual a la dimensión **Tiempo empleado por visita - Agrupado** .

1. En el menú de componentes, busque la dimensión **Tiempo empleado por visita - Agrupado** y arrástrela al área grande de la tabla improvisada denominada 'Colocar una dimensión aquí'.
2. Arrastre las métricas deseadas al espacio de trabajo junto con la métrica **Ocurrencias** creada automáticamente. Consulte la guía [de traducción de](common-metrics.md) métricas para obtener detalles sobre cómo obtener cada métrica respectiva.

Consulte la dimensión [Tiempo empleado por visita](/help/components/c-variables/dimensionslist/reports-time-spent-per-visit.md) en la guía del usuario Componentes para obtener más información.

## Tecnología: explorador y SO

Hay varias dimensiones principales disponibles en el informe Explorador y sistema operativo.

* La dimensión principal del **explorador** también está disponible en Analysis Workspace como dimensión.
* La dimensión principal del sistema **operativo** también está disponible en Analysis Workspace como dimensión.
* La dimensión principal de la resolución **de** pantalla está disponible en Analysis Workspace como dimensión **Resolución** del monitor.
* La dimensión **Colores** de pantalla principal está disponible en Analysis Workspace como dimensión **Profundidad** de color.
* La dimensión principal de la versión **** Flash no está disponible en Adobe Analytics, pero si se desea, una eVar puede recopilar estos datos.

1. En el menú de componentes, localice la dimensión deseada indicada arriba y arrástrela al área grande de la tabla improvisada con la etiqueta 'Colocar una dimensión aquí'.
2. Arrastre las métricas deseadas al espacio de trabajo junto con la métrica **Ocurrencias** creada automáticamente. Consulte la guía [de traducción de](common-metrics.md) métricas para obtener detalles sobre cómo obtener cada métrica respectiva.

Consulte las páginas siguientes en la guía del usuario Componentes para obtener más información sobre sus dimensiones respectivas:

* [Explorador](/help/components/c-variables/dimensionslist/reports-browsers.md)
* [Sistema operativo ](/help/components/c-variables/dimensionslist/reports-operating-system.md)
* [Resolución del monitor](/help/components/c-variables/dimensionslist/reports-technology.md)
* [Profundidad de color](/help/components/c-variables/dimensionslist/reports-color-depth.md)

## Tecnología - Red

El informe de red es aproximadamente igual a la dimensión **Dominio** .

1. En el menú de componentes, busque la dimensión **Dominio** y arrástrela al área grande de la tabla improvisada con la etiqueta 'Colocar una dimensión aquí'.
2. Arrastre las métricas deseadas al espacio de trabajo junto con la métrica **Ocurrencias** creada automáticamente. Consulte la guía [de traducción de](common-metrics.md) métricas para obtener detalles sobre cómo obtener cada métrica respectiva.

Consulte la dimensión [Dominio](/help/components/c-variables/dimensionslist/reports-domains.md) en la guía del usuario Componentes para obtener más información.

## Móvil - Información general

El informe de información general móvil es aproximadamente igual a la dimensión Tipo **de dispositivo** móvil. Tenga en cuenta que el valor 'Otro' es equivalente al tráfico de escritorio.

1. En el menú de componentes, busque la dimensión Tipo **de dispositivo** móvil y arrástrela al área grande de la tabla improvisada con la etiqueta 'Colocar una dimensión aquí'.
2. Arrastre las métricas deseadas al espacio de trabajo junto con la métrica **Ocurrencias** creada automáticamente. Consulte la guía [de traducción de](common-metrics.md) métricas para obtener detalles sobre cómo obtener cada métrica respectiva.

Consulte la dimensión Tipo [de dispositivo](/help/components/c-variables/dimensionslist/reports-device-types.md) móvil en la guía del usuario Componentes para obtener más información.

## Móvil - Dispositivos

El informe de dispositivos móviles es aproximadamente igual a la dimensión de dispositivos **** móviles.

1. En el menú de componentes, busque la dimensión Dispositivo **móvil** y arrástrela hasta el área grande de la tabla improvisada con la etiqueta 'Colocar una dimensión aquí'.
2. Arrastre las métricas deseadas al espacio de trabajo junto con la métrica **Ocurrencias** creada automáticamente. Consulte la guía [de traducción de](common-metrics.md) métricas para obtener detalles sobre cómo obtener cada métrica respectiva.

Consulte la dimensión Dispositivo [móvil](/help/components/c-variables/dimensionslist/reports-devices.md) en la guía del usuario Componentes para obtener más información.

## Personalizado

Los informes personalizados se definen por implementación. Póngase en contacto con el administrador de Analytics de su organización o con el consultor de implementación para interpretar estos informes. Normalmente, una organización mantiene un documento [de diseño de](/help/implement/prepare/solution-design.md) solución para realizar un seguimiento de los valores de las variables personalizadas y de cómo se rellenan.

## Prueba comparativa

Los informes de evaluación comparativa permiten ver cómo se comparan las facetas de los datos con los promedios del sector. Adobe no comparte datos de referencia entre sus clientes en este momento.

## Flujo de usuarios

El informe de flujo está disponible en ambas plataformas. Para crear un informe de flujo:

1. Haga clic en el icono de visualizaciones de la izquierda y arrastre una visualización de flujo al espacio de trabajo encima de la tabla improvisada
2. Busque la dimensión **Páginas** y, a continuación, haga clic en el icono de flecha para mostrar los valores de la página. Los valores de dimensión son de color amarillo.
3. Busque el valor de página deseado para comenzar y arrástrelo al espacio etiquetado como 'Dimensión o elemento' en el centro
4. Este informe de flujo es interactivo. Haga clic en cualquiera de los valores para expandir los flujos a páginas posteriores o anteriores. Utilice el menú que aparece al hacer clic con el botón derecho para expandir o contraer columnas. También se pueden utilizar distintas dimensiones dentro del mismo informe de flujo.

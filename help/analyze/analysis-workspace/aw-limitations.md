---
description: Lista de limitaciones conocidas en Adobe Analysis Workspace y sus componentes relacionados
title: Limitaciones conocidas en Analysis Workspace
translation-type: tm+mt
source-git-commit: 6e4eff57aa58cf4ad3535780614bdce5fa3c666f

---


# Limitaciones conocidas en Analysis Workspace

Esta es una lista de limitaciones conocidas en Analysis Workspace y sus componentes relacionados:

## Tablas

* No se pueden agregar columnas de comparación de fechas cuando se utilizan intervalos de fechas o métricas como filas de una tabla.
* La creación de métricas a partir de una selección se desactiva cuando los segmentos se utilizan como filas de una tabla. Además, la creación de una métrica a partir de una selección no debe aplicarse a columnas alineadas con la fecha.
* El formato condicional de las filas de desglose no puede utilizar intervalos personalizados.
* Las filas totales de la tabla no pueden incluir tendencias cuando se calculan los totales sumando la configuración de valores de fila (generalmente se utiliza con elementos de fila estáticos).
* [!UICONTROL El análisis de contribución] se puede ejecutar _solo_ con la granularidad [!UICONTROL diaria]. No se puede ejecutar con datos [!UICONTROL por hora], [!UICONTROL semanales], etc.

## Visualizaciones

* Las visualizaciones que aprovechan la segmentación, como [!UICONTROL Abandonos], [!UICONTROL Flujos], [!UICONTROL Cohorte] e [!UICONTROL Histograma], no pueden aceptar las métricas calculadas como entradas.
* [!UICONTROL Flujo]: Las dimensiones de entrada y salida, por ejemplo: [!UICONTROL página de entrada], no se pueden usar en Flujos.
* [!UICONTROL Cohorte]: Los números no enteros no se pueden usar como criterios de cohorte.

## Paneles

* Comparación de segmentos: El segmento [!UICONTROL Todos los demás] no se crea si se utiliza una plantilla de segmento en la zona de colocación inicial.

## Componentes &gt; Segmentos

* Ciertas métricas y dimensiones no se pueden segmentar, como [!UICONTROL Ocurrencias], [!UICONTROL Visitantes únicos], etc.
* Determinados componentes y operadores no están disponibles si se crea un segmento desde Workspace (en lugar de hacerlo desde [!UICONTROL Componentes &gt; Segmentos]). Por ejemplo, Dirección IP.

## Componentes &gt; Métricas calculadas

* Las métricas calculadas no se pueden usar en determinadas visualizaciones. Consulte “Visualizaciones”.
* Las métricas calculadas no se pueden usar en el panel de [!UICONTROL Attribution], ya que las métricas calculadas pueden incluir modelos de atribución independientes.
* Determinados componentes y operadores no están disponibles si se crea una métrica calculada desde Workspace (en lugar de hacerlo desde [!UICONTROL Componentes &gt; Segmentos]). Por ejemplo, [!UICONTROL Dirección IP].

## Componentes &gt; Intervalos de fechas

* Los intervalos de fechas personalizados no admiten [!UICONTROL Este día del año pasado], [!UICONTROL Este día del mes pasado], etc.

## Componentes &gt; Grupos de informes virtuales

* Cuando se habilita el procesamiento del tiempo del informe, no se admiten determinados componentes. Para obtener una lista completa, consulte [Procesamiento de intervalo de tiempo](/help/components/vrs/vrs-report-time-processing.md).

## Componentes &gt; Configuración de informes

* Algunas de las opciones de la página [!UICONTROL Configuración de informes] no se aplican. Analysis Workspace solo utiliza la configuración de [!UICONTROL Idioma, moneda y codificación] de la parte inferior: [!UICONTROL Separador de miles], [!UICONTROL Codificación de informes programados] y [!UICONTROL Carácter separador de CSV].

## Attribution IQ

* Un subconjunto de métricas no se admite en [!UICONTROL Attribution IQ]. Para obtener una lista completa, consulte las preguntas más frecuentes sobre [Attribution IQ](/help/analyze/analysis-workspace/attribution-iq/attribution-faq.md).

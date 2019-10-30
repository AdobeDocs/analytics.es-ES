---
description: 'null'
seo-description: 'null'
seo-title: Limitaciones del espacio de trabajo, limitaciones conocidas en Analysis Workspace
title: Limitaciones conocidas en Analysis Workspace
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Limitaciones conocidas en Analysis Workspace

Esta es una lista de limitaciones conocidas en Analysis Workspace y sus componentes relacionados:

## Tablas

* No se pueden agregar columnas de comparación de fechas cuando se utilizan intervalos de fechas o métricas como filas de una tabla.
* Crear métrica a partir de selección se desactiva cuando los segmentos se utilizan como filas de una tabla. Además, Crear métrica a partir de selección no debe aplicarse a columnas alineadas con la fecha.
* El formato condicional de las filas de desglose no puede utilizar intervalos personalizados.
* Las filas totales de la tabla no pueden ser de tendencias cuando se calculan los totales sumando la configuración de valores de fila (generalmente se utiliza con elementos de fila estáticos).
* [!UICONTROL El análisis] de contribución se puede ejecutar [!UICONTROL sólo] con la granularidad _diaria_. No se puede ejecutar con datos [!UICONTROL por hora], [!UICONTROL semanales], etc.

## Visualizaciones

* Las visualizaciones que aprovechan la segmentación, como [!UICONTROL Visitas en el orden previsto], [!UICONTROL Flujo], [!UICONTROL Cohorte]e [!UICONTROL Histograma], no pueden aceptar las métricas calculadas como entradas.
* [!UICONTROL Flujo]: Las dimensiones de entrada y salida, por ejemplo: página [!UICONTROL de]entrada, no se pueden usar en Flujo.
* [!UICONTROL Cohorte]: Los no enteros no se pueden usar como criterios de cohorte.

## Paneles

* Comparación de segmentos: El segmento [!UICONTROL Todos los demás] no se crea si se utiliza una plantilla de segmento en la zona de colocación inicial.

## Componentes &gt; Segmentos

* Ciertas métricas y dimensiones no se pueden segmentar, como [!UICONTROL Ocurrencias], Visitantes únicos, etc.
* Determinados componentes y operadores no están disponibles si se crea un segmento desde Workspace (en lugar de hacerlo desde [!UICONTROL Componentes &gt; Segmentos]). Por ejemplo, Dirección IP.

## Componentes &gt; Métricas calculadas

* Las métricas calculadas no se pueden usar en ciertas visualizaciones. Consulte "Visualizaciones" más arriba.
* Las métricas calculadas no se pueden usar en el panel [!UICONTROL Atribución] , ya que las métricas calculadas pueden incluir modelos de atribución independientes.
* Algunos componentes y operadores no están disponibles si se crea una métrica calculada desde Workspace (en lugar de hacerlo desde [!UICONTROL Componentes &gt; Segmentos]). Por ejemplo, Dirección [!UICONTROL IP].

## Componentes &gt; Intervalos de fechas

* Los intervalos de fechas personalizados no admiten [!UICONTROL Este día del año]pasado, [!UICONTROL Este día del mes]pasado, etc.

## Componentes &gt; Grupos de informes virtuales

* Cuando se habilita el procesamiento del tiempo del informe, no se admiten determinados componentes. Para obtener una lista completa, consulte Procesamiento [](/help/components/vrs/vrs-report-time-processing.md)de intervalo de tiempo.

## Componentes &gt; Configuración de informes

* Algunas de las opciones de la página Configuración [!UICONTROL de] informes no se aplican. Analysis Workspace solo utiliza la configuración de [!UICONTROL idioma, moneda y codificación] de la parte inferior: Separador [!UICONTROL de]miles, Codificación [!UICONTROL de informes]programados y Carácter separador de [!UICONTROL CSV].

## Attribution IQ

* Un subconjunto de métricas no se admite en [!UICONTROL Atribución IQ]. Para obtener una lista completa, consulte las preguntas más frecuentes sobre IQ de [atribución](/help/analyze/analysis-workspace/attribution-iq/attribution-faq.md).
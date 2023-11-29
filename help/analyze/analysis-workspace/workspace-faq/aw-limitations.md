---
description: Lista de limitaciones conocidas en Adobe Analysis Workspace y componentes relacionados
title: Limitaciones conocidas en Analysis Workspace
feature: Workspace Basics
role: User, Admin
exl-id: 520e970b-1387-4f70-985b-bfe397f4a21b
source-git-commit: 2eff7656741bdba3d5d7d1f33e9261b59f8e6083
workflow-type: tm+mt
source-wordcount: '411'
ht-degree: 90%

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

## Componentes > Segmentos

* Ciertas métricas y dimensiones no se pueden segmentar, como [!UICONTROL Ocurrencias], [!UICONTROL Visitantes únicos], etc.
* Segmentos ad hoc creados en [zona desplegable del panel](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/panels.html?lang=es) son un tipo de filtro rápido. No aparecen en el carril izquierdo de Workspace ni en el administrador de componentes del segmento a menos que se hagan públicos. Para obtener más información, consulte [Segmentos rápidos](/help/analyze/analysis-workspace/components/segments/quick-segments.md).

## Componentes > Métricas calculadas

* Las métricas calculadas no se pueden usar en determinadas visualizaciones. Consulte “Visualizaciones”.
* Las métricas calculadas no se pueden usar en el panel de [!UICONTROL Attribution], ya que las métricas calculadas pueden incluir modelos de atribución independientes.
* Determinados componentes y operadores no están disponibles si se crea una métrica calculada desde Workspace (en lugar de hacerlo desde [!UICONTROL Componentes > Segmentos]). Por ejemplo, [!UICONTROL Dirección IP].

## Componentes > Intervalos de fechas

* Los intervalos de fechas personalizados no admiten [!UICONTROL Este día del año pasado], [!UICONTROL Este día del mes pasado], etc.

## Componentes > Grupos de informes virtuales

* Cuando se habilita el procesamiento del tiempo del informe, no se admiten determinados componentes. Para obtener una lista completa, consulte [Procesamiento de intervalo de tiempo](/help/components/vrs/vrs-report-time-processing.md).

## Componentes > Todos los componentes > Configuración de informes

* Algunas de las opciones de la página [!UICONTROL Configuración de informes] no se aplican. Analysis Workspace solo utiliza la configuración de [!UICONTROL Idioma, moneda y codificación] de la parte inferior: [!UICONTROL Separador de miles], [!UICONTROL Codificación de informes programados] y [!UICONTROL Carácter separador de CSV].

## Atribución

* Un subconjunto de métricas no se admite en [!UICONTROL Attribution]. Para obtener una lista completa, consulte las [preguntas más frecuentes sobre Attribution ](/help/analyze/analysis-workspace/attribution/faq.md).

---
title: Crear un informe básico en Analysis Workspace
description: Descubra cómo crear un informe básico en Analysis Workspace en un formato dirigido a usuarios familiarizados con herramientas de terceros como Google Analytics.
translation-type: tm+mt
source-git-commit: 3ce18f3f222286aed08c81dd2c958dab7e443df3

---


# Crear un informe básico en Analysis Workspace para los usuarios de Google Analytics

Analysis Workspace (una de las funciones principales de Adobe Analytics) proporciona un área sólida para que un usuario obtenga cualquier perspectiva sobre los datos recopilados. Los informes son muy diferentes entre Google Analytics y Adobe Analytics:

* La estructura de informes de Google Analytics permite seleccionar un tipo concreto de datos, como ubicación geográfica o tráfico de referencia. La plataforma utiliza una vista de informes prefabricada basada en la mejor manera esperada de ver esos datos.
* La estructura de informes de Analysis Workspace proporciona un lienzo en blanco, lo que proporciona más flexibilidad para satisfacer las necesidades exactas de informes.

Como Analysis Workspace funciona más como un lienzo que como informes prefabricados, recrear informes de Google Analytics es simplemente una cuestión de utilizar las visualizaciones y los componentes adecuados.

## Términos clave utilizados en Workspace

* **Los paneles** son los componentes principales del espacio de trabajo. En casi todos los casos, se utiliza un panel improvisado.
* **Las visualizaciones** conforman todos los paneles improvisados. Su propósito es representar los datos en diferentes formatos. La mayoría de las veces ese formato es una tabla, pero otras veces puede ser cosas como un gráfico circular o de líneas. Muchos informes de Google Analytics tienen el equivalente de dos visualizaciones: un gráfico de líneas y una tabla improvisada.
* **Los componentes** se colocan en una visualización para devolver datos. Los componentes se pueden mezclar de muchas maneras diferentes para satisfacer las necesidades de informes.
   * **Las dimensiones** son valores variables y generalmente contienen texto. Los ejemplos incluyen nombre de página, referente o país geográfico. Normalmente se enumeran como filas en una tabla.
   * **Las métricas** generalmente significan un evento o conversión de algún tipo. Los ejemplos incluyen eventos comunes, como una vista de página, o algo más significativo como una compra o un registro. Generalmente se ven como columnas en tablas para mostrar el número de veces que se produjo ese evento por dimensión.
   * **Los segmentos** son un subconjunto de sus datos y se comportan de manera similar a los segmentos en Google Analytics. Permiten crear filtros personalizados, lo que le permite centrarse en una parte específica de sus datos.
   * **Los intervalos** de fechas permiten organizar los datos según el momento en que se produjo un evento. Son la columna vertebral de las tendencias de visualización a lo largo del tiempo y suelen estar emparejadas con una métrica.

## Crear un informe básico en Workspace

Cree un informe de todas las páginas (similar al de Google Analytics) arrastrando los componentes adecuados a un lienzo de área de trabajo.

1. Inicie sesión en [ExperienceCloud.adobe.com](https://experiencecloud.adobe.com) con sus credenciales de Adobe ID.
2. Haga clic en el icono de 9 cuadrados en la esquina superior derecha y, a continuación, haga clic en el logotipo de Analytics.
3. En la barra de navegación superior, haga clic en Espacio de trabajo.
4. Haga clic en el botón 'Crear nuevo proyecto'.
5. En la ventana emergente modal, asegúrese de que está seleccionado 'Proyecto en blanco' y, a continuación, haga clic en Crear.
6. A la izquierda se muestra una lista de dimensiones, métricas, segmentos e intervalos de fechas. Busque la dimensión Páginas (de color naranja) y arrástrela al lienzo rotulado 'Colocar una dimensión aquí'.
7. Se puede ver un informe que muestra las páginas principales de este mes. Analysis Workspace rellena automáticamente el informe con la métrica [Ocurrencias](/help/components/c-variables/c-metrics/metrics-occurrences.md) .
8. Una tabla de Google Analytics suele contener entre 7 y 8 métricas. Busque la métrica Tasa de salida hacia otro sitio (de color verde) y arrástrela junto al encabezado de la métrica Ocurrencias. Si arrastra la métrica Tasa de salida hacia otro sitio junto a Ocurrencias, ambas métricas se muestran una junto a la otra.
9. Muchas métricas se pueden colocar en paralelo arrastrando las métricas junto a los encabezados de métricas existentes. Consulte las métricas [de uso](common-metrics.md) común para obtener información sobre cómo obtener las métricas que se utilizan normalmente en Google Analytics.

   ![Nueva métrica](/help/technotes/ga-to-aa//assets/new_metric.png)

## Comience con una plantilla de informe prediseñada en Workspace

Cree la plantilla Consumo de contenido (similar al informe Todas las páginas de Google Analytics) accediendo a una plantilla de proyecto.

1. Haga clic en el botón 'Crear nuevo proyecto'.
2. Busque y haga doble clic en el icono 'Consumo de contenido (Web)' que aparece en Todas las plantillas.
3. Examine cada una de las visualizaciones prediseñadas: Flujo de página de entrada, Tabla de páginas principales, Flujo de página de salida, Flujo de sección del sitio de entrada y Tabla de secciones del sitio principales.

   ![Selección de plantilla](/help/technotes/ga-to-aa/assets/content_consumption_template.png)

## Experimente con la herramienta

Como Analysis Workspace es una herramienta de generación de informes, no afecta a la recopilación de datos. No hay repercusiones en arrastrar indiscriminadamente componentes a un proyecto para ver qué funciona. Arrastre diferentes combinaciones de dimensiones y métricas al proyecto del área de trabajo para ver qué hay disponible.

Si arrastra accidentalmente un componente no válido al proyecto del área de trabajo o desea volver atrás un paso, pulse ctrl+Z (Windows) o cmd+Z (Mac) para deshacer la última acción realizada. También puede empezar con una pizarra limpia haciendo clic en *[!UICONTROL Proyecto]&gt;[!UICONTROL Nuevo]* en el menú superior izquierdo.

Adobe ha colocado muchas funciones en Analysis Workspace en el menú contextual que se muestra al hacer clic con el botón derecho. La mayoría de las visualizaciones y componentes se pueden pulsar con el botón derecho para obtener un análisis e interacción más detallados. Considere la posibilidad de hacer clic con el botón secundario en los componentes del espacio de trabajo para ver qué opciones están disponibles.

## Comprender qué dimensiones y métricas utilizar

Si se siente cómodo con Analysis Workspace y desea volver a crear un informe específico que se vea normalmente en Google Analytics, ubique el informe en su página respectiva:

* [Informes en tiempo real](realtime-reports.md)
* [Informes de audiencia](audience-reports.md)
* [Informes de adquisición](acquisition-reports.md)
* [Informes de comportamiento](behavior-reports.md)
* [Informes de conversión](conversions-reports.md)

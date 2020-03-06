---
title: Crear un informe básico en Analysis Workspace
description: Obtenga información sobre cómo crear un informe básico en Analysis Workspace en un formato dirigido a usuarios familiarizados con herramientas de terceros como Google Analytics.
translation-type: tm+mt
source-git-commit: 099662d021c1919f0760e79154536cfd0e23e959

---


# Crear un informe básico en Analysis Workspace para los usuarios de Google Analytics

Analysis Workspace (una de las funciones principales de Adobe Analytics) proporciona un área sólida para que un usuario obtenga cualquier perspectiva sobre los datos recopilados. Los informes son muy diferentes entre Google Analytics y Adobe Analytics:

* La estructura de informes de Google Analytics permite seleccionar un tipo concreto de datos, como ubicación geográfica o tráfico de referencia. La plataforma utiliza una vista de informes prefabricada basada en la mejor manera esperada de ver esos datos.
* La estructura de informes de Analysis Workspace proporciona un lienzo en blanco, lo que proporciona una mayor flexibilidad para satisfacer las necesidades exactas de informes.

Como Analysis Workspace funciona más como un lienzo que como informes prefabricados, recrear informes de Google Analytics es simplemente una cuestión de utilizar las visualizaciones y los componentes adecuados.

## Términos clave utilizados en Workspace

* **Los paneles** son los componentes principales del espacio de trabajo. En casi todos los casos, se utiliza un panel improvisado.
* **Las visualizaciones** conforman todos los paneles improvisados. Su propósito es representar los datos en diferentes formatos. La mayoría de las veces ese formato es una tabla, pero otras veces puede ser cosas como un anillo o un gráfico de líneas. Muchos informes de Google Analytics tienen el equivalente de dos visualizaciones: un gráfico de líneas y una tabla improvisada.
* **Los componentes** se colocan en una visualización para devolver datos. Los componentes se pueden mezclar de muchas maneras diferentes para satisfacer las necesidades de informes.
   * **Las dimensiones** son valores variables y generalmente contienen texto. Los ejemplos incluyen nombre de página, referente o país geográfico. Normalmente se enumeran como filas en una tabla.
   * **Las métricas** generalmente significan un evento o conversión de algún tipo. Los ejemplos incluyen eventos comunes, como una vista de página, o algo más significativo como una compra o un registro. Generalmente se ven como columnas en tablas para mostrar el número de veces que se produjo ese evento por dimensión.
   * **Los segmentos** son un subconjunto de sus datos y se comportan de manera similar a los segmentos en Google Analytics. Permiten crear filtros personalizados, lo que le permite centrarse en una parte específica de sus datos.
   * **Los intervalos** de fechas permiten organizar los datos según el momento en que se produjo un evento. Son la columna vertebral de las tendencias de visualización a lo largo del tiempo y suelen estar emparejadas con una métrica.

## Crear un informe básico en Workspace

Cree un informe de Todas las páginas (similar al de Google Analytics) arrastrando los componentes adecuados a un lienzo de área de trabajo.

1. Inicie sesión en [experiencecloud.adobe.com](https://experiencecloud.adobe.com) con sus credenciales de Adobe ID.
1. Haga clic en el icono de 9 cuadrados en la esquina superior derecha y, a continuación, haga clic en el logotipo de Analytics.
1. En la barra de navegación superior, haga clic en Workspace.
1. Haga clic en el botón Crear nuevo proyecto.
1. En la ventana emergente modal, compruebe que está seleccionado “Proyecto en blanco” y, a continuación, haga clic en Crear.
1. A la izquierda se muestra una lista de dimensiones, métricas, segmentos e intervalos de fechas. Busque la dimensión Páginas (de color naranja) y arrástrela al lienzo rotulado &#39;Colocar una dimensión aquí&#39;.
1. Se puede ver un informe que muestra las páginas más visitadas de este mes. Analysis Workspace automatically populates the report with the [Occurrences](/help/components/c-variables/c-metrics/metrics-occurrences.md) metric.
1. Una tabla de Google Analytics suele contener entre 7 y 8 métricas. Busque la métrica Tasa de salida hacia otro sitio (de color verde) y arrástrela junto al encabezado de la métrica Ocurrencias. Si arrastra la métrica Tasa de salida hacia otro sitio junto a Ocurrencias, ambas métricas se muestran una junto a la otra.
1. Muchas métricas se pueden colocar en paralelo arrastrando las métricas junto a los encabezados de métricas existentes. Consulte las métricas [de uso](common-metrics.md) común para obtener información sobre cómo obtener las métricas que se utilizan normalmente en Google Analytics.

   ![Nueva métrica](/help/technotes/ga-to-aa/assets/new_metric.png)

## Comience con una plantilla de informe prediseñada en Workspace

Cree la plantilla Consumo de contenido (similar al informe Todas las páginas de Google Analytics) accediendo a una plantilla de proyecto.

1. Haga clic en el botón Crear nuevo proyecto.
1. Busque y haga doble clic en el icono &#39;Consumo de contenido (Web)&#39; que aparece en Todas las plantillas.
1. Examine cada una de las visualizaciones prediseñadas: Flujo de página de entrada, Tabla de páginas principales, Flujo de página de salida, Flujo de sección del sitio de entrada y Tabla de secciones del sitio principales.

   ![Selección de plantilla](/help/technotes/ga-to-aa/assets/content_consumption_template.png)

## Experimente con la herramienta

Como Analysis Workspace es una herramienta de generación de informes, no afecta a la recopilación de datos. No hay repercusiones en arrastrar indiscriminadamente componentes a un proyecto para ver qué funciona. Arrastre diferentes combinaciones de dimensiones y métricas al proyecto del espacio de trabajo para ver qué hay disponible.

Si arrastra accidentalmente un componente no válido al proyecto del espacio de trabajo o desea volver atrás un paso, pulse ctrl+Z (Windows) o cmd+Z (Mac) para deshacer la última acción realizada. You can also start with a clean slate by clicking *[!UICONTROL Project]>[!UICONTROL New]*in the upper left menu.

Adobe ha colocado muchas funciones en Analysis Workspace en el menú contextual que se muestra al hacer clic con el botón derecho. La mayoría de las visualizaciones y componentes se pueden pulsar con el botón derecho para obtener un análisis e interacción más detallados. Considere la posibilidad de hacer clic con el botón secundario en los componentes del espacio de trabajo para ver qué opciones están disponibles.

## Comprender qué dimensiones y métricas utilizar

Si se siente cómodo con Analysis Workspace y desea volver a crear un informe específico que se vea normalmente en Google Analytics, ubique el informe en su página respectiva:

* [Informes en tiempo real](realtime-reports.md)
* [Informes de audiencia](audience-reports.md)
* [Informes de adquisición](acquisition-reports.md)
* [Informes de comportamiento](behavior-reports.md)
* [Informes de conversión](conversions-reports.md)

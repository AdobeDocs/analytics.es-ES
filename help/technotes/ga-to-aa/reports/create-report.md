---
title: Crear un informe básico en Analysis Workspace
description: Información sobre la creación de un informe básico en Analysis Workspace en un formato dirigido a usuarios familiarizados con herramientas de terceros, como Google Analytics.
feature: Third-party Integration
exl-id: 513da3f1-ad24-4d5b-bc35-dbcd3694cbdf
TQID: https://experienceleague.adobe.com/huQkwfObQW132aNeBiEMuPPeJ5H-6UaaVdJX77dHHUY
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
  - id: dcae653e-62c6-4cc8-84e6-ee110b848296
  - id: e38cbddc-1633-4cd5-bed5-9f289f2a6029
  - id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 869
ht-degree: 100%

---

# Crear un informe básico en Analysis Workspace para usuarios de Google Analytics

Analysis Workspace (una de las funciones principales de Adobe Analytics) proporciona un área sólida para que un usuario acceda a cualquier tipo de información sobre los datos recopilados. Los informes son muy diferentes entre Google Analytics y Adobe Analytics:

* La estructura de informes de Google Analytics permite seleccionar un tipo concreto de datos, como la ubicación geográfica o el tráfico de referencia. La plataforma emplea una vista de informes prefabricada, basada en una forma óptima para ver esos datos.
* La estructura de informes de Analysis Workspace proporciona un lienzo en blanco, lo que aporta una mayor flexibilidad para satisfacer las necesidades específicas relacionadas con los informes.

Como Analysis Workspace funciona más como un lienzo que los informes prefabricados, para recrear informes de Google Analytics simplemente hay que emplear las visualizaciones y los componentes adecuados.

## Términos clave utilizados en Workspace

* **Los paneles** son los componentes principales del espacio de trabajo. En casi todos los casos, se utiliza un panel de forma libre.
* **Las visualizaciones** aúnan todos los paneles de forma libre. Su propósito es representar los datos en diferentes formatos. En la mayor parte de los casos, dicho formato es una tabla, pero otras veces puede tener la forma de un gráfico de anillos o de líneas. Muchos informes de Google Analytics equivalen a dos visualizaciones: un gráfico de líneas y una tabla de forma libre.
* **Los componentes** se colocan en una visualización para devolver datos. Los componentes se pueden mezclar de muchas maneras diferentes para cubrir las necesidades del sistema de informes.
   * **Las dimensiones** son valores variables que suelen contener texto, como el nombre de la página, el referente o el país. Lo habitual es que aparezcan como filas de una tabla.
   * **Las métricas** normalmente dan cuenta de un evento o de un tipo de conversión. Por ejemplo: eventos comunes, como una vista de página, u otro más significativo, como una compra o un registro. Normalmente aparecen como columnas en tablas, mostrando la cantidad de veces que se produjo ese evento en cada dimensión.
   * **Los segmentos** son un subconjunto de los datos y se comportan de manera similar a los segmentos de Google Analytics. Permiten crear filtros personalizados, lo que permite concentrar la atención en una parte específica de los datos.
   * **Los intervalos de fecha** permiten organizar los datos según el momento en que se produjo un evento. Son la columna vertebral de las tendencias de visualización a lo largo del tiempo y suelen estar acompañadas de una métrica.

## Crear un informe básico en Workspace

Cree un informe de todas las páginas (similar al de Google Analytics) arrastrando los componentes adecuados a un lienzo del espacio de trabajo.

1. Inicie sesión en [experiencecloud.adobe.com](https://experiencecloud.adobe.com) con sus credenciales de Adobe ID.
1. Haga clic en el icono de 9 cuadrados en la esquina superior derecha y, a continuación, haga clic en el logotipo de Analytics.
1. En la barra de navegación superior, haga clic en Workspace.
1. Haga clic en el botón Crear nuevo proyecto.
1. En la ventana emergente modal, compruebe que está seleccionado “Proyecto en blanco” y, a continuación, haga clic en Crear.
1. A la izquierda se muestra una lista de dimensiones, métricas, segmentos e intervalos de fechas. Busque la dimensión Páginas (de color naranja) y arrástrela al lienzo denominado “Coloque una dimensión aquí”.
1. Se puede ver un informe que muestra las páginas más visitadas del mes actual. Analysis Workspace rellena automáticamente el informe con la métrica [Ocurrencias](/help/components/metrics/occurrences.md).
1. Una tabla de Google Analytics suele contener entre siete y ocho métricas. Busque la métrica Tasa de salida hacia otro sitio (de color verde) y arrástrela junto al encabezado de la métrica Ocurrencias. Si arrastra la métrica Tasa de salida hacia otro sitio junto a Ocurrencias, ambas métricas se muestran una al lado de la otra.
1. Muchas métricas se pueden colocar en paralelo, arrastrándolas junto a los encabezados de las métricas incluidas previamente. Consulte [las métricas de uso común](common-metrics.md) para obtener información sobre el acceso a las métricas empleadas normalmente en Google Analytics.

   ![Nueva métrica](/help/technotes/ga-to-aa/assets/new_metric.png)

## Comience con una plantilla de informe prediseñada en Workspace

Cree la plantilla Consumo de contenido (similar al informe Todas las páginas de Google Analytics) accediendo a una plantilla de proyecto.

1. Haga clic en el botón Crear nuevo proyecto.
1. Busque y haga doble clic en el icono “Consumo de contenido (Web)” que aparece en Todas las plantillas.
1. Explore todas las visualizaciones prediseñadas: Flujo de página de entrada, Tabla de páginas principales, Flujo de página de salida, Flujo de sección del entrada al sitio y Tabla de principales secciones del sitio.

   ![Selección de plantilla](/help/technotes/ga-to-aa/assets/content_consumption_template.png)

## Experimente con la herramienta

Como Analysis Workspace es una herramienta de generación de informes, no afecta a la recopilación de datos. No hay repercusiones en arrastrar indiscriminadamente componentes a un proyecto para ver qué funciona. Arrastre diferentes combinaciones de dimensiones y métricas al proyecto de Workspace para ver qué hay disponible.

Si arrastra accidentalmente un componente no válido al proyecto de Workspace o desea volver atrás un paso, pulse ctrl+Z (Windows) o cmd+Z (Mac) para deshacer la última acción realizada. También puede empezar con una pizarra limpia haciendo clic en *[!UICONTROL Proyecto] > [!UICONTROL Nuevo]* en el menú superior izquierdo.

Adobe incluye muchas funciones en Analysis Workspace, en el menú contextual que se muestra al hacer clic con el botón derecho. Para obtener un análisis y una interacción más detallados con la mayoría de las visualizaciones, haga clic sobre ellas con el botón derecho. Haciendo clic con el botón derecho sobre los componentes del espacio de trabajo, se pueden consultar las opciones disponibles.

## Dimensiones y métricas que se pueden usar

Si se maneja bien con Analysis Workspace y desea volver a crear un informe específico que normalmente se ve en Google Analytics, ubique el informe en su página correspondiente:

* [Informes en tiempo real](realtime-reports.md)
* [Informes de público](audience-reports.md)
* [Informes de adquisición](acquisition-reports.md)
* [Informes de comportamiento](behavior-reports.md)
* [Informes de conversión](conversions-reports.md)

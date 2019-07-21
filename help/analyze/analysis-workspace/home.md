---
description: Cómo empezar a utilizar Adobe Analytics.
keywords: Analysis Workspace
seo-description: Cómo empezar a utilizar Adobe Analytics.
seo-title: Guía de introducción
solution: Analytics
title: Guía de introducción
topic: Reports and Analytics
uuid: 851 feadb -5 e 30-45 ab -9 f 66-02 bdf 844 fa 54
translation-type: tm+mt
source-git-commit: a0158b98089c044091f61796d782604865aa4eba

---


# Analysis Workspace

Analysis Workspace es una de las herramientas señalizadas de Adobe para tomar decisiones procesables basadas en datos para su organización. La visualización más común, la tabla improvisada, permite crear fácilmente informes personalizados usando dimensiones, métricas, segmentos e intervalos de fechas.

## Requisitos previos

[Enviar datos a Adobe Analytics mediante Adobe Experience Platform Launch](../../implement/implement-with-launch/validate-publish-prod.md): El uso de Analysis Workspace requiere una implementación operativa. Asegúrese de que su organización envía datos a Adobe antes de utilizar la herramienta. Otras implementaciones, como la DTM o las implementaciones manuales heredadas, también pueden funcionar.

## Obtener un informe de clasificación básico en Workspace

Obtener un informe de clasificación básico mediante Analysis Workspace. Un informe clasificado muestra una vista total agregada de cada valor de dimensión, mostrando primero los valores más altos. Estos tipos de informes son útiles para ver qué componentes del sitio son los más efectivos, como por ejemplo cuáles son las páginas que obtienen la mayor cantidad de tráfico o cuáles son los productos más vendidos.

1. Log in to [experiencecloud.adobe.com](https://experiencecloud.adobe.com) using your Adobe ID credentials.
2. Haga clic en el icono 9 cuadrado en la esquina superior derecha y, a continuación, haga clic en el logotipo de color de color.
3. En la barra de navegación superior, haga clic en Espacio de trabajo.
4. Haga clic en el botón'Crear nuevo proyecto '.
5. En la ventana emergente modal, asegúrese de que está seleccionada la opción «Proyecto en blanco» y, a continuación, haga clic en Crear.
6. A la izquierda, debería ver una lista de dimensiones, métricas, segmentos e intervalos de fechas. Busque la dimensión Páginas (naranja color) y arrástrela hasta el lienzo donde dice'Soltar una dimensión aquí '.
7. Tenga en cuenta que si el grupo de informes tiene datos, se puede ver un informe que muestre las páginas principales de este mes. Analysis Workspace automatically populated the report with the [Occurrences](../../components/c-variables/c-metrics/metrics-occurrences.md) metric.
8. Locate the Visits metric (colored green), and drag it either **over** or **next to** the Occurrences metric header (avoid placing it above the metric). Si arrastra la métrica Visitas sobre Ocurrencias, la métrica se reemplaza en los informes. Si arrastra la métrica Visitas al lado de Ocurrencias, ambas métricas se muestran en paralelo.
9. If you'd like to save your project, click *[!UICONTROL Project]&gt;[!UICONTROL Save]* in the upper left menu.

## Obtener un informe de tendencias básico en Workspace

Obtener un informe de tendencias básico mediante Analysis Workspace. Un informe de tendencias muestra una vista de horas extras de las métricas utilizando el intervalo de fechas seleccionado. Estos tipos de informes son útiles para identificar tendencias a lo largo del tiempo y se pueden utilizar para medir el éxito o el fracaso de las decisiones comerciales realizadas. Por ejemplo: puede ver un informe de vistas de páginas con tendencia a lo largo del tiempo para ver si un rediseño del sitio contribuyó a aumentar o disminuir el tráfico.

1. Log in to [experiencecloud.adobe.com](https://experiencecloud.adobe.com) using your Adobe ID credentials.
2. Haga clic en el icono 9 cuadrado en la esquina superior derecha y, a continuación, haga clic en el logotipo de color de color.
3. En la barra de navegación superior, haga clic en Espacio de trabajo.
4. Haga clic en el botón'Crear nuevo proyecto '.
5. En la ventana emergente modal, asegúrese de que está seleccionada la opción «Proyecto en blanco» y, a continuación, haga clic en Crear.
6. A la izquierda, debería ver una lista de dimensiones, métricas, segmentos e intervalos de fechas. Busque la dimensión Vistas de página y arrástrela hasta el espacio pequeño del lienzo rotulado'Soltar una métrica aquí '. Evite soltar en el espacio reservado para dimensiones (al menos para este ejercicio).
7. Tenga en cuenta que si el grupo de informes tiene datos, debe ver un informe de vistas de página básico con tendencia a lo largo del mes actual. Analysis Workspace incluye automáticamente el intervalo de fechas'Día ', para que pueda ver la tendencia de las vistas de página del mes actual.
8. Localice el intervalo de fechas de la semana (color púrpura) en la lista de componentes de intervalo de fechas a la izquierda. Haga clic en el título del intervalo de fechas para expandir y ver todos los componentes de intervalo de fechas, o utilice la barra de búsqueda.
9. Arrastre el intervalo de fechas Semana sobre el encabezado del intervalo de fechas Día en el lienzo para reemplazarlo.
10. Tenga en cuenta que el informe de tendencias ahora se agrega por semana en lugar de por día.
11. If you'd like to save your project, click *[!UICONTROL Project]&gt;[!UICONTROL Save]* in the upper left menu.

## Experimente con la herramienta

Como Analysis Workspace es una herramienta de creación de informes, no afecta a la recopilación de datos. No existen consecuencias para arrastrar componentes de forma indiscriminada a un proyecto para ver qué funciona. Arrastre diferentes combinaciones de dimensiones y métricas al proyecto de su espacio de trabajo para ver lo que está disponible para usted.

Si accidentalmente arrastra un componente no válido a su proyecto de espacio de trabajo o desea retroceder, pulse Ctrl + Z (Windows) o cmd + Z (Mac) para deshacer la última acción realizada. You can also start with a clean slate by clicking *[!UICONTROL Project]&gt;[!UICONTROL New]* in the upper left menu.

## Resolución de problemas

**Cuando arrastro una métrica, indica'Datos no válidos '.**

Los datos no válidos implican que Adobe no puede devolver datos utilizando la combinación de dimensiones y métricas utilizadas en el informe. Por ejemplo, no se pueden devolver como datos dos métricas apiladas una encima de la otra, ya que no hay manera de mostrar dos métricas de ese modo. En su lugar, coloque las métricas en paralelo.

**Cuando arrastro una métrica, no veo datos reales, solo ceros.**

Si crea correctamente un informe de espacio de trabajo pero no hay datos, puede comprobar algunos:

* Verifique el grupo de informes y asegúrese de que se llena con datos.
* Si utiliza un segmento en el informe, es posible que los criterios de segmento no coincidan con ningún dato. Intente eliminar el segmento o ajustar la definición del segmento.
* Compruebe el intervalo de fechas en la esquina superior derecha y asegúrese de que está establecido en un valor que esperaba.
* Navegue hasta su sitio web y utilice el depurador para validar que se estén recopilando los datos.

## Recursos adicionales

* [Notas de la versión de Analysis Workspace](../../analyze/analysis-workspace/new-features-in-analysis-workspace.md): Lea las funciones más recientes introducidas en la herramienta.
* [Analysis Workspace en YouTube](https://www.youtube.com/playlist?list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS): Aprenda a utilizar la mayoría de las funciones de Analysis Workspace a través de esta amplia lista de reproducción.
* Sugerencias del producto: Las sugerencias del día, junto con vídeos cortos, aparecen veces en la esquina inferior derecha de Analysis Workspace. If these tips are dismissed, they can be reached through *[!UICONTROL Help]&gt;[!UICONTROL Tips]* at any time.
* [Comunidad de Analysis Workspace](https://forums.adobe.com/community/experience-cloud/analytics-cloud/analytics/analysis-workspace): Analice Analysis Workspace con otros usuarios y vote las funciones que desee ver en la herramienta.
* Anuncios de blog:
   * [Fortalecer las empresas con un análisis más inteligente](https://blogs.adobe.com/digitalmarketing/analytics/adobe-analytics-fall-2016-release-empowering-organizations-smarter-analysis/)
   * [Las nuevas funciones en Adobe Analytics logran que la información valiosa sea más accesible](https://blogs.adobe.com/digitalmarketing/analytics/new-adobe-analytics-capabilities-make-powerful-insights-accessible/)
   * [5 consejos para optimizar su productividad con Analysis Workspace](https://blogs.adobe.com/digitalmarketing/analytics/5-tips-maximize-productivity-analysis-workspace/)
   * [Perspectivas más rápidas con Analysis Workspace](https://blogs.adobe.com/digitalmarketing/analytics/faster-insights-with-the-analysis-workspace/)
   * [Por qué debería utilizar Analysis Workspace](https://blogs.adobe.com/digitalmarketing/analytics/why-you-should-be-using-analysis-workspace-in-adobe-analytics/)

## Pasos siguientes

Hay muchas instrucciones para ir a fin de profundizar su comprensión de Analysis Workspace. Estos son algunos conceptos básicos que Adobe recomienda:

### Para usuarios finales que buscan ampliar los conocimientos sobre cómo utilizar Analysis Workspace

* [Detalles sobre la IU de Workspace](../../analyze/analysis-workspace/build-workspace-project/t-freeform-project.md): Ahora que ha creado un informe básico, familiarícese con el resto de la interfaz.
* [Visualizaciones en Workspace](visualizations/freeform-analysis-visualizations.md): Las tablas improvisadas son solo un tipo de visualización en Analysis Workspace. Aprenda a utilizar otras visualizaciones, como gráficos de líneas, gráficos de barras y mapas geográficos.
* [Dimensiones en Espacio de trabajo](../../analyze/analysis-workspace/components/dimensions/t-breakdown-fa.md): Obtenga más información sobre las dimensiones y cómo utilizarlas en más de un solo informe de clasificación.
* [Métricas en Espacio de trabajo](../../analyze/analysis-workspace/components/apply-create-metrics.md): Obtenga más información sobre las métricas y cómo utilizarlas en otras partes de las tablas improvisadas.
* [Introducción a la segmentación](../../analyze/analysis-workspace/components/t-freeform-project-segment.md): Obtenga información sobre qué segmentos son y extrae un informe básico usando un segmento.
* [Intervalos de fechas en Workspace](../../analyze/analysis-workspace/components/calendar-date-ranges/calendar.md): Obtenga información sobre fechas relativas y móviles, y utilícelas en proyectos de espacio de trabajo.
* Uso compartido de proyectos en Workspace: Muestre a su colega el formidable proyecto de espacio de trabajo creado.
* [(Avanzado) Paneles en Workspace](c-panels/panels.md): Utilice funciones avanzadas en Workspace, como Atribución y Comparación de segmentos.

### Para los analistas y administradores que buscan mejorar la calidad del espacio de trabajo en su organización

* [Permisos de Analysis Workspace](https://marketing.adobe.com/resources/help/en_US/mcloud/admin_getting_started.html): Asigne permisos de usuario a Workspace a través de Adobe Admin Console.
* [Cree un documento de diseño de solución](../../implement/prepare/solution-design.md): Comience la planificación de la forma en que su organización recopila dimensiones o métricas adicionales específicas del sitio.
* [Plantillas en Espacio de trabajo](../../analyze/analysis-workspace/build-workspace-project/starter-projects.md): Cree plantillas para que sus colegas puedan comenzar con un espacio de proyecto adaptado a sus necesidades.
* [Depuración del espacio de trabajo](curate-share/curate.md): Cree un proyecto que limite los componentes disponibles, haciendo que el espacio de trabajo sea más accesible para aquellos que estén menos familiarizados con la herramienta
---
description: Cómo empezar a usar Adobe Analytics.
keywords: Analysis Workspace
solution: Analytics
title: Guía de introducción
topic: Reports and analytics
uuid: 851feadb-5e30-45ab-9f66-02bdf844fa54
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Analysis Workspace

Analysis Workspace es una de las principales herramientas de Adobe para tomar decisiones procesables basadas en datos para su organización. La visualización más común, la tabla improvisada, permite crear fácilmente informes personalizados con dimensiones, métricas, segmentos e intervalos de fechas.

## Requisitos previos

[Envío de datos a Adobe Analytics mediante Adobe Experience Platform Launch](/help/implement/implement-with-launch/validate-publish-prod.md): El uso de Analysis Workspace requiere una implementación que funcione. Asegúrese de que su organización está enviando datos a Adobe antes de utilizar la herramienta. Otras implementaciones, como la DTM o las implementaciones manuales heredadas, también pueden funcionar.

## Extraer un informe de clasificación básico en Workspace

Extraiga un informe clasificado básico con Analysis Workspace. Un informe de clasificación muestra una vista total agregada de cada valor de dimensión, mostrando primero los valores más altos. Estos tipos de informes son útiles para ver qué componentes del sitio son los más efectivos, como por ejemplo qué páginas obtienen la mayor cantidad de tráfico o qué productos se venden más.

1. Inicie sesión en [ExperienceCloud.adobe.com](https://experiencecloud.adobe.com) con sus credenciales de Adobe ID.
2. Haga clic en el icono de 9 cuadrados en la esquina superior derecha y, a continuación, haga clic en el logotipo de Analytics.
3. En la barra de navegación superior, haga clic en Espacio de trabajo.
4. Haga clic en el botón 'Crear nuevo proyecto'.
5. En la ventana emergente modal, asegúrese de que está seleccionado 'Proyecto en blanco' y, a continuación, haga clic en Crear.
6. A la izquierda, debería ver una lista de dimensiones, métricas, segmentos e intervalos de fechas. Busque la dimensión Páginas (de color naranja) y arrástrela al lienzo donde dice 'Colocar una dimensión aquí'.
7. Tenga en cuenta que si el grupo de informes tiene datos, se puede ver un informe que muestre las páginas principales de este mes. Analysis Workspace llenó automáticamente el informe con la métrica [Ocurrencias](/help/components/c-variables/c-metrics/metrics-occurrences.md) .
8. Busque la métrica Visitas (de color verde) y arrástrela **sobre** o **junto** al encabezado de la métrica Ocurrencias (evite colocarla encima de la métrica). Si arrastra la métrica Visitas sobre Ocurrencias, la métrica se reemplaza en los informes. Si arrastra la métrica Visitas junto a Ocurrencias, ambas métricas se muestran una al lado de la otra.
9. Si desea guardar el proyecto, haga clic en *[!UICONTROL Proyecto]&gt;[!UICONTROL Guardar]* en el menú superior izquierdo.

## Extraer un informe de tendencias básico en Workspace

Extraiga un informe de tendencias básico con Analysis Workspace. Un informe de tendencias muestra una vista de horas extras de las métricas que utilizan el intervalo de fechas seleccionado. Estos tipos de informes son útiles para identificar las tendencias a lo largo del tiempo y pueden utilizarse para medir el éxito o el fracaso de las decisiones comerciales tomadas. Por ejemplo: puede mirar un informe de vistas de páginas con tendencias a lo largo del tiempo para ver si el rediseño del sitio ayudó a aumentar o disminuir el tráfico.

1. Inicie sesión en [ExperienceCloud.adobe.com](https://experiencecloud.adobe.com) con sus credenciales de Adobe ID.
2. Haga clic en el icono de 9 cuadrados en la esquina superior derecha y, a continuación, haga clic en el logotipo de Analytics.
3. En la barra de navegación superior, haga clic en Espacio de trabajo.
4. Haga clic en el botón 'Crear nuevo proyecto'.
5. En la ventana emergente modal, asegúrese de que está seleccionado 'Proyecto en blanco' y, a continuación, haga clic en Crear.
6. A la izquierda, debería ver una lista de dimensiones, métricas, segmentos e intervalos de fechas. Busque la dimensión Vistas de página y arrástrela al pequeño espacio del lienzo rotulado 'Colocar una métrica aquí'. Evite soltarlo en el espacio reservado para dimensiones (al menos para este ejercicio).
7. Tenga en cuenta que si el grupo de informes tiene datos, debería ver un informe de vistas de página básico con tendencias a lo largo del mes actual. Analysis Workspace introdujo automáticamente el intervalo de fechas 'Día' para que pueda ver la tendencia de las vistas de página del mes actual.
8. Busque el intervalo de fechas de la semana (de color púrpura) en la lista de componentes de intervalo de fechas de la izquierda. Haga clic en el título del intervalo de fechas para expandir y ver todos los componentes del intervalo de fechas o utilice la barra de búsqueda.
9. Arrastre el intervalo de fechas de la semana sobre el encabezado del intervalo de fechas del día en el lienzo para reemplazarlo.
10. Tenga en cuenta que el informe de tendencias ahora se agrega por semana en lugar de por día.
11. Si desea guardar el proyecto, haga clic en *[!UICONTROL Proyecto]&gt;[!UICONTROL Guardar]* en el menú superior izquierdo.

## Experimente con la herramienta

Dado que Analysis Workspace es una herramienta de generación de informes, no afecta a la recopilación de datos. No hay repercusiones en arrastrar indiscriminadamente componentes a un proyecto para ver qué funciona. Arrastre diferentes combinaciones de dimensiones y métricas al proyecto del área de trabajo para ver qué hay disponible.

Si arrastra accidentalmente un componente no válido al proyecto del área de trabajo o desea volver atrás un paso, pulse ctrl+Z (Windows) o cmd+Z (Mac) para deshacer la última acción realizada. También puede empezar con una pizarra limpia haciendo clic en *[!UICONTROL Proyecto]&gt;[!UICONTROL Nuevo]* en el menú superior izquierdo.

## Resolución de problemas

**Cuando arrastro una métrica, significa 'Datos no válidos'.**

Datos no válidos significa que Adobe no puede devolver datos mediante la combinación de dimensiones y métricas utilizadas en el informe. Por ejemplo: dos métricas apiladas una encima de la otra no se pueden devolver como datos, ya que no hay forma de mostrar dos métricas de esa manera. En su lugar, coloque las métricas en paralelo.

**Cuando arrastro una métrica, no veo ningún dato real, solo ceros.**

Si crea correctamente un informe de área de trabajo pero no hay datos, puede comprobar algunas cosas:

* Verifique dos veces el grupo de informes y asegúrese de que se rellena con datos.
* Si utiliza un segmento en el informe, es posible que los criterios del segmento no coincidan con ningún dato. Intente eliminar el segmento o ajustar la definición del mismo.
* Compruebe el intervalo de fechas en la esquina superior derecha y asegúrese de que está establecido en un valor que esperaría.
* Vaya al sitio web y utilice el depurador para validar que se estén recopilando datos.

## Recursos adicionales

* [Notas](/help/analyze/analysis-workspace/new-features-in-analysis-workspace.md)de la versión de Analysis Workspace: Lea las últimas funciones introducidas en la herramienta.
* [Espacio de trabajo de análisis en YouTube](https://www.youtube.com/playlist?list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS): Aprenda a utilizar la mayoría de las funciones de Analysis Workspace a través de esta extensa lista de reproducción.
* Sugerencias del producto: Las sugerencias del día, junto con vídeos cortos, aparecen ocasionalmente en la esquina inferior derecha de Analysis Workspace. Si estas sugerencias se descartan, se puede acceder a ellas a través de *[!UICONTROL Ayuda]&gt;[!UICONTROL Sugerencias]* en cualquier momento.
* [Comunidad](https://forums.adobe.com/community/experience-cloud/analytics-cloud/analytics/analysis-workspace)de Analysis Workspace: Analice Analysis Workspace con otros usuarios y vote sobre las funciones que desee ver en la herramienta.
* Publicaciones del blog:
   * [Fortalecer las empresas con un análisis más inteligente](https://blogs.adobe.com/digitalmarketing/analytics/adobe-analytics-fall-2016-release-empowering-organizations-smarter-analysis/)
   * [Las nuevas funciones en Adobe Analytics logran que la información valiosa sea más accesible](https://blogs.adobe.com/digitalmarketing/analytics/new-adobe-analytics-capabilities-make-powerful-insights-accessible/)
   * [5 consejos para optimizar su productividad con Analysis Workspace](https://blogs.adobe.com/digitalmarketing/analytics/5-tips-maximize-productivity-analysis-workspace/)
   * [Perspectivas más rápidas con Analysis Workspace](https://blogs.adobe.com/digitalmarketing/analytics/faster-insights-with-the-analysis-workspace/)
   * [Por qué debería utilizar Analysis Workspace](https://blogs.adobe.com/digitalmarketing/analytics/why-you-should-be-using-analysis-workspace-in-adobe-analytics/)

## Pasos siguientes

Hay muchas direcciones que seguir para comprender mejor Analysis Workspace. A continuación se indican algunos aspectos básicos que Adobe recomienda:

### Para usuarios finales que buscan ampliar sus conocimientos sobre cómo utilizar Analysis Workspace

* [Detalles de la IU](/help/analyze/analysis-workspace/build-workspace-project/t-freeform-project.md)de Workspace: Ahora que ha creado un informe básico, familiarícese con el resto de la interfaz.
* [Visualizaciones en Workspace](visualizations/freeform-analysis-visualizations.md): Las tablas improvisadas son simplemente un tipo de visualización en Analysis Workspace. Aprenda a utilizar otras visualizaciones, como gráficos de líneas, gráficos de barras y mapas geográficos.
* [Dimensiones en Workspace](/help/analyze/analysis-workspace/components/dimensions/t-breakdown-fa.md): Obtenga más información sobre las dimensiones y cómo utilizarlas en algo más que en los informes clasificados.
* [Métricas en Workspace](/help/analyze/analysis-workspace/components/apply-create-metrics.md): Obtenga más información sobre las métricas y cómo utilizarlas en otras partes de las tablas improvisadas.
* [Introducción a la segmentación](/help/analyze/analysis-workspace/components/t-freeform-project-segment.md): Obtenga información sobre los segmentos y extraiga un informe básico mediante un segmento.
* [Intervalos de fechas en Workspace](/help/analyze/analysis-workspace/components/calendar-date-ranges/calendar.md): Obtenga información sobre las fechas relativas y móviles y utilícelas en proyectos de espacio de trabajo.
* Uso compartido de proyectos en Workspace: Muestre a su colega el impresionante proyecto de Workspace que ha creado.
* [Paneles (avanzados) en Workspace](c-panels/panels.md): Utilice funciones avanzadas en Workspace, como Atribución y Comparación de segmentos.

### Para analistas y administradores que buscan mejorar la calidad del espacio de trabajo en su organización

* [Permisos](https://marketing.adobe.com/resources/help/en_US/mcloud/admin_getting_started.html)de Analysis Workspace: Asigne permisos de usuario a Workspace a través de Adobe Admin Console.
* [Crear un documento](/help/implement/prepare/solution-design.md)de diseño de solución: Comience a planificar cómo su organización recopila dimensiones o métricas adicionales específicas del sitio.
* [Plantillas en Workspace](/help/analyze/analysis-workspace/build-workspace-project/starter-projects.md): Cree plantillas para que sus colegas puedan empezar con un espacio de proyecto adaptado a sus necesidades.
* [Revisión](curate-share/curate.md)del espacio de trabajo: Cree un proyecto que limite los componentes disponibles, haciendo que el espacio de trabajo sea más accesible para los menos familiarizados con la herramienta

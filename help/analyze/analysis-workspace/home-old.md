---
description: Introducción a Adobe Analytics.
keywords: Analysis Workspace
title: Guía de introducción
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '1337'
ht-degree: 98%

---


# Analysis Workspace

Analysis Workspace es una de las principales herramientas de Adobe para tomar decisiones procesables basadas en datos para su organización. La visualización más común, la tabla improvisada, permite crear fácilmente informes personalizados con dimensiones, métricas, segmentos e intervalos de fechas.

## Requisitos previos

[Envío de datos a Adobe Analytics mediante Adobe Experience Platform Launch](/help/implement/launch/validate-publish-prod.md): El uso de Analysis Workspace requiere una implementación activa. Compruebe que su organización está enviando datos a Adobe antes de utilizar la herramienta. Otras implementaciones, como DTM o las implementaciones manuales heredadas, también pueden funcionar.

## Extraer un informe de clasificación básico en Workspace

Extraer un informe de clasificación básico con Analysis Workspace. Un informe de clasificación muestra una vista total agregada de cada elemento de dimensión, mostrando primero los valores más altos. Estos tipos de informes son útiles para ver qué componentes del sitio son los más efectivos, como por ejemplo qué páginas obtienen la mayor cantidad de tráfico o qué productos se venden más.

1. Inicie sesión en [experiencecloud.adobe.com](https://experiencecloud.adobe.com) con sus credenciales de Adobe ID.
2. Haga clic en el icono de 9 cuadrados en la esquina superior derecha y, a continuación, haga clic en el logotipo de Analytics.
3. En la barra de navegación superior, haga clic en Workspace.
4. Haga clic en el botón Crear nuevo proyecto.
5. En la ventana emergente modal, compruebe que está seleccionado “Proyecto en blanco” y, a continuación, haga clic en Crear.
6. A la izquierda, debería ver una lista de dimensiones, métricas, segmentos e intervalos de fechas. Busque la dimensión Páginas (de color naranja) y arrástrela al lienzo hasta la zona con el texto “Coloque una dimensión aquí”.
7. Tenga en cuenta que si el grupo de informes tiene datos, se puede ver un informe que muestre las páginas principales de este mes. Analysis Workspace llenó automáticamente el informe con la métrica [Ocurrencias](/help/components/metrics/occurrences.md).
8. Busque la métrica Visitas (de color verde) y arrástrela **sobre** o **junto** al encabezado de la métrica Ocurrencias (evite colocarla encima de la métrica). Si arrastra la métrica Visitas sobre Ocurrencias, la métrica se reemplaza en los informes. Si arrastra la métrica Visitas junto a Ocurrencias, ambas métricas se mostrarán una al lado de la otra.
9. Si desea guardar el proyecto, haga clic en *[!UICONTROL Proyecto] > [!UICONTROL Guardar]* en el menú superior izquierdo.

## Extraer un informe de tendencias básico en Workspace

Extraer un informe de tendencias básico con Analysis Workspace. Un informe de tendencias muestra una vista de horas extras de las métricas que utilizan el intervalo de fechas seleccionado. Estos tipos de informes son útiles para identificar las tendencias a lo largo del tiempo y pueden utilizarse para medir el éxito o el fracaso de las decisiones comerciales tomadas. Por ejemplo: puede consultar un informe de vistas de páginas con tendencias a lo largo del tiempo para ver si el rediseño del sitio ayudó a aumentar o disminuir el tráfico.

1. Inicie sesión en [experiencecloud.adobe.com](https://experiencecloud.adobe.com) con sus credenciales de Adobe ID.
2. Haga clic en el icono de 9 cuadrados en la esquina superior derecha y, a continuación, haga clic en el logotipo de Analytics.
3. En la barra de navegación superior, haga clic en Workspace.
4. Haga clic en el botón Crear nuevo proyecto.
5. En la ventana emergente modal, compruebe que está seleccionado “Proyecto en blanco” y, a continuación, haga clic en Crear.
6. A la izquierda, debería ver una lista de dimensiones, métricas, segmentos e intervalos de fechas. Busque la dimensión Vistas de página y arrástrela al pequeño espacio con el texto “Coloque una métrica aquí”. Evite soltarlo en el espacio reservado para dimensiones (al menos para este ejercicio).
7. Tenga en cuenta que si el grupo de informes tiene datos, debería ver un informe de vistas de página básico con tendencias del mes actual. Analysis Workspace introdujo automáticamente el intervalo de fechas “Día” para que pueda ver la tendencia de las vistas de página del mes actual.
8. Busque el intervalo de fechas de la semana (de color púrpura) en la lista de componentes de intervalo de fechas de la izquierda. Haga clic en el título del intervalo de fechas para expandir y ver todos los componentes del intervalo de fechas o utilice la barra de búsqueda.
9. Arrastre el intervalo de fechas de la semana sobre el encabezado del intervalo de fechas del día en el lienzo para reemplazarlo.
10. Tenga en cuenta que el informe de tendencias ahora se agrega por semana en lugar de por día.
11. Si desea guardar el proyecto, haga clic en *[!UICONTROL Proyecto] > [!UICONTROL Guardar]* en el menú superior izquierdo.

## Experimente con la herramienta

Como Analysis Workspace es una herramienta de generación de informes, no afecta a la recopilación de datos. No hay repercusiones en arrastrar indiscriminadamente componentes a un proyecto para ver qué funciona. Arrastre diferentes combinaciones de dimensiones y métricas al proyecto del espacio de trabajo para ver qué hay disponible.

Si arrastra accidentalmente un componente no válido al proyecto del espacio de trabajo o desea volver atrás un paso, pulse ctrl+Z (Windows) o cmd+Z (Mac) para deshacer la última acción realizada. También puede empezar de nuevo haciendo clic en *[!UICONTROL Proyecto] > [!UICONTROL Nuevo]* en el menú superior izquierdo.

## Resolución de problemas

**Cuando arrastro una métrica, significa “Datos no válidos”.**

Datos no válidos significa que Adobe no puede devolver datos mediante la combinación de dimensiones y métricas utilizadas en el informe. Por ejemplo: dos métricas apiladas una encima de la otra no se pueden devolver como datos, ya que no hay forma de mostrar dos métricas de esa manera. En su lugar, coloque las métricas en paralelo.

**Cuando arrastro una métrica, no veo ningún dato real, solo ceros.**

Si crea correctamente un informe de espacio de trabajo pero no hay datos, puede comprobar algunas cosas:

* Compruebe el grupo de informes y asegúrese de que se rellena con datos.
* Si utiliza un segmento en el informe, es posible que los criterios del segmento no coincidan con ningún dato. Intente eliminar el segmento o ajustar la definición del mismo.
* Compruebe el intervalo de fechas en la esquina superior derecha y compruebe que está establecido en un valor que esperaba.
* Vaya al sitio web y utilice Debugger para validar que se están recopilando datos.

## Recursos adicionales

* [Notas de la versión de Analysis Workspace](/help/analyze/analysis-workspace/new-features-in-analysis-workspace.md): Descubra las últimas funciones introducidas en la herramienta.
* [Analysis Workspace en YouTube](https://www.youtube.com/playlist?list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS): Aprenda a utilizar la mayoría de las funciones de Analysis Workspace mediante esta extensa lista de reproducción.
* Sugerencias del producto: Las sugerencias del día, junto con vídeos cortos, aparecen ocasionalmente en la esquina inferior derecha de Analysis Workspace. Si omite estas sugerencias, siempre se puede acceder a ellas a través de *[!UICONTROL Ayuda] > [!UICONTROL Sugerencias]*.
* [Comunidad de Analysis Workspace](https://forums.adobe.com/community/experience-cloud/analytics-cloud/analytics/analysis-workspace): Analice Analysis Workspace con otros usuarios y vote las funcionalidades que desee ver en la herramienta.
* Publicaciones del blog:
   * [Empowering Organizations with Smarter Analysis](https://blogs.adobe.com/digitalmarketing/analytics/adobe-analytics-fall-2016-release-empowering-organizations-smarter-analysis/) (Fortalecer las empresas con un análisis más inteligente)
   * [New Adobe Analytics Capabilities Make Powerful Insights More Accessible](https://blogs.adobe.com/digitalmarketing/analytics/new-adobe-analytics-capabilities-make-powerful-insights-accessible/) (Las nuevas funciones en Adobe Analytics logran que la información valiosa sea más accesible)
   * [5 Tips to Maximize Your Productivity with Analysis Workspace](https://blogs.adobe.com/digitalmarketing/analytics/5-tips-maximize-productivity-analysis-workspace/) (5 consejos para optimizar su productividad con Analysis Workspace)
   * [Faster Insights with Analysis Workspace](https://blogs.adobe.com/digitalmarketing/analytics/faster-insights-with-the-analysis-workspace/) (Perspectivas más rápidas con Analysis Workspace)
   * [Why You Should Be Using Analysis Workspace](https://blogs.adobe.com/digitalmarketing/analytics/why-you-should-be-using-analysis-workspace-in-adobe-analytics/) (Por qué debería utilizar Analysis Workspace)

## Pasos siguientes

Hay muchas formas diferentes de comprender mejor Analysis Workspace. A continuación se indican algunos aspectos básicos que Adobe recomienda:

### Para usuarios finales que buscan ampliar sus conocimientos sobre cómo utilizar Analysis Workspace

* [Detalles de la IU de Workspace](/help/analyze/analysis-workspace/build-workspace-project/t-freeform-project.md): Ahora que ha creado un informe básico, familiarícese con el resto de la interfaz.
* [Visualizaciones en Workspace](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md): Las tablas improvisada son simplemente un tipo de visualización en Analysis Workspace. Aprenda a utilizar otras visualizaciones, como gráficos de líneas, gráficos de barras y mapas geográficos.
* [Dimensiones en Workspace](/help/analyze/analysis-workspace/components/dimensions/t-breakdown-fa.md): Obtenga más información sobre las dimensiones y cómo utilizarlas en algo más que en los informes de clasificación.
* [Métricas en Workspace](/help/analyze/analysis-workspace/components/apply-create-metrics.md): Obtenga más información sobre las métricas y cómo utilizarlas en otras partes de tablas improvisada.
* [Introducción a la segmentación](/help/analyze/analysis-workspace/components/t-freeform-project-segment.md): Obtenga información sobre los segmentos y extraiga un informe básico con un segmento.
* [Intervalos de fechas en Workspace](/help/analyze/analysis-workspace/components/calendar-date-ranges/calendar.md): Obtenga información sobre las fechas relativas y móviles y utilícelas en proyectos de Workspace.
* Uso compartido de proyectos en Workspace: Muestre a sus compañeros el impresionante proyecto de Workspace que ha creado.
* [Paneles (avanzados) en Workspace](/help/analyze/analysis-workspace/c-panels/panels.md): Utilice funciones avanzadas en Workspace, como Atribución y Comparación de segmentos.

### Para analistas y administradores que buscan mejorar la calidad de Workspace en su organización

* [Permisos de Analysis Workspace](https://docs.adobe.com/content/help/es-ES/core-services/interface/manage-users-and-products/admin-getting-started.html): Asigne permisos de usuario a Workspace mediante Adobe Admin Console.
* [Plantillas en Workspace](/help/analyze/analysis-workspace/build-workspace-project/starter-projects.md): Cree plantillas para que sus compañeros puedan empezar con un espacio de proyecto adaptado a sus necesidades.
* [Preparación personalizada de Workspace](/help/analyze/analysis-workspace/curate-share/curate.md): Cree un proyecto que limite los componentes disponibles para que el Workspace sea más fácil de usar para los menos familiarizados con la herramienta

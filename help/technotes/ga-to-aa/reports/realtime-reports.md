---
title: Informes en tiempo real en Adobe Analytics
description: Aprenda a extraer informes en tiempo real en Adobe Analytics, dirigidos a usuarios que están más familiarizados con Google Analytics.
exl-id: 0ca27992-fff8-4bb4-8582-31fd401b23f6
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '979'
ht-degree: 100%

---

# Informes en tiempo real

Los informes en tiempo real muestran lo que está sucediendo en el sitio en cada momento. Este tipo de informes es especialmente útil para ver los resultados inmediatos de las actualizaciones realizadas en el sitio. Por ejemplo: una empresa que realiza una venta el Black Friday puede medir el tráfico de páginas específicas y determinar qué ventas priorizar en función del rendimiento que se obtiene en ese momento.

![Informe en tiempo real](/help/technotes/ga-to-aa/assets/realtime.png)

Los informes en tiempo real son una de las pocas características que aún no se han introducido en Analysis Workspace. Utilice Reports &amp; Analytics para obtener estos datos. Estos necesitan una sencilla configuración para empezar a recopilar datos.

Para llegar a la página de configuración de informes en tiempo real (se requieren permisos de administración):

1. Haga clic en [!UICONTROL Informes] en el encabezado de navegación de Adobe Analytics.
2. En el menú de la izquierda, haga clic en *[!UICONTROL Métricas del sitio]* > *[!UICONTROL Tiempo real]*.
3. Si el grupo de informes aún no está habilitado en tiempo real, se muestra un mensaje con un vínculo para configurar el grupo de informes. Si el grupo de informes tiene habilitada la actualización en tiempo real, haga clic en [!UICONTROL Configurar] cerca del título del informe en tiempo real.

Adobe permite que haya hasta tres informes en tiempo real recopilando datos simultáneamente. Cada uno debe configurarse antes de empezar a recopilar datos en tiempo real.

![Configuración de informes en tiempo real](/help/technotes/ga-to-aa/assets/realtime_config.png)

## Ubicaciones en tiempo real

Las ubicaciones en tiempo real indican dónde se encuentran los visitantes en el momento en que están visitando el sitio. Para configurar uno de los tres informes en tiempo real con el fin de que muestre los datos de ubicación:

1. Haga clic en [!UICONTROL Configurar] cerca del título del informe en tiempo real.
2. En uno de los espacios de informes en tiempo real:
   * Asigne un nombre al informe en tiempo real. Por ejemplo, “Ubicaciones”.
   * Las instancias generalmente se utilizan como la Métrica. Los usuarios o visitantes únicos no están disponibles en los informes en tiempo real en este momento.
   * Para la Dimensión principal, normalmente se utiliza la segmentación geográfica País. También están disponibles las segmentaciones geográficas Región, DMA de EE. UU. y Ciudad.
   * Para las dos dimensiones secundarias, utilice los datos adicionales que desee ver para este tráfico. Las dimensiones secundarias no tienen que ser específicas de la ubicación.
3. Haga clic en [!UICONTROL Guardar y Ver informe].

## Fuentes de tráfico en tiempo real

Las fuentes de tráfico en tiempo real indican en cada momento de dónde provienen los visitantes cuando están visitando el sitio. Para configurar uno de los tres informes en tiempo real con el fin de que muestre los datos de las fuentes de tráfico:

1. Haga clic en “Configurar” cerca del título del informe en tiempo real.
2. En uno de los espacios de informes en tiempo real:
   * Asigne un nombre al informe en tiempo real. Por ejemplo, “Fuentes de tráfico”.
   * Las instancias generalmente se utilizan como la Métrica. Los usuarios o visitantes únicos no están disponibles en los informes en tiempo real en este momento.
   * Para la Dimensión principal, normalmente se utiliza el Dominio de referencia. También están disponibles el motor de búsqueda y la palabra clave de búsqueda.
   * Para las dos dimensiones secundarias, utilice los datos adicionales que desee ver para este tráfico. Las dimensiones secundarias no tienen por qué ser específicas de las fuentes de tráfico.
3. Haga clic en [!UICONTROL Guardar y Ver informe].

## Contenido en tiempo real

El contenido en tiempo real indica las páginas que están viendo los visitantes en el momento actual. Para configurar uno de los tres informes en tiempo real para que muestre los datos de contenido:

1. Haga clic en [!UICONTROL Configurar] cerca del título del informe en tiempo real.
2. En uno de los espacios de informes en tiempo real:
   * Asigne un nombre al informe en tiempo real. Por ejemplo, “Contenido”.
   * Las instancias generalmente se utilizan como la Métrica. Los usuarios o visitantes únicos no están disponibles en los informes en tiempo real en este momento.
   * Para la Dimensión principal, se suele utilizar Página. La Sección del sitio y el Servidor también están disponibles si en la implementación se definen estas variables.
   * Para las dos dimensiones secundarias, utilice los datos adicionales que desee ver para este tráfico. Las dimensiones secundarias no tienen por qué ser específicas del contenido.
3. Haga clic en [!UICONTROL Guardar y Ver informe].

## Eventos en tiempo real

Los eventos en tiempo real indican los eventos que están teniendo una mayor frecuencia en el sitio. En Google Analytics, un evento captura el número de veces que se ha producido una acción concreta (normalmente, una acción que no está relacionada con una vista de página). Los eventos de GA se envían con una categoría, una etiqueta y una acción. En Adobe Analytics, los eventos personalizados son métricas a las que se asignan nombres descriptivos en Admin Console y que se pueden analizar junto con cualquier dimensión. Si busca una dimensión en Adobe Analytics similar a los eventos de Google Analytics, puede aplicar la dimensión Vínculo personalizado, que a menudo se utiliza como captador global para recopilar datos que no están relacionados con las vistas de página (además de los Vínculos de salida, para Salidas y Vínculos de descarga, para Descargas).

>[!NOTE]
>
>Cuando se utilizan eventos personalizados en informes en tiempo real, el elemento de dimensión debe definirse en la misma visita que el evento personalizado. Por ejemplo, si se visualiza un evento personalizado del tipo “Registros” para la dimensión “Dominio de referencia”, no se devuelve ningún dato sin una implementación adicional. Dado que el dominio de referencia solo aparece en la primera visita y que un evento personalizado suele aparecer más adelante durante esa visita, los datos no se pueden asociar en los informes en tiempo real. Estos datos están disponibles con Analysis Workspace mediante la latencia de procesamiento estándar, que suele ser de entre treinta y noventa minutos.

## Conversiones en tiempo real

Las conversiones en tiempo real presentan los datos de forma diferente entre plataformas. Los objetivos de Google Analytics son similares a las métricas y a los eventos de éxito de Adobe Analytics. La mayoría de las métricas de Adobe Analytics (tanto métricas personalizadas como eventos de éxito como métricas estándar como ingresos) se pueden usar en los informes en tiempo real. Al igual que Google Analytics, se pueden aplicar dimensiones como el nombre del producto, el código de seguimiento y el rendimiento de las campañas en los informes en tiempo real.

1. Haga clic en [!UICONTROL Configurar] cerca del título del informe en tiempo real.
2. En uno de los espacios de informes en tiempo real:
   * Asigne un nombre al informe en tiempo real. Por ejemplo, “Conversiones”.
   * Las instancias generalmente se utilizan como la Métrica. Los usuarios o visitantes únicos no están disponibles en los informes en tiempo real en este momento.
   * Para la dimensión principal, se suele emplear el código de seguimiento. La dimensión Productos también está disponible si su implementación la utiliza.
   * Para las dos dimensiones secundarias, utilice los datos adicionales que desee ver para este tráfico. Las dimensiones secundarias no tienen por qué ser específicas de las conversiones.
3. Haga clic en [!UICONTROL Guardar y Ver informe].

>[!NOTE]
>
>Si utiliza eventos fuera de Instancias, como Pedidos, asegúrese de que la implementación defina la dimensión y el evento en la misma visita. Si las dimensiones y los eventos no se activan en la misma visita, esos datos están disponibles en Analysis Workspace mediante la latencia de procesamiento estándar, que suele ser de entre treinta y noventa minutos.

---
title: Informes en tiempo real en Adobe Analytics
description: Descubra cómo extraer informes en tiempo real en Adobe Analytics, dirigidos a usuarios más familiarizados con Google Analytics.
translation-type: tm+mt
source-git-commit: 3ce18f3f222286aed08c81dd2c958dab7e443df3

---


# Informes en tiempo real

Los informes en tiempo real muestran lo que está sucediendo en el sitio en este momento. Estos tipos de informes son especialmente valiosos para ver los resultados inmediatos de las actualizaciones realizadas en el sitio. Por ejemplo: una empresa que ejecuta una venta en Black Friday puede medir el tráfico de páginas específicas y determinar qué ventas priorizar en función del rendimiento en ese momento.

![Informe en tiempo real](/help/technotes/ga-to-aa/assets/realtime.png)

Los informes en tiempo real son una de las pocas funciones que aún no se han introducido en Analysis Workspace. Utilice Informes y análisis para obtener estos datos. Requieren una configuración sencilla para empezar a recopilar datos.

Para llegar a la página de configuración de informes en tiempo real (se requieren permisos de administración):

1. Haga clic en [!UICONTROL Informes] en el encabezado de navegación de Adobe Analytics.
2. En el menú de la izquierda, haga clic en Métricas *[!UICONTROL del sitio]* &gt; Tiempo *[!UICONTROL real]*.
3. Si el grupo de informes aún no está habilitado en tiempo real, se muestra un mensaje con un vínculo para configurar el grupo de informes. Si el grupo de informes tiene habilitado en tiempo real, haga clic en [!UICONTROL Configurar] cerca del título del informe en tiempo real.

Adobe permite que hasta tres informes en tiempo real recopilen datos simultáneamente. Cada uno debe configurarse antes de empezar a recopilar datos en tiempo real.

![Configuración de informes en tiempo real](/help/technotes/ga-to-aa/assets/realtime_config.png)

## Ubicaciones en tiempo real

Las ubicaciones en tiempo real indican dónde residen los visitantes mientras visitan el sitio en este momento. Para configurar uno de los tres informes en tiempo real para que muestre los datos de ubicación:

1. Haga clic en [!UICONTROL Configurar] cerca del título del informe en tiempo real.
2. En uno de los espacios de informes en tiempo real:
   * Asigne un nombre al informe en tiempo real; por ejemplo, "Ubicaciones".
   * Las instancias generalmente se utilizan como métricas. Los usuarios/visitantes únicos no están disponibles en los informes en tiempo real en este momento.
   * Para la dimensión principal, generalmente se utiliza País de segmentación geográfica. También están disponibles Región de segmentación geográfica, DMA de EE.UU. de segmentación geográfica y Ciudad de segmentación geográfica.
   * Para las dos dimensiones secundarias, utilice los datos adicionales preferidos que desee ver para este tráfico. Las dimensiones secundarias no tienen que ser específicas de la ubicación.
3. Click [!UICONTROL Save and View Report].

## Fuentes de tráfico en tiempo real

Las fuentes de tráfico en tiempo real indican de dónde provienen los visitantes mientras visitan el sitio en este momento. Para configurar uno de los tres informes en tiempo real para que muestre los datos de las fuentes de tráfico:

1. Haga clic en 'Configurar' cerca del título del informe en tiempo real.
2. En uno de los espacios de informes en tiempo real:
   * Asigne un nombre al informe en tiempo real; por ejemplo, "Fuentes de tráfico".
   * Las instancias generalmente se utilizan como métricas. Los usuarios/visitantes únicos no están disponibles en los informes en tiempo real en este momento.
   * Para la dimensión principal, el dominio de referencia suele utilizarse. También están disponibles el motor de búsqueda y la palabra clave de búsqueda.
   * Para las dos dimensiones secundarias, utilice los datos adicionales preferidos que desee ver para este tráfico. Las dimensiones secundarias no tienen por qué ser específicas de las fuentes de tráfico.
3. Click [!UICONTROL Save and View Report].

## Contenido en tiempo real

El contenido en tiempo real indica las páginas que ven los visitantes en ese momento. Para configurar uno de los tres informes en tiempo real para que muestre los datos de contenido:

1. Haga clic en [!UICONTROL Configurar] cerca del título del informe en tiempo real.
2. En uno de los espacios de informes en tiempo real:
   * Asigne un nombre al informe en tiempo real; por ejemplo, "Contenido".
   * Las instancias generalmente se utilizan como métricas. Los usuarios/visitantes únicos no están disponibles en los informes en tiempo real en este momento.
   * Para la dimensión principal, se suele utilizar Página. La sección del sitio y el servidor también están disponibles si la implementación define estas variables.
   * Para las dos dimensiones secundarias, utilice los datos adicionales preferidos que desee ver para este tráfico. Las dimensiones secundarias no tienen por qué ser específicas del contenido.
3. Click [!UICONTROL Save and View Report].

## Eventos en tiempo real

Los eventos en tiempo real indican qué eventos suceden más en el sitio. En Google Analytics, un evento captura el número de veces que se ha producido una acción específica (generalmente una acción que no está relacionada con una vista de página). Los eventos GA se envían con una categoría, una etiqueta y una acción. En Adobe Analytics, los eventos personalizados son métricas a las que se asignan nombres descriptivos en la consola de administración y que se pueden analizar junto con cualquier dimensión. Si busca una dimensión en Adobe Analytics similar a los eventos de Google Analytics, considere la posibilidad de aplicar la dimensión Vínculo personalizado, que a menudo se utiliza como captador global para recopilar datos que no están relacionados con las vistas de página (además de los vínculos de salida, para salidas y para descargar vínculos, para descargas).

> [!NOTE] Cuando se utilizan eventos personalizados en informes en tiempo real, el valor de dimensión debe definirse en la misma visita que el evento personalizado. Por ejemplo, si se visualiza un evento personalizado 'Registros' para la dimensión 'Dominio de referencia', no se devolverá ningún dato sin una implementación adicional. Dado que el dominio de referencia solo aparece en la primera visita y que normalmente aparece un evento personalizado más adelante en la visita, los datos no se pueden asociar en los informes en tiempo real. Estos datos están disponibles mediante Analysis Workspace mediante la latencia de procesamiento estándar, que suele ser de 30 a 90 minutos.

## Conversiones en tiempo real

Las conversiones en tiempo real presentan los datos de forma diferente entre plataformas. Los objetivos de Google Analytics son similares a las métricas y a los eventos de éxito de Adobe Analytics. Puede utilizar la mayoría de las métricas en Adobe Analytics (tanto métricas personalizadas como eventos de éxito como métricas estándar como ingresos) en los informes en tiempo real. Al igual que Google Analytics, también puede aplicar dimensiones como el nombre del producto, el código de seguimiento y el rendimiento de las campañas en los informes en tiempo real.

1. Haga clic en [!UICONTROL Configurar] cerca del título del informe en tiempo real.
2. En uno de los espacios de informes en tiempo real:
   * Asigne un nombre al informe en tiempo real; por ejemplo, "Conversiones".
   * Las instancias generalmente se utilizan como métricas. Los usuarios/visitantes únicos no están disponibles en los informes en tiempo real en este momento.
   * Para la dimensión principal, el código de seguimiento se suele utilizar. La dimensión Productos también está disponible si su implementación la utiliza.
   * Para las dos dimensiones secundarias, utilice los datos adicionales preferidos que desee ver para este tráfico. Las dimensiones secundarias no tienen por qué ser específicas de las conversiones.
3. Click [!UICONTROL Save and View Report].

> [!NOTE] Si utiliza eventos fuera de Instancias, como Pedidos, asegúrese de que la implementación define la dimensión y el evento en la misma visita. Si las dimensiones y los eventos no se activan en la misma visita, esos datos están disponibles en Analysis Workspace mediante la latencia de procesamiento estándar, que suele ser de 30 a 90 minutos.

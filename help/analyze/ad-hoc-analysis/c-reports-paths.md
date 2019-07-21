---
description: Muestra información sobre el orden en que se accede a las páginas del sitio Web. Puede recopilar información sobre los lugares a los que va un visitante antes y después de visitar una página del sitio.
seo-description: Muestra información sobre el orden en que se accede a las páginas del sitio web. Puede recopilar información sobre los lugares a los que va un visitante antes y después de visitar una página del sitio.
seo-title: Informes de rutas
solution: Analytics
title: Informes de rutas
topic: Ad Hoc Analysis
uuid: 5881 cb 1 c -6 d 66-49 fe-ac 84-70 b 82662 acd 2
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Informes de rutas

Muestra información sobre el orden en que se accede a las páginas del sitio Web. Puede recopilar información sobre los lugares a los que va un visitante antes y después de visitar una página del sitio.

## Paths reports {#concept_CB32E270FB9E4D929C91FDFE428CB224}

Muestra información sobre el orden en que se accede a las páginas del sitio Web. Puede recopilar información sobre los lugares a los que va un visitante antes y después de visitar una página del sitio.

Los informes de rutas incluyen informes exhaustivos estándar y de análisis avanzado opcionales que revelan el flujo de navegación de las páginas vistas. Se pueden ver las rutas completas, las rutas más largas y las rutas más populares; explicar el flujo de página, las visitas en el orden previsto y las bajas de manera gráfica; mostrar patrones nuevos y cambiantes en el tiempo; y analizar las rutas de entrada y salida.

** [!UICONTROL Next Page Flow] ** or ** [!UICONTROL Next Site Flow]**: Displays a two-level-deep branching graphic of a selected page (or section, department, and so on), that your visitors view after moving away from the selected page. Use este informe para analizar e identificar los pasos que siguen los visitantes con más frecuencia después de ver una página determinada. Puede:

* Comprender los pasos que se siguen con mayor frecuencia después de ver una página seleccionada.
* Optimizar el diseño de rutas del sitio para canalizar el tráfico hacia una página objetivo.
* Identificar hacia dónde se dirigen los visitantes en lugar de visitar las páginas objetivo.

** [!UICONTROL Next Page] ** (or next categories): Provides detailed site path analysis by showing you the pages on your site that visitors viewed after seeing a selected page. Por ejemplo, cuando selecciona y genera informes sobre todo el sitio, el informe muestra las diez páginas de aterrizaje principales con las cinco páginas siguientes más populares enumeradas debajo de cada página de aterrizaje. Esta información le ayudará a entender qué contenido, qué características y qué otros datos instan a los visitantes a navegar por el sitio.

** [!UICONTROL Previous Page Flow] ** (or other previous categories flow): Displays two levels of the most popular pages that your visitors view before the selected page. El informe también indica el momento en el que los visitantes entran en el sitio.

** [!UICONTROL Previous Page] ** (or other previous categories): Provides detailed site path analysis by showing you the pages on your site that visitors viewed before seeing a selected page on your site.

** [!UICONTROL Fallout] **: Displays the visit attrition and conversion rates between each checkpoint you define. Los pasos están organizados desde arriba hacia abajo, con las cifras y porcentajes sin procesar a la izquierda, y la conversión y los porcentajes de visitas en el orden previsto a la derecha.

Consulte [Informe de visitas en el orden previsto](../../analyze/ad-hoc-analysis/c-reports-paths.md#concept_0ED452F3B1D04A19A59DD04D76D20347) para obtener más información.

** [!UICONTROL Path Length] **: Shows how deep visitors browse into your site (both by percentage and by total count). Dicho de otro modo, el informe indica la cantidad de páginas en las que entra el visitante promedio antes de retirarse.

** [!UICONTROL Page Analysis] **: Contains a subset of reports that let you analyze the following:

* ** [!UICONTROL Page Summary / Site Category Summary] **: Tells you everything you need to know about the page report. Este informe toma y organiza información específica acerca de una página individual y la presenta en un informe único.
* ** [!UICONTROL Reloads] **: Shows the number of times individual pages were reloaded by visitors.
* ** [!UICONTROL Time Spent on Page / Site Category] **: Displays the length of time that visitors browse individual pages in your site. El tiempo empleado se divide en diez categorías: menos de 15 segundos, entre 15 y 30 segundos, entre 30 y 60 segundos, entre 1 y 3 minutos, entre 3 y 5 minutos, entre 5 y 10 minutos, entre 10 y 15 minutos, entre 20 y 30 minutos y más de 30 minutos.
* ** [!UICONTROL Clicks to Page] **: Identifies the number of clicks visitors used to access each page in your site. La profundidad de una página se mide contando la cantidad de páginas vistas antes de ella.

** [!UICONTROL Entries &amp; Exits] **: The [!UICONTROL Entry Page] report shows you, by percentage and by total visits, which pages on your site are the first ones seen by new visitors. Se pueden ver:

* ** [!UICONTROL Entry Pages] ** (or sections): Displays, by percentage and by total visits, which pages on your site are the first pages seen by a new visitor. Puede utilizar este informe para identificar qué páginas web del sitio son los puntos de entrada más frecuentes; optimizar los principales puntos de entrada al sitio y dirigir el tráfico de entrada hacia los mensajes clave.
* ** [!UICONTROL Original Entry Pages] **: Shows the first page viewed for first-time visitors to your site. Cada uno de los usuarios se cuenta una sola vez, a menos que estos borren sus cookies o que no se los esté rastreando con cookies.
* ** [!UICONTROL Single Page Visits] **: Shows pages that are most often both the entry and exit pages for visitor browsing sessions.
* ** [!UICONTROL Exit Pages] **: Displays, by percentage and by total visits, the pages on your site that were the last pages visitors viewed before leaving your site.

## Informe de visitas en el orden previsto {#concept_0ED452F3B1D04A19A59DD04D76D20347}

El [!UICONTROL informe de visitas en el orden previsto] muestra dónde los visitantes abandonan una secuencia preestablecida de páginas o la continúan. y señala las tasas de conversión y de abandono a lo largo de cada paso de la secuencia. Por ejemplo, se puede hacer un seguimiento de dónde los visitantes abandonan la secuencia prevista a lo largo del proceso de compra. Para ello se selecciona un punto inicial y un punto de conclusión y se agregan puntos intermedios para crear una ruta de navegación del sitio web.

<!-- 

c_reports_fallout.xml

 -->

Los datos de visitas en el orden previsto se pueden analizar en el nivel de la visita o del visitante. También se pueden ver una ruta de tendencia, que muestran un gráfico de la tasa de abandono de la secuencia prevista a lo largo de un período indicado. Se pueden configurar páginas aisladas o grupos de páginas como puntos de comprobación del informe, o agregar cualquier dimensión o métrica, en cualquier combinación o secuencia. También se pueden utilizar como puntos de comprobación en el informe categorías configuradas en los Reports and Analytics de marketing.

Este informe resulta útil para examinar:

* Las tasas de conversión a través de procesos específicos en el sitio (tales como un proceso de registro o de compra).
* Flujos de tráfico generales, con un alcance más amplio: entre las personas que visitaron la página principal, este flujo muestra cuántas fueron de allí a realizar una búsqueda y cuántas continuaron para ver un elemento específico.
* Correlaciones entre los eventos del sitio. Las correlaciones muestran el porcentaje de personas que leyeron la política de confidencialidad y procedieron a realizar la compra de un producto.

## Ejecutar un informe de visitas en el orden previsto {#task_3594E8BE55964C1C8B0BEC8DEABF82D3}

Instrucciones para ejecutar un [!UICONTROL informe de visitas en el orden previsto].

<!-- 

t_fallout.xml

 -->

1. Click **[!UICONTROL Reports]** &gt; **[!UICONTROL New Report]** &gt; **[!UICONTROL Fallout.]**

   Other Fallout reports are found in **[!UICONTROL Reports]** &gt; **[!UICONTROL Paths]**.

1. (Opcional) Si quiere filtrar los datos de acuerdo con un segmento específico, arrastre el segmento al campo [!UICONTROL Colocar segmento aquí.]
1. Puede arrastrar cualquier artículo de dimensión al campo [!UICONTROL Colocar evento o artículos de dimensión aquí.]
1. Click **[!UICONTROL Show Fallout At]**Visit or Visitor level, depending on whether you want to view fallout at the visit level, or across visitor sessions.
1. Agregue al informe artículos de dimensión, por ejemplo páginas.

## Asignar páginas a un informe de visitas en el orden previsto {#task_B386289703494FA7B5A40FF9F97CB537}

Instrucciones para asignar páginas a un informe de visitas en el orden previsto.

<!-- 

t_fallout_assign_pages.xml

 -->

1. Click **[!UICONTROL Reports]** &gt; **[!UICONTROL Paths]** &gt; **[!UICONTROL Pages]** &gt; **[!UICONTROL Pages Fallout]**.
1. En el panel [!UICONTROL Dimensiones], busque las páginas que desea agregar y arrástrelas al campo [!UICONTROL Colocar evento o elementos de dimensión aquí.]

## Informe de visitas en el orden previsto: descripciones de campos {#reference_74255CC8D6134F349FEBFEC72934C866}

Descripciones de campos del [!UICONTROL informe de visitas en el orden previsto].

<!-- 

r_dsc_fallout.xml

 -->

| Campo | Descripción |
|--- |--- |
| Mostrar visitas en el orden previsto en el nivel de la visita o del visitante | Permite alternar entre visitas y visitantes para analizar las rutas seguidas por los visitantes. Estas opciones permiten analizar el interés de los visitantes, en el nivel de los visitantes, durante todas las visitas. Los informes de análisis de sitio, de flujo y de visitas en el orden previsto están habilitados para el control de rutas. Si se cambia esta opción, el informe se volverá a ejecutar y los datos se restringirán de acuerdo con la selección. |
| Éxito total  | Un indicador de éxito total. Refleja el valor tal cual era en el último punto de comprobación de la ruta. |
| Éxito total % | Un total acumulado del porcentaje de llegada a un punto de comprobación. |
| Punto de comprobación % | Porcentaje de éxito entre puntos de comprobación (no es acumulado). |
| Incluir todas las visitas | Agrega todas las visitas como punto de comprobación inicial. |
| Visitas en el orden previsto | Permite ver las páginas que se vieron después de que el visitante abandonó la ruta de puntos de comprobación especificada. |
| Visita en orden imprevisto | Permite ver las páginas que se vieron en el siguiente paso de la ruta de puntos de comprobación especificada. |

---
description: Preguntas frecuentes sobre la instalación, configuración y utilización de las funciones de Activity Map.
title: Preguntas frecuentes sobre Activity Map
topic: Activity map
uuid: e4f6d4e2-55d1-4e32-bf70-a334178af370
translation-type: ht
source-git-commit: 3fe3442eae1bdd8b90acffc9c25d184714613c16

---


# Preguntas frecuentes sobre Activity Map

Preguntas frecuentes sobre la instalación, configuración y utilización de las funciones de Activity Map.

## Implementación y AppMeasurement

**P: ¿Cuáles son los pasos de implementación necesarios para habilitar el nuevo Activity Map?**

R: Consulte [Habilitar Activity Map](/help/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-enable.md)

**P: ¿Todos los clientes de Analytics tienen acceso a la página de habilitación de Activity Map de las Herramientas de administración?**

R: Los clientes de Adobe SiteCatalyst no tienen acceso a la página de habilitación de Activity Map de Admin Console. Solo las empresas que disponen de los contratos Adobe Analytics Standard y Adobe Analytics Premium tienen acceso a esta página de configuración.

**P: ¿El nuevo código de AppMeasurement se puede configurar a través de la Dynamic Tag Management (DTM)?**

R: Sí, se puede [implementar manualmente](https://docs.adobe.com/content/help/es-ES/dtm/using/tools/analytics-dtm.translate.html) el nuevo código de AppMeasurement.

**P: ¿Cuáles son los cambios más importantes de la biblioteca AppMeasurement v1.6?**

R: El único cambio que ha habido en AppMeasurement v1.6 es el de la metodología del proceso de seguimiento de vínculos de Activity Map, que requiere la recopilación del nombre de la página, el ID del vínculo y el ID de la región.

**P: ¿AppMeasurement se va a implantar en el nivel de dominio o en páginas determinadas?**

R: AppMeasurement se implanta en el nivel de grupo de informes. El nivel de grupo de informes suele estar asociado a un nivel de dominio, pero esto depende de cada implementación.

**P: DTM carga automáticamente una versión de la API de visitante (1.3.4) anterior a la que Activity Map necesita (1.5.1). ¿Esto causa algún problema?**

R: No. La funcionalidad de Activity Map no depende de la API de visitante.

## Aplicación Activity Map

<!--**Q: How does Activity Map support Single-Page Applications (SPA)?**

A: 

* Every few seconds, Activity Map scans the web page, looking for changes to the page. ActivityMap finds new content on the page without needing a new page load, but this new content is always attributed to the first pageName found when the page loaded.

* Activity Map checks to see if the visibility of links that it knows about has changed. If a change in visibility is found, then the [Links On Page](/help/analyze/activity-map/activitymap-links-report.md) table's Present column for that link updates with **[!UICONTROL Displayed]** or **[!UICONTROL Hidden]**.

* When user interaction creates new content, any new elements that are found by AppMeasurement to be a link will be added to the **[!UICONTROL Links On Page]** table. Activity Map sends a new data request that includes these new links. The new links should appear in the **[!UICONTROL Links On Page]** table when the data request is handled by the UI.-->

**P: ¿Activity Map proporciona datos sobre &quot;vistas&quot;?**

R: No, Adobe no realiza el seguimiento de los vínculos que se visualizaron.

**P: ¿Puedo usar Activity Map si antes no he utilizado ClickMap de visitantes en el sitio web?**

R: No es necesario tener instalada la versión heredada (que ahora se denomina ClickMap) para implementar la versión nueva. Adobe seguirá admitiendo la versión heredada durante un período de tiempo limitado.

**P: ¿Qué exploradores y versiones se admiten en Activity Map?**

R: Admitimos la última versión de los cuatro exploradores principales (IE, Chrome, Firefox y Safari).

**P: ¿Qué es la configuración de solapamiento predeterminada?**

R: De forma predeterminada, Activity Map muestra TODOS los vínculos que han recopilado datos.

Cuando aparecen paneles emergentes sobre las páginas web del cliente, las superposiciones que pertenecen a vínculos que se encuentran debajo del panel emergente podrían mostrarse encima del panel emergente.

**P: ¿Por qué faltan algunas superposiciones de elementos clasificados?**

R: Algunos vínculos clasificados pueden estar ocultos y no verse en la página (los vínculos de submenú, por ejemplo). Como consecuencia, las superposiciones de vínculos correspondientes no se verán. Normalmente, deberían verse clasificaciones de superposiciones con algunos valores de clasificación ausentes, ya que la clasificación se calcula para todos los vínculos que hay en la página (el visible más los ocultos).

**P: ¿Cómo se determina la clasificación de vínculos en el informe Todos los vínculos?**

* En los modos **Degradación** y **Burbujas**, la clasificación se determina mediante la columna de métrica. En el caso de los vínculos con el mismo valor de métrica, la clasificación se basa también en el orden alfabético del ID de los vínculos.
* En el modo **Ganadores y perdedores**, la clasificación se determina, principalmente, mediante la columna % de ganancia. En el caso de los vínculos con la misma ganancia, la clasificación se basa también en el orden alfabético del ID de los vínculos.

**P: ¿Por qué los datos relacionados con los clics en vínculos no se recopilan cuando Activity Map se está ejecutando?**

R: Mientras Activity Map está en uso, la etiqueta de Analytics no recopila datos relacionados con los clics en vínculos. Este comportamiento emula el del complemento ClickMap.

**P: ¿En qué se parecen el informe Todos los vínculos de Activity Map y los informes de Activity Map de Reports &amp; Analytics?**

R: Para extraer el informe Todos los vínculos en Activity Map, se crea una solicitud de desglose de la siguiente manera: Página de Activity Map = &quot;visitedpage&quot;, desglosada por Vínculo y región de Activity Map en `<list of link&regions present in the page at rendering time>`.

Para disponer de un informe equivalente en Reports &amp; Analytics, primero habría que ir al informe Página de Activity Map. Aquí habría que filtrar por el nombre de la página visitada en Activity Map. El nombre de la página visitada aparece en la columna izquierda, en el panel inferior Detalles de página de Activity Map. Cuando se encuentre la página, podrá realizar el desglose a partir de ella y elegir los vínculos y las regiones de Activity Map como dimensión secundaria.

Sin embargo, cabe destacar que el informe obtenido en Informes y análisis recoge todos los vínculos y regiones que se recopilaron para esa página. Pero Activity Map solo incluye en el informe los vínculos y las regiones que están actualmente en la página web. De modo que si tiene un sitio de noticias, solo se verán los datos relacionados con las noticias que estén visibles en ese momento, pero no las que estaban presentes en momentos anteriores del día.

**P: ¿Cómo funciona Activity Map con las páginas que contienen varias etiquetas con varios grupos de informes?**

R: De forma predeterminada, Activity Map usa el grupo de informes asociado a la primera etiqueta que la página envía. Puede seleccionar otro grupo de informes etiquetado desde la ficha Configuración de Activity Map > Otros.

**P: ¿Durante cuánto tiempo analiza Activity Map la etiqueta de Analytics?**

R: Analizamos la etiqueta de Analytics durante un máximo de 20 segundos tras un evento de página completa.

**P: ¿Cómo gestiona Activity Map el contenido dinámico?**

R: Activity Map comprueba cada dos segundos si hay cambios en el estado de la página web, por ejemplo:

* Contenido HTML que se ha vuelto visible
* Contenido HTML que se ha ocultado
* Contenido HTML nuevo que se ha insertado

Si el contenido se oculta o muestra, la aplicación cambia automáticamente el estado de los vínculos afectados (y, por lo tanto, realiza superposiciones) de oculto a mostrado o viceversa.

Si se inserta contenido, la aplicación recupera los vínculos asociados, extrae de ellos los datos de análisis y añade superposiciones para los vínculos.

**P: ¿En qué métrica se basa el informe Flujo de página?**

R: Todos los datos mostrados se basan en las vistas de página.

**P: ¿Cuál es el comportamiento de Activity Map con distintos tipos de páginas?**

*Página web sin la etiqueta de Analytics*

Aparece un mensaje de advertencia debajo de la barra de herramientas que indica que no hay etiqueta.

*Página web con una etiqueta de Analytics incompatible (AppMeasurement v1.5 o anterior)*

Aparece un mensaje de advertencia que indica que es necesario actualizar el código de la página a v1.6 o más.

*Página web con una etiqueta de Analytics compatible (AppMeasurement v1.6 o posterior) pero sin la creación de informes de Activity Map habilitada en las Herramientas de administración*

Aparece un mensaje de advertencia que indica que debe pedirle al administrador que \[habilite el informe de Activity Map\](/home/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-enable.md&quot;) .

**P: ¿Puedo exportar los datos de Activity Map (contextData) mediante un [Analytics Data Feed](https://docs.adobe.com/content/help/es-ES/analytics/export/analytics-data-feed/data-feed-overview.translate.html)?**

R: No.

## Segmentación en Activity Map

**P: ¿Los segmentos están unidos a los segmentos de cada usuario? ¿Los segmentos compartidos están disponibles en Activity Map?**

R: Activity Map hereda los segmentos del sistema de informes de Analytics.

**P: ¿Los segmentos funcionan en el modo Activo?**

R: No, los segmentos no funcionan en el modo Activo. La funcionalidad es equivalente a la de los informes en tiempo real de Reports &amp; Analytics.

## Grupos de informes virtuales

**P: ¿Activity Map es compatible con los grupos de informes virtuales?**

R: Sí. Sin embargo, debido a las limitaciones de los grupos de informes virtuales, el modo Activo de Activity Map no es compatible con los grupos de informes virtuales.

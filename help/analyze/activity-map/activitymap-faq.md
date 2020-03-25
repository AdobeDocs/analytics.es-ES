---
description: Preguntas frecuentes sobre la instalación, configuración y utilización de las funciones de Activity Map.
title: Preguntas frecuentes sobre Activity Map
topic: Activity map
uuid: e4f6d4e2-55d1-4e32-bf70-a334178af370
translation-type: tm+mt
source-git-commit: 0e125be6e1710c65effa0adc8097e8916c8a3290

---


# Preguntas frecuentes sobre Activity Map

Preguntas frecuentes sobre la instalación, configuración y utilización de las funciones de Activity Map.

## Implementación y AppMeasurement

**P: ¿Cuáles son los pasos de implementación necesarios para habilitar el nuevo Activity Map?**

R: Consulte [Habilitar Activity Map](/help/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-enable.md)

**P: ¿Todos los clientes de Analytics tienen acceso a la página de habilitación de Activity Map de las Herramientas de administración?**

R: Los clientes de Adobe SiteCatalyst no tienen acceso a la página de habilitación de Activity Map de Admin Console. Solo las compañías con contratos de Adobe Analytics Standard y Adobe Analytics Premium tienen acceso a esta página de configuración.

**P: ¿Se puede configurar el nuevo código de AppMeasurement mediante la administración dinámica de etiquetas (DTM)?**

A: Sí, puede implementar [](https://marketing.adobe.com/resources/help/en_US/dtm/analytics_dtm.html) manualmente el nuevo código de AppMeasurement.

**P: ¿Cuáles son los grandes cambios en la biblioteca de AppMeasurement v1.6?**

A: El único cambio en AppMeasurement v1.6 está en la metodología del proceso de seguimiento de vínculos de mapa de Actividad que requiere la recopilación del nombre de página, el ID del vínculo y el ID de la región.

**P: ¿AppMeasurement se implementará en el nivel de dominio en lugar de en páginas específicas?**

R: AppMeasurement se implanta en el nivel de grupo de informes. El nivel de grupo de informes generalmente está asociado con un nivel de dominio, pero esto difiere con cada implementación.

**P: La DTM carga automáticamente una versión anterior (1.3.4) de la API de Visitante que la que desea el mapa de Actividad (1.5.1). ¿Esto es un problema?**

R: No. La funcionalidad de mapa de Actividad no depende de la API de visitante.

## Aplicación Activity Map

<!--**Q: How does Activity Map support Single-Page Applications (SPA)?**

A: 

* Every few seconds, Activity Map scans the web page, looking for changes to the page. ActivityMap finds new content on the page without needing a new page load, but this new content is always attributed to the first pageName found when the page loaded.

* Activity Map checks to see if the visibility of links that it knows about has changed. If a change in visibility is found, then the [Links On Page](/help/analyze/activity-map/activitymap-links-report.md) table's Present column for that link updates with **[!UICONTROL Displayed]** or **[!UICONTROL Hidden]**.

* When user interaction creates new content, any new elements that are found by AppMeasurement to be a link will be added to the **[!UICONTROL Links On Page]** table. Activity Map sends a new data request that includes these new links. The new links should appear in the **[!UICONTROL Links On Page]** table when the data request is handled by the UI.-->

**P: ¿Proporciona el mapa de Actividad datos sobre &quot;vistas&quot;?**

A: No, Adobe no realiza el seguimiento de los vínculos que se vieron.

**P: ¿Puedo utilizar Mapa de Actividad si anteriormente no utilizaba ClickMap de Visitante en mi sitio web?**

A: La instalación de la versión heredada (ahora simplemente denominada ClickMap) no es un requisito previo para implementar la nueva versión. Adobe seguirá admitiendo la versión heredada durante un período de tiempo limitado.

**P: ¿Qué exploradores y versiones son compatibles con el mapa de Actividad?**

A: Es compatible con la versión más reciente de los cuatro navegadores principales (Chrome, Firefox, Safari e IE).

**P: ¿Cuáles son los ajustes predeterminados de superposición?**

A: De forma predeterminada, el mapa de Actividad muestra TODOS los vínculos que han recopilado datos.

Cuando se muestran paneles emergentes en la parte superior de las páginas web del cliente, las superposiciones pertenecientes a vínculos que se encuentran debajo del panel emergente pueden mostrarse en la parte superior del panel emergente.

**P: ¿Por qué faltan algunas superposiciones de elementos clasificados?**

A: Algunos vínculos clasificados pueden estar ocultos en la página (por ejemplo, los vínculos de submenú). Como consecuencia, no se mostrarán las superposiciones de vínculos correspondientes. Por lo tanto, puede esperar ver clasificaciones de superposiciones que faltan algunos valores de clasificación específicos, ya que la clasificación se calcula para todos los vínculos de la página (el actual + los ocultos).

**P: ¿Cómo se determina la clasificación de vínculos en el informe Todos los vínculos?**

* En el modo **Degradado** y **Burbujas** : La clasificación está determinada por la columna de métrica. Para los vínculos con el mismo valor de métrica, la clasificación se basa en el orden alfabético del ID del vínculo.
* En el modo **Ganador y Perdedor** , la clasificación está determinada principalmente por la columna % de ganancia. Para los vínculos con la misma ganancia, la clasificación se basa en el orden alfabético del ID del vínculo.

**P: ¿Por qué no se recopilan los datos de clics en vínculos cuando se está ejecutando el mapa de Actividad?**

A: Mientras el mapa de Actividad está en uso, la etiqueta de Analytics no recopila datos de clics en vínculos. Este comportamiento sigue el comportamiento del complemento ClickMap.

**P: ¿Cómo se compara el informe Todos los vínculos de Mapa de Actividades con el sistema de informes de Mapa de Actividades de Informes y análisis?**

R: Para extraer el informe Todos los vínculos en Activity Map, se crea una solicitud de desglose de la siguiente manera: Página de Activity Map = &quot;visitedpage&quot;, desglosada por Vínculo y región de Activity Map en `<list of link&regions present in the page at rendering time>`.

Para obtener un informe equivalente en Informes y análisis, primero debe desplazarse al informe Página de mapa de Actividad. Allí, filtraría el nombre de página visitado en el mapa de Actividad. El nombre de la página visitada se muestra en la columna izquierda del panel inferior Detalles de la página de mapa de Actividad. Una vez encontrada la página, puede desglosar desde esa página y elegir Vínculos y regiones de mapa de Actividad como dimensión secundaria.

Sin embargo, es importante tener en cuenta que el informe obtenido en I&amp;A lista todos los vínculos y regiones que se recopilaron para esa página. Sin embargo, el mapa de Actividad solo informa sobre los vínculos y regiones que están presentes en la página web. Así que si tienen un sitio de noticias, solo mostrará los datos de la noticia presente en este momento, y no las noticias que estuvieron presentes más temprano ese día.

**P: ¿Cómo funciona el mapa de Actividad con las páginas que contienen varias etiquetas que enumeran varios grupos de informes?**

A: De forma predeterminada, Mapa de Actividad utiliza el grupo de informes asociado con la primera etiqueta que envía la página. Puede seleccionar otro grupo de informes etiquetado desde la ficha Configuración de Activity Map > Otros.

**P: ¿Durante cuánto tiempo analiza el mapa de Actividad la etiqueta de Analytics?**

A: Analizamos la etiqueta de Analytics durante un máximo de 20 segundos después de completar el evento de una página.

**P: ¿Cómo gestiona Actividad Map el contenido dinámico?**

A: El mapa de Actividad comprueba cada 2 segundos si ha encontrado cambios en el estado de la página web, como:

* Contenido HTML que se ha vuelto visible
* Contenido HTML oculto
* Nuevo contenido HTML insertado

Si el contenido se oculta o se muestra, la aplicación cambia automáticamente el estado de los vínculos afectados (y, por lo tanto, las superposiciones) de oculto a mostrado o de mostrado a oculto.

Si se inserta contenido nuevo, la aplicación recuperará los vínculos asociados, extraerá datos de análisis para ellos y agregará superposiciones para estos vínculos.

**P: ¿En qué métrica se basa el informe Flujo de página?**

A: Todos los datos mostrados se basan en vistas de página.

**P: ¿Puede explicar el comportamiento del mapa de Actividad con varios tipos de páginas?**

*Página web sin etiqueta de Analytics*

Debajo de la barra de herramientas aparece un mensaje de advertencia que indica que no hay ninguna etiqueta presente.

*Página web con una etiqueta de Analytics incompatible (AppMeasurement v1.5 o anterior)*

Se muestra un mensaje de advertencia que indica que debe actualizar el código de página a v1.6 o más.

*Página web con una etiqueta de Analytics compatible (AppMeasurement v1.6 o posterior) pero sin la creación de informes de Activity Map habilitada en las Herramientas de administración*

Aparece un mensaje de advertencia que indica que debe pedirle al administrador que \[habilite el informe de Activity Map\](/home/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-enable.md&quot;) .

**P: ¿Puedo exportar los datos de Activity Map (contextData) mediante un [Analytics Data Feed](https://docs.adobe.com/content/help/en/analytics/export/analytics-data-feed/data-feed-overview.html)?**

R: No.

## Segmentación en Activity Map

**P: ¿Los segmentos están vinculados a segmentos de usuarios individuales? ¿Los segmentos compartidos están disponibles en el mapa de Actividad?**

A: El mapa de Actividad hereda los segmentos de sistema de informes de Analytics.

**P: ¿Funcionan los segmentos en el modo Activo?**

A: No, los segmentos no funcionan en el modo Activo. La funcionalidad es equivalente a la del sistema de informes en tiempo real en Informes y análisis.

## Grupos de informes virtuales

**P: ¿El mapa de Actividad es compatible con los grupos de informes virtuales?**

R: Sí. Sin embargo, debido a las limitaciones del grupo de informes virtuales, el modo Activo de Mapa de Actividad no es compatible con los grupos de informes virtuales.

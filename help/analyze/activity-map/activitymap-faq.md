---
description: Preguntas más frecuentes sobre la configuración, configuración y utilización de funciones en [!DNL Activity Map].
seo-description: Preguntas más frecuentes sobre la configuración, configuración y utilización de funciones en [!DNL Activity Map].
seo-title: Preguntas más frecuentes sobre [!DNL Activity Map]
solution: Analytics
title: Preguntas más frecuentes sobre [!DNL Activity Map]
topic: Activity Map
uuid: e4f6d4e2-55d1-4e32-bf70-a334178af370
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# [!DNL Activity Map] Preguntas más frecuentes

Preguntas frecuentes sobre la instalación, configuración y utilización de las funciones de [!DNL Activity Map].

## Implementación y AppMeasurement {#section_FB46DD652E854C07AD339D7DD5CBCEC6}

**P: ¿Cuáles son los pasos de implementación necesarios para habilitar el nuevo[!DNL Activity Map]?**

A: Revise [Habilitar [!DNL Activity Map]](/help/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-enable.md)

**P: ¿Todos los clientes de Analytics tienen acceso a la página de habilitación de Activity Map de las Herramientas de administración?**

A: Adobe SiteCatalyst customers do not have access to the Admin Console's [!DNL Activity Map] Enablement page. Solo las empresas que disponen de los contratos Adobe Analytics Standard y Adobe Analytics Premium tienen acceso a esta página de configuración.

**P: ¿El nuevo código de AppMeasurement se puede configurar a través de la Dynamic Tag Management (DTM)?**

R: Sí, se puede [implementar manualmente](https://marketing.adobe.com/resources/help/en_US/dtm/analytics_dtm.html) el nuevo código de AppMeasurement.

**P: ¿Cuáles son los cambios más importantes de la biblioteca AppMeasurement v1.6?**

A: The only change in AppMeasurement v1.6 is in the [!DNL Activity Map] link tracking process methodology that requires the collection of Page name, Link ID and RegionID.

**P: ¿AppMeasurement se va a implantar en el nivel de dominio o en páginas determinadas?**

R: AppMeasurement se implanta en el nivel de grupo de informes. El nivel de grupo de informes suele estar asociado a un nivel de dominio, pero esto depende de cada implementación.

**[!DNL Activity Map]P: DTM carga automáticamente una versión de la API de visitante (1.3.4) anterior a la que necesita (1.5.1). ¿Esto causa algún problema?**

R: No. [!DNL Activity Map] no depende de VisitorAPI.

## [!DNL Activity Map] application {#section_E4F2DAC09EBA4E3BA7BACB49A0A89F8D}

**[!DNL Activity Map]P: ¿Puedo usar si antes no he utilizado ClickMap de visitantes en el sitio web?**

R: No es necesario tener instalada la versión heredada (que ahora se denomina ClickMap) para implementar la versión nueva. Adobe seguirá admitiendo la versión heredada durante un período de tiempo limitado.

**P: ¿Qué exploradores y versiones se admiten en[!DNL Activity Map]?**

R: Solo se admite la última versión de los cuatro exploradores principales (IE, Chrome, Firefox y Safari).

**P: ¿Qué es la configuración de solapamiento predeterminada?**

A: By default, [!DNL Activity Map] shows ALL links that have collected data.

Cuando aparecen paneles emergentes sobre las páginas web del cliente, las superposiciones que pertenecen a vínculos que se encuentran debajo del panel emergente podrían mostrarse encima del panel emergente.

**P: ¿Por qué faltan algunas superposiciones de elementos clasificados?**

R: Algunos vínculos clasificados pueden estar ocultos y no verse en la página (los vínculos de submenú, por ejemplo). Como consecuencia, las superposiciones de vínculos correspondientes no se verán. Normalmente, deberían verse clasificaciones de superposiciones con algunos valores de clasificación ausentes, ya que la clasificación se calcula para todos los vínculos que hay en la página (el visible más los ocultos).

**P: ¿Cómo se determina la clasificación de vínculos en el informe Todos los vínculos?**

* En los modos **Degradación** y **Burbujas**, la clasificación se determina mediante la columna de métrica. En el caso de los vínculos con el mismo valor de métrica, la clasificación se basa también en el orden alfabético del ID de los vínculos.
* En el modo **Ganadores y perdedores**, la clasificación se determina, principalmente, mediante la columna % de ganancia. En el caso de los vínculos con la misma ganancia, la clasificación se basa también en el orden alfabético del ID de los vínculos.

**[!DNL Activity Map]P: ¿Por qué los datos relacionados con los clics en vínculos no se recopilan cuando se está ejecutando?**

A: While [!DNL Activity Map] is in use, link click data is not collected by the Analytics tag. Este comportamiento emula el del complemento ClickMap.

**P: ¿Por qué el desplegable de las métricas muestra las mismas métricas varias veces?**

A: [!DNL Activity Map] lists metrics for all report suites. Por este motivo, algunas métricas pueden estar duplicadas si la empresa no las [ha consolidado](https://marketing.adobe.com/resources/help/en_US/analytics/calcmetrics/cm_transition.html).

El menú desplegable de las métricas le permite limitar la lista de métricas calculadas a las asignadas al grupo de informes de las páginas visitadas.

**P: ¿Cómo se compara el informe[!DNL Activity Map]Todos los vínculos con los informes de Informes y análisis[!DNL Activity Map]?**

A: Para extraer el informe Todos los vínculos en [!DNL Activity Map], creamos una solicitud de desglose de la siguiente manera: [!DNL Activity Map] Página = "página visitada", desglosada por [!DNL Activity Map] Vínculo y región en `<list of link&regions present in the page at rendering time>`.

To get an equivalent report in Reports &amp; Analytics, you would need to first navigate to the [!DNL Activity Map] Page report. Aquí habría que filtrar por el nombre de la página visitada en [!DNL Activity Map]. The visited Pagename is shown in the left column in the [!DNL Activity Map] Page Details Bottom Panel. Once the page has been found, you can break down from that page and choose [!DNL Activity Map] Links &amp; Regions as a secondary dimension.

Sin embargo, cabe destacar que el informe obtenido en Informes y análisis recoge todos los vínculos y regiones que se recopilaron para esa página. But [!DNL Activity Map] only reports on Links&amp;Regions that are currently present in the webpage. De modo que si tiene un sitio de noticias, solo se verán los datos relacionados con las noticias que estén visibles en ese momento, pero no las que estaban presentes en momentos anteriores del día.

**[!DNL Activity Map]P: ¿Cómo funciona con las páginas que contienen varias etiquetas con varios grupos de informes?**

A: By default, [!DNL Activity Map] uses the report suite that is associated with the first tag that is sent by the page.

Puede seleccionar otro grupo de informes etiquetado desde la ficha [!DNL Activity Map]Configuración de  &gt;  &gt; Otros.

**[!DNL Activity Map]P: ¿Durante cuánto tiempo analiza la etiqueta de Analytics?**

R: Analizamos la etiqueta de Analytics durante un máximo de 20 segundos tras un evento de página completa.

**P: ¿Cómo[!DNL Activity Map]gestiona el contenido dinámico?**

A: [!DNL Activity Map] checks every 2 seconds to see if it has found changes in the state of the web page such as:

* Contenido HTML que se ha vuelto visible
* Contenido HTML que se ha ocultado
* Contenido HTML nuevo que se ha insertado

Si el contenido se oculta o muestra, la aplicación cambia automáticamente el estado de los vínculos afectados (y, por lo tanto, realiza superposiciones) de oculto a mostrado o viceversa.

Si se inserta contenido, la aplicación recupera los vínculos asociados, extrae de ellos los datos de análisis y añade superposiciones para los vínculos.

**P: ¿En qué métrica se basa el informe Flujo de página?**

R: Todos los datos mostrados se basan en las vistas de página.

**[!DNL Activity Map]P: ¿Cuál es el comportamiento de con distintos tipos de páginas?**

*Página web sin la etiqueta de Analytics*

Aparece un mensaje de advertencia debajo de la barra de herramientas que indica que no hay etiqueta.

*Página web con una etiqueta de Analytics incompatible (AppMeasurement v1.5 o anterior)*

Aparece un mensaje de advertencia que indica que debe (/home/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-enable.md) actualizar el código de página a la versión 1.6.

*[!DNL Activity Map]Página web con una etiqueta de Analytics compatible (AppMeasurement v1.6 o posterior) pero sin la creación de informes de habilitada en las Herramientas de administración*

Se muestra un mensaje de advertencia que indica que debe solicitar al administrador que \[Habilite el [!DNL Activity Map] informe\](/home/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-enable.md").

**P: ¿Puedo exportar[!DNL Activity Map]datos (contextData) mediante la fuente[de datos](https://marketing.adobe.com/resources/help/en_US/reference/analytics-data-feed.html)de Analytics?**

R: No.

## Segmentación en [!DNL Activity Map]{#section_44D6C5F59B8542DC8A3AF38BD8078DCA}

**P: ¿Los segmentos están unidos a los segmentos de cada usuario? Or are shared Admin-level segments available in[!DNL Activity Map]?**

A: [!DNL Activity Map] inherits your Admin-level segments (reporting segments) from Analytics.

**P: ¿Los segmentos funcionan en el modo Activo?**

R: No, los segmentos no funcionan en el modo Activo. La funcionalidad es equivalente a la de los informes en tiempo real de Reports &amp; Analytics.

## Grupos de informes virtuales {#section_BDB0CA9E732F478EAC349A79753A78DB}

**P: ¿Es[!DNL Activity Map]compatible con los grupos de informes virtuales?**

R: Sí. However, due to virtual report suite limitations, [!DNL Activity Map]'s Live Mode is not compatible with virtual report suites.

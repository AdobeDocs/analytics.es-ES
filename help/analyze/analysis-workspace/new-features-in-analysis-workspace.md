---
description: Nuevas funciones de Analysis Workspace.
keywords: Analysis Workspace
title: Novedades en Analysis Workspace
topic: Reports and analytics
uuid: ff50ef9f-e5b8-442e-bfa6-2f224ba9f111
translation-type: tm+mt
source-git-commit: 69a0e706e2788bf92ba70ea0fd53267c3e2cb80d

---


# Novedades en Analysis Workspace

## Abril de 2020

Nueva función lanzada el 16 de abril de 2020.

| Función | Descripción |
|--- |--- |
| Generar automáticamente [!UICONTROL Freeform Tables] a partir de un estado en blanco | Anteriormente, no se podían soltar componentes directamente en un proyecto en blanco o en un panel en blanco; primero tenía que agregar una tabla improvisada. Ahora puede soltar componentes directamente en un proyecto o panel en blanco, y automáticamente se creará una tabla improvisada en un formato recomendado. Además, se mejoró la forma en que se gestionan los tipos de componentes mixtos (p. ej., dimensiones y métricas) al soltarlos en blanco [!UICONTROL Freeform Table] juntos. |

## Marzo de 2020

Nuevas funciones lanzadas el 12 de marzo de 2020.

| Función | Descripción |
|--- |--- |
| Compatibilidad con varios grupos de informes en Workspace | Ahora puede incorporar datos de varios grupos de informes en un único proyecto para su vista en paralelo. [Más información...](https://docs.adobe.com/content/help/es-ES/analytics/analyze/analysis-workspace/build-workspace-project/multiple-report-suites.html) |
| Plantilla del tutorial de formación | Esta nueva plantilla estándar le guía por la terminología común y por los pasos para crear su primera análisis en Workspace. Está disponible como plantilla estándar en el modo Nuevo proyecto y reemplaza el proyecto de muestra actual para los usuarios nuevos que no tienen otros proyectos en su lista. [Más información...](/help/analyze/analysis-workspace/build-workspace-project/starter-projects.md) |

## Febrero de 2020

Nuevas funciones lanzadas el 20 de febrero de 2020.

| Función | Descripción |
|--- |--- |
| Nueva plantilla de espacio de trabajo para organizaciones que utilizan Análisis entre dispositivos | Esta plantilla muestra la eficacia del CDA para unir visitas y le enseña las métricas y dimensiones exclusivas del CDA. Se necesita un grupo de informes que utilice CDA. Consulte [Configuración de análisis entre dispositivos](https://docs.adobe.com/content/help/es-ES/analytics/components/cda/cda-setup.translate.html) para obtener más información. |
| Nuevas teclas de acceso directo en Workspace | <ul><li>Contraer/Expandir todos los paneles: `alt + m`</li><li>Contraer/Expandir panel activo: `alt + ctrl + m`</li><li>Buscar carril izquierdo: `ctrl + /`</li><li>Mover al panel siguiente: `alt + Right Key`</li><li>Mover al panel anterior: `alt + Left Key`</li></ul>[Más información...](https://docs.adobe.com/content/help/es-ES/analytics/analyze/analysis-workspace/build-workspace-project/fa-shortcut-keys.translate.html) |
| Otras mejoras de Workspace | <ul><li>Cuando se coloca un panel o una visualización en Workspace, el carril izquierdo cambiará automáticamente a componentes para lograr un flujo de trabajo más fluido.</li><li>Los componentes de plantilla ahora se pueden activar (por ejemplo, etiquetados, favoritos, aprobados).</li><li>Las listas de métricas y segmentos filtrados oferta el botón + para agregar un nuevo componente si no encuentra lo que necesita.</li></ul> |
| Depurador de área de trabajo | El Debugger de Workspace se ha agregado al menú Ayuda, lo que le ofrece una forma sencilla de habilitarlo para depurar solicitudes de Workspace. [Más información...](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/reporting-tricks.md) |

## Enero de 2020

Nueva función lanzada el 16 de enero de 2020.

| Función | Descripción |
|--- |--- |
| [Generador de tablas improvisadas](https://docs.adobe.com/content/help/es-ES/analytics/analyze/analysis-workspace/visualizations/freeform-table.html) | Con el Creador de tablas de forma libre, puede arrastrar y soltar varias dimensiones, desgloses, métricas y segmentos para crear tablas que respondan a preguntas comerciales más complejas. Los datos no se actualizarán inmediatamente. Instead, updates occur after you click **[!UICONTROL Build]**, saving you time once you know what table you want to construct. Además, esta función ofrece:<ul><li>**Vista previa**: Puede obtener una vista previa del formato de una tabla antes de dedicar su tiempo a procesar datos reales.</li><li>**Configuración de desglose y filas flexibles**: Puede definir los niveles de fila y desglose para cada fila de dimensión. Anteriormente, Workspace imponía valores predeterminados que no se podían cambiar hasta que se devolvían los datos.</li><li>**Desglose por posición**: Puede definir filas de dimensión para que siempre _se desglosen por posición_ en lugar de _por elemento específico_ (valor predeterminado).</li><li>**Ordenación manual de filas estáticas**: Puede ordenar manualmente las filas estáticas para que las filas de la tabla se muestren exactamente como las necesita. Anteriormente, las filas estáticas solo se podían ordenar por una columna de métrica o alfabéticamente.</li></ul> |

## Octubre de 2019

Mejoras publicadas el jueves, 10 de octubre de 2019.

| Mejora | Descripción |
|--- |--- |
| Actualizar a totales de tabla improvisada | Las tablas improvisadas ahora incluyen dos totales, uno **[!UICONTROL Table total]** y otro **[!UICONTROL Grand total]**. La fila Total de la tabla cuenta los [filtros de informe](https://docs.adobe.com/content/help/es-ES/analytics/analyze/analysis-workspace/build-workspace-project/pagination-filtering-sorting.html) aplicados. Anteriormente, solo la segmentación afectaba a los totales. [Más información](https://docs.adobe.com/content/help/es-ES/analytics/analyze/analysis-workspace/build-workspace-project/workspace-totals.html)<br/>Además, se han agregado **[!UICONTROL Show Totals]** y **[!UICONTROL Show Grand Total]** opciones a **[!UICONTROL Column Settings]**.<br/>Con este cambio a totales improvisados, se actualizarán las visualizaciones dependientes (por ejemplo, visualizaciones vinculadas), así como los datos CSV y PDF exportados. **[!UICONTROL Summary Number]** |
| Opción para eliminar No especificado/Ninguno | Se ha añadido la funcionalidad de eliminar “No especificado (Ninguno)” con facilidad a los filtros de informe. |
| Obsolescencia de los componentes de granularidad morados | Los componentes de hora de granularidad morados (Minuto, Hora, Día, Semana, Mes, Trimestre, Año) han quedado obsoletos. Los componentes de hora morados siempre se han comportado exactamente como sus equivalentes de dimensión naranjas, por lo que este cambio simplificará la experiencia. No es necesario realizar **ninguna acción** si ha utilizado uno de los componentes de tiempo morados en el pasado.<br/>Con este cambio, también se ha cambiado el nombre de la sección púrpura **[!UICONTROL Time]** a **[!UICONTROL Date Ranges]**. |

## Agosto de 2019

Mejoras publicadas el jueves, 8 de agosto de 2019.

| Mejora | Descripción |
|--- |--- |
| Aumento del límite de elementos para el filtro desplegable de 50 a 200 | Hemos aumentado el límite de elementos que se pueden colocar en un filtro desplegable de 50 a 200. Esta mejora admite una variedad de casos de uso, como agregar todos los países (195) a un filtro, o todos los estados y provincias de EE. UU. (52). |

## Julio de 2019

Mejoras publicadas el jueves, 18 de julio de 2019.

| Mejora | Descripción |
|--- |--- |
| Mejoras de análisis de cohorte | Se han añadido [nuevas configuraciones de análisis de cohorte](https://docs.adobe.com/content/help/es-ES/analytics/analyze/analysis-workspace/visualizations/cohort-table/t-cohort.html): <ul><li>Mostrar sólo porcentaje</li><li>Redondear el porcentaje al entero más cercano</li><li>Mostrar una fila porcentual promedia</li></ul> |
| Mostrar elementos de los últimos 18 meses | En el carril izquierdo, los usuarios tienen la opción de _Mostrar elementos de los últimos 18 meses_. Anteriormente, el período retroactivo era de 6 meses como máximo. Esto facilita la comparación con páginas o campañas del último año, hasta hace 18 meses. |
| Nueva plantilla de Analysis Workspace | Hemos añadido una nueva plantilla denominada [&quot;Magento: Marketing y comercio&quot;](https://docs.adobe.com/content/help/es-ES/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html) para Analysis Workspace. Está diseñada específicamente para los clientes de comercio electrónico de Magento, pero cualquier minorista puede utilizarla para obtener una información sin precedentes sobre sus actividades comerciales. |

## Junio de 2019

Mejoras publicadas el jueves, 13 de junio de 2019.

| Mejora | Descripción |
|--- |--- |
| Nuevos filtros predeterminados | Se han agregado nuevos filtros predeterminados a la búsqueda del carril izquierdo. Además de los filtros actuales (Dimensiones, Métricas, Aprobado, etc.), se han añadido nuevos filtros como Métricas calculadas, Atributos del cliente, eVars, Props, Vídeo, etc. para facilitar la búsqueda de los componentes que necesita. |

## Mayo de 2019

Mejora publicada el 09 de mayo de 2019.

| Mejora | Descripción |
|--- |--- |
| Se agregó una nueva configuración a la configuración de visualización de flujo: Incluir instancias de repetición. | [Configuración de flujo](/help/analyze/analysis-workspace/visualizations/c-flow/flow-settings.md) |

## Abril de 2019

Mejora publicada el 11 de abril de 2019.

| Mejora | Descripción |
|--- |--- |
| Mejoras en las optimizaciones | [Optimización del rendimiento](/help/analyze/analysis-workspace/new-features-in-analysis-workspace.md) |

## Enero de 2019

Nuevas funciones y mejoras publicadas el 17 de enero de 2019.

| Función | Descripción |
|--- |--- |
| [Análisis de cohorte](/help/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) | Las mejoras importantes en la Análisis de cohorte le permiten:<ul><li>Aplique una inclusión de segmentos y devuelva métricas por separado. </li><li>Mostrar la reproducción en lugar de la retención.</li><li>Mostrar tablas de latencia (tiempo transcurrido antes y después de un evento de inclusión).</li><li>Personalice la dimensión de cohorte (para agrupar visitantes basados en una eVar, no solo en el tiempo).</li><li>Cálculo de cohorte móvil: calcule la retención y la pérdida en función de un período de tiempo previo, no de la cohorte original. </li><li>Añada en varias métricas en los campos de inclusión y devolución, así como aplique segmentos. (No se admiten las métricas calculadas)</li></ul> |
| [Ver densidad](/help/analyze/analysis-workspace/build-workspace-project/view-density.md) | Esta nueva configuración le permite ver más datos en una sola pantalla al reducir el margen vertical del carril izquierdo, las tablas de forma libre y las tablas de cohorte. Puede acceder a ella desde Proyecto > Info y configuración del proyecto. |
| [Compatibilidad con variables de diversos valores en Attribution IQ](attribution-iq.md) | Algunas dimensiones en Analytics pueden contener múltiples valores en una sola visita, como listVars, la variable de producto, las props de lista o eVars de merchandising. Analysis Workspace permite aplicar Attribution IQ a cualquiera de estos tipos de variables en el nivel de visita. |
| Mejoras en el rendimiento | Mejoras de velocidad en las visualizaciones de desglose: los proyectos con muchos desgloses se cargarán más rápido. |

## Noviembre de 2018

Nuevas funciones y mejoras lanzadas el 1 de noviembre de 2018.

| Función | Descripción |
|--- |--- |
| [Depuración de proyectos y grupos de informes virtuales: mejoras](/help/analyze/analysis-workspace/curate-share/curate-projects-vrs.md) | Estos cambios se introdujeron en octubre de 2018. Se han realizado cambios en los componentes que los administradores y no administradores pueden ver en los proyectos depurados de Workspace y en los grupos de informes virtuales depurados. <br> Anteriormente, cualquier usuario podía ver los componentes no depurados al hacer clic en el botón Mostrar todos los componentes. La experiencia actualizada de organización permite un control más detallado sobre qué componentes son visibles.</br> |

## Octubre de 2018

Nuevas funciones y mejoras lanzadas el 11 de octubre de 2018.

<table id="table_3DDC812B2F66416F868004416D248BF3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Función </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Administración desplegable de paneles</b> </p> </td> 
   <td colname="col2"> <p>Hicimos algunos cambios en la gestión de los despliegues de paneles, que se introdujeron en el informe de septiembre. Al hacer clic con el botón secundario en el menú desplegable, ahora puede </p> 
    <ul id="ul_4BDEC66EEB2243628FE32B43E377E5BD"> 
     <li id="li_EF8277BE972540D3B2604D82BC7C0918">Elimine una lista desplegable (esta opción siempre está presente). </li> 
     <li id="li_6A991208F2744274817DBE1E9D1B443F">Elimine una etiqueta (si se muestra una etiqueta). </li> 
     <li id="li_5C1CFC465C2E41D2B35E8841EFDC82AA">Añada una etiqueta (si no se muestra ninguna etiqueta). </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Vínculos en las descripciones emergentes de visualizaciones y paneles</b> </p> </td> 
   <td colname="col2"> <p>Hemos agregado vínculos a vídeos y documentación pertinentes en las descripciones emergentes de visualizaciones y paneles. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Septiembre de 2018

Nuevas funciones y mejoras lanzadas el 13 de septiembre de 2018.

<table id="table_137719BFA03C44A78FDE872DF8B228A4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Función </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Desplegables de panel</b> </p> </td> 
   <td colname="col2"> <p>La zona de colocación del panel ahora tiene funciones desplegables. Las listas desplegables permiten a los usuarios finales interactuar con los datos de un proyecto de forma controlada. Ejemplo: Supongamos que tiene varias versiones de un proyecto para proporcionar un sistema de informes específico del país. Ahora puede contraer esos proyectos en un solo proyecto y agregarlos a un menú desplegable de país. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Paletas de color</b> </p> </td> 
   <td colname="col2"> <p>Ahora puede cambiar la combinación de colores utilizada en Workspace seleccionando una paleta de colores diferente o especificando su propia paleta. Esto afecta a muchas cosas en Workspace, incluida la mayoría de las visualizaciones. Esto <b>NO afecta</b> al cambio de resumen, al formato condicional en tablas improvisadas y a la visualización de mapa. </p> <p>Nota: La compatibilidad con paletas de color no está habilitada para Internet Explorer 11. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Nueva plantilla: Consumo de audio</b> </p> </td> 
   <td colname="col2"> <p>Consulte <a href="https://marketing.adobe.com/resources/help/es_ES/sc/appmeasurement/hbvideo/media-workspace-templates.html"  >Audio Analytics</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>
## Agosto de 2018

Nuevas funciones y mejoras lanzadas el 9 de agosto de 2018.

<table id="table_DD77C02344414DCD9AC0A6A22E648B72"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Función </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Guías de zona de colocación</b> </p> </td> 
   <td colname="col2"> <p>Estas guías le ayudan a comprender mejor lo que hace cada acción de arrastrar y soltar. Por ejemplo, al pasar el ratón sobre una columna, se mostrarán elementos como Añadir, Reemplazar, Filtrar por y Desglosar. </p> <p>También agregamos guías amarillas y rojas que le avisan cuando está realizando una acción que no está recomendada o prohibida, como apilar dos métricas una encima de la otra (lo que lleva a datos no válidos). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Añadir opción de panel en blanco</b> </p> </td> 
   <td colname="col2"> <p>Se ha añadido un símbolo + debajo del panel de inicio para facilitar la adición de paneles adicionales. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Julio de 2018

Nuevas funciones y mejoras lanzadas el 19 de julio de 2018.

<table id="table_336E121310204DC492EA004F40830B0F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Función </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b> <a href="attribution-iq.md"  > Attribution IQ </a> </b> </p> </td> 
   <td colname="col2"> <p>Attribution IQ permite realizar un análisis más sofisticado e inteligente del rendimiento de marketing. Los nuevos modelos de atribución se pueden utilizar en métricas en el área de trabajo de Análisis (en cualquier tabla o desglose) y en métricas calculadas. Un nuevo panel Atribución permite una mejor visualización y comparación. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b> Mejoras en el carril izquierdo </b> </p> </td> 
   <td colname="col2"> <p>Se han realizado mejoras en el carril izquierdo para que sea más intuitivo y fácil de usar: </p> 
    <ul id="ul_087BEDF4338946DA857CD82CB69F98C2"> 
     <li id="li_C751AACAC60442DC93118F0819F8EEA7"> La función Crear (+) de los componentes (métricas, segmentos, fechas) se puso en línea con los encabezados. </li> 
     <li id="li_DE2EB184A02D4CE58C23F518DB85EFDD"> Se Añadió "+ Ver todo" en la parte inferior de cada lista de sección para que quede claro que hay más de 5 opciones. </li> 
     <li id="li_5208F3C6026647B09F4A85131B175175">Acciones de superficie (como etiqueta, favorito) con iconos cuando se seleccionan componentes. </li> 
     <li id="li_11E601488A844515928231E09889BC54">Se han realizado mejoras estéticas en la interfaz de usuario. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Totales para métricas calculadas </b> </p> </td> 
   <td colname="col2"> <p>Ahora, cuando es posible, se muestran los totales de las métricas calculadas, incluidos los porcentajes </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Nuevo <a href="/help/analyze/analysis-workspace/components/calendar-date-ranges/calendar.md"  > ajuste </a>preestablecido de intervalo de fechas </b> </p> </td> 
   <td colname="col2"> <p>Se Añadió 'Últimas 13 semanas completas' en los ajustes preestablecidos de intervalo de fechas en Espacio de trabajo de Análisis. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Junio de 2018

Nuevas funciones y mejoras publicadas el 14 de junio de 2018.

<table id="table_57035A06D99447A6BE6ED825A648ED3F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Función </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b> <a href="/help/analyze/analysis-workspace/components/dimensions/view-dimensions.md"  > Columnas de dimensión dinámica </a> </b> </p> </td> 
   <td colname="col2"> <p>Anteriormente, cuando se soltaba una dimensión en una columna, se mostraban los 5 valores principales para dimensiones no horarias (y 15 para dimensiones temporales) y se mantenían estáticos esos valores (es decir, los 5 valores seleccionados nunca cambiaban). </p> <p>A partir de ahora, de forma predeterminada, se muestran valores dinámicos en lugar de estáticos, con la opción de convertirlos en valores estáticos. Otras cosas a tener en cuenta: </p> 
    <ul id="ul_C802BC32CB084E30B4E58E9E90B9A63D"> 
     <li id="li_452466AB416F4737B532849C604BD4CC">Haga clic (i) en la dimensión dinámica y verá la clasificación (1 de 5 primeros) y el tipo de dimensión. </li> 
     <li id="li_588F6199E38D47869AC855A4C2A4D1B7">A medida que se actualizan los datos, las columnas de dimensiones dinámicas se actualizarán para mostrar los elementos de dimensión 5/15 actuales. </li> 
     <li id="li_19D47638D4D94416B0DAD2B2FB835ABE">Una columna de dimensión dinámica que se copia o mueve se convertirá en estática. </li> 
     <li id="li_B95411689AE04774B7B9BA128F2DB96F">Al pasar el ratón por encima de una columna de dimensión estática verá un icono de bloqueo que indica que la dimensión es estática. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Nuevo modo de funciones de espacio de trabajo </b> </p> </td> 
   <td colname="col2"> <p>Al igual que las sugerencias del día del mes pasado, este modal muestra las nuevas funciones del espacio de trabajo la primera vez que inicia sesión en Workspace después de una nueva versión. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Mayo de 2018

Nuevas funciones y mejoras publicadas el 10 de mayo de 2018.

<table id="table_EE4C690A178B4F80BDAF2BB4424D6020"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Función </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Sugerencias del día</b> </p> </td> 
   <td colname="col2"> <p>Proporcionaremos Consejos del día (junto con un breve vídeo) en la esquina inferior derecha de la interfaz. Estas sugerencias están pensadas para familiarizarle con una gran variedad de interesantes funciones del espacio de trabajo de Análisis. Puede elegir rechazar estas sugerencias o acceder a ellas a través de <span class="uicontrol">Ayuda</span> &gt; <span class="uicontrol">Sugerencias</span> en cualquier momento. </p> <p><img  src="assets/tip_of_day.png" width="300px" id="image_44A2AA712E4242EC92A180380E66AD7D" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b> <a href="/help/analyze/analysis-workspace/components/t-freeform-project-segment.md"  > Plantillas de segmentos </a> y <a href="/help/analyze/analysis-workspace/components/apply-create-metrics.md"  > plantillas de métricas calculadas </a></b> </p> </td> 
   <td colname="col2"> <p>El carril izquierdo ahora muestra plantillas de segmento y plantillas de métricas calculadas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Posibilidad de desplazarse mientras arrastra componentes</b> </p> </td> 
   <td colname="col2"> <p>Ahora puede desplazarse hacia arriba y hacia abajo mientras arrastra los componentes a una nueva ubicación. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Información adicional sobre  <a href="/help/analyze/analysis-workspace/virtual-analyst/c-anomaly-detection/view-anomalies.md"  > anomalías </a></b> </p> </td> 
   <td colname="col2"> <p>Al pasar el ratón por encima de una anomalía en un gráfico de líneas, la información ahora muestra la fecha y el valor sin procesar de la anomalía. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Abril de 2018

Nuevas funciones y mejoras publicadas el 12 de abril de 2018.

<table id="table_B9E784CD14A1453EB360FCCDC612250F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Función </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/analyze/analysis-workspace/build-workspace-project/column-row-settings/column-settings.md"  > Configuración Justificar el texto del encabezado activada de forma predeterminada </a> </p> </td> 
   <td colname="col2"> <p>Ahora, la configuración de columna <span class="uicontrol">Justificar el texto del encabezado</span> está activada de forma predeterminada en las tablas improvisadas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/analyze/analysis-workspace/build-workspace-project/column-row-settings/table-settings.md"  >Nueva configuración de filas</a> </p> </td> 
   <td colname="col2"> <p>La nueva configuración <span class="uicontrol">Calcular porcentaje por fila</span> obliga a la tabla improvisada a calcular los porcentajes de las celdas en la fila en lugar de en la columna. Esto resulta particularmente útil en los porcentajes de tendencias, como averiguar cómo se comporta una dimensión en comparación con el resto a lo largo del tiempo. Se activa de forma predeterminada al hacer clic en el icono <span class="uicontrol">Visualizar</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#section_D3BB5042A92245D8BF6BCF072C66624B"  > Configuración de la visualización “Apilada al 100 %”</a> </p> </td> 
   <td colname="col2"> <p>Una nueva configuración en las visualizaciones de áreas apiladas, barras apiladas o barras horizontales apiladas convierte el gráfico en una visualización apilada al 100 % para que pueda analizar las proporciones relativas. </p> <p><img placement="break"  src="visualizations/assets/stacked_100_percent.png" width="500px" id="image_ED9C94CE5EAF4500B1EF71BE8701B6D2" /> </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p> Disponibilidad exclusiva de <a href="/help/analyze/analysis-workspace/virtual-analyst/overview.md"  >Detección de anomalías y Análisis de contribución</a> en Analysis Workspace </p> </td> 
   <td colname="col2"> <p>Las características Detección de anomalías y Análisis de contribución se han eliminado del conjunto de funciones de Reports &amp; Analytics, y ahora solo están disponibles en Analysis Workspace. </p> <p>Tenga en cuenta que los clientes de Adobe Analytics Select y Adobe Analytics Foundation solo tienen acceso a la Detección de anomalías de “granularidad diaria” en Workspace. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Marzo de 2018

Nuevas funciones y mejoras publicadas el 8 de marzo de 2018.

<table id="table_580CF2C1322E4FB78870BE2B1F497B2F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Función </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/analyze/analysis-workspace/build-workspace-project/column-row-settings/column-settings.md"  > Justificación del texto del encabezado </a> </p> </td> 
   <td colname="col2"> <p>Ahora puede justificar el texto del encabezado en las tablas improvisadas para que los encabezados sean más legibles y las tablas se puedan compartir con mayor facilidad. Hemos añadido una opción en la configuración de columna llamada “Justificar el texto del encabezado”. Esto resulta muy útil en el procesamiento de archivos .pdf y en las métricas con nombres largos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/analyze/analysis-workspace/components/apply-create-metrics.md"  > Clic con el botón derecho para crear una métrica </a> </p> </td> 
   <td colname="col2"> <p>Con el fin de facilitar la creación rápida de métricas calculadas, se ha añadido la opción <span class="uicontrol">Crear métrica a partir de selección</span> al menú que se abre al hacer clic con el botón derecho en las tablas improvisadas. Esta opción se muestra cuando se selecciona al menos una celda de columna de encabezado. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/analyze/analysis-workspace/visualizations/map-visualization.md"  > Mejoras en la visualización de Mapa </a> </p> </td> 
   <td colname="col2"> <p>Para poder mostrar comparaciones entre períodos (por ejemplo, año tras año) en la visualización de mapas, hemos añadido estas mejoras: </p> 
    <ul id="ul_F570E6AB174C45788620CF50E2742A08"> 
     <li id="li_746E329037764644A9CCF79161C26350">La visualización Mapa ahora puede mostrar números negativos. Por ejemplo, si está trazando una métrica año tras año, el mapa puede mostrar -33% en Nueva York. </li> 
     <li id="li_E05F0380627044E6A4E8A60C98494BF7">Con las métricas que son del tipo "porcentaje", la agrupación agrupa los porcentajes promedio juntos. </li> 
     <li id="li_44C04306EA1B413E91B8256B340D5296">Una nueva combinación de colores: Positivo/Negativo (verde/rojo) </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/analyze/analysis-workspace/build-workspace-project/starter-projects.md"  > Actualizaciones en las plantillas personalizadas </a> </p> </td> 
   <td colname="col2"> <p>Para las plantillas personalizadas recientemente publicadas, tenemos </p> 
    <ul id="ul_787F48253F454163B99F6DD50F199FE2"> 
     <li id="li_828DD547DDB54A81B9FFB9FE92790F6C">Se Añadió un icono de plantilla en la parte superior del proyecto (cerca del título) para ayudar a diferenciar el modo de edición de plantilla del uso de una plantilla como punto de partida para un proyecto. </li> 
     <li id="li_EEAA4D115CB74A57BABD524B2561E0CC">Hemos permitido que los usuarios que no son administradores puedan crear (guardar como) y editar plantillas de proyecto del Workspace, siempre que se les haya concedido el permiso Crear/presentar proyectos en Analysis Workspace. ( <span class="ignoretag"> <span class="uicontrol"> Administración</span> &gt; <span class="uicontrol">Administración de usuarios</span> &gt; <span class="uicontrol">Grupos</span> &gt; <span class="uicontrol">Editar acceso a todos los informes</span> &gt; <span class="uicontrol">Personalizar herramientas de Analytics</span> &gt; <span class="uicontrol">Crear/presentar proyectos en Analysis Workspace </span> </span>). </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## Febrero de 2018

Nueva función y mejoras publicadas el 8 de febrero de 2018.

<table id="table_824BBE4A554B4DB092ADA9044383D0FA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Función </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/analyze/analysis-workspace/build-workspace-project/starter-projects.md#create-custom-template"  > Plantillas personalizadas de Workspace </a> </p> </td> 
   <td colname="col2"> <p>Ahora puede crear sus propias plantillas de Workspace y guardarlas para que otros usuarios de su organización puedan empezar a trabajar con los datos pertinentes para ellos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/analyze/analysis-workspace/build-workspace-project/t-freeform-project.md"  > Nuevo modo para iniciar los proyectos </a> </p> </td> 
   <td colname="col2"> <p>Al hacer clic en “nuevo proyecto”, se abre una pantalla nueva que le ofrece la posibilidad de empezar con </p> 
    <ul id="ul_FE90E6B9AF334A029D66A43901F8FA0B"> 
     <li id="li_F1DFD9AE140C4E5B849D4C522D5968DB">un proyecto en blanco, </li> 
     <li id="li_23BD391D68674C299858A97BFE10598B">una plantilla estándar (integrada) de Workspace o </li> 
     <li id="li_04D84FE375B84BF88843AA0D43A234BF">una plantilla personalizada de Workspace (ver arriba). </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Compatibilidad con copia al hacer clic con el botón derecho </p> </td> 
   <td colname="col2"> <p>Se ha agregado la opción "Copiar al portapapeles" al hacer clic con el botón derecho para permitirle copiar celdas o tablas de forma consistente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/analyze/analysis-workspace/build-workspace-project/column-row-settings/column-settings.md"  >Mejora en los porcentajes de las columnas</a> </p> </td> 
   <td colname="col2"> <p>El “porcentaje del total” mostrado en las columnas antes tenía como límite el 100 %, aunque determinadas situaciones supusieran valores superiores al 100 % del total (por ejemplo, en el caso de los promedios). </p> <p>Ahora mostramos porcentajes buenos por encima del 100%, para ser más precisos. También estamos moviendo el límite superior al 1000 % para garantizar que las columnas puedan crecer en anchura demasiado grande. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/analyze/analysis-workspace/build-workspace-project/column-row-settings/column-settings.md#section_3DD847151DA14914888A70FC4FD7BDFB"  > Posibilidad de usar el formato condicional en los desgloses </a> </p> </td> 
   <td colname="col2"> <p>Ahora, la aplicación de formato condicional (colores, etc.) en tablas de forma libre está activada automáticamente en los desgloses, a menos que los límites “Personalizados” estén seleccionados. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Cambios en la vista de <a href="/help/analyze/analysis-workspace/components/calendar-date-ranges/calendar.md"  >calendario predeterminada</a> </p> </td> 
   <td colname="col2"> <p>Ahora, el calendario del Workspace mostrará de forma predeterminada el mes actual y el anterior, en vez de mostrar el mes actual y el siguiente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Mejora al seleccionar los colores o mantener el puntero sobre ellos en las tablas del Workspace </p> </td> 
   <td colname="col2"> <p>La diferencia de colores al pasar el ratón por encima de una celda de tabla improvisada en lugar de hacer clic en una celda se ha hecho más clara. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Enero de 2018

Nuevas funciones y mejoras publicadas el 18 de enero de 2018.

<table id="table_7A2E678577F94BDABB1276C826E6554F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Función </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Más <a href="/help/analyze/analysis-workspace/build-workspace-project/pagination-filtering-sorting.md"  >opciones de filtrado</a> de elementos de dimensión en tablas Freeform </p> </td> 
   <td colname="col2"> <p>Se han agregado estas opciones de filtrado (avanzadas) para elementos de dimensión (además de las opciones existentes "contiene" y "no contiene"): </p> 
    <ul id="ul_869B3E943E304C0282D56AD96BB79E18"> 
     <li id="li_81A49BA0CA3041C7AB892FAD2D129E5A">Contiene todos los términos </li> 
     <li id="li_2AB564F917844F82839A91949D0B684A">Contiene cualquier término </li> 
     <li id="li_16C7938EDC8F422EA006FB63F2881EF1">Contiene la frase </li> 
     <li id="li_5130EBE9A7A54CCFA313F3C3C268B367">No contiene ningún término </li> 
     <li id="li_861825154EDC49EBA57514FD0A2AE462">No contiene la frase </li> 
     <li id="li_5364BFB73ECF4B92A6663693ABD4BCF5">Es igual a </li> 
     <li id="li_1EBF3119B6364842A35D39BAD645F4AF">No es igual a </li> 
     <li id="li_487886E0A6EC4245A0E85D2E8B4A20FB">Comienza con </li> 
     <li id="li_A73F54DFBAAB44D4A4134342A3124E47">Finaliza con </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#section_05B7914D4C9E443F97E2BFFDEC70240C"  > Copia y pegado de visualizaciones/paneles</a> entre paneles y proyectos </p> </td> 
   <td colname="col2"> <p>Ahora puede hacer clic con el botón secundario y copiar una visualización o panel, y luego pegar ("insertar") que copió el elemento en otro lugar del proyecto o en otro proyecto. </p> <p>Puede utilizar esta capacidad para crear "bloques de construcción" (visualizaciones/paneles predefinidos) que se pueden copiar en otros proyectos para iniciarse más rápidamente, con datos específicos de su empresa. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/analyze/analysis-workspace/build-workspace-project/starter-projects.md"  >Nuevas plantillas móviles para “mensajería” y “ubicación”</a> </p> </td> 
   <td colname="col2"> <p>Se han añadido dos nuevas plantillas de proyecto: </p> 
    <ul id="ul_2F5976C849474A2B8A6BCDA2559F2855"> 
     <li id="li_51B7830E062A4CFDBDF219C56249A733">Una nueva plantilla de proyecto móvil para "Mensajería" que se centra en el rendimiento de la mensajería en la aplicación y push. </li> 
     <li id="li_D2FB258EF3AF4EB19CEB258D08F4EBBE">Una nueva plantilla de proyecto móvil para "Ubicación" que incluye un mapa que muestra los datos de ubicación. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Mejora del cambio de tamaño de columna </p> </td> 
   <td colname="col2"> <p>Al cambiar el tamaño de la columna situada más a la izquierda, Workspace mantiene ahora los porcentajes de anchura del resto de las columnas (no solo ajusta el ancho de la columna siguiente a la derecha). Este cambio acelera la creación de tablas tanto para la análisis como para el uso compartido. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Visualización de <a href="/help/analyze/analysis-workspace/visualizations/freeform-table.md"  >400 filas</a> en una tabla </p> </td> 
   <td colname="col2"> <p>Ahora se pueden mostrar 400 filas en una tabla (frente a las 200 anteriores) para permitir tendencias de 365 días. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Compatibilidad con la <a href="/help/analyze/analysis-workspace/visualizations/map-visualization.md"  >visualización Mapa</a> en PDF </p> </td> 
   <td colname="col2"> <p>La visualización Mapa, introducida en octubre de 2017, puede representarse ahora en PDF. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/analyze/analysis-workspace/build-workspace-project/t-freeform-project.md"  > Intravínculos relativos</a> al guardar como/copiar un proyecto </p> </td> 
   <td colname="col2"> <p>Anteriormente, cuando se copiaba un proyecto o se utilizaba “Guardar como”, todos los intravínculos guardados apuntaban al proyecto original, y no al copiado. </p> <p>Ahora, los intravínculos son relativos al proyecto en el que residen después de la operación de copiar o guardar como. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Análisis de contribución: <a href="https://marketing.adobe.com/resources/help/es_ES/analytics/contribution/ca_main.html"  >notificación de tokens </a> </p> </td> 
   <td colname="col2"> <p>Si la compañía tiene un número limitado de tokens de Análisis de contribución, la interfaz de usuario del espacio de trabajo de Análisis ahora muestra una notificación cuando se consume un token. De este modo, sabe cuántos tokens le quedan.  </p> <p>(Usuarios administradores: es posible restringir quién puede utilizar estos tokens mediante la edición de los permisos de grupo. El permiso se denomina “Detección de anomalías y análisis de contribución” en <span class="uicontrol">Analytics</span> &gt; <span class="uicontrol">Administración</span> &gt; <span class="uicontrol">Administración de usuarios</span> &gt; <span class="uicontrol">Editar grupos</span> &gt; <span class="uicontrol">Editar el acceso a todos los informes</span> &gt; <span class="uicontrol">Personalizar las herramientas del grupo de informes</span> &gt; <span class="uicontrol">Herramientas e informes</span>).  </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Archivos CSV con caracteres de varias despedidas </p> </td> 
   <td colname="col2"> Los archivos CSV enviados por correo electrónico que contienen caracteres multibyte ahora se pueden abrir en MS Excel. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Cambios en evento#, eVar# y prop# </p> </td> 
   <td colname="col2"> <p>Evento#, eVar# y prop#, que se agregaron a los nombres de dimensión en el carril izquierdo (en 2017), solo aparecerán cuando <b>busque</b> el componente. </p> <p>(También se aplica al creador de grupos de informes virtuales). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Cambios en Ninguno/No especificado </p> </td> 
   <td colname="col2"> <p>Se ha cambiado el modo en que Ninguno/No especificado funciona en el espacio de trabajo de Análisis de modo que sea coherente con Informes y análisis, el Generador de segmentos y el menú de valores de dimensión en el espacio de trabajo de Análisis. </p> <p>Esto significa que el valor se mostrará como "No especificado" en lugar de como "Ninguno" en la mayoría de los proyectos de Análisis Workspace. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Noviembre de 2017

Nueva función lanzada el 9 de noviembre de 2017.

<table id="table_C502E81253634E6CBAE7F12C7B62F7B6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Función </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Lista de componentes incompatibles </p> </td> 
   <td colname="col2"> <p>En ocasiones, no todos los componentes incluidos en un proyecto se incluyen en el grupo de informes. El mensaje resultante “Grupo de informes incompatible” que se muestra al cargar un proyecto o al cambiar a un grupo de informes incluye ahora una lista con los componentes incompatibles. </p> </td> 
  </tr> 
 </tbody> 
</table>

## octubre de 2017

Nuevas funciones lanzadas el 26 de octubre de 2017.

<table id="table_892279F2B4AF4DB38C64AA9AFC5657A7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Función </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/analyze/analysis-workspace/visualizations/map-visualization.md"  > Visualización de mapas </a> </p> </td> 
   <td colname="col2"> <p>La nueva Visualización de mapas de Analysis Workspace permite ver fácilmente las interacciones de los clientes en el contexto de su ubicación. De una vista macro (global) a una vista micro (de la ciudad), puede fácilmente aumentar y reducir distintos niveles de jerarquía en la visualización para ver clústeres de usuarios en las regiones. </p> <p>Puede visualizar los datos de ubicación a través de la dirección IP (en conjuntos de datos no móviles) o arrojar los datos de latitud y longitud (para clientes que usen el SDK móvil) en Analysis Workspace.  </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/analyze/analysis-workspace/visualizations/line.md"  > Selector de granularidad en visualizaciones de tendencias </a> </p> </td> 
   <td colname="col2"> <p>Ahora puede alternar fácilmente entre granularidades de tiempo cuando la dimensión del origen de datos es una dimensión de tiempo. Puede cambiar las granularidades desde una lista desplegable en la configuración de visualización. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/analyze/analysis-workspace/components/t-freeform-project-segment.md"  > Dimensiones y eventos completos en la zona de colocación de segmentos </a> </p> </td> 
   <td colname="col2"> <p>Anteriormente, solo se podían soltar elementos de dimensión, intervalos de fechas o segmentos en zonas de colocación de segmentos. Ahora puede colocar una dimensión o evento completo en la zona de colocación del segmento. En ambos casos, Análisis Workspace creará segmentos de visitas "existentes". </p> <p>Ejemplos: "Visita donde existe eVar1" o "Visita donde existe evento1". </p> <p>Nota: No se pueden colocar métricas calculadas en una zona de segmentos. Solo sirven para la zona de segmentos aquellas dimensiones/métricas para las que se pueden crear segmentos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/analyze/analysis-workspace/visualizations/t-sync-visualization.md"  > Visualizaciones conectadas en la configuración de fuentes de datos </a> </p> </td> 
   <td colname="col2"> <p>Si hay visualizaciones conectadas a una tabla improvisada o de cohorte, el punto superior izquierdo (Configuración de fuente de datos) ahora lista las visualizaciones conectadas. Al pasar el ratón por encima se resaltará la visualización vinculada y al hacer clic en ella se le dirigirá. </p> <p>Además, existe una casilla de verificación "Mostrar/Ocultar tabla de datos" que permite mostrar u ocultar la tabla de datos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/analyze/analysis-workspace/build-workspace-project/t-freeform-project.md"  > Se ha añadido event# a los nombres de evento del carril izquierdo </a> </p> </td> 
   <td colname="col2"> <p>Antes de octubre de 2017, evar# y prop# se agregaban a los nombres de dimensión y se podía buscar en esos números. La misma funcionalidad ahora está disponible para eventos. </p> <p>Ejemplo: "Suscripciones" ahora aparece en el carril izquierdo como "Suscripciones (evento1)". </p> <p>Recuerde: </p> 
    <ul id="ul_5DF85C65F7004539949DDC4F23922296"> 
     <li id="li_A685834B4914460D87568583BB39C474">El número de evento no se muestra en la tabla (para mantener los títulos cortos). </li> 
     <li id="li_D742D04470244633900335B7F5A79FD9">Para mantener la coherencia, las props y las eVars tampoco muestran sus números dentro de las tablas. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/analyze/analysis-workspace/build-workspace-project/t-freeform-project.md"  > Dimensiones integradas, ordenadas en un orden lógico de forma predeterminada </a> </p> </td> 
   <td colname="col2"> <p>El orden de clasificación predeterminado para algunas dimensiones integradas se ha actualizado en estos casos: </p> 
    <ul id="ul_B9C0C761F39E43A4977EC028F4D4525C"> 
     <li id="li_FE72ADDCD32A4FF7907462726D6E7758">Cuando se arrastran a una tabla improvisada. </li> 
     <li id="li_5D78DD0DCB7347AC85E260F53109010C">Cuando se ven en el carril izquierdo. </li> 
    </ul> <p>Por ejemplo, si se coloca "Hora del día" en una tabla, se ordenará de 12:00 a 23:00. Todavía tiene la opción de ordenar por cualquier columna de métrica. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/analyze/analysis-workspace/virtual-analyst/c-anomaly-detection/view-anomalies.md"  > Opción para permitir que el intervalo de confianza vuelva a escalar un gráfico </a> </p> </td> 
   <td colname="col2"> <p>El intervalo de confianza de detección de anomalías no escala automáticamente el eje y de una visualización para que el gráfico sea más legible. </p> <p>Ahora tiene la opción de permitir que el intervalo de confianza escale el gráfico. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/components/c-alerts/alert-manager.md"  > Alertas: se ha añadido la opción <b>Renovar</b> </a> </p> </td> 
   <td colname="col2"> <p>En el Administrador de alertas, cuando se seleccionan una o varias alertas, estas se pueden renovar haciendo clic en <span class="uicontrol">Renovar</span>. </p> <p>Esto amplía sus fechas de caducidad 1 año a partir del momento en que se hace clic en <span class="uicontrol">Renovar</span>, fuera cual fuera su fecha de caducidad original. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Mejoras en la interfaz de usuario </p> </td> 
   <td colname="col2"> 
    <ul id="ul_645B43AC6F554353B887DD58F0AA86E8"> 
     <li id="li_05B16A84008E4DA3A5DE91AF3C942D55">Panel en blanco: Ahora, los inicios se realizan resaltando todas las visualizaciones que puede añadir al panel, como Mapa, Visitas en el orden previsto, Flujo, Histograma, Cohorte y Venn. Tiene la opción de guardar este panel como el estado de inicio predeterminado del proyecto. </li> 
     <li id="li_9F1ED138DB0E453DA6BD4B4A512492CC">El nuevo estilo del carril izquierdo hace que los paneles, las visualizaciones y los componentes del carril izquierdo sean más visibles y utilizables. </li> 
     <li id="li_5DF6177F0EFD4D4D9D432768DEA3F37D">Tabla improvisada: Las tablas improvisadas en blanco ahora mostrarán un GIF animado que muestra el paradigma de arrastrar y soltar de Espacio de trabajo de Análisis. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## Septiembre de 2017

Nuevas funciones lanzadas el 21 de septiembre de 2017.

<table id="table_DC0DA93B8A3B481080FCB2BA8F985753"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Función </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/analyze/analysis-workspace/components/dimensions/time-parting-dimensions.md"  >Dimensiones de partición de tiempo en Analysis Workspace</a> </p> </td> 
   <td colname="col2"> <p>Las dimensiones basadas en la marca de tiempo se han agregado de forma predeterminada a Espacio de trabajo de Análisis. Las dimensiones incluyen: </p> 
    <ul id="ul_9BDBC0B344504E85840040E493873A47"> 
     <li id="li_826A8CBF4FDB4C98AC176C7145C09DB2">Hora del día (por ejemplo: 01, 12, 15, 23) </li> 
     <li id="li_FD6AAD4D3F544224A757D8124F973BE5">AM/PM (por ejemplo, AM PM) </li> 
     <li id="li_5CAE35FB8E3E490A8FCF72DF8AC619CC">Día de la semana (por ejemplo: lunes, martes, miércoles, etc.) </li> 
     <li id="li_930DFC6BFCC740A392EC7FA859FF0E73">Fin de semana/día de la semana (por ejemplo, fin de semana, día de la semana) </li> 
     <li id="li_C09F8BF8C598498392732C183C5BB720">Día del mes (por ejemplo: 1, 2, .... 30, 31) </li> 
     <li id="li_E80A8932C32B4410A9BC703090FB5CFF">Mes del año (por ejemplo, enero, febrero y marzo) </li> 
     <li id="li_67620F09B58244B2B17317E0DB97067A">Día del año (por ejemplo, día 1, día 2, etc.) </li> 
     <li id="li_A96CD77357064FC19D92EFA8244560D6">Trimestre del año (por ejemplo, T1, T2, etc.) </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/analyze/analysis-workspace/build-workspace-project/column-row-settings/column-settings.md"  > Administrar varias columnas a la vez en tablas de formas libres </a> </p> </td> 
   <td colname="col2"> <p>Ahora puede cambiar la configuración de varias columnas a la vez. Solo tiene que seleccionar varias columnas y hacer clic en el icono de configuración de cualquiera de ellas. Cualquier cambio que realice se aplicará a todas las columnas con celdas seleccionadas en ellas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/analyze/analysis-workspace/visualizations/c-flow/multi-dimensional-flow.md"  > Flujo: etiquetado interdimensional </a> </p> </td> 
   <td colname="col2"> <p>Existe una nueva etiqueta de dimensión en la parte superior de cada columna Flujo que hace que el uso de varias dimensiones en una visualización de flujo sea más intuitivo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/analyze/analysis-workspace/visualizations/histogram.md#section_09D774C584864D4CA6B5672DC2927477"  > Método de contabilización de accesos de histograma </a> </p> </td> 
   <td colname="col2"> <p>Anteriormente, había dos métodos de contabilización en una visualización de histograma: Visita y Visitante (predeterminado). </p> <p>Ahora puede utilizar un tercer método de recuento, "Visita individual", como contenedor de segmentos. “Ocurrencias” se utiliza como métrica del eje Y en la tabla de forma libre. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Botón <span class="uicontrol">Borrar todo</span> para la configuración de Comparación de segmentos y Análisis de contribución </p> </td> 
   <td colname="col2"> <p>Ahora, en lugar de borrar manualmente cada elemento, se pueden borrar todos en las siguientes áreas de Workspace: </p> 
    <ul id="ul_73E06D64CDCA4E83B9FEC2FD99D41CD3"> 
     <li id="li_A51EF8FADFA04CC19FD79C1675597659"> <a href="/help/analyze/analysis-workspace/virtual-analyst/contribution-analysis/run-contribution-analysis.md#section_F6932F4BF74544B5872164E7B1E0C6FC"  > Componentes excluidos de Análisis de contribución </a> </li> 
     <li id="li_30E612D5A7584484967260931DB9E30E"> <a href="/help/analyze/analysis-workspace/c-panels/c-segment-comparison/segment-comparison.md"> Componentes excluidos de Comparación de segmentos </a> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/analyze/analysis-workspace/visualizations/summary-number-change.md"  >Nombres actualizados para los tipos de visualización Cambio de resumen</a> </p> </td> 
   <td colname="col2"> <p>Se cambiaron los nombres de dos opciones de cambio de resumen actuales para aclarar su significado: </p> 
    <ul id="ul_7301D1C73E72424F911EE8DAAD9247A0"> 
     <li id="li_89D94632E0C94263A84887AF5B360E27">Mostrar cambio &gt; Mostrar cambio de porcentaje </li> 
     <li id="li_D48EB4055019449DAF2998CB9A5D23DF">Mostrar diferencia &gt; Mostrar diferencia sin procesar </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/analyze/analysis-workspace/visualizations/summary-number-change.md"  >Más lugares decimales para Números/Cambios de resumen abreviados</a> </p> </td> 
   <td colname="col2"> <p>Anteriormente, las visualizaciones de número/cambio de resumen abreviadas mostraban 0 lugares decimales. </p> <p>Ahora puede elegir entre 0 y 3 decimales para mejorar el sistema de informes. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Agosto de 2017

Nuevas funciones lanzadas el 17 de agosto de 2017.

<table id="table_C29887097C894B1C91AD7086F0DAEC73"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Función </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/analyze/analysis-workspace/build-workspace-project/t-freeform-project.md"  > Etiquetado de un proyecto mientras se guarda </a> </p> </td> 
   <td colname="col2"> <p>Ahora puede agregar etiquetas a un proyecto mientras lo guarda. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/analyze/analysis-workspace/build-workspace-project/freeform-overview.md"  > Columna Etiquetas de la página de lista de proyectos </a> </p> </td> 
   <td colname="col2"> <p>Se ha añadido una columna <span class="wintitle">Etiquetas</span> en la página de lista de proyectos de Workspace. En esta columna se muestran las etiquetas de cada proyecto. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/analyze/analysis-workspace/visualizations/c-flow/flow.md"  > Exportación de visualizaciones de flujo como archivos .csv </a> </p> </td> 
   <td colname="col2"> <p>Puede descargar visualizaciones de flujo como archivos .csv, lo que le permitirá analizar los resultados de flujo en Microsoft Excel (visualizados como una tabla) o en otra herramienta. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/components/c-alerts/intellligent-alerts.md"  > Alertas inteligentes: intervalos de confianza adicionales </a> </p> </td> 
   <td colname="col2"> <p>Para las alertas basadas en la detección de anomalías, se han añadido dos nuevos niveles de confianza (99,75% y 99,9%). Los valores predeterminados de algunas selecciones de granularidad también han cambiado: </p> 
    <ul id="ul_EB1F07A4D2204D57B2DDD9838CE4F5D9"> 
     <li id="li_542AAACE703F4EBFBD91F11F5ABC2929">por hora: ahora 99,75% </li> 
     <li id="li_D01E4598FB33473FAAC5D60441FD081B"> diario: ahora 99 % </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## Julio de 2017

Nuevas funciones lanzadas el 20 de julio de 2017.

<table id="table_64E3A9960F314E2F9FFC738696EACDF7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Función </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b> <a href="/help/analyze/analysis-workspace/visualizations/text.md"  > Editor de texto enriquecido </a></b> </p> </td> 
   <td colname="col2"> <p>Le permite cambiar los ajustes de fuente (negrita, cursiva, etc.) y los hipervínculos en visualizaciones de cuadros de texto y descripciones de paneles/visualizaciones. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b> <a href="/help/analyze/analysis-workspace/analysis-workspace-features.md#section_253EA04E067F4A29A8B54CE2B7631086"  > Intravínculos (vínculos de visualización rápida) </a></b> </p> </td> 
   <td colname="col2"> <p><b>La vinculación</b> interna permite vincular a paneles y visualizaciones específicos dentro de un proyecto desde un cuadro de texto, por ejemplo, para crear una tabla de contenido del proyecto. Puede compartir estos vínculos como lo haría con el de un proyecto para llevar a un usuario hasta una visualización o panel específico de un proyecto. Se han añadido las opciones nuevas “Obtener vínculo del panel” y “Obtener vínculo de visualización”, a las que se accede con el botón derecho. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b> <a href="/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#section_94F1988CB4B9434BA1D9C6034062C3DE"  > Edición de etiquetas de leyenda </a></b> </p> </td> 
   <td colname="col2"> <p>Le permite cambiar el nombre de las series en las leyendas de visualización (visitas en el orden previsto, área, área apilada, barra, barra apilada, anillo, histograma, barra horizontal, barras horizontales apiladas, línea, dispersión y Venn) para ayudarle a hacer que las imágenes sean más consumibles. </p> <p>La edición de leyendas <b>no</b> se aplica a: Visualizaciones de rectángulo, viñeta, cambio o número de resumen, texto, improvisado, histograma, cohorte o flujo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b> <a href="/help/analyze/analysis-workspace/visualizations/t-sync-visualization.md"  > Actualizaciones de “Administrar fuentes de datos” </a></b> </p> </td> 
   <td colname="col2"> <p>Hemos rediseñado el modo de administrar las fuentes de datos para dar más importancia a las visualizaciones. Ya no hay tablas separadas y ocultas cuando se bloquea el origen de datos en una tabla. </p> <p>En su lugar, mantendremos la imagen vinculada a la tabla desde la que la creó. Esto también resolverá un error con tablas vinculadas en directo, donde se cambia la granularidad y luego se revierte a la granularidad antigua en la siguiente carga del proyecto. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b> <a href="/help/analyze/analysis-workspace/virtual-analyst/contribution-analysis/run-contribution-analysis.md"  > Posibilidad de resaltar una anomalía específica </a></b> </p> </td> 
   <td colname="col2"> <p>Ahora resaltamos la anomalía con un punto azul dentro de la análisis de contribución y los proyectos de alerta inteligente vinculados a ella. Esto proporciona una indicación más clara de la anomalía que se está analizando. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>“Obtener vínculo del proyecto” para los inicios de sesión de Experience Cloud</b> </p> </td> 
   <td colname="col2"> <p>Antes, si iniciaba sesión con las credenciales de Experience Cloud y navegaba a Analytics, no podía utilizar la función <span class="ignoretag"> <span class="uicontrol"> Compartir</span> &gt; <span class="uicontrol"> Obtener vínculo del proyecto</span></span>. Este problema está resuelto. Para que esta opción esté disponible, aún es necesario haber guardado el proyecto. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><a href="/help/analyze/analysis-workspace/curate-share/schedule-projects.md"  >Filtro “Proyectos caducados” en el Administrador de proyectos programados</a></b> </p> </td> 
   <td colname="col2"> <p>Ahora puede filtrar proyectos caducados en el administrador de proyectos programados. A continuación, puede decidir si desea reiniciar o eliminar estos proyectos. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Junio de 2017

Nuevas funciones lanzadas el 8 de junio de 2017.

<table id="table_5B859A64363A44A98FC55E7AFB3C1D0C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Función </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b> <a href="/help/analyze/analysis-workspace/visualizations/fallout/configuring-fallout.md"  > Mejoras en la visita en el orden previsto</a></b> </td> 
   <td colname="col2"> 
    <ul id="ul_8A979BC0BE0F4D008F68B019A2D83A08"> 
     <li id="li_C8093834980B43A094FA9E2A7906E135">Segmentos ilimitados para la comparación </li> 
     <li id="li_45D709C9B04F4E6A9BD94FD03E0C80FA">Posibilidad de nombrar y administrar más fácilmente grupos de puntos de contacto (agregar, eliminar, mover, etc.) </li> 
     <li id="li_BC609CDFD9AA4EB081987922DB318040">Clic derecho &gt; <span class="uicontrol">Tendencia del punto de contacto %</span>: tendencia del porcentaje total de la visita en el orden previsto </li> 
     <li id="li_C72BB725368644DDA3FCE479A918CDB3">Clic derecho &gt; <span class="uicontrol">Tendencia de todos los puntos de contacto %</span>: tendencia de todos los porcentajes de punto de contacto en la visita en el orden previsto (excepto para <span class="wintitle">Todas las visitas</span>, si se incluye) en el mismo gráfico. </li> 
     <li id="li_40D0A8B481B04F21BEC0A4E421C77865">Posibilidad de constreñir puntos de contacto individuales a la siguiente visita (en oposición a hacerlo de forma eventual) dentro de la ruta. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <a href="/help/analyze/analysis-workspace/visualizations/c-flow/flow-settings.md"  > <b>Mejoras de flujo</b> </a> </td> 
   <td colname="col2"> 
    <ul id="ul_54675DB3F59E4B24AF0C8F6E6AB2F3C1"> 
     <li id="li_DEF7D9BF03CD4A2D86A4BDD89FB3731A">Se ha añadido una nueva configuración de visualización denominada <span class="wintitle">Inhabilitar el truncado de etiquetas</span> (valor predeterminado = sin marcar). </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><a href="/help/analyze/analysis-workspace/components/calendar-date-ranges/calendar.md"  >Cambios en el calendario</a></b> </td> 
   <td colname="col2"> Se han realizado cambios en el calendario para adaptarlo al calendario de Reports &amp; Analytics: 
    <ul id="ul_BD706B07369F4339BF4925F22FEC1C7F"> 
     <li id="li_33A47BAAD3C04C8784D2FC00A6F6782E">El primer clic inicio una selección de intervalo de fechas. A continuación, resalte el intervalo en cualquier dirección hasta el segundo clic, que selecciona el final del intervalo de fechas. Si se mantiene pulsada la tecla Mayús (o se utiliza el clic derecho) mientras se hace clic en la primera fecha, se anexará al intervalo. </li> 
     <li id="li_C3BEC56ABCED482C82A41EA0550B3077">Ampliación de los períodos de consulta para los distintos datos acumulados (por ejemplo, permitir que los días se remonten hasta dos años) </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Búsqueda mejorada de elementos de dimensión</b> </p> </td> 
   <td colname="col2"> 
    <ul id="ul_E955585818FF4553A869003B94DDB697"> 
     <li id="li_A37D2DB6290842578FE752DD8E712B73">Velocidad mejorada </li> 
     <li id="li_BADFD0FF3D574F1C8F19EFB37F95969C">Opción <span class="uicontrol">Mostrar elementos principales de los últimos 6 meses</span> que obtiene más datos, si es necesario. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b> <a href="/help/analyze/analysis-workspace/build-workspace-project/column-row-settings/column-settings.md"  > Casilla de verificación Usar límites porcentuales </a></b> </p> </td> 
   <td colname="col2"> 
    <ul id="ul_7B6B794EDF874A4D87770AB9BAB42F33"> 
     <li id="li_0B403D892320434FBAD9A7F7B808947C"> Se Añadió una casilla de verificación para denotar recortes porcentuales, especialmente para métricas basadas en porcentajes (también funciona con métricas no basadas en porcentajes). </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Mejoras </b>en el Administrador de componentes </p> </td> 
   <td colname="col2"> 
    <ul id="ul_BB22F84ABFB04685A9752AD4BDE6E60A"> 
     <li id="li_B3D460C15C454911A9D7254F50815355">Fechas de caducidad Añadidas para alertas y proyectos programados </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b> <a href="/help/components/c-alerts/alert-manager.md"  > Mejoras en el Administrador de alertas </a> </b> </p> </td> 
   <td colname="col2"> 
    <ul id="ul_72464DC499744290BA37DB3B1E143F74"> 
     <li id="li_C687F0A3A99F4CC39B482BDA0F7B75DD">Se ha añadido la posibilidad de habilitar/deshabilitar alertas. </li> 
     <li id="li_F7415EE7DF29417FAF416594E36A38A4">Se ha añadido la columna “habilitada / deshabilitada”. </li> 
     <li id="li_61B3A60A2AFB4BD0AA4D83803AB95B1E">Se ha añadido un filtro para las alertas habilitadas/deshabilitadas. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Nuevas <b>  <a href="/help/analyze/analysis-workspace/build-workspace-project/fa-shortcut-keys.md"  > teclas de acceso directo </a></b> </p> </td> 
   <td colname="col2"> <p>Se han añadido las siguientes teclas de acceso directo: </p> 
    <ul id="ul_5AE965D910DA4883BC2067CDFDBBA75A"> 
     <li id="li_6DBD6DFB9CA54F89B9A0627F3B1D5928">alt + mayús + 1 = ir al panel Paneles </li> 
     <li id="li_1B7E7C1115A84DB8A1BC07EA1C3AB15F">alt + mayús + 2 = ir al panel Visualizaciones </li> 
     <li id="li_1BDB09DDEEDC4E7DB0D1C08A4E02A613">alt + mayús + 3 = ir al panel Componentes </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## Abril de 2017

Nuevas funciones lanzadas el 20 de abril de 2017.

<table id="table_53EEFB870ED943F5BFD71FAB2DBCE49B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Función </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/analyze/analysis-workspace/build-workspace-project/starter-projects.md"  > Plantilla Personas </a> </p> </td> 
   <td colname="col2"> <p>Nota: La plantilla Personas y su métrica asociada Personas solo se pueden usar como parte de la <a href="https://marketing.adobe.com/resources/help/es_ES/mcdc/mcdc-people.html"  >cooperación entre dispositivos de Adobe Experience Cloud</a>. </p> <p>La plantilla se basa en la métrica Personas, que es una versión deduplicada de la métrica Visitantes únicos. La métrica Personas proporciona una medida de la frecuencia con la que los consumidores que usan varios dispositivos interactúan con la marca. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Mejoras en la opción Deshacer/Rehacer </p> </td> 
   <td colname="col2"> <p>En estas listas se muestran las acciones que puede y las que no puede  <a href="/help/analyze/analysis-workspace/build-workspace-project/undo-redo.md"  > deshacer y rehacer en Analysis Workspace</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Febrero de 2017

Nueva función lanzada el 16 de febrero de 2017:

<table id="table_227D3668E9FD4FF4A1906FC619DCAFBF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Función </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/analyze/analysis-workspace/build-workspace-project/column-row-settings/table-settings.md"  > Desglose por posición </a> </p> </td> 
   <td colname="col2"> <p>Permite el desglose por posición de tabla. Ejemplo: “Siempre quiero desglosadas las 7 filas superiores de una tabla improvisada”. Ahora hay una casilla de verificación cuando se crea una tabla improvisada que le permite activar "Desglose por posición". Esta configuración está deshabilitada de forma predeterminada. </p> <p>Anteriormente, la lista de valores en el desglose estaba “bloqueada”. Esto llevaba a una situación en la que, por ejemplo, si realizaba un desglose de <span class="wintitle">Fecha</span> por <span class="wintitle">Página</span>, obtenía una lista de las 50 primeras páginas para el intervalo de fechas seleccionado. </p> <p>Si se guardaba ese informe y se ejecutaba un mes después, era probable que las 50 primeras páginas hubieran cambiado. Sin embargo, Análisis Workspace "confiaba" en los resultados del desglose original y devolvía las mismas páginas, pero con el mes actual como intervalo de fechas. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Enero de 2017

Nueva función lanzada el 19 de enero de 2017:

<table id="table_0AB06B81BFA34521A9BF1150E64663C3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Función </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/analyze/analysis-workspace/curate-share/download-send.md"  >Enviar y descargar un PDF sin tener que guardar el proyecto</a> </p> </td> 
   <td colname="col2"> <p>Ahora puede enviar y descargar un PDF en Workspace sin tener que guardar el proyecto. El nombre del archivo PDF coincide con el nombre actual del proyecto. El PDF descargado incluye los cambios no guardados en el proyecto. Tenga en cuenta que no puede programar proyectos sin guardar. (También puede enviar y descargar archivos CSV sin guardar, pero no puede programarlos). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/analyze/analysis-workspace/curate-share/curate.md"  >Compartir automáticamente componentes de proyectos</a> </p> </td> 
   <td colname="col2"> <p>Ahora tiene la opción de compartir automáticamente los componentes del proyecto (segmentos, métricas calculadas e intervalos de fecha) con todos los destinatarios. Después de compartirse, estos componentes aparecerán en el menú desplegable de componentes de Workspace del destinatario. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Visualización de visitas en el orden previsto en formato CSV </p> </td> 
   <td colname="col2"> <p>Compatibilidad Añadida con la visualización de visitas en el orden previsto en formato CSV. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/analyze/analysis-workspace/components/t-freeform-project-segment.md"  > Intervalos de fechas en los segmentos </a> </p> </td> 
   <td colname="col2"> <p>Puede soltar intervalos de fechas en zonas de colocación de segmentos (por ejemplo, zonas de colocación de segmentos de panel, zonas de colocación de segmentos de visualización de visitas en el orden previsto, etc.). Los intervalos de fecha se convierten automáticamente en segmentos. Los intervalos de fechas pueden ser personalizados y no personalizados, pero no granularidades como hora/día/semana/mes/trimestre/año. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/analyze/analysis-workspace/components/calendar-date-ranges/time-comparison.md"  > Agregar un periodo de tiempo a cada columna de una tabla </a> </p> </td> 
   <td colname="col2"> <p>Ahora puede agregar un período de tiempo a cada columna de una tabla, permitiéndole agregar un período de tiempo diferente al período en el que está configurado el calendario. Esta función es otra forma de comparar fechas. También puede alinear fechas de cada columna con todos los inicios de la misma fila. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Noviembre de 2016

Nueva función lanzada el 10 de noviembre de 2016:

<table id="table_9B2B9CC7A3574A99A716BF1C9745E32B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Función </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/analyze/analysis-workspace/components/calendar-date-ranges/time-comparison.md"  > Comparación de fechas </a> </p> </td> 
   <td colname="col2"> <p>La nueva función de comparación de fechas permite utilizar cualquier columna para crear una comparación de fechas comunes, por ejemplo, año tras año, trimestre tras trimestre, mes tras mes, etc. </p> <p>Las comparaciones de fechas incluyen automáticamente la columna  Diferencia, que muestra el cambio de porcentaje. </p> </td> 
  </tr> 
 </tbody> 
</table>

## octubre de 2016

Nuevas funciones lanzadas el 20 de octubre de 2016:

<table id="table_56258080C60F480AA83E1D5DE7D2C782"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Nueva función </th> 
   <th colname="col2" class="entry"> Cómo puede usarla </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b> <a href="/help/analyze/analysis-workspace/visualizations/fallout/fallout-flow.md"  > Análisis de visitas en el orden previsto </a></b> </td> 
   <td colname="col2"> <p>La nueva función de visitas en el orden previsto traerá la funcionalidad de canal de mercadotecnia a Análisis Workspace. Un canal le permite identificar dónde abandonan los clientes una campaña de marketing o dónde se desvían de una ruta de conversión definida mientras interactúan con su sitio web o campaña entre canales. La Análisis de visitas en el orden previsto le permite crear embudos sólidos con nuevas visualizaciones y la flexibilidad inherente que proporciona el espacio de trabajo de Análisis para identificar la conversión de las métricas de éxito clave. La Análisis de visitas en el orden previsto le permite </p> <p> </p> 
    <ul id="ul_E7C8255BA5D84F74ABBC6CC0E148DFB0"> 
     <li id="li_B7AC104F2A9348DCB2BCAA2FC9D3F3E6">Arrastrar, soltar y reorganizar pasos de canal (puntos de contacto) </li> 
     <li id="li_CC85524BC64546CD84794CC02C24CF21">Analizar visitas en el orden previsto multidimensionales (mezclar y hacer coincidir valores de diferentes dimensiones y métricas) </li> 
     <li id="li_FA59CEE0211E4894B9109FF6A2FA3F80">Identifique los siguientes pasos para saber hacia dónde se dirigen los clientes inmediatamente después de la visita en el orden previsto </li> 
    </ul> <p><img placement="break"  src="assets/fallout2.png" width="500px" id="image_193B0E7870734DAFA063BBFA121A3E34" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <a href="/help/analyze/analysis-workspace/visualizations/c-flow/flow.md"  > Visualización de flujo </a></b> </td> 
   <td colname="col2"> <p>La nueva función de flujo le permite realizar vistas del flujo/viaje del cliente a través de sitios/aplicaciones mediante visualizaciones nuevas, actualizadas y flexibles en el espacio de trabajo de Análisis para descubrir cómo se mueven y avanzan los clientes a través de sus sitios/aplicaciones. El flujo le permite </p> <p> </p> 
    <ul id="ul_F1D4A99743664CB3B17E9485CF5E72FC"> 
     <li id="li_0F7AF953EAB746DC95032FF9A533E560">Visualizar el viaje del cliente a través de los recursos </li> 
     <li id="li_697A47BE06CF4284ACA3DBE4CA4012BF">Analizar los siguientes pasos inmediatos desde la entrada, la salida o un elemento de dimensión específico en el viaje del cliente </li> 
     <li id="li_D13AD928AC434D599D43836FB334B14D">Crear dinámicamente un segmento de usuarios mediante la designación de un punto específico en una ruta seleccionada </li> 
    </ul> <p><img placement="break"  src="assets/flow.png" width="500px" id="image_8ED88B5EDAA046978170F8BBB4018DA2" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><a href="/help/components/c-alerts/intellligent-alerts.md"  >Alertas inteligentes</a></b> </td> 
   <td colname="col2"> <p>Dado que el nuevo sistema de alertas para todas las alertas inteligentes de Adobe Analytics le permite crear y gestionar alertas en Analysis Workspace, finalice con la vista previa de alerta y la contribución de reglas. Puede: </p> <p> </p> 
    <ul id="ul_02BD64D3047942009880B8F1DA1F2A40"> 
     <li id="li_01504AABBC514DF38354683843222541">Generar alertas basadas en anomalías (umbrales del 90 %, 95 % o 99 %); % de cambio; arriba/abajo). </li> 
     <li id="li_9BFE2B4C429D441287F1A37A08E62A40">Obtener una vista previa de la frecuencia con la que se activará una alerta. </li> 
     <li id="li_08D310196581483DB499C00358835B73">Enviar alertas por correo electrónico o SMS con vínculos a proyectos de Analysis Workspace autogenerados. </li> 
     <li id="li_2ADF9465EE474CDB839ED867662CCE6F">Crear alertas “apiladas” que capturan varias métricas en una sola alerta. </li> 
    </ul> <p><img placement="break"  src="assets/intel-alerts.png" width="400px" id="image_10069C33B6B1437CA578B8194FC75AD8" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <a href="/help/analyze/analysis-workspace/virtual-analyst/c-anomaly-detection/anomaly-detection.md"  > Detección de anomalías y análisis de contribución </a></b> </td> 
   <td colname="col2"> <p>Avísenos si un cambio en datos de tendencias es significante y cuál fue el motivo. </p> <p>Tanto la Detección de anomalías como el Análisis de contribuciones ahora son flujos de trabajo principales en Analysis Workspace. </p> <p>Importante: El análisis de contribución está disponible solamente para clientes de Adobe Analytics Premium. </p> <p>Puede: </p> <p> </p> 
    <ul id="ul_9CEE47788F3640838D8598F2E2C020D6"> 
     <li id="li_787236BB5EA545B8833B311C06C24337">Detectar automáticamente anomalías de datos estadísticamente significativas en los datos. </li> 
     <li id="li_2FB3D94DEEF14DD5ADA6AD69E15F243D">Ejecute la Análisis de contribución para cualquier anomalía diaria e incrúsela en el proyecto de Espacio de trabajo de Análisis. </li> 
    </ul> <p><img placement="break"  src="assets/anomaly_linechart.png" width="500px" id="image_DFAF4034E2AC4B4AAB140EA004112722" /> </p> <p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <a href="/help/analyze/analysis-workspace/build-workspace-project/starter-projects.md"  > Proyectos iniciales </a></b> </td> 
   <td colname="col2"> Para facilitar a los usuarios el inicio del área de trabajo de Análisis, hemos creado algunas plantillas de proyecto prediseñadas para problemas empresariales comunes, como <p> </p> 
    <ul id="ul_603F5ACC16F74D53AEB9F762FAC91656"> 
     <li id="li_6B3F2E5D4B044EC19D45E5501E33DB91">Retención de usuarios </li> 
     <li id="li_7240EE8852FC4642B3AD4837C990A775">Adquisición de aplicación móvil </li> 
    </ul> <p><img placement="break"  src="assets/starter.png" width="500px" id="image_A62AFD39812E43DCBF30D5E072A7E892" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><a href="/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md">Visualización del histograma</a></b> </td> 
   <td colname="col2"> <p>Los histogramas permiten a los usuarios ver distribuciones de usuarios en cualquier evento de éxito. Puede personalizar los cubos y los tamaños de cubos para adaptarse a cualquier distribución e identificar usuarios de alto valor y bajo valor. </p> <p><img placement="break"  src="assets/histogram3.png" width="500px" id="image_E3277073B50140E0A3FD7C1601CF9661" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Actualizaciones diversas </td> 
   <td colname="col2"> 
    <ul id="ul_2585F74DC7754C819017F280E16BF06F"> 
     <li id="li_412446013E7F42DBB1BF50F9E2C4D92F"> 
      <!--AN-124610: -->Se ha agregado “Contar instancias repetidas” como ajuste de nivel de proyecto (<span class="uicontrol">Proyecto</span> &gt; <span class="uicontrol">Info y configuración del proyecto </span>). Esta configuración especifica si las instancias repetidas se cuentan en los informes. Si tiene varios valores secuenciales para la misma variable, puede contarlos como una o como varias instancias de la variable. </li> 
     <li id="li_480E1B307C62418CBC2F50ADE32B9EE9">Se Añadió un nuevo botón llamado "Aplicar a todos los paneles" junto a "Cancelar" y "Ejecutar" en el calendario. Se cambió "Ejecutar" a "Aplicar". Si hace clic en el botón nuevo, no sólo cambiará el intervalo de fechas seleccionado para el panel actual, sino también para todos los demás paneles del proyecto. </li> 
     <li id="li_4D10DFE307344D06AA60792FABE5B57E"> 
      <!--AN-124168: -->Se ha agregado un botón “Acciones” en el carril de navegación izquierdo que incluye estas acciones: Etiquetar, Favorito, Aprobar, <b>Compartir (nuevo)</b>, <b>Eliminar (¡nuevo!)</b>. </li> 
     <li id="li_946EC05568D4447193E9307546DF6F9B">Se ha Añadido un filtro en la barra de búsqueda que permite filtrar por etiquetas, favoritos, elementos aprobados y componentes. </li> 
     <li id="li_4EA118ACCD3B4F88B0ECF72717F631FA">Se ha Añadido un icono de previsualización en filas manuales (no en filas dinámicas que lista elementos de dimensión) que permite previsualización de segmentos, métricas e intervalos de fechas. </li> 
     <li id="li_81D5241EA3FD49CEA0E9F412837D87A8"> 
      <!--AN-128702: -->Se ha actualizado el vínculo de YouTube para tutoriales de Analysis Workspace: <a href="https://www.youtube.com/playlist?list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS"  >https://www.youtube.com/playlist?list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS</a>. </li> 
     <li id="li_D81DB98C49664D2884CCCC1DB0058CD8"> 
      <!--AN-124004:-->Para las visualizaciones, hemos agregado una opción al menú contextual del botón secundario denominada <span class="uicontrol">Comenzar de nuevo</span> (funcionará para Flujo, Venn e Histograma), que elimina la configuración para la visualización actual y abre un nuevo panel donde puede volver a configurarla. </li> 
     <li id="li_84632BFCE1794B49A31FF45067FA04B7">Una nueva configuración de visualización denominada “Leyenda visible” permite ocultar el texto de detalles de filtro para la visualización Número de resumen/Cambio de resumen. </li> 
     <li id="li_EE8C48642DD54A04B08F4222F9565BF6">Una nueva configuración de visualización para las visualizaciones Cambio de resumen permite mostrar la diferencia entre 2 porcentajes. Para los valores que no son de porcentaje, si selecciona la opción “Mostrar diferencia”, mostrará un número. </li> 
     <li id="li_17AAABCA7B3A477182FB70453CA2EEBB">Se ha ajustado el número de filas para las dimensiones de tiempo. </li> 
     <li id="li_35A91D50CD514CD0B939C24AEEC64BF4">Se ha actualizado el aspecto del carril de navegación izquierdo en el Generador de segmentos y en el Creador de métricas calculadas para que parezca que el área de trabajo de Análisis. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## junio de 2016

Nuevas funciones lanzadas el 16 de junio de 2016:

* [Nuevo permiso](https://marketing.adobe.com/resources/help/es_ES/reference/groups.html) de grupo que permite a los administradores permitir o denegar el acceso de los usuarios a la ficha **[!UICONTROL Analytics]** > **[!UICONTROL Workspace]** . Desde el 16 de junio de 2016, todos los usuarios tienen permiso para acceder a esta ficha. Para denegar el acceso, solo tiene que eliminar usuarios del grupo Acceso a área de trabajo de Análisis.
* The [Segment Comparison Panel](/help/analyze/analysis-workspace/c-panels/c-segment-comparison/segment-comparison.md)discovers the most statistically significant differences between any two segments through an automated analysis of every single metric and dimension you have access to.
* [Nueva estructura](/help/analyze/analysis-workspace/build-workspace-project/freeform-overview.md) del menú Proyectos que reorganiza el menú superior y lo hace más extensible. Por ejemplo, la creación de un **nuevo panel** de cohorte ahora implica crear un panel en blanco y arrastrarlo en una visualización de tabla de cohorte.
* [Nuevo carril](/help/analyze/analysis-workspace/build-workspace-project/freeform-overview.md)izquierdo: Paneles, Visualizaciones, Componentes
* Un nuevo tipo de [Visualización Venn](/help/analyze/analysis-workspace/visualizations/venn.md) le permite arrastrar hasta tres segmentos y una métrica y construir un diagrama de Venn.
* El gráfico de líneas [Selección de tendencias](/help/analyze/analysis-workspace/analysis-workspace-features.md#section_34930C967C104C2B9092BA8DCF2BF81A) de una tabla jerárquica ahora está vinculado.
* [Icono “Crear imagen”](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md): al hacer clic en el botón aparece una suposición inteligente sobre su siguiente acción (gráfico de barras, Venn...).
* Funcionalidad de filas [](/help/analyze/analysis-workspace/build-workspace-project/column-row-settings/manual-vs-dynamic-rows.md) manuales ampliada
* [Añadir zona de colocación de segmentos](/help/analyze/analysis-workspace/components/t-freeform-project-segment.md)
* Actualizaciones menores:

   * Posibilidad de eliminar todas las visualizaciones de un panel y todos los paneles de un proyecto. (Anteriormente, había que mantener al menos una visualización o un panel).
   * Changes to the [shortcut keys](/help/analyze/analysis-workspace/build-workspace-project/fa-shortcut-keys.md) (hotkeys) that can facilitate work with Analysis Workspace.
   * Cambios de estilo: fuentes más pequeñas en las visualizaciones, muestras de color en las filas; selector de fecha desplazado hacia abajo (en los paneles).

## Abril de 2016

Nuevas funciones lanzadas el 21 de abril de 2016:

<table id="table_2649645FDED84B71952F741ABB3FC20E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Función </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Enviar archivo </td> 
   <td colname="col2"> <p>Envíe un proyecto de Analysis Workspace por correo electrónico o programe su entrega. Consulte <a href="/help/analyze/analysis-workspace/curate-share/t-schedule-report.md"  >Enviar archivo: programar un proyecto para su entrega</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Descargar archivo PDF </td> 
   <td colname="col2"> <p>En el menú Acción, puede descargar un proyecto de Espacio de trabajo de Análisis en formato PDF (similar a la descarga en formato CSV). </p> </td> 
  </tr> 
 </tbody> 
</table>

## Enero de 2016

Nuevas funciones lanzadas el 21 de enero de 2016.

* [Deshacer acciones](/help/analyze/analysis-workspace/new-features-in-analysis-workspace.md#section_12890C393D5E4FC8A3CF050318BD8482)
* [Vincular a este proyecto](/help/analyze/analysis-workspace/new-features-in-analysis-workspace.md#section_453E70F7409F4501B8E976A0D18C9A46)
* [Visualizaciones de gráficos de viñetas, diagramas de dispersión y gráficos de rectángulos](/help/analyze/analysis-workspace/new-features-in-analysis-workspace.md#section_B19EA50EBF5546E99D3A142827153FD6)
* [“Guardar como” para segmentos, métricas y fechas](/help/analyze/analysis-workspace/new-features-in-analysis-workspace.md#section_04C8B10A0751453AAE5F1BC35938C6CE)
* [Botón Agregar nuevo segmento](/help/analyze/analysis-workspace/new-features-in-analysis-workspace.md#section_85CC88C02C79456EA2B41F2BFBB64FC4)
* [Formato condicional](/help/analyze/analysis-workspace/new-features-in-analysis-workspace.md#section_5775B505D83041408B8C3EAEC5D7C32B)
* [Vista previa de dimensión](/help/analyze/analysis-workspace/new-features-in-analysis-workspace.md#section_F519EBF889B244E8B25BB6BA2833325A)
* [Leyenda visible](/help/analyze/analysis-workspace/new-features-in-analysis-workspace.md#section_28D10D86CAE343AB838808C1DD2E7983)
* [Eje Y delimitador a cero](/help/analyze/analysis-workspace/new-features-in-analysis-workspace.md#section_83DF5DE79EF04F9F8DCB3154F5E799B3)
* [Nombre del proyecto en el título de la ficha](/help/analyze/analysis-workspace/new-features-in-analysis-workspace.md#section_497C61A030984BCCA2CEA553312C3226)
* [Transferir propiedad del proyecto](/help/analyze/analysis-workspace/new-features-in-analysis-workspace.md#section_989C2CCB80B5408EB85E6B12C8D943E3)


## Deshacer acciones {#section_12890C393D5E4FC8A3CF050318BD8482}

Ahora puede deshacer la mayoría de las acciones que realiza en Analysis Workspace.

To undo, click **[!UICONTROL Undo]** from the action menu.

![](assets/undo.png)

También puede utilizar [accesos directos de teclado](/help/analyze/analysis-workspace/build-workspace-project/fa-shortcut-keys.md) estándar de Windows y Mac (ctrl o cmd + z) para Deshacer.

*`Undo`* es particularmente útil para deshacer desgloses en la tabla.

Acciones que *`not`* no se pueden deshacer:

* Changing the configuration of a [!UICONTROL Cohort Table] (such as dragging metrics, changing values). Sin embargo, puede hacer clic **[!UICONTROL Undo]** después de hacer clic en **[!UICONTROL Run]**.

* Cambiar el tamaño o mover paneles y subpaneles.

Acciones que borran el historial de deshacer:

* Guardando el proyecto.
* Cambiar el grupo de informes.

## Vincular a este proyecto {#section_453E70F7409F4501B8E976A0D18C9A46}

In a project, click **[!UICONTROL Link to This Project]** from the Actions menu to email a saved project&#39;s URL to other users. Los destinatarios administrativos pueden editar y guardar un proyecto compartido de esta forma. De lo contrario, estos proyectos son de solo lectura.

![](assets/link-to-this-project.png)

>[!NOTE] La opción para compartir vínculos de informes no está disponible si su empresa utiliza el inicio de sesión único (tanto el inicio de sesión único heredado como al iniciar sesión mediante Experience Cloud).

## Visualizaciones de gráficos de viñetas, diagramas de dispersión y gráficos de rectángulos {#section_B19EA50EBF5546E99D3A142827153FD6}

Las siguientes nuevas visualizaciones están disponibles en la versión de enero de 2016.

**Gráfico de viñetas**

Puede ver cómo se compara un valor que le interese con otros rangos de rendimiento (objetivos) o cómo se compara con ellos.

![](assets/bullet-image.png)

El gráfico de viñetas presenta una única medida principal (por ejemplo, los ingresos anuales actuales hasta la fecha), compara esa medida con una o más medidas para enriquecer su significado (por ejemplo, en comparación con los ingresos por destinatarios) y la muestra en el contexto de intervalos cualitativos de rendimiento, como altos, medios y bajos. You can specify goal ranges in [!UICONTROL Visualization Settings].

**Diagrama de dispersión**

![](assets/scatter.png)

Muestra las impresiones servidas y cuántos usuarios únicos han visto esas impresiones. El tamaño de cada punto de datos proporciona una indicación visual del número promedio de veces que un visor se ha expuesto a un anuncio. El tamaño y los datos varían según las dimensiones, los intervalos de fechas y los filtros seleccionados.

>[!NOTE] Una tabla asociada con un diagrama de dispersión que requiere al menos dos columnas. La primera columna define el eje X y la segunda columna define el eje Y. Si hay una tercera columna disponible, el gráfico de dispersión la utiliza para determinar el radio del punto. En otras palabras, las columnas *1*, *2* y *3* se asignan a *X*, *Y*** ypunto radius.

**Gráfico de rectángulos**

Muestra datos jerárquicos (estructurados en árbol) como un conjunto de rectángulos anidados. A cada rama del árbol se le da un rectángulo, que luego está en mosaico con rectángulos más pequeños que representan subramificaciones.

![](assets/treemap.png)

Cuando las dimensiones de color y tamaño están correlacionadas de alguna manera con la estructura de árbol, a menudo se pueden ver patrones que serían difíciles de identificar de otras formas, como si un determinado color fuera particularmente relevante. Una segunda ventaja de las trampas es que, mediante la construcción, hacen un uso eficiente del espacio.

## “Guardar como” para segmentos, métricas y fechas  {#section_04C8B10A0751453AAE5F1BC35938C6CE}

When editing an existing (saved) segment the Analysis Workspace Segment Builder, click **[!UICONTROL Save As]** to make a copy.

![](assets/segment-save-as.png)

The new segment displays in the [!UICONTROL Segments] group in the [!UICONTROL Components] panel.

*`Save As`* también está disponible para el [!UICONTROL Calculated Metric Builder] y [!UICONTROL Date Range Builder].

## Botón Agregar nuevo segmento {#section_85CC88C02C79456EA2B41F2BFBB64FC4}

The **[!UICONTROL Add New Segment]** button has been added to the location where you drag-and-drop segments onto a project.

![](assets/add-new-segment.png)

This enhancement is helpful if you prefer to directly create segments when working in a project, rather than using the [!UICONTROL Segment] panel to create segments.

## Formato condicional  {#section_5775B505D83041408B8C3EAEC5D7C32B}

En Configuración de columna, puede aplicar formato condicional a los datos de celda.

![](assets/conditional-formatting.png)

<table id="table_4285E6982FBD4B66AC95AAF6C5C7B347"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Formato condicional </td> 
   <td colname="col2"> <p> Aplica los colores siguientes a las celdas, según los valores de los datos: </p> 
    <ul id="ul_97E3AD5F6B41460C882D8B4EE0A8C77A"> 
     <li id="li_88874B4250224DE781C03E4A5931D6A2">Verde: valores altos </li> 
     <li id="li_B4863F967C7544D7AA2847696FB85525">Amarillo: valores intermedios </li> 
     <li id="li_5B06D7CD0C39437898DA55EA653A1124">Rojo: valores bajos </li> 
    </ul> <p>Sustituir una dimensión en la tabla restablece los límites de formato condicional. Cuando se sustituye una métrica se vuelven a calcular los límites de dicha columna (donde las métricas se encuentran en el eje X y las dimensiones se encuentran en el eje Y). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Generado automáticamente </td> 
   <td colname="col2"> <p>Genera automáticamente límites para el formato condicional. El límite superior es el valor más alto de esta columna. El límite inferior es el más bajo y el punto medio es la media de los límites superior e inferior. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Personalizado </td> 
   <td colname="col2"> <p>Puede asignar de forma manual los valores de los campos <span class="uicontrol">Superior</span>, <span class="uicontrol">Punto medio</span> y <span class="uicontrol">Límite inferior</span> para el formato condicional. Esto le proporciona la flexibilidad para determinar si el valor de una columna es bueno, medio o malo. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Vista previa de dimensión  {#section_F519EBF889B244E8B25BB6BA2833325A}

In the [!UICONTROL Dimensions] component panel, you can hover over the information icon next to a dimension and see a top-five preview.

![](assets/dimension-preview.png)

## Leyenda visible  {#section_28D10D86CAE343AB838808C1DD2E7983}

En [!UICONTROL Visualization Settings] la **[!UICONTROL Legend Visible]** opción se muestra u oculta la leyenda de una visualización.

![](assets/legend-visible.png)

## Eje Y delimitador a cero {#section_83DF5DE79EF04F9F8DCB3154F5E799B3}

Dependiendo de los números de los gráficos de línea y de área, la parte inferior del eje Y podría no ser cero. Al habilitar **[!UICONTROL Anchor Y Axis at Zero]** en [!UICONTROL Visualization Settings] fuerza el eje Y a cero, para una vista más precisa de las tendencias. Los siguientes ejemplos muestran cómo cambia un gráfico de ingresos con esta configuración habilitada y deshabilitada:

**Eje Y delimitador a cero desactivado**

![](assets/anchor_Y_axis_off.png)

**Eje Y delimitador a cero activado**

![](assets/anchor_Y_axis.png)

## Nombre del proyecto en el título de la ficha  {#section_497C61A030984BCCA2CEA553312C3226}

Al guardar un proyecto, el título de la ficha del navegador se mostrará como “`<Project Name>` - Analysis Workspace”. Esta mejora resulta útil si abre varios proyectos en varias fichas del navegador.

## Transferir propiedad del proyecto  {#section_989C2CCB80B5408EB85E6B12C8D943E3}

Los administradores pueden transferir proyectos de [!UICONTROL Analysis Workspace] de un usuario a otro.

Vaya a **[!UICONTROL Admin]** > **[!UICONTROL User Management]** > **[!UICONTROL Transfer]** para transferir proyectos.

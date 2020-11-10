---
description: Compara la terminología y tareas de los Ad Hoc Analysis con las de Analysis Workspace.
title: Analysis Workspace comparado con los Ad Hoc Analysis
uuid: e4b3e40f-2b08-49a0-95f1-384d85c1640d
translation-type: ht
source-git-commit: 56ca9fa36db9d7dd126808280ba17f29f4b787d9
workflow-type: ht
source-wordcount: '1002'
ht-degree: 100%

---


# Analysis Workspace comparado con los Ad Hoc Analysis

>[!IMPORTANT]
>
>Adobe Ad Hoc Analysis quedará obsoleto el 1 de marzo de 2021. [Más información](https://adobe.ly/discoverworkspace)

Compara la terminología y tareas de los Ad Hoc Analysis con las de Analysis Workspace.

Analysis Workspace aporta mucha de la funcionalidad de los Ad Hoc Analysis al flujo de trabajo del explorador. Aunque parte de la terminología y la funcionalidad se comparten entre ambos productos, en Analysis Workspace se han introducido nuevos términos y enfoques de análisis.

[Aquí](https://experienceleague.adobe.com/docs/analytics/admin/admin-overview/analytics-product-comparison.html?lang=es-ES) tiene una comparativa técnica de las características principales y los requisitos del sistema de ambos productos.

## Comparación de terminología clave {#section_6109406B83B043A18E46D38F130B1D2E}

| Ad Hoc Analysis | Analysis Workspace |
|--- |--- |
| Proyecto | Workspace o proyecto |
| Workspace | Panel |
| Información general de la tienda de aplicaciones | Tabla improvisada |
| Gráfico/diagrama | Visualización |
| Jerarquía: Proyecto > Workspace > Informes | Jerarquía: Proyecto > Paneles > Tablas |
| Plantillas de informes Jerárquicas, De tendencia, Totales | Visualización de tabla improvisada |
| Plantilla de flujo | Visualización de flujo |
| Abandono | Visualización de visitas en el orden previsto |

## Comparación de tareas clave {#section_F31446F1DFA742D794A30D713E223440}

<table id="table_90D4461F04F34D70844C5E3FBB0BBE44"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Ad Hoc Analysis Tarea </th> 
   <th colname="col2" class="entry"> Tarea de Analysis Workspace </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Añadir dimensiones y segmentos a las columnas de métricas </p> </td> 
   <td colname="col2"> <p>Puede añadir elementos dimensionales o segmentos como encabezados de columna para crear fácilmente vistas comparativas de métricas. <a href="https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/metrics/adding-dimensions-and-metrics-to-your-project-in-analysis-workspace.html?lang=es-ES"  > Vídeo: Añadir dimensiones y métricas al proyecto en Analysis Workspace</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Aplicar segmentos </p> </td> 
   <td colname="col2"> <p>Los segmentos están disponibles en el menú de componente Segmento y pueden aplicarse en tres lugares en Analysis Workspace: </p> 
    <ol id="ol_800D81FE2C84459B94B085C51E140330"> 
     <li id="li_F2E050902F9A4831BBA57F466E07DEAE">En el <b>nivel del panel</b>, que se aplica a muchas visualizaciones del panel. Esto es similar a aplicar un segmento a un Workspace en análisis específicos. </li> 
     <li id="li_2D88E43E0161485C95B08DC3C593EFD9">Como <b>filas en una tabla</b>. Esto es similar a añadir segmentos a la sección “Filas/Desgloses” del generador de tablas de análisis específicos. </li> 
     <li id="li_102E1A1DAA9247C08FC46C5AB3D78113">Como <b>columnas de una tabla</b>. Esto es similar a añadir segmentos a la sección “Columnas” del generador de tablas de Ad Hoc Analysis, o a aplicar un segmento en el nivel de informes en Ad Hoc Analysis. </li> 
    </ol> <p><a href="https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/applying-segments/applying-segments-to-your-analysis-workspace-project.html?lang=es-ES"  > Vídeo: Uso de segmentos en Workspace</a> </p> <p><a href="https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/using-panels/panel-level-segments.html?lang=es-ES"  > Vídeo: Aplicación de segmentos a un panel</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Crear segmentos temporales (“específicos”) </p> </td> 
   <td colname="col2"> <p>Puede <a href="/help/analyze/analysis-workspace/components/t-freeform-project-segment.md"  >crear segmentos instantáneos temporales (“específicos”)</a> en Analysis Workspace arrastrando elementos de dimensión a la zona de colocación de segmentos en la parte superior del panel. Además, se pueden añadir filtros desplegables en la zona de colocación del panel para crear muchos segmentos temporales a la vez, lo que permite interacciones de proyecto controladas. </p> <p><a href="https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/applying-segments/ad-hoc-temporary-segments.html?lang=es-ES"  > Vídeo: Segmentos ad hoc en Analysis Workspace</a> </p> <p><a href="https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/applying-segments/using-drop-down-filters.html?lang=es-ES"  > Vídeo: Filtros desplegables en Analysis Workspace</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Elegir intervalos y granularidades de fechas </p> </td> 
   <td colname="col2"> <p>Los intervalos y granularidades de fechas están disponibles en el menú de componente Tiempo y se pueden utilizar de tres maneras: </p> 
    <ol id="ol_8B57C8A840694A879B22B809C58E7482"> 
     <li id="li_58FAE6A87B494A5C9007CD35BB101608">Pueden aplicarse intervalos de fechas a las columnas/filas y anular el intervalo de fechas seleccionado en el panel. Esto es similar a los intervalos de fechas en el nivel de informes. </li> 
     <li id="li_85BB89EFF9C8466A992815BB7804EA37">“Aplicar” aplica un intervalo de fechas a todas las visualizaciones dentro de un panel. Esto es similar al intervalo de fechas de un Workspace en los Ad Hoc Analysis. </li> 
     <li id="li_BC18564A8FBB48F4A522BCAC60838759">“Aplicar a todos los paneles” aplica un intervalo de fechas a todos los paneles de un proyecto de Workspace. Esto es similar al intervalo de fechas de un proyecto en los Ad Hoc Analysis. </li> 
    </ol> <p><a href="https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/calendar-and-date-ranges/using-dates-in-analysis-workspace.html?lang=es-ES"  > Vídeo: Trabajo con fechas en Analysis Workspace</a> </p> <p><a href="https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/calendar-and-date-ranges/creating-custom-date-ranges-in-analysis-workspace.html?lang=es-ES"  > Vídeo: Intervalos de fechas personalizados</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Utilizar visitas en el orden previsto y embudos de conversión </p> </td> 
   <td colname="col2"> <p>Las <a href="/help/analyze/analysis-workspace/visualizations/fallout/fallout-flow.md"  >visualizaciones de visitas en el orden previsto</a> están disponibles en Analysis Workspace en el menú de componente Visualización. De forma similar a los Ad Hoc Analysis: </p> 
    <ol id="ol_625FF45AED4E403DBEE1A906282E8531"> 
     <li id="li_7B6C5F2682774641B82D2021786AE5C4">Las visitas en el orden previsto pueden abarcar una visita o visitante, y puede incluirse “Todas las visitas” de manera opcional. Las visitas en el orden previsto se pueden clasificar rápidamente en tendencias mediante el menú que se abre al hacer clic con el botón derecho. </li> 
     <li id="li_CFBDDAB8E96A445DB0624640AEB25994">Los elementos dimensionales pueden conectarse mediante un operador OR (como en los grupos) y el embudo puede utilizar eventos. </li> 
     <li id="li_6638E6A62C744A27B2C066E5F9EC62C0">Los pasos siguientes de las visitas en el orden imprevisto y en el orden previsto también se pueden representar mediante el menú que se abre al hacer clic con el botón derecho. </li> 
    </ol> <p>Además, las visitas en el orden previsto permiten en Analysis Workspace el uso de <a href="/help/analyze/analysis-workspace/visualizations/fallout/configuring-interdimensional-fallout.md"  > dimensiones mixtas</a> dentro de los pasos, una mejora respecto a los Ad Hoc Analysis. Las dimensiones mixtas dentro de los pasos se gestionan mediante un operador AND. </p> <p><a href="https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/analyzing-customer-journeys/fallout-visualization.html?lang=es-ES"  > Vídeo: Visualización de abandonos</a> </p> <p><a href="https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/analyzing-customer-journeys/multi-dimensional-fallout.html?lang=es-ES"  > Vídeo: Uso de múltiples dimensiones en Visitas en el orden previsto</a> </p> <p><a href="https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/analyzing-customer-journeys/comparing-segments-in-fallout.html?lang=es-ES"  > Vídeo: Comparación de segmentos en Visitas en el orden previsto</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Examinar el flujo (rutas) </p> </td> 
   <td colname="col2"> <p>Las <a href="/help/analyze/analysis-workspace/visualizations/c-flow/flow.md"  >visualizaciones de flujo</a> están disponibles en Analysis Workspace en el menú de componente Visualización. De forma similar a los Ad Hoc Analysis: </p> 
    <ul id="ul_42D259310823496499F7D1474E1639AF"> 
     <li id="li_5DE6980EF66A49E58B8946A0422BC02C">Un flujo puede abarcar una visita o visitante. </li> 
     <li id="li_70A692266D32416BA3D70C1F8999F837">Las estadísticas clave se muestran como porcentajes de vistas de ruta. </li> 
    </ul> <p>Además, Flujo permite el uso de <a href="/help/analyze/analysis-workspace/visualizations/c-flow/multi-dimensional-flow.md"  > dimensiones mixtas</a> y la capacidad de hacer clic con el botón derecho y crear un segmento, una mejora sobre los Ad Hoc Analysis. </p> <p>Actualmente, Flujo en Analysis Workspace <b>no</b> permite a los usuarios elegir un evento de éxito. </li> 
    </ul> <p><a href="https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/analyzing-customer-journeys/flow-visualization.html?lang=es-ES"  > Vídeo: Descripción general de la visualización de flujo</a> </p> <p><a href="https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/analyzing-customer-journeys/text-wrapping-and-multi-dimensional-flow.html?lang=es-ES"  > Vídeo: Flujo multidimensional</a> </p> <p><a href="https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/analyzing-customer-journeys/expanding-on-flow-visualization.html?lang=es-ES"  > Vídeo: Creación de segmentos a partir de flujos</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Realizar desgloses infinitos </p> </td> 
   <td colname="col2"> <p>Analysis Workspace le permite profundizar infinitos niveles dentro del explorador. Se pueden mezclar segmentos y dimensiones. Es posible desglosar al mismo tiempo varios elementos de dimensión haciendo una selección múltiple y, a continuación, arrastrando a una dimensión desglosada. </p> <p><a href="https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/building-freeform-tables/dimension-breakdown-by-position.html?lang=es-ES"  > Vídeo: Desgloses mejorados</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Realizar rápidamente la tendencia de datos </p> </td> 
   <td colname="col2"> <p>Se pueden visualizar datos rápidamente haciendo clic en el icono de gráfico dentro de la fila del informe. Además, estas visualizaciones rápidas se vincularán a la tabla de origen, de modo que puede hacer clic de un valor de la tabla al siguiente y ver cómo el gráfico se actualiza automáticamente. </p> <p><a href="https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/visualizations/dimension-graph-live-linking.html?lang=es-ES"  > Vídeo: Vinculación entre dimensiones y gráficos</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Seleccionar grupos de informes </p> </td> 
   <td colname="col2"> <p>Se pueden añadir varios grupos de informes a un solo proyecto en Analysis Workspace.  </p> <p><a href="https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/using-panels/multiple-report-suites-in-analysis-workspace.html?lang=es-ES"  > Vídeo: Varios grupos de informes en Workspace</a> </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Attribution IQ </p> </td> 
   <td colname="col2"> <p><a href="/help/analyze/analysis-workspace/attribution/overview.md"  > Attribution IQ</a> en Analysis Workspace permite agregar muchos tipos nuevos de modelos de atribución a las Tablas improvisadas, Visualizaciones y Métricas calculadas. Incluye más de 10 modelos algorítmicos y basados en reglas. </p>  <p><a href="https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/attribution-iq/using-attribution-iq-in-freeform-tables.html?lang=es-ES"  > Vídeo: Attribution IQ en tablas de forma libre</a> </p> </td> 
  </tr>  
 </tbody> 
</table>


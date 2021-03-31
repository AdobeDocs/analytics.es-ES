---
description: Utilizar alertas en Reports & Analytics.
subtopic: Alerts
title: Alertas
uuid: e1333a9b-eba0-45b7-b7e6-46e06190db64
feature: Alertas
role: Profesional empresarial, administrador
translation-type: tm+mt
source-git-commit: 894ee7a8f761f7aa2590e06708be82e7ecfa3f6d
workflow-type: tm+mt
source-wordcount: '889'
ht-degree: 99%

---


# Alertas

## Alertas {#concept_8AB25AF6FB52478DB98C1BA4577A2E16}

Como el nuevo sistema de alertas, las alertas inteligentes de Adobe Analytics le permiten crear y gestionar alertas, junto con la previsualización de alerta y la contribución de reglas. Puede

* Generar alertas en función de anomalías (umbrales del 90 %, 95 % o 99 %; cambio de %; por encima/por debajo).
* Obtener una vista previa de la frecuencia con la que se activará una alerta.
* Enviar alertas por correo electrónico o SMS con vínculos a proyectos de Analysis Workspace autogenerados.
* Crear alertas “apiladas” que capturan varias métricas en una sola alerta.

Puede acceder a este nuevo sistema de Alertas en **[!UICONTROL Más]** > **[!UICONTROL Alertas]** en cualquier análisis de Reports &amp; Analytics.

Para obtener más información, consulte la documentación de Analysis Workspace sobre las [Alertas inteligentes](https://docs.adobe.com/content/help/es-ES/analytics/analyze/analysis-workspace/virtual-analyst/intelligent-alerts/intellligent-alerts.html).

## Añadir una alerta {#task_51187E8BF19544DDA9EF2057E6F11D35}

Instrucciones para añadir una alerta en Adobe Analytics.

<!-- 

t_add_an_alert.xml

 -->

Vaya al nuevo Generador de alertas en el menú **[!UICONTROL Analytics]** > **[!UICONTROL Componentes]**. Sin embargo, todavía puede acceder a él desde informes en Reports &amp; Analytics:

1. En Reports &amp; Analytics, abra el informe en el que desee establecer una alerta.
1. Haga clic en **[!UICONTROL Más]** > **[!UICONTROL Agregar alerta]**.
1. De este modo, se le dirigirá al [nuevo Generador de alertas](https://docs.adobe.com/content/help/es-ES/analytics/analyze/analysis-workspace/virtual-analyst/intelligent-alerts/alert-builder.html).

## Visualización o edición de alertas existentes {#task_2ADF2A05EB784B8BBAFE293AC8243C46}

Contexto de tarea

1. Vaya a **[!UICONTROL Analytics]** > **[!UICONTROL Componentes]** > **[!UICONTROL Alertas]**. Le llevará al nuevo [Administrador de alertas](https://docs.adobe.com/content/help/es-ES/analytics/analyze/analysis-workspace/virtual-analyst/intelligent-alerts/alert-manager.html).

## Migración de alertas heredadas {#concept_7E8179F5EF6E4913B0CE5CF4FF186911}

El nuevo Administrador de alertas, cuyo lanzamiento se producirá en otoño de 2016 (como parte de Analysis Workspace), no incluirá varias de las funciones existentes en las alertas de Analytics. La tabla siguiente muestra una lista de las funciones de alerta en desuso que migrarán al nuevo Administrador de alertas de forma distinta.

<!-- 

deprecated_alerts.xml

 -->

<table id="table_9307013B16AC4AC7BFC6F4C440FCFDE4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Función de alertas heredadas </th> 
   <th colname="col2" class="entry"> Descripción </th> 
   <th colname="col3" class="entry"> ¿Obsoleto o migrado? </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Totales (todos los elementos) </p> </td> 
   <td colname="col2"> <p>Crear alertas de todos los elementos de un informe de dimensión. </p> </td> 
   <td colname="col3"> <p>En algunos casos, tanto si crea una alerta de todos los elementos de un informe de dimensión como si establece una alerta únicamente de la métrica agregada en sí (no aplicable a una dimensión), se produce el mismo resultado. Por ejemplo, digamos que crea una alerta mensual de Todos los elementos en la métrica "Ingresos". Podría obtener el mismo resultado simplemente ejecutando el informe Ingresos y configurando una alerta mensual en él. </p> <p>En esta situación, la alerta Totales (Todos los elementos) heredada ya no estará disponible y se migrará a la versión posterior más sencilla. </p> <p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Primeros 1000 elementos </p> <p> </p> </td> 
   <td colname="col2"> <p>Crear alertas para los primeros 1000 elementos de un informe. </p> </td> 
   <td colname="col3"> <p>Ya no está disponible en el nuevo Administrador de alertas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Alertas de visitantes únicos basadas en el tiempo (Diario, Semanal, Mensual, etc. Visitantes únicos) </p> <p> </p> </td> 
   <td colname="col2"> <p>Cree alertas para los informes de visitantes únicos por horas, diarios, semanales y mensuales. </p> </td> 
   <td colname="col3"> <p>En el nuevo Administrador de alertas, ya no serán compatibles algunas de las alertas de Visitantes únicos basadas en el tiempo. Por ejemplo, donde anteriormente podía establecer una alerta semanal para los Visitantes únicos diarios, ahora puede establecer una alerta diaria, semanal, etc. sobre la métrica Visitantes únicos en adelante. (Analysis Workspace admite la métrica Visitantes únicos, pero no las métricas de Visitantes únicos métricas de visitantes únicos). </p> <p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Buscar </p> </td> 
   <td colname="col2"> <p>Crear alertas para un informe de dimensiones con una búsqueda aplicada. Únicamente es aplicable a "Totales" ("Todos los elementos") o a los "Primeros 1000 elementos". </p> <p> </p> </td> 
   <td colname="col3"> <p>Ya no está disponible en el nuevo Administrador de alertas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Informes específicos de Reports &amp; Analytics </p> </td> 
   <td colname="col2"> <p>Crear alertas para diversos informes que existen en Reports &amp; Analytics y que no se corresponden con un informe de Analysis Workspace, como 
     <ul id="ul_9A690970A5AE4ED39E664DF23EF3164F"> 
      <li id="li_E2F44EDBA1D945CEBAC4802ED714E7A1">JavaScript </li> 
      <li id="li_B847C6A988854F76824F099681705EC9">Longitud de ruta </li> 
      <li id="li_4AF656460BC748E8802FAF258D01842F">Bots </li> 
      <li id="li_A300D2803B244774839BEC23D3EB533A">Zonas horarias </li> 
      <li id="li_7A0B4CF92F4D47238B7B329EEC213322">Dominios de nivel superior </li> 
     </ul> </p> <p> </p> </td> 
   <td colname="col3"> <p>Ya no está disponible en el nuevo Administrador de alertas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Alertas con una ranura ASI como el grupo de informes </p> </td> 
   <td colname="col2"> <p>Ya no puede crear o editar ranuras ASI y no estarán disponibles para su uso en Analysis Workspace. Por tanto, ya no son compatibles con las nuevas alertas. </p> <p> </p> </td> 
   <td colname="col3"> <p>No está disponible en el nuevo Administrador de alertas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Alertas con métricas de participación </p> </td> 
   <td colname="col2"> <p> Las <a href="https://docs.adobe.com/content/help/es-ES/analytics/analyze/analysis-workspace/attribution/overview.html"  >métricas de participación</a> están disponibles en Reports &amp; Analytics pero actualmente no están disponibles en el nuevo sistema de alertas de Analysis Workspace. </p> <p> </p> </td> 
   <td colname="col3"> <p>No está disponible en el nuevo Administrador de alertas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Alertas mensuales para grupos de informes de calendario personalizados </p> </td> 
   <td colname="col2"> <p>Esto solo afecta a los clientes con alertas configuradas para grupos de informes que tengan <a href="https://docs.adobe.com/content/help/es-ES/analytics/analyze/report-builder/data-requests/date-ranges/custom-calendar.html"  > fechas de inicio mensuales personalizadas </a> (Federación Nacional Minorista de EE. UU./NRF y tipos de calendario personalizados). </p> <p>No afecta a las alertas de los grupos de informes del calendario gregoriano ni del gregoriano modificado. Anteriormente, estas alertas se enviaban el primer día del mes gregoriano (por ejemplo, el 1 de enero, el 1 de febrero, etc.). Esto no funcionará con la nueva función de detección de anomalías de alertas, la cual tiene en cuenta los datos del mes anterior para la detección de anomalías. En el futuro, añadiremos la compatibilidad con nuestro sistema de programación para calendarios personalizados, de modo que tanto las Alertas como los Proyectos programados podrán programarse para enviarse el primer día del mes del calendario personalizado en lugar de simplemente el primer día del mes gregoriano. </p> <p> </p> </td> 
   <td colname="col3"> <p>Todavía no está disponible en el nuevo Administrador de alertas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Alertas que no se han ejecutado desde septiembre de 2015. </p> </td> 
   <td colname="col2"> <p>Existen diversos motivos por los cuales las alertas no se hayan ejecutado desde septiembre de 2015, incluidos: </p> 
    <ul id="ul_15812938A2454537AF6ADDB039DE16BC"> 
     <li id="li_D079A819CEE04F609AF18C09EEE83F0D">Ha hecho clic en "Deshabilitar" en la alerta del Administrador de alertas. </li> 
     <li id="li_E23D01FA0B1341AD8BC1DDD16FB1366F">La alerta incurre en errores y nunca se completa correctamente. </li> 
    </ul> <p> </p> </td> 
   <td colname="col3"> Estas alertas no se migrarán al nuevo sistema. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Alertas que se han marcado como "deshabilitadas" </td> 
   <td colname="col2"> Actualmente no hay forma de deshabilitar/volver a habilitar las alertas en la nueva interfaz de usuario, pero hay planes para añadir esta funcionalidad. <p> </p> </td> 
   <td colname="col3"> Estas alertas no se migrarán al nuevo sistema. </td> 
  </tr> 
 </tbody> 
</table>


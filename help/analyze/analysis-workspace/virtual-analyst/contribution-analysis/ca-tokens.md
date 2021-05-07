---
description: Utilice el análisis de contribución para identificar anomalías estadísticas y correlaciones en los datos.
title: Resumen de los análisis de contribución
uuid: 2bd295b0-c5ce-4443-86af-024efd20c021
feature: Herramientas de IA
role: Business Practitioner, Administrator
exl-id: 86fc8696-90a8-4626-b1c7-6413d3f8a648
translation-type: tm+mt
source-git-commit: 6588896cd47e15127b1b1d0a2d229e0ed2dbaaaa
workflow-type: tm+mt
source-wordcount: '1164'
ht-degree: 91%

---

# Resumen de los análisis de contribución

Análisis de contribución descubre patrones ocultos en sus datos para explicar las anomalías estadísticas e identificar correlaciones tras acciones de cliente inesperadas, valores que sobrepasan el límite y picos o caídas repentinos de métricas seleccionadas en segmentos de audiencia convergentes.

Ha ocurrido algo. ¿Por qué? Su informe Detección de anomalías muestra un pico inusual en los pedidos y desea saber por qué. ¿Qué ha pasado fuera de lo normal? ¿Quién está respondiendo a qué campaña o referencia? ¿Algo se ha hecho viral? ¿Qué factores específicos han contribuido a esta anomalía? Y quizá lo más importante: ¿cómo puedo capturar información importante acerca de mi cliente y repetir este comportamiento? (O, si hay una caída en una métrica o una subida en una métrica negativa, ¿cómo puedo evitarla en el futuro?)

Análisis de contribución le ayuda a evaluar los datos inmediatamente para saber por qué se ha producido una anomalía. Desglosa las contribuciones en anomalías en cuestión de segundos, algo que tardaba semanas, proporcionando patrones para segmentos de audiencia y ayudando a desarrollar un diálogo para las interacciones con el cliente. Puede utilizar el análisis de contribución de forma estratégica para identificar y capturar asociaciones significativas y desarrollar nuevos segmentos de audiencia, o utilizarlo de forma táctica para identificar actividades que sobrepasen el límite o actividades fraudulentas que activen una alerta.

[Detección de anomalías](/help/analyze/analysis-workspace/virtual-analyst/c-anomaly-detection/anomaly-detection.md) identifica picos de datos y caídas estadísticas pronunciadas basándose en métricas y segmentos de audiencia concretos. Establece una norma histórica basada en un período de prueba y, a continuación, representa desplazamientos extremos correlacionados con eventos específicos. Puede realizar un informe sobre un aumento abrupto en una métrica positiva de pedidos o un aumento en una métrica negativa de devoluciones, o caídas en ambas, capturando puntos de datos estadísticamente relevantes para ser evaluados por un análisis de contribución. Una vez identificada una anomalía estadística, el análisis de contribución le permite desglosar y evaluar variables de marketing y de campaña relevantes en todos los puntos de datos anómalos. Ejecuta algoritmos avanzados y procesos de aprendizaje automático para evaluar asociaciones que hayan contribuido a un pico o caída significativos. Estos cálculos aparecen en visualizaciones interactivas diseñadas para ofrecerle distintas perspectivas que le ayuden a entender por qué se ha producido algún evento y qué hacer al respecto.

El análisis de contribución le ayuda a desarrollar un diálogo para describir por qué se ha producido una anomalía y cómo responder a ella, capturando métricas relevantes e identificando puntos ocultos que le darán una razón general para las interacciones de la audiencia y las tendencias en los intereses de los clientes. Algunas veces las anomalías son fáciles de ver y corregir, como un pedido aislado de 2000 kayaks. Por el contrario, otras veces es difícil, como identificar una tendencia emergente a lo largo de un período de tiempo en una región que solo reacciona a una determinada campaña con objetivo. Unir elementos de contribución en métricas para varias dimensiones y sus asociaciones le proporciona una idea general de las interacciones de su audiencia y le ayuda a proporcionar contexto a los puntos de datos anómalos.

Estos son algunos casos de uso:

* Identificar el potencial de remarketing mediante la supervisión de cambios en la demanda de productos.
* Mejorar la experiencia del cliente reaccionando a determinados intereses de la audiencia.
* Identificar pedidos fraudulentos de forma temprana como informe sobre ámbitos que sobrepasan el límite.
* Protegerse del espionaje empresarial identificando usos y descargas masivas.
* Supervisar operaciones como, por ejemplo, los informes sobre la falta de etiquetas de javascript.

Después del análisis completo de una anomalía, se genera un resumen de contribución para los elementos principales ordenados según el número total de ocurrencias y el porcentaje del elemento de los valores de contribución. Una puntuación de contribución normalizada le permite comprar, contrastar y asociar fácilmente otros elementos de dimensión significativos.

## Tokens de Análisis de contribución: descripción general {#section_3EF8D2BBCE6E4C309D753BCF04A453D0}

>[!IMPORTANT]
>
>La funcionalidad Análisis de contribución se ha eliminado del conjunto de funciones de Reports &amp; Analytics y ahora solo está disponible en Analysis Workspace.

Los clientes que tengan algún derecho de Análisis de contribución pueden ejecutar análisis de contribución completos tantas veces al mes como deseen en Analysis Workspace. Quedan **excluidos** los clientes de producto específico (SiteCatalyst 15), los de Analytics Foundation y los de Analytics Select, que en ningún caso tienen acceso a la función Análisis de contribución.

El número de ejecuciones por empresa está limitado por los tokens mensuales, que se conceden según el producto de Adobe Analytics que la empresa haya adquirido. También se puede restringir el acceso a Análisis de contribución para evitar un uso indebido de los tokens.

## Preguntas frecuentes {#section_11D0431AD2014B96AB9561CA66A367CE}

| Pregunta | Respuesta |
| --- | --- |
| ¿Por qué Adobe ha introducido los tokens? | El Análisis de contribución es una de las funcionalidades más aclamadas de Adobe Analytics. Al permitirle realizar un número pequeño de ejecuciones “completas” al mes (en lugar de ofrecerle únicamente 3 dimensiones para algunos productos de Analytics), podrá ver mejor las ventajas que aporta un análisis de contribución completo e ilimitado. |
| ¿Cómo funciona la creación de tokens en Análisis de contribución? ¿Hay que pagar un token para cargar un proyecto con un análisis de contribución existente o solo cuando se ejecuta uno nuevo? | Cada empresa (y no cada usuario) recibe un número determinado de tokens al mes, lo cual le permite ejecutar un análisis de contribución “completo” en Analysis Workspace.  Siempre que se genera un nuevo análisis de contribución, hay que pagar un token. Cargar proyectos con análisis de contribución previamente ejecutados no cuesta ningún token. |
| ¿Se aplican tokens al análisis de contribución en Reports &amp; Analytics? | No. El análisis de contribución ya no se ofrece en Reports &amp; Analytics a partir de abril de 2018. |
| Si mi empresa se queda sin tokens y deseamos ejecutar más análisis de contribución, ¿qué podemos hacer? | Puede actualizar a otro producto de Adobe Analytics, por ejemplo, de Standard (2 tokens/mes) a Ultimate (20 tokens/mes). No consiste simplemente en comprar más tokens: es preciso actualizar el tipo de paquete existente. |
| ¿Cómo se restringe el acceso a Análisis de contribución? | De forma predeterminada, solo los administradores tienen acceso para ejecutar los análisis de contribución. Sin embargo, los administradores pueden conceder acceso a otros usuarios creando un grupo de permisos en [Adobe Admin Console](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/home.html). Conceda permiso para usar los análisis de contribución solamente a los usuarios que tengan una razón legítima para usarlos y que sepa que no harán un uso indebido de este permiso. El permiso se denomina [!UICONTROL Análisis de contribución] en [!UICONTROL Herramientas del grupo de informes]. [Más información](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/permissions/report-suite-tools.html) |
| ¿Cómo puedo saber de cuántos tokens al mes dispone mi empresa y qué cantidad hemos usado en el mes actual? | Vaya a [!UICONTROL Administración] > [!UICONTROL Todos los administradores] >[!UICONTROL Inicio Configuración de la empresa] >[!UICONTROL Ver niveles de acceso de las funciones]. Buscar en<ul><li>Análisis de contribución: número de tokens de uso mensual</li><li>Análisis de contribución: número de tokens de uso que se han utilizado este mes</li></ul> |

## Derechos de Detección de anomalías y Análisis de contribución {#section_9278D58F21A840AA9B1ED1BD07A1EF0A}

A continuación encontrará una lista detallada de los derechos de Detección de anomalías y Análisis de contribución en Analysis Workspace.

>[!IMPORTANT]
>
>La detección de anomalías y el análisis de contribución se han eliminado del conjunto de funciones de Reports &amp; Analytics, y ahora solo están disponibles en Analysis Workspace. Tenga en cuenta que los clientes de Adobe Analytics Select y Adobe Analytics Foundation solo tienen acceso a la Detección de anomalías de “granularidad diaria” en Workspace.

<table id="table_5C9B7E4AE82640B5A913519E576889B5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Derecho de Adobe Analytics </th> 
   <th colname="col2" class="entry"> Detección de anomalías </th> 
   <th colname="col3" class="entry"> Análisis de contribución </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Foundation </p> </td> 
   <td colname="col2"> <p>Solo “granularidad diaria” </p> </td> 
   <td colname="col3" colsep="1"> <p>Sin tokens </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><a href="https://www.adobe.com/es/data-analytics-cloud/analytics/select.html?promoid=B4XQ3X7G&amp;mv=other"  >Select</a> </p> </td> 
   <td colname="col2"> <p>Solo “granularidad diaria” </p> </td> 
   <td colname="col3"> <p>Sin tokens </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><a href="https://www.adobe.com/es/data-analytics-cloud/analytics/prime.html?promoid=91BF51TR&amp;mv=other"  >Prime</a> </p> </td> 
   <td colname="col2"> <p>Sí </p> </td> 
   <td colname="col3"> <p>10 tokens al mes </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><a href="https://www.adobe.com/es/data-analytics-cloud/analytics/ultimate.html?promoid=8N4B5F1V&amp;mv=other"  > Ultimate</a> </p> </td> 
   <td colname="col2"> <p>Sí </p> </td> 
   <td colname="col3"> <p>20 tokens al mes </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>+Predictive Workbench </p> </td> 
   <td colname="col2"> <p>Sí </p> </td> 
   <td colname="col3"> <p>Tokens ilimitados </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Standard </p> 
    <ul id="ul_73D52020793B44868C9CE0F90893075D"> 
     <li id="li_21EE0871C87E43C8B781219B2BA0FA74">Adobe Analytics Core </li> 
     <li id="li_AB3593200F33439BAEE8FEB13CAE57F4">Adobe Analytics OD </li> 
     <li id="li_2B7D625519BC4A4CB598C95F15D3029B">Adobe Analytics: MA </li> 
    </ul> </td> 
   <td colname="col2"> <p>Sí </p> </td> 
   <td colname="col3"> <p>2 tokens al mes </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Premium (360, Attribution) </p> </td> 
   <td colname="col2"> <p>Sí </p> </td> 
   <td colname="col3"> <p>2 tokens al mes </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Premium (Complete, <a href="https://www.adobe.com/es/data-analytics-cloud/analytics/predictive-intelligence.html"  >Predictive Intelligence</a>) </p> </td> 
   <td colname="col2"> <p>Sí </p> </td> 
   <td colname="col3"> <p>Tokens ilimitados </p> </td> 
  </tr> 
 </tbody> 
</table>

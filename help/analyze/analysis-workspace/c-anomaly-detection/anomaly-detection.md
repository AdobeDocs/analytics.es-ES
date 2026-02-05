---
description: Obtenga información acerca de la detección de anomalías de datos en Analysis Workspace.
title: Información general de la detección de anomalías
feature: Anomaly Detection
role: User, Admin
exl-id: b1625206-c774-40ef-9d92-25ee8ff1478d
source-git-commit: fcc165536d77284e002cb2ba6b7856be1fdb3e14
workflow-type: ht
source-wordcount: '1292'
ht-degree: 100%

---

# Información general de la detección de anomalías

Puede ver y analizar las anomalías de datos en contexto, dentro de Analysis Workspace. El análisis de contribución funciona junto con la detección de anomalías para identificar qué ha contribuido a la anomalía.


>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Detección de anomalías](https://video.tv.adobe.com/v/25444?quality=12&learn=on){target="_blank"} para ver un vídeo de demostración.

>[!ENDSHADEBOX]

>[!IMPORTANT]
>
>Los clientes de Adobe Analytics Select y Adobe Analytics Foundation solo tienen acceso a la detección de anomalías de *granularidad diaria* en Workspace. Para obtener más información, consulte la información relativa a los [derechos de Detección de anomalías y Análisis de contribución](#anomaly-detection-and-contribution-analysis-entitlements).

## Detección de anomalías

La Detección de anomalías constituye un método estadístico para determinar el cambio experimentado en una métrica determinada respecto a los datos anteriores.

La detección de anomalías permite separar las “señales verdaderas” del “ruido” y así identificar los posibles factores que contribuyeron a hacer saltar estas señales o anomalías. En otras palabras, le permite identificar las fluctuaciones estadísticas que son importantes y las que no lo son. A continuación, podrá identificar la causa raíz de una anomalía real. Además, se pueden consultar predicciones de métricas (KPI) fiables.

Algunos ejemplos de anomalías que puede investigar son:

* Caídas drásticas en un valor de pedido promedio
* Picos en pedidos con ingresos bajos
* Picos o caídas en registros de prueba
* Caídas en vistas de páginas de destino
* Picos en eventos de almacenamiento de vídeo
* Picos en tasas de bits de vídeo bajas

Tanto la detección de anomalías como el [análisis de contribución](/help/analyze/analysis-workspace/c-anomaly-detection/anomaly-detection.md) son flujos de trabajo principales en Analysis Workspace. Puede ejecutar el análisis de contribución para cualquier anomalía diaria e incrustar el resultado en su proyecto de Analysis Workspace.

El algoritmo de Detección de anomalías de Analysis Workspace incluye:

* Compatibilidad con las granularidades horaria, semanal y mensual, además de con la granularidad diaria.
* Diferenciación por temporadas (como el “Black Friday”) y períodos vacacionales.

## Análisis de contribución

El análisis de contribución descubre patrones ocultos en sus datos para explicar las anomalías estadísticas e identificar correlaciones subyacentes

* acciones de cliente inesperadas,
* valores que sobrepasan el límite, y
* picos o caídas repentinos

para métricas seleccionadas en segmentos de público convergentes.


>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Análisis de contribución](https://video.tv.adobe.com/v/25443?quality=12&learn=on){target="_blank"} para ver un vídeo de demostración.

>[!ENDSHADEBOX]


Ha ocurrido algo. ¿Por qué? Su informe Detección de anomalías muestra un pico inusual en los pedidos y desea saber por qué. ¿Qué ha pasado fuera de lo común? ¿Quién está respondiendo a qué campaña o referencia? ¿Algo se ha hecho viral? ¿Qué factores específicos han contribuido a esta anomalía? Y quizá lo más importante: ¿cómo puedo capturar información importante acerca de mi cliente y repetir este comportamiento? (O, si hay una caída en una métrica o una subida en una métrica negativa, ¿cómo puedo evitarla en el futuro?)

Análisis de contribución le ayuda a evaluar los datos inmediatamente para saber por qué se ha producido una anomalía. Desglosa las contribuciones a una anomalía en segundos cuando antes solía tardar semanas, proporcionando patrones para segmentos de público y ayudándole a desarrollar una narrativa para las interacciones con los clientes. Puede utilizar el análisis de contribución de forma estratégica para identificar y capturar asociaciones significativas. A continuación, utilice estas asociaciones de forma estratégica para desarrollar nuevos segmentos de público o de forma táctica para identificar actividades fraudulentas o que sobrepasan el límite y que activen una alerta.

[Detección de anomalías](#anomaly-detection) identifica picos de datos y caídas estadísticas pronunciadas basándose en métricas y segmentos de público concretos. La detección de anomalías establece una norma histórica basada en un período de prueba y, a continuación, representa desplazamientos extremos correlacionados con eventos específicos. La detección de anomalías puede reportar un aumento abrupto en una métrica positiva de pedidos o un aumento en una métrica negativa de devoluciones, o caídas en ambas, capturando puntos de datos estadísticamente relevantes para ser evaluados por un análisis de contribución. Una vez identificada una anomalía estadística, el análisis de contribución permite explorar en profundidad y evaluar variables de marketing y campaña relevantes en todos los puntos de datos anómalos. Ejecuta algoritmos avanzados y procesos de aprendizaje automático para evaluar asociaciones que hayan contribuido a un pico o caída significativos. Estos cálculos aparecen en visualizaciones interactivas diseñadas para ofrecerle distintas perspectivas que le ayuden a entender por qué se ha producido algún evento y qué hacer al respecto.

El análisis de contribución le ayuda a desarrollar una narrativa para describir por qué se produjo una anomalía. Y cómo responder a anomalías, capturando métricas relevantes e identificando puntos ocultos que le proporcionan una razón general para las interacciones de público y las tendencias de interés de los clientes. En ocasiones, una anomalía es fácil de detectar y corregir, como un pedido erróneo de 2.000 kayaks. Por el contrario, otras veces es difícil, como identificar una tendencia emergente a lo largo de un período de tiempo en una región que solo reacciona a una determinada campaña con objetivo. La agrupación de elementos de contribución en métricas de varias dimensiones y sus asociaciones le ofrece una idea general de las interacciones de público y le ayuda a proporcionar contexto para puntos de datos anómalos.

Estos son algunos casos de uso:

* Identificar el potencial de remarketing mediante la supervisión de cambios en la demanda de productos.
* Mejorar la experiencia del cliente reaccionando a determinados intereses del público.
* Identificar pedidos fraudulentos de forma temprana como informe sobre ámbitos que sobrepasan el límite.
* Protegerse del espionaje empresarial identificando usos y descargas masivas.
* Supervise operaciones como, por ejemplo, la creación de informes sobre la falta de etiquetas de Javascript.

Después del análisis completo de una anomalía, se genera un resumen de contribución para los elementos principales ordenados según el número total de ocurrencias y el porcentaje del elemento de los valores de contribución. Una puntuación de contribución normalizada le permite comprar, contrastar y asociar fácilmente otros elementos de dimensión significativos.

## Tokens de análisis de contribución

Todos los clientes con derecho de análisis de contribución pueden ejecutar dicho análisis de forma completa un número limitado de veces al mes en Analysis Workspace. El análisis de contribución **excluye** clientes de productos específicos (SiteCatalyst 15), clientes de Analytics Foundation y de Analytics Select, que no tienen derecho al análisis de contribución.

El número de ejecuciones por empresa está limitado por tokens mensuales que se conceden en función del producto de Adobe Analytics que haya adquirido su empresa. El número de ejecuciones por empresa incluye la capacidad de restringir el acceso a Análisis de contribución para evitar el uso indebido de tokens.

## Preguntas frecuentes

| Pregunta | Respuesta |
| --- | --- |
| ¿Por qué Adobe ha introducido los tokens? | El Análisis de contribución es una de las funcionalidades más aclamadas de Adobe Analytics. Al permitirle realizar un número pequeño de ejecuciones completas al mes (en lugar de ofrecerle únicamente 3 dimensiones para algunos productos de Analytics), podrá ver mejor las ventajas que aporta un análisis de contribución completo e ilimitado. |
| ¿Cómo funcionan los tokens en el análisis de contribución? ¿Hay que pagar un token para cargar un proyecto con un análisis de contribución existente o solo cuando se ejecuta uno nuevo? | Cada empresa (y no cada usuario) recibe un número determinado de tokens al mes, lo cual le permite ejecutar un análisis de contribución “completo” en Analysis Workspace.  Cada vez que genera un nuevo análisis de contribución, paga un token. No debe pagar nigún token al cargar proyectos con análisis de contribución previos a la ejecución. |
| Si mi empresa se queda sin tokens y desea ejecutar más análisis de contribución, ¿qué podemos hacer? | Puede actualizar a otro producto de Adobe Analytics, por ejemplo, de Standard (2 tokens/mes) a Ultimate (20 tokens/mes). No puede comprar más tokens. Debe actualizar dentro del marco de empaquetado existente. |
| ¿Cómo se restringe el acceso a Análisis de contribución? | De forma predeterminada, solo los administradores tienen acceso para ejecutar los análisis de contribución. Sin embargo, los administradores pueden conceder acceso a otros usuarios creando un grupo de permisos en [Adobe Admin Console](/help/admin/admin-console/home.md). Conceda un permiso para usar el análisis de contribución solamente a los usuarios que tengan una razón legítima para usarlos y que sepa que no harán un uso indebido de este permiso. El permiso se denomina [!UICONTROL Análisis de contribución] en [!UICONTROL Herramientas del grupo de informes]. [Más información](/help/admin/admin-console/permissions/report-suite-tools.md) |
| ¿Cómo puedo saber de cuántos tokens al mes dispone mi empresa y qué cantidad ha usado en el mes actual? | Vaya a [!UICONTROL Administración] > [!UICONTROL Todos los administradores] > [!UICONTROL Inicio de la configuración de la compañía] > [!UICONTROL Ver niveles de acceso a funcionalidades]. Buscar en<ul><li>Análisis de contribución: número de tokens de uso mensual</li><li>Análisis de contribución: número de tokens de uso que se han utilizado este mes</li></ul> |

## Derechos de Detección de anomalías y Análisis de contribución

A continuación encontrará una lista detallada de los derechos de Detección de anomalías y Análisis de contribución en Analysis Workspace.

<table id="table_5C9B7E4AE82640B5A913519E576889B5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Derechos de Adobe Analytics </th> 
   <th colname="col2" class="entry"> Detección de anomalías </th> 
   <th colname="col3" class="entry"> Análisis de contribución </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Foundation </p> </td> 
   <td colname="col2"> <p>Solo granularidad diaria </p> </td> 
   <td colname="col3" colsep="1"> <p>Sin tokens </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><a href="https://business.adobe.com/es/products/adobe-analytics/compare-products.html?promoid=B4XQ3X7G&amp;mv=other"  >Select</a> </p> </td> 
   <td colname="col2"> <p>Solo granularidad diaria </p> </td> 
   <td colname="col3"> <p>Sin tokens </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><a href="https://business.adobe.com/es/products/adobe-analytics/compare-products.html?promoid=91BF51TR&amp;mv=other"  >Prime</a> </p> </td> 
   <td colname="col2"> <p>Sí </p> </td> 
   <td colname="col3"> <p>10 tokens al mes </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><a href="https://business.adobe.com/es/products/adobe-analytics/compare-products.html?promoid=8N4B5F1V&amp;mv=other"  > Ultimate</a> </p> </td> 
   <td colname="col2"> <p>Sí </p> </td> 
   <td colname="col3"> <p>20 tokens al mes </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Complemento de Predictive Workbench </p> </td> 
   <td colname="col2"> <p>Sí </p> </td> 
   <td colname="col3"> <p>Tokens ilimitados </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Standard </p> 
    <ul id="ul_73D52020793B44868C9CE0F90893075D"> 
     <li id="li_21EE0871C87E43C8B781219B2BA0FA74">Adobe Analytics Core </li> 
     <li id="li_AB3593200F33439BAEE8FEB13CAE57F4">Adobe Analytics OD </li> 
     <li id="li_2B7D625519BC4A4CB598C95F15D3029B">Adobe Analytics MA </li> 
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
   <td colname="col1"> <p>Premium (Complete, <a href="https://business.adobe.com/es/products/analytics/predictive-analytics.html"  >Predictive Intelligence</a>) </p> </td> 
   <td colname="col2"> <p>Sí </p> </td> 
   <td colname="col3"> <p>Tokens ilimitados </p> </td> 
  </tr> 
 </tbody> 
</table>

---
description: El nuevo sistema Alertas inteligentes permite un control más granular sobre las alertas e integra la detección de anomalías en el sistema de alerta.
seo-description: El nuevo sistema Alertas inteligentes permite un control más granular sobre las alertas e integra la detección de anomalías en el sistema de alerta.
seo-title: Alertas inteligentes sobre validación
title: Descripción general de las alertas inteligentes
uuid: b 9 bf 75 ad-bb 6 f -49 fe -8 c 55-355 ea 3 c 50 a 71
translation-type: tm+mt
source-git-commit: 2f06b402486d4162a968764b398e13893b4a7a75

---


# Descripción general de las alertas inteligentes

>[!Important]
>El uso de datos con marca de hora para crear alertas podría provocar que las alertas &gt; se activen incorrectamente. Por lo tanto, recomendamos aprovechar &gt; datos sin marca de hora para alertas inteligentes.

El nuevo sistema Alertas inteligentes permite un control más granular sobre las alertas e integra la detección de anomalías en el sistema de alerta.

[Alertas inteligentes en YouTube](https://www.youtube.com/watch?v=UVH9xr_2REA&list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS&index=65) (5:34)

## Información general {#section_6AC8CA81DEA94E99B0F192B60D0FDF03}

El nuevo Generador de alertas y el Administrador de alertas en Analysis Workspace sustituyen la funcionalidad de alertas existente en Reports &amp; Analytics. Las alertas inteligentes le permiten

* Generar alertas en función de anomalías (umbrales del 90 %, 95 %, 99 %, 99,75 % y 99,9 %; cambio de %; por encima/por debajo).
* Obtener una vista previa de la frecuencia con la que se activará una alerta.
* Enviar alertas por correo electrónico o SMS con vínculos a proyectos de Analysis Workspace autogenerados.
* Crear alertas “apiladas” que capturan varias métricas en una sola alerta.

Los componentes del nuevo sistema de alerta incluyen: Generador de alertas, Administrador de alertas, Vista previa de alertas y un mejor acceso en contexto para la creación de alertas. La interfaz de usuario del sistema de alertas anterior ya no estará disponible, pero las alertas se migrarán. Algunas de las funcionalidades de alerta heredadas [ya no estarán disponibles](https://marketing.adobe.com/resources/help/en_US/sc/user/deprecated_alerts.html).

Hay cuatro formas en las que puede acceder al Generador de alertas:

* Mediante el acceso directo siguiente en Analysis Workspace:

   `ctrl (or cmd) + shift + a`
* By going directly to the Alert Builder:  **[!UICONTROL Workspace]** &gt; **[!UICONTROL Components]** &gt; **[!UICONTROL New Alert]** .
* Seleccione uno o más elementos de línea de la tabla improvisada, haga clic con el botón derecho y seleccione **[!UICONTROL Crear alerta a partir de la selección]**. De esta forma se abrirá el Generador de alertas, que se rellenará con las métricas y filtros adecuados aplicados a partir de la tabla. A continuación, puede editar la alerta si fuera necesario.

   ![](assets/create-alert-from-selection.png)

* From within a Reports &amp; Analytics report, by going to  **[!UICONTROL More]** &gt; **[!UICONTROL Add Alert]** . De esta forma se abrirá el nuevo Generador de alertas, que se rellenará con las métricas y filtros adecuados aplicados a partir del informe. A continuación, puede editar la alerta si fuera necesario.

   ![](assets/add-alert.png)

## FAQ: How alerts are calculated and triggered {#section_1F3B1DAF21784306953B49AAD4C3DCAB}

Los porcentajes de umbral son desviaciones estándar. Por ejemplo, 95 % = 2 desviaciones estándar y 99 % = 3 desviaciones estándar. En función de la granularidad de tiempo que seleccione, se emplean [distintos modelos](../../../analyze/analysis-workspace/virtual-analyst/c-anomaly-detection/statistics-anomaly-detection.md#concept_0705DC91F0F44951AC2226EC846E824C) para calcular cuánto se aleja (cuántas desviaciones estándar tiene) cada punto de datos respecto a la norma. Si establece un umbral más bajo (por ejemplo, 90 %), obtendrá más anomalías que con otro más alto (99 %). Los umbrales 99,75 % y 99,99 % se introdujeron específicamente para la granularidad horaria, de modo que no se activen tantas anomalías.

<table id="table_B3AA85E1DE3543DCA34966A52E3CE4AB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Pregunta </th> 
   <th colname="col2" class="entry"> Respuesta </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>P: ¿Hasta dónde se remonta la detección de anomalías de una alerta para determinar anomalías de datos?</b> </p> </td> 
   <td colname="col2"> <p>El periodo de aprendizaje varía en función de la granularidad seleccionada. (Consulte <a href="../../../analyze/analysis-workspace/virtual-analyst/c-anomaly-detection/statistics-anomaly-detection.md#concept_0705DC91F0F44951AC2226EC846E824C" format="dita" scope="local"> Técnicas estadísticas utilizadas en la detección de anomalías </a> para obtener más información.) Aquí tiene un resumen: </p> 
    <ul id="ul_4F8C2A41F06C498DBF5E7AE5DE803773"> 
     <li id="li_E246091A3F1E484C8444AF4052FCA784">Mensual = 15 meses + el mismo intervalo del año anterior </li> 
     <li id="li_CC014FB38AE1492B9647E990C29BFB3C">Semanal = 15 semanas + el mismo intervalo del año anterior </li> 
     <li id="li_2517EE2097534324BE9C1B54CD181A62">Diaria = 35 días + el mismo intervalo del año anterior </li> 
     <li id="li_710BC8B009354542AA4962A59A646099">Horaria = 336 horas </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>P: Si quiero que se me alerte en caso solo de un descenso o solo de un pico en el comportamiento, ¿puedo utilizar la función de anomalías o es preciso emplear un valor absoluto?</b> </p> </td> 
   <td colname="col2"> <p>Utilizar un valor absoluto seguiría activando alertas tanto en los descensos como en los picos. No es posible aislar las alertas para diferenciar descensos y picos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>P: ¿Puedo configurar las alertas para que se activen solo durante determinadas horas del día (por ejemplo, en horario laboral o fuera del horario laboral)? </b> </p> </td> 
   <td colname="col2"> <p>En estos momentos, no. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>P: ¿Se puede obtener una tabla de los “valores esperados” que forman la línea de puntos, o hay alguna forma de saber cuáles son esos valores? </b> </p> </td> 
   <td colname="col2"> <p>No en Workspace, pero es posible en el Report Builder (consulte este vídeo acerca de <a href="https://www.youtube.com/watch?v=-a-8W6GQZnU" format="https" scope="external">Detección de anomalías en el Report Builder </a>). </p> <p>Tenga en cuenta que el Report Builder emplea métodos de detección de anomalías menos sofisticados. Utiliza un periodo de entrenamiento de 30 días y un intervalo fijo del 95 %, de forma similar a la <a href="https://marketing.adobe.com/resources/help/en_US/reference/anomaly.html" format="html" scope="external">Detección de anomalías de Reports &amp; Analytics </a>. </p> </td> 
  </tr> 
 </tbody> 
</table>


---
description: La configuración de filas varía en función del componente que haya arrastrado a la tabla.
title: Configuración de filas
uuid: f30c31d5-1fd4-4b93-94c3-ca441099fe2e
translation-type: tm+mt
source-git-commit: 5c2f2d098398927d8379f2eb9ea69ca9acbfd726

---


# Configuración de filas

La configuración de filas varía en función del componente que haya arrastrado a la tabla.

También puede utilizar [acciones del botón secundario en una tabla](/help/analyze/analysis-workspace/visualizations/freeform-table.md) para administrar las filas seleccionadas.

Para obtener acceso a la configuración de fila de tabla, haga clic en el icono Configuración junto a una dimensión, segmento, métrica, periodo de tiempo o desglose dentro de cada uno de estos elementos:

![](assets/row-settings.png)

<table id="table_7ACE6413DB1F40349ED2860020F92E55"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Configuración de fila </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><a href="/help/analyze/analysis-workspace/components/calendar-date-ranges/time-comparison.md"  > Comparaciones de fechas</a> </p> </td> 
   <td colname="col2"> <p><b>Alinee fechas de cada columna con todas a partir de la misma fila. </b> </p> <p>Cuando elija alinear las fechas, por ejemplo en una comparación mes tras mes entre octubre y septiembre de 2016, la columna izquierda comenzará el 1 de octubre y la de la derecha comenzará el 1 de septiembre: </p> <p><img placement="break"  src="assets/add-time-period-column3.png" width="500px" id="image_99398B13FEDA4715B8B818DF6093CA37" /> </p> <p>Deshabilitado de forma predeterminada. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Porcentajes </p> </td> 
   <td colname="col2"> <p><b>Calcular porcentajes por fila</b> </p> <p>Obliga a la tabla improvisada a calcular los porcentajes de las celdas en la fila en lugar de en la columna. Esto es muy útil en porcentajes de tendencia. Se activa de forma predeterminada al usar el icono <span class="uicontrol">Visualizar</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Totales de columna </p> </td> 
   <td colname="col2"> <p>Esta configuración solo se muestra con las <a href="/help/analyze/analysis-workspace/build-workspace-project/column-row-settings/manual-vs-dynamic-rows.md"  > filas manuales (estáticas)</a> (cuando ha seleccionado un conjunto finito de elementos), no con las filas dinámicas (cuando suelta una dimensión que muestra todos los elementos). <p>Nota: Para las filas manuales de <i>métricas</i>, la configuración está deshabilitada porque no tiene sentido sumar métricas aparte de las filas actuales de una tabla. </p> </p> <p><b>Calcular los totales sumando los valores actuales de cada columna (habilitado de forma predeterminada):</b> </p> <p>Esta opción solo calcula las filas actuales de la tabla (cálculo del lado del cliente). </p> <p><b>Calcular los totales basados en todas las filas para cada métrica (deshabilitado de forma predeterminada):</b> </p> <p>Esta opción incluye todos los elementos de dimensión para dicha dimensión, incluso los que no aparecen en la lista (cálculo del lado del servidor). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Desgloses </p> </td> 
   <td colname="col2"> <p><b>Desglose por posición:</b> </p> <p>Puede realizar desgloses según una ubicación fija en una tabla de forma libre. Por ejemplo, puede especificar que se desglosen siempre las primeras siete filas. </p> <p>(Anteriormente, la lista de valores en el desglose estaba “bloqueada”. Esto llevaba a una situación en la que, por ejemplo, si realizaba un desglose de <span class="term">Fecha</span> por <span class="term">Página</span>, obtenía una lista de las 50 primeras páginas para el intervalo de fechas seleccionado. Si se guardaba ese informe y se ejecutaba un mes después, era probable que las 50 primeras páginas hubieran cambiado. No obstante, Analysis Workspace utilizaría los resultados del desglose original y devolvería las mismas páginas, pero con el mes en curso como intervalo de fechas.) </p> <p>Para realizar desgloses basados en una ubicación fija: </p> 
    <ol id="ol_A396A11566AA4F52BC3ABBC373CEF477"> 
     <li id="li_BDAB1E9A48D44944A4F7C31F1182B923">Desglose algunas de las filas de su tabla. </li> 
     <li id="li_C5610437D3714CCEB9F3C771864B4336">Haga clic en el icono de configuración (engranaje) junto a la fila que quiere en una posición fija. </li> 
     <li id="li_675E429DC3B94201978166F9408D30B1">Active la casilla junto a <span class="uicontrol">Desglose por posición</span>. </li> 
     <li id="li_E8A417D0D6D1438CAE825843BA0A7060">Cambie el criterio de ordenación o el intervalo de fechas y vea que ahora los desgloses están vinculados a la posición de la fila, no a las filas en sí. </li> 
    </ol> <p>Deshabilitado de forma predeterminada. </p> </td> 
  </tr> 
 </tbody> 
</table>

| Configuración de fila | Descripción |
|--- |--- |
| Comparaciones de fechas | Alinee fechas de cada columna con todas a partir de la misma fila.   Cuando elija alinear las fechas, por ejemplo en una comparación mes tras mes entre octubre y septiembre de 2016, la columna izquierda comenzará el 1 de octubre y la de la derecha comenzará el 1 de septiembre.<br>Deshabilitado de forma predeterminada. |
| Porcentajes | Calcular porcentajes por fila Fuerza la tabla improvisada para calcular los porcentajes de celda en la fila en lugar de en la columna. Esto es muy útil en porcentajes de tendencia.<br>Habilitado de forma predeterminada al utilizar el icono Visualizar. |
| Totales de columna | Esta configuración solo se muestra con las [static) rows](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/build-workspace-project/column-row-settings/manual-vs-dynamic-rows.html) (when you have selected a finite set of items), not with dynamic rows (i.e., when you drop in a dimension that shows all items).<ul><li>**[!UICONTROL Mostrar la suma de las filas actuales como el total]**: muestra una suma del lado del cliente de las filas de la tabla, lo que significa que el total** no eliminará&#x200B;**las métricas duplicadas como visitas o visitantes.</li><li>**[!UICONTROL Mostrar total general]**: muestra una suma del lado del servidor, lo que significa que el total anulará la duplicación de métricas como visitas o visitantes.</li></ul> |
| Desgloses | **[!UICONTROL Desglose por posición]**:  Puede realizar desgloses en función de una ubicación fija en una tabla improvisada. Por ejemplo, puede especificar que se desglosen siempre las primeras siete filas.<br>(Anteriormente, la lista de valores en el desglose estaba “bloqueada”. Esto llevaba a una situación en la que, por ejemplo, si realizaba un desglose de Fecha por Página, obtenía una lista de las 50 primeras páginas para el intervalo de fechas seleccionado. Si se guardaba ese informe y se ejecutaba un mes después, era probable que las 50 primeras páginas hubieran cambiado. No obstante, Analysis Workspace utilizaría los resultados del desglose original y devolvería las mismas páginas, pero con el mes en curso como intervalo de fechas.)<br>Para realizar desgloses basados en una ubicación fija:1. Desglose algunas de las filas de su tabla. 2. Haga clic en el icono Configuración (engranaje) junto a la fila de tabla que desee que esté en una posición fija. 3. Marque la casilla de verificación situada junto a Desglosar por posición. 4. Cambie el orden de clasificación o el intervalo de fechas y observe que los desgloses están ahora vinculados a la posición de la fila, no a las filas predefinidas.<br>Deshabilitado de forma predeterminada. |
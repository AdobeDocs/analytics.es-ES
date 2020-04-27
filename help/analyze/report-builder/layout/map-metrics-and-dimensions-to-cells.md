---
description: Antes de comenzar a asignar elementos a la hoja de cálculo, compruebe que la hoja no esté protegida. Si el esquema de protección de la hoja de cálculo evita todas las acciones del usuario, no se podrán seleccionar celdas en la hoja. En primer lugar, desproteja la hoja y después añada asignaciones de celda.
title: Asignación de métricas y dimensiones a las celdas
topic: Report builder
uuid: 50893e1c-5f2c-4558-8001-41e70d74d6e7
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Asignación de métricas y dimensiones a las celdas

Antes de comenzar a asignar elementos a la hoja de cálculo, compruebe que la hoja no esté protegida. Si el esquema de protección de la hoja de cálculo evita todas las acciones del usuario, no se podrán seleccionar celdas en la hoja. En primer lugar, desproteja la hoja y después añada asignaciones de celda.

El número de áreas y celdas para asignar difiere según la métrica seleccionada, la granularidad, el intervalo de fechas y los filtros establecidos. Por ejemplo, si selecciona [!UICONTROL Site Metric] > [!UICONTROL Traffic Report], establece [!UICONTROL Week] la granularidad y establece el intervalo de fechas para [!UICONTROL Last 2 Weeks], se le pedirá que asigne tres celdas (al usar [!UICONTROL Custom Layout]) en la [!UICONTROL Request Wizard: Step 2]. La solicitud recupera los datos de la semana uno y la información de la semana dos, donde cada valor de punto de datos es igual al valor de una vista de página. Your third cell serves as the row heading, which you can configure using [!UICONTROL Format Options].

Si se asignan por error ubicaciones incompatibles en la hoja de cálculo, Report Builder genera un error.

Las secciones siguientes contienen más información:

* [Seleccionar un rango de celdas ](/help/analyze/report-builder/layout/map-metrics-and-dimensions-to-cells.md#section_1E37FB46DA194FB7A1050B8833A48AC6)
* [Técnicas para la selección de celdas ](/help/analyze/report-builder/layout/map-metrics-and-dimensions-to-cells.md#section_760421C3D7F84D67A639174710C93B22)
* [Problemas en la asignación ](/help/analyze/report-builder/layout/map-metrics-and-dimensions-to-cells.md#section_CC1BCF841291447EB3A994EB08F3A099)

## Seleccionar un rango de celdas {#section_1E37FB46DA194FB7A1050B8833A48AC6}

On the [!UICONTROL Request Wizard: Step 2], when you enable [!UICONTROL Custom Layout] for a trended request, you can map the request to a range of cells.

Haga clic en **[!UICONTROL Range Selector]** ![select_cell_icon.png](assets/select_cell_icon.png)

situado junto al elemento que desee asignar.

* **Todas las celdas del rango:** Requiere que seleccione un grupo de celdas para una solicitud de [!UICONTROL Custom Layout] estilo.
* **Primera celda del rango:** Permite seleccionar la celda superior izquierda del rango y muestra la [!UICONTROL Range] orientación para especificar la orientación horizontal o vertical de las celdas de entrada y salida (columna o fila). Utilice esta opción para que Report Builder seleccione las celdas por usted.
* **Orientación de rango:** permite orientar los rangos de celdas como columnas o filas.
* **Seleccionar ubicación de celda superior del rango:** muestra las referencias de celdas.

## Técnicas para la selección de celdas {#section_760421C3D7F84D67A639174710C93B22}

You select the data by clicking the **[!UICONTROL Range Selection]** icon  ![select_cell_icon.png](assets/select_cell_icon.png)

y arrastrando el ratón sobre el rango de celdas deseado. Una selección continua se destaca mediante un borde negro.

![](assets/twenty_cells.gif)

Las filas seleccionadas independientes tienen un borde blanco y delgado alrededor de cada fila.

![](assets/twoXten_cells_highlighted.gif)

To map separate rows in one request, use the [!UICONTROL Control] key, then click and drag the cursor over the desired cells. Esto se puede hacer si la solicitud requiere cuatro áreas con diez celdas cada una, en lugar de un área continua con 40 celdas.

![](assets/map4.png)

Después de seleccionar celdas, vuelva a hacer clic en el **[!UICONTROL Range Selector]** formulario para volver al [!UICONTROL Range Selection] formulario [!UICONTROL Request Wizard: Step 2].

## Problemas en la asignación {#section_CC1BCF841291447EB3A994EB08F3A099}

Si selecciona por error asignar una celda que ya tiene una asignación activa, observará que no aparece ninguna referencia de celda en el cuadro de texto situado junto al icono del selector de rango. When you click [!UICONTROL OK], report builder displays the error, &quot;The range selected intersects another request&#39;s range. Cambie su selección.&quot;

* If you still need to use the cell, right-click on the desired cell or cells, and select **[!UICONTROL Delete Request]**.

Si desea evitar este mensaje, puede adoptar dos enfoques:

* Planear el formato del informe añadiendo el formato a las celdas que tienen solicitudes y asignaciones
* Comprobar las áreas de la hoja de cálculo que contengan asignaciones

Para comprobar las áreas con solicitudes insertadas, puede realizar lo siguiente:

* Launch the [!UICONTROL Request Manager] and click on individual requests listed in the table. Al hacer clic en la solicitud, se resaltan las celdas de la hoja de cálculo donde está asignada la solicitud.
* Select cells in the spreadsheet you intend to use for a new mapping and click [!UICONTROL From Sheet]. The [!UICONTROL Request Manager] selects the request in the list which has an output item that intersects the selected cell. Si no se selecciona ninguna solicitud, la celda está disponible.
* Select cells in the spreadsheet, right-click in the context menu and verify if [!UICONTROL Edit Request] is available. Si es así, existe una solicitud asociada a estas celdas.

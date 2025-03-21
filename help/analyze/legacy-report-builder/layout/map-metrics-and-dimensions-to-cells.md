---
description: Obtenga información sobre cómo seleccionar un rango de celdas, técnicas para seleccionar celdas y resolución de problemas con la asignación.
title: Obtenga información sobre cómo asignar métricas y dimensiones a celdas
uuid: 50893e1c-5f2c-4558-8001-41e70d74d6e7
feature: Report Builder
role: User, Admin
exl-id: e63fc679-39eb-417b-9a2b-6620db63a824
source-git-commit: fcecc8a493852f5682fd7fbd5b9bb484a850922c
workflow-type: tm+mt
source-wordcount: '671'
ht-degree: 69%

---

# Asignación de métricas y dimensiones a las celdas

{{legacy-arb}}

Antes de comenzar a asignar elementos a la hoja de cálculo, compruebe que la hoja no esté protegida. Si el esquema de protección de la hoja de cálculo evita todas las acciones del usuario, no se podrán seleccionar celdas en la hoja. En primer lugar, desproteja la hoja y después añada asignaciones de celda.

El número de áreas y celdas que se van a asignar difiere según la métrica que seleccione, la granularidad, el intervalo de fechas y los filtros que defina. Por ejemplo, si selecciona [!UICONTROL Métrica del sitio] > [!UICONTROL Informe de tráfico], establece la granularidad de [!UICONTROL Semana] y establece el intervalo de fechas para [!UICONTROL Últimas 2 semanas], se le pedirá que asigne tres celdas (al usar [!UICONTROL Diseño personalizado]) en el [!UICONTROL Asistente para solicitudes: Paso 2]. La solicitud recupera los datos de la semana uno y de la semana dos, donde cada valor de punto de datos es igual al valor de una vista de página. La tercera celda sirve como encabezado de fila, que se puede configurar utilizando [!UICONTROL Opciones de formato].

Si se asignan por error ubicaciones incompatibles en la hoja de cálculo, Report Builder genera un error.

Para obtener más información, consulte las secciones siguientes:

* [Seleccionar un rango de celdas ](/help/analyze/legacy-report-builder/layout/map-metrics-and-dimensions-to-cells.md#section_1E37FB46DA194FB7A1050B8833A48AC6)
* [Técnicas para la selección de celdas ](/help/analyze/legacy-report-builder/layout/map-metrics-and-dimensions-to-cells.md#section_760421C3D7F84D67A639174710C93B22)
* [Problemas en la asignación](/help/analyze/legacy-report-builder/layout/map-metrics-and-dimensions-to-cells.md#section_CC1BCF841291447EB3A994EB08F3A099)

## Seleccionar un rango de celdas {#section_1E37FB46DA194FB7A1050B8833A48AC6}

En el [!UICONTROL Asistente para solicitudes: Paso 2], cuando se activa [!UICONTROL Diseño personalizado] para una solicitud de tendencias, la solicitud se puede asignar a un rango de celdas.

Haga clic en **[!UICONTROL Selector de rango]** ![select_cell_icon.png](assets/select_cell_icon.png) junto al elemento que desee asignar.

* **Todas las celdas del rango:** requiere que seleccione un grupo de celdas para una solicitud de estilo de [!UICONTROL diseño personalizado].
* **Primera celda del rango:** permite seleccionar la celda superior izquierda del rango y muestra la orientación del [!UICONTROL rango] para especificar la orientación horizontal o vertical de las celdas de entrada y salida (columna o fila). Utilice esta opción para que el Report Builder seleccione las celdas por usted.
* **Orientación de rango:** permite orientar los rangos de celdas como columnas o filas.
* **Seleccionar ubicación de celda superior del rango:** muestra las referencias de celdas.

## Técnicas para seleccionar celdas {#section_760421C3D7F84D67A639174710C93B22}

Los datos se seleccionan haciendo clic en el icono **[!UICONTROL Selección de rango]** ![select_cell_icon.png](assets/select_cell_icon.png)

y arrastrando el ratón sobre el rango de celdas deseado. Una selección continua se destaca mediante un borde negro.

![](assets/twenty_cells.gif)

Las filas seleccionadas independientes tienen un borde blanco y delgado alrededor de cada fila.

![](assets/twoXten_cells_highlighted.gif)

Para asignar filas independientes en una solicitud, utilice la tecla [!UICONTROL Crtl] y después haga clic y arrastre el cursor sobre las celdas deseadas. Esto se puede hacer si la solicitud requiere cuatro áreas con diez celdas cada una, en lugar de un área continua con 40 celdas.

![](assets/map4.png)

Una vez seleccionadas las celdas, haga clic de nuevo en el **[!UICONTROL selector de rango]** del formulario [!UICONTROL Selección de rango] para volver al [!UICONTROL Asistente para solicitudes: Paso 2].

## Solución de problemas de asignación{#section_CC1BCF841291447EB3A994EB08F3A099}

Si elige asignar por error a una celda que ya tiene una asignación activa, no aparecerá ninguna referencia de celda en el cuadro de texto situado junto al icono de selección de rango. Al hacer clic en [!UICONTROL Aceptar], el Report Builder muestra el error *El rango seleccionado se cruza con el rango de otra solicitud. Cambie su selección.*

* Si aún necesita utilizar la celda, haga clic con el botón derecho en la celda o celdas deseadas y seleccione **[!UICONTROL Eliminar solicitud]**.

Si desea evitar este mensaje, puede adoptar dos enfoques:

* Planear el formato del informe añadiendo el formato a las celdas que tienen solicitudes y asignaciones
* Comprobar las áreas de la hoja de cálculo que contengan asignaciones

Para comprobar las áreas con solicitudes insertadas, puede realizar lo siguiente:

* Inicie el [!UICONTROL Asistente para solicitudes] y haga clic en las solicitudes individuales incluidas en la tabla. Al hacer clic en la solicitud, se resaltan las celdas de la hoja de cálculo donde está asignada la solicitud.
* Seleccione las celdas de la hoja de cálculo que vaya a utilizar para una nueva asignación y haga clic en [!UICONTROL Desde hoja]. El [!UICONTROL Administrador de solicitudes] selecciona la solicitud en la lista que tiene un elemento de salida que se cruza con la celda seleccionada. Si no se selecciona ninguna solicitud, la celda está disponible.
* Seleccione celdas en la hoja de cálculo, haga clic con el botón derecho en el menú contextual y compruebe si la opción [!UICONTROL Editar solicitud] está disponible. Si es así, existe una solicitud asociada a estas celdas.

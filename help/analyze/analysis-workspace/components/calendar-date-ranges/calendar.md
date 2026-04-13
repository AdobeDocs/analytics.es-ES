---
description: Utilice el calendario y los intervalos de fechas para especificar intervalos de fechas en Analysis Workspace.
title: Información general sobre los intervalos de fechas
feature: Date Ranges
role: User, Admin
exl-id: fbf4bc18-65ba-4e39-96c1-4c41a8e3baa9
source-git-commit: ca84a5f807545d7196e2e0e90d3209c32d3fd789
workflow-type: tm+mt
source-wordcount: '532'
ht-degree: 100%

---


# Información general sobre los intervalos de fechas

En un proyecto de Workspace, normalmente se usa el [calendario de un panel](/help/analyze/analysis-workspace/c-panels/panels.md#calendar) para especificar el intervalo de fechas para las visualizaciones de ese panel.

Los componentes de intervalo de fechas le permiten definir y anular la configuración de calendario del panel.


## Usar intervalos de fechas

Puede utilizar un componente de intervalo de fechas para redefinir el calendario del panel.

O bien, puede utilizar un intervalo de fechas en una tabla de forma libre como una métrica o dimensión.

![Uso del intervalo de fechas](assets/date-ranges-usage.png)

- **Métrica**.  Por ejemplo, para comparar una dimensión durante dos meses diferentes para una métrica específica.
- **Dimensión**.  Para comparar una métrica en diferentes elementos de dimensión para la dimensión de intervalo de fechas.

>[!NOTE]
>
>Cuando se utilizan intervalos de fechas en una tabla de forma libre, los intervalos de fechas anulan el calendario especificado para el panel al que pertenece la tabla de forma libre.
>

Use un intervalo de fechas como lo [haría con cualquier componente](/help/analyze/analysis-workspace/components/analysis-workspace-components.md#analysis-workspace-components). Arrastre el intervalo de fechas desde el panel de componente ![Calendario](/help/assets/icons/Calendar.svg) **[!UICONTROL Intervalos de fechas]** y suelte el componente en:

- **[!UICONTROL Calendario]**: ![Cambiar](/help/assets/icons/Switch.svg) **[!UICONTROL Sustituya]** la configuración actual del calendario por el intervalo de fechas.
- **Encabezado de la columna de métrica**:![Cambiar](/help/assets/icons/Switch.svg) **[!UICONTROL Sustituya]** la métrica, ![Añadir](/help/assets/icons/Add.svg)**[!UICONTROL Añada ]**el intervalo de fechas como métrica o ![Filtrar](/help/assets/icons/Filter.svg)**[!UICONTROL  Filtre ]**la métrica mediante el componente de intervalo de fechas.
- **Encabezado de la columna de Dimension**: ![Cambiar](/help/assets/icons/Switch.svg) **[!UICONTROL Reemplace]** las dimensiones actuales. La nueva dimensión ahora es **[!UICONTROL Intervalos de fechas]**. Cuando la dimensión sea Intervalos de fechas, podrá ![Añadir](/help/assets/icons/Add.svg)**[!UICONTROL Añadir ]**intervalos de fechas adicionales como elementos de dimensión.
- **Elemento de dimensión**: Realice un ![Desglose](/help/assets/icons/Breakdown.svg) **[!UICONTROL Desglose]** del elemento de dimensión específico por el intervalo de fechas.

También puede añadir una columna de intervalo de fechas directamente en una visualización de tabla de forma libre:

1. En una columna de métrica, seleccione en el menú contextual:

   - **[!UICONTROL Añadir columna de período de tiempo]**. Puede seleccionar entre las opciones sugeridas que se basan en el calendario actual o crear un [intervalo de fechas personalizado](#custom-date-ranges).
   - **[!UICONTROL Comparar períodos de tiempo]** Puede seleccionar entre una opción sugerida basada en el calendario actual o crear un [intervalo de fechas personalizado](#custom-date-ranges).

1. En función de su selección, se añadirán columnas de intervalo de fechas adicionales a la tabla de forma libre.

## Intervalos de fechas no compatibles

Analysis Workspace proporciona una serie de intervalos de fechas predeterminados.


| Día | Semana | Mes | Trimestre | Año |
|---|---|---|---|---|
| Hoy | Esta semana | Este mes | Este trimestre | Este año |
| Ayer | Esta semana (sin incluir hoy) | Este mes (sin incluir hoy) | Este trimestre (sin incluir hoy) | Este año (sin incluir hoy) |
| Hace 2 días | Hace 2 semanas | Hace 2 meses |   |  |
| Hace 3 días | Hace 3 semanas | Hace 3 meses  |  | |
| Últimos 7 días | Semana pasada | Mes pasado | Último trimestre | Año pasado |
| Últimos 14 días | Últimas 2 semanas completas | 2 últimos meses completos | Últimos 4 trimestres completos | |
| Últimos 30 días | Últimas 3 semanas completas | 3 últimos meses completos | | |
| Últimos 60 días | Últimas 4 semanas completas | 6 últimos meses completos | | |
| Últimos 90 días | Últimas 12 semanas completas | 12 últimos meses completos | | |
| Últimos 7 días completos | Últimas 52 semanas completas | 13 últimos meses completos | | |
| Últimos 14 días completos | | | | |
| Últimos 30 días completos | | | | |
| Últimos 90 días completos | | | | |

<table style="table-layout:fixed">

## Intervalos de fechas personalizados

Puede crear sus propios intervalos de fechas personalizados. Consulte [Crear intervalo de fechas](create.md) para ver las distintas opciones disponibles para crear intervalos de fechas. A continuación, puede generar, modificar y guardar intervalos de fechas en el [Generador de intervalos de fechas](create.md#date-range-builder).

Utilice el [administrador de intervalos de fechas](manage.md) para administrar los intervalos de fechas.



<!--
# Calendar and date ranges overview {#date-range}

>[!CONTEXTUALHELP]
>id="components_dateranges_endtime"
>title="End time"
>abstract="End times always include 59 seconds."



In the calendar, you can specify dates and date ranges, or select a preset.


>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Calendar and date ranges overview](https://video.tv.adobe.com/v/23973?quality=12&learn=on){target="_blank"} for a demo video.

>[!ENDSHADEBOX]


Calendar selections apply at the panel level, but you have the option to apply them to all panels. When you click a date range in Workspace, the interface displays the current calendar month and the previous calendar month. You can adjust these two calendars by clicking the right and left arrows in each respective upper corner.

![Calendar](assets/aw_calendar2.png){width="60%"} 

## Select and apply date ranges {#select-apply}

The first click on a calendar starts a date range selection. The second click completes a date range selection, which becomes highlighted. If the `Shift` key is held down (or right-click is used), it appends to the currently selected range.

You can also drag dates (and time dimensions) into a Workspace project. You can select specific days, weeks, months, years, or a rolling date.

[Using Date Ranges and Calendar in Analysis Workspace](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/calendar-and-date-ranges/using-dates-in-analysis-workspace.html?lang=es) (4:07)

| Setting | Description |
|--- |--- |
|Selected Days|Selected days/weeks/months/years.|
|Make date range components relative to panel calendar| If disabled, any date range components used within a table, visualization, or panel drop zone override the panel calendar. <p>If enabled, any date range components used within a table, visualization, or panel drop zone are in relation to the panel date range. For example, if the panel date range is set to November 1 through November 30, and a Last Week date range component is used in a freeform table, the information in the freeform table refers to the last week in October. |
|Use rolling dates| Rolling dates allow you to generate a dynamic report that looks forward or backward for a set period of time based on when you ran the report. For example, if you want to report on all Orders placed "Last Month" (based on the Created Date field) and ran that report in December, you'd see orders placed in November. If you ran that same report in January, you'd see orders placed in December.<ul><li>**[!UICONTROL Date Preview]**: Indicates what time period the rolling calendar encompasses.</li><li>**[!UICONTROL Start]**: You can choose among current day, current week, current month, current quarter, current year.</li><li>**[!UICONTROL End]**: You can choose among current day, current week, current month, current quarter, current year.</li></ul>To view an example, see [Custom date ranges](/help/analyze/analysis-workspace/components/calendar-date-ranges/custom-date-ranges.md). <br>Selected by default.|
|Date Range|Lets you pick a preset date range. Last 30 days is the default. **[!UICONTROL This week/month/quarter/year (excluding today)]** lets you choose from date ranges that do not include partial-day data from today.|
|Apply to All Panels|Lets you not only change the selected date range for the current panel, but also for all other panels within the project.|
|Apply|Applies the date range to this panel only.|

## About relative panel date ranges {#relative-panel-dates}

If you're working in Workspace, you can make the date range components relative to the panel calendar. 
Three common use cases where you'll see relative panel dates take effect are Combo charts, Key metrics summary, and Freeform table date ranges.

To use relative panel date ranges

1. Select the **Workspace** tab.
1. Select **Blank project**.
1. Add dimensions, metrics, and segments from the left rail. 
1. Click the panel date range field to toggle the relative panel date range setting.
1. Select **Make date range components relative to panel calendar**.
    * Select the option to make the date range components relative to the panel calendar.
        If relative dates are selected, then rolling dates will be based on the start date of the panel calendar and not today's date.
    * If this option isn't selected, then rolling dates will be based on today's date.

    ![relative panel dates](assets/relative-date-selected.png){width="60%"} 

1. Click **Apply**.
    The relative dates are shown in the upper-right.

    ![relative dates in freeform ](assets/relative-date-range1.png)

## Guidelines for relative panel date ranges {#guidelines}

Keep in mind the following guidelines when using relative panel date ranges.

### Formulas and relative date ranges {#formula-relative-dates}

If you have relative dates selected, all date formulas will use the panel's start date as the starting point.

### Custom calendars and relative date ranges {#custom-calendar-formulas}

When you use a week-based custom calendar and you add months or years, the formula calculates the offset of the day in the given period. The actual date may be different because of the offset. The formula chooses the day landing in the same place in the custom calendar. For example, the third Friday of the third week in a custom calendar.

### About segments that use rolling dates and relative panel date ranges {#segments-relative-dates}

If you build a segment or use a segment with a rolling date, for example, the Last 7 Days or the Last 2 Weeks, and you click on the segment preview, it will start the rolling date from *Today* instead of the panel start date. As a result the preview for the segment will not match when you actually use the segment in the table. The preview is impacted, not the segment itself. 

## Guidelines for panel date ranges and previews {#guidelines-panel-dates}

* Starting with the February release, component and data previews will be based on the panel date range and not the last 90 days. 
* All components listed in the left rail will be available based on the panel date range. 
* All date previews in the segment and calculated metric builders will be based on the panel date range (unless accessed from the component managers, which do not have an associated panel, they will still be based on the last 90 days). 
* Any data previews will display data or components based on the panel date range.

-->
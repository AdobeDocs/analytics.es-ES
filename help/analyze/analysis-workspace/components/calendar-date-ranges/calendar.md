---
description: En el calendario, se pueden indicar fechas e intervalos de fechas o seleccionar ajustes preestablecidos.
title: Resumen de calendario e intervalos de fechas
uuid: 3d7727ba-9070-4f7c-815f-c98baa4e3a2d
translation-type: tm+mt
source-git-commit: 8ce13270a254af140e38b981e9edd9b5e122cdf9
workflow-type: tm+mt
source-wordcount: '383'
ht-degree: 84%

---


# Resumen de calendario e intervalos de fechas

En el calendario, se pueden indicar fechas e intervalos de fechas o seleccionar ajustes preestablecidos.

Las selecciones de calendario se aplican a nivel de panel, pero tiene la opción de aplicarlas a todos los paneles. Al hacer clic en un intervalo de fechas en Workspace, la interfaz muestra el mes natural actual y el mes natural anterior. Puede ajustar estos dos calendarios haciendo clic en las flechas derecha e izquierda de cada esquina superior respectiva.

![Calendario](assets/aw_calendar.png)

El primer clic en un calendario inicia una selección de intervalo de fechas. El segundo clic completa una selección de intervalo de fechas, que se resalta. Si la tecla `Shift` se mantiene pulsada (o se utiliza el clic derecho), se anexa al rango seleccionado actualmente.

También puede arrastrar fechas (y dimensiones temporales) a un proyecto de Workspace. Se pueden seleccionar fechas, semanas, meses o años concretos, o bien fechas móviles.

[Uso de intervalos de fechas y calendarios en Analysis Workspace en YouTube](https://www.youtube.com/watch?v=L4FSrxr3SDA&amp;list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS&amp;index=28) (4:07)

| Configuración | Descripción |
|--- |--- |
| Días seleccionados | Días/semanas/meses/años seleccionados. |
| Usar fechas móviles | Las fechas móviles le permiten generar un informe dinámico que observa un periodo de tiempo anterior o posterior basándose en el momento en el que ejecuta el informe. Por ejemplo, si desea un informe sobre todos los pedidos realizados el “último mes” (basándose en el campo Fecha de creación) y se ejecuta dicho informe en diciembre, verá los pedidos realizados en noviembre. Si ejecutara ese mismo informe en enero, vería los pedidos realizados en diciembre.<ul><li>**[!UICONTROL Previsualización]** de fecha: Indica el período de tiempo que abarca el calendario móvil.</li><li>**[!UICONTROL Inicio]**: Puede elegir entre el día actual, la semana actual, el mes actual, el trimestre actual y el año actual.</li><li>**[!UICONTROL Fin]**: Puede elegir entre el día actual, la semana actual, el mes actual, el trimestre actual y el año actual.</li></ul>Por ejemplo, consulte [este enlace](/help/analyze/analysis-workspace/components/calendar-date-ranges/custom-date-ranges.md). |
| Intervalo de fecha | Le permite seleccionar un rango de fechas preestablecido. La opción predeterminada es los últimos 30 días. **[!UICONTROL Esta semana/mes/trimestre/año (excluido hoy)]** le permite elegir entre intervalos de fechas que no incluyen datos de día parcial a partir de hoy. |
| Aplicar a todos los paneles | No solo le permite cambiar el intervalo de fechas seleccionado para el panel actual, sino también para todos los demás paneles dentro del proyecto. |
| Aplicar | Aplica el rango de fechas únicamente a este panel. |

---
description: En el calendario, se pueden indicar fechas e intervalos de fechas o seleccionar ajustes preestablecidos.
title: Resumen de calendario e intervalos de fechas
uuid: 3d7727ba-9070-4f7c-815f-c98baa4e3a2d
feature: Conceptos básicos de Workspace
role: User, Admin
exl-id: fbf4bc18-65ba-4e39-96c1-4c41a8e3baa9
source-git-commit: 7226b4c77371b486006671d72efa9e0f0d9eb1ea
workflow-type: ht
source-wordcount: '375'
ht-degree: 100%

---

# Resumen de calendario e intervalos de fechas

En el calendario, se pueden indicar fechas e intervalos de fechas o seleccionar ajustes preestablecidos.

Las selecciones de calendario se aplican a nivel de panel, pero tiene la opción de aplicarlas a todos los paneles. Al hacer clic en un intervalo de fechas en Workspace, la interfaz muestra el mes natural actual y el mes natural anterior. Puede ajustar estos dos calendarios haciendo clic en las flechas derecha e izquierda de cada esquina superior respectiva.

![Calendario](assets/aw_calendar.png)

El primer clic en un calendario inicia una selección de intervalo de fechas. El segundo clic completa una selección de intervalo de fechas, que se resalta. Si la tecla `Shift` se mantiene pulsada (o se utiliza el clic derecho), se anexa al rango seleccionado actualmente.

También puede arrastrar fechas (y dimensiones temporales) a un proyecto de Workspace. Se pueden seleccionar fechas, semanas, meses o años concretos, o bien fechas móviles.

[Uso de intervalos de fechas y calendarios en Analysis Workspace](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/calendar-and-date-ranges/using-dates-in-analysis-workspace.html?lang=es) (4:07)

| Configuración | Descripción |
|--- |--- |
| Días seleccionados | Días/semanas/meses/años seleccionados. |
| Usar fechas móviles | Las fechas móviles le permiten generar un informe dinámico que observa un periodo de tiempo anterior o posterior basándose en el momento en el que ejecuta el informe. Por ejemplo, si desea un informe sobre todos los pedidos realizados el “último mes” (basándose en el campo Fecha de creación) y se ejecuta dicho informe en diciembre, verá los pedidos realizados en noviembre. Si ejecutara ese mismo informe en enero, vería los pedidos realizados en diciembre.<ul><li>**[!UICONTROL Vista previa de fecha]**: indica qué periodo de tiempo incluye el calendario móvil.</li><li>**[!UICONTROL Inicio]**: puede elegir entre el día, la semana, el mes, el trimestre o el año actuales.</li><li>**[!UICONTROL Fin]**: puede elegir entre el día, la semana, el mes, el trimestre o el año actuales.</li></ul>Por ejemplo, consulte [este enlace](/help/analyze/analysis-workspace/components/calendar-date-ranges/custom-date-ranges.md). |
| Intervalo de fechas | Le permite seleccionar un rango de fechas preestablecido. La opción predeterminada es los últimos 30 días. **[!UICONTROL Esta semana, mes, trimestre o año (excluido hoy)]** le permite elegir entre intervalos de fechas que no incluyen datos de día parcial de hoy. |
| Aplicar a todos los paneles | No solo le permite cambiar el intervalo de fechas seleccionado para el panel actual, sino también para todos los demás paneles dentro del proyecto. |
| Aplicar | Aplica el rango de fechas únicamente a este panel. |

---
description: En el calendario, se pueden indicar fechas e intervalos de fechas o seleccionar ajustes preestablecidos.
title: Resumen de calendario e intervalos de fechas
feature: Calendar
role: User, Admin
exl-id: fbf4bc18-65ba-4e39-96c1-4c41a8e3baa9
source-git-commit: d7a6867796f97f8a14cd8a3cfad115923b329c7c
workflow-type: ht
source-wordcount: '942'
ht-degree: 100%

---

# Resumen de calendario e intervalos de fechas {#date-range}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_dateranges_endtime"
>title="Hora de finalización"
>abstract="Las horas de finalización siempre incluyen 59 segundos."

<!-- markdownlint-enable MD034 -->


En el calendario, se pueden indicar fechas e intervalos de fechas o seleccionar ajustes preestablecidos.


>[!BEGINSHADEBOX]

Vea ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Información general de calendario e intervalos de fechas](https://video.tv.adobe.com/v/328094?quality=12&learn=on&captions=spa){target="_blank"} para ver un vídeo de demostración.

>[!ENDSHADEBOX]


Las selecciones de calendario se aplican a nivel de panel, pero tiene la opción de aplicarlas a todos los paneles. Al hacer clic en un intervalo de fechas en Workspace, la interfaz muestra el mes natural actual y el mes natural anterior. Puede ajustar estos dos calendarios haciendo clic en las flechas derecha e izquierda de cada esquina superior respectiva.

![Calendario](assets/aw_calendar2.png){width="60%"}

## Selección y aplicación de intervalos de fechas {#select-apply}

El primer clic en un calendario inicia una selección de intervalo de fechas. El segundo clic completa una selección de intervalo de fechas, que se resalta. Si la tecla `Shift` se mantiene pulsada (o se utiliza el clic derecho), se anexa al rango seleccionado actualmente.

También puede arrastrar fechas (y dimensiones temporales) a un proyecto de Workspace. Se pueden seleccionar fechas, semanas, meses o años concretos, o bien fechas móviles.

[Uso de intervalos de fechas y calendarios en Analysis Workspace](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/calendar-and-date-ranges/using-dates-in-analysis-workspace.html?lang=es) (4:07)

| Configuración | Descripción |
|--- |--- |
| Días seleccionados | Días/semanas/meses/años seleccionados. |
| Hacer que los componentes del intervalo de fecha sean relativos al calendario del panel | Si está deshabilitado, cualquier componente de intervalo de fechas utilizado dentro de una tabla, visualización o zona de colocación de paneles anula el calendario del panel. <p>Si está habilitado, cualquier componente de intervalo de fechas utilizado en una tabla, visualización o zona de colocación del panel estará en relación con el intervalo de fechas del panel. Por ejemplo, si el intervalo de fechas del panel está establecido entre el 1 y el 30 de noviembre y se utiliza un componente Intervalo de fechas de la última semana en una tabla de forma libre, la información de la tabla de forma libre se refiere a la última semana de octubre. |
| Usar fechas móviles | Las fechas móviles le permiten generar un informe dinámico que observa un periodo de tiempo anterior o posterior basándose en el momento en el que ejecuta el informe. Por ejemplo, si desea un informe sobre todos los pedidos realizados el “último mes” (basándose en el campo Fecha de creación) y se ejecuta dicho informe en diciembre, verá los pedidos realizados en noviembre. Si ejecutara ese mismo informe en enero, vería los pedidos realizados en diciembre.<ul><li>**[!UICONTROL Vista previa de fecha]**: indica qué periodo de tiempo incluye el calendario móvil.</li><li>**[!UICONTROL Inicio]**: puede elegir entre el día, la semana, el mes, el trimestre o el año actuales.</li><li>**[!UICONTROL Fin]**: puede elegir entre el día, la semana, el mes, el trimestre o el año actuales.</li></ul>Para ver un ejemplo, consulte [Intervalos de fechas personalizados](/help/analyze/analysis-workspace/components/calendar-date-ranges/custom-date-ranges.md). <br>Seleccionado de forma predeterminada. |
| Intervalo de fechas | Le permite seleccionar un rango de fechas preestablecido. La opción predeterminada es los últimos 30 días. **[!UICONTROL Esta semana, mes, trimestre o año (excluido hoy)]** le permite elegir entre intervalos de fechas que no incluyen datos de día parcial de hoy. |
| Aplicar a todos los paneles | No solo le permite cambiar el intervalo de fechas seleccionado para el panel actual, sino también para todos los demás paneles dentro del proyecto. |
| Aplicar | Aplica el rango de fechas únicamente a este panel. |

## Acerca de los intervalos de fechas relativos del panel {#relative-panel-dates}

Si está trabajando en el Espacio de trabajo, puede hacer que los componentes del intervalo de fecha sean relativos al calendario del panel.
Tres casos de uso habituales en los que las fechas relativas del panel surten efecto son los gráficos combinados, el resumen de métricas clave y los intervalos de fechas de la tabla de forma libre.

Para usar intervalos de fechas relativos del panel

1. Seleccione la pestaña **Espacio de trabajo**.
1. Seleccione **Proyecto en blanco**.
1. Agregue dimensiones, métricas y segmentos desde el carril izquierdo.
1. Haga clic en el campo Intervalo de fecha del panel para cambiar el valor del intervalo de fecha del panel relativo.
1. Seleccione **Hacer que los componentes del intervalo de fecha sean relativos al calendario del panel**.
   * Seleccione la opción para que los componentes del intervalo de fecha sean relativos al calendario del panel.
Si se seleccionan fechas relativas, las fechas móviles se basarán en la fecha de inicio del calendario del panel y no en la fecha actual.
   * Si esta opción no está seleccionada, las fechas móviles se basarán en la fecha actual.

   ![fechas relativas del panel](assets/relative-date-selected.png){width="60%"}

1. Haga clic en **Aplicar**.
Las fechas relativas se muestran en la esquina superior derecha.

   ![fechas relativas en forma libre ](assets/relative-date-range1.png)

## Pautas para intervalos de fechas relativos del panel {#guidelines}

Tenga en cuenta las siguientes directrices cuando utilice intervalos de fechas relativos del panel.

### Fórmulas e intervalos de fechas relativos {#formula-relative-dates}

Si tiene seleccionadas fechas relativas, todas las fórmulas de fecha utilizarán la fecha de inicio del panel como punto de partida.

### Calendarios personalizados e intervalos de fechas relativos {#custom-calendar-formulas}

Cuando se usa un calendario personalizado basado en semanas y se añaden meses o años, la fórmula calcula el desplazamiento del día en un período determinado. La fecha real puede ser diferente debido a dicho desplazamiento. La fórmula elige el día que cae en el mismo lugar del calendario personalizado. Por ejemplo, el tercer viernes de la tercera semana en un calendario personalizado.

### Acerca de los segmentos que utilizan fechas móviles e intervalos de fechas relativos del panel {#segments-relative-dates}

Si genera o utiliza un segmento con una fecha móvil, por ejemplo, los últimos siete días o las últimas dos semanas, y hace clic en la vista previa del segmento, se inicia la fecha móvil desde *hoy* en lugar de la fecha de inicio del panel. Como resultado, la vista previa del segmento no coincidirá cuando realmente utilice el segmento en la tabla. Se ve afectada la vista previa, no el propio segmento.

## Directrices para los intervalos de fechas del panel y las vistas previas {#guidelines-panel-dates}

* A partir de la versión de febrero, las vistas previas de componentes y datos se basarán en el intervalo de fechas del panel y no en los últimos 90 días.
* Todos los componentes enumerados en el carril izquierdo estarán disponibles en función del intervalo de fechas del panel.
* Todas las vistas previas de fechas en los generadores de segmentos y métricas calculadas se basarán en el intervalo de fechas del panel (a menos que se acceda desde los administradores de componentes, que no tienen un panel asociado, seguirán basándose en los últimos 90 días).
* Cualquier vista previa de datos mostrará datos o componentes basados en el intervalo de fechas del panel.
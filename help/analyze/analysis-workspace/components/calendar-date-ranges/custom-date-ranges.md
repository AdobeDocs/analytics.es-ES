---
description: Cree intervalos de fechas personalizados en Analysis Workspace y guárdelos como componentes de tiempo.
keywords: Analysis Workspace
seo-description: Cree intervalos de fechas personalizados en Analysis Workspace y guárdelos como componentes de tiempo.
seo-title: Crear intervalos de fechas
solution: Analytics
title: Crear intervalos de fechas
topic: Reports and Analytics
uuid: c 8873 d 41-454 d -4 f 22-ad 1 f -38 cacec 5 a 3 bc
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Crear intervalos de fechas

Cree intervalos de fechas personalizados en Analysis Workspace y guárdelos como componentes de tiempo.

**[!UICONTROL Componentes]** &gt; **[!UICONTROL Nuevo intervalo de fechas]**

Se aplica un intervalo de fechas en el nivel de panel. To add a date range to your project, click **Panels** &gt; *`<select panel>`*, and specify a new date range.

## Date range for "two months ago" {#section_C4109C57CB444BB2A79CC8082BD67294}

El siguiente intervalo de fechas personalizado muestra un intervalo de fechas para “dos meses atrás”, con una visualización de cambio de resumen que muestra el cambio direccional.

![](assets/date-range-two-months-ago.png)

El intervalo de fechas personalizado se muestra en la parte superior del panel de componente [!UICONTROL Intervalo de fechas] del proyecto:

![](assets/date-range-panel-two-months-ago.png)

Puede arrastrar este intervalo de fechas personalizado en un columna a lo largo de un intervalo de fechas móvil mensual mediante el valor preestablecido Último mes para ver una comparación. Agregue una visualización de cambio de resumen y seleccione los totales de cada columna para mostrar un cambio direccional:

![](assets/date-range-two-months-table.png)

## Use a 7-day rolling date range {#section_7EF63B2E9FF54D2E9144C4F76956A8DD}

Se aplica un intervalo de fechas al nivel de panel. Para agregar un intervalo de fechas al proyecto, haga clic en **Acciones** &gt; **Agregar panel**, y especifique el nuevo intervalo de fechas.

En el Generador de intervalos de fechas, puede crear un intervalo de fechas personalizado que se muestra en el panel Componentes con otros intervalos de fechas.

Por ejemplo, puede crear un intervalo de fechas que especifica una ventana móvil de 7 días y que termina una semana atrás:

![](assets/create_date_range.png)

Utilice *`rolling daily`*.

* La configuración de inicio sería *`current day minus 14 days`*.

* La configuración de fin sería *`current day minus 7 days`*.

Este intervalo de fechas puede ser un componente que arrastre en cualquier tabla improvisada.

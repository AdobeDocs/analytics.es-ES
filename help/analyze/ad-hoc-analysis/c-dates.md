---
description: En el calendario, se pueden indicar fechas e intervalos de fechas o seleccionar ajustes preestablecidos. Puede realizar selecciones de calendario en los niveles de proyecto, área de trabajo e informe. El intervalo de fechas de un proyecto es la fecha predeterminada. Sin embargo, un intervalo de fechas del espacio de trabajo anula el intervalo de fechas del proyecto. Del mismo modo, el intervalo de fechas de un informe anula la configuración de fecha de un área de trabajo y proyecto. No puede seleccionar un intervalo de fechas fuera del intervalo de disponibilidad de datos.
title: Fechas e intervalos de fechas
uuid: 8f099db7-e74b-4384-ac46-61a545f1dd62
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Fechas e intervalos de fechas

En el calendario, se pueden indicar fechas e intervalos de fechas o seleccionar ajustes preestablecidos. Puede realizar selecciones de calendario en los niveles de proyecto, área de trabajo e informe. El intervalo de fechas de un proyecto es la fecha predeterminada. Sin embargo, un intervalo de fechas del espacio de trabajo anula el intervalo de fechas del proyecto. Del mismo modo, el intervalo de fechas de un informe anula la configuración de fecha de un área de trabajo y proyecto. No puede seleccionar un intervalo de fechas fuera del intervalo de disponibilidad de datos.

## Fechas e intervalos de fechas {#concept_AB32765013F449908B5964AB622C75FF}

En el calendario, se pueden indicar fechas e intervalos de fechas o seleccionar ajustes preestablecidos. Puede realizar selecciones de calendario en los niveles de proyecto, área de trabajo e informe. El intervalo de fechas de un proyecto es la fecha predeterminada. Sin embargo, un intervalo de fechas del espacio de trabajo anula el intervalo de fechas del proyecto. Del mismo modo, el intervalo de fechas de un informe anula la configuración de fecha de un área de trabajo y proyecto. No puede seleccionar un intervalo de fechas fuera del intervalo de disponibilidad de datos.

![](assets/Delete_Standard.png) Una **[!UICONTROL Clear Date]** opción habilitada indica que se ha especificado un intervalo de fechas en el nivel del informe.

También puede arrastrar fechas (y dimensiones temporales) al informe o al [!UICONTROL Table Builder]. Puede seleccionar días, semanas, meses, años específicos o una fecha móvil. Si utiliza el calendario personalizado en los informes y análisis de marketing, un grupo de informes hereda esa configuración y actualiza el informe en consecuencia.

Al seleccionar un intervalo de fechas al crear un proyecto, si se utiliza Preconfigurado a la izquierda, se establecerá una fecha móvil mientras que si se utiliza el calendario a la derecha no se establecerá. An easy way to tell whether your date range is rolling is the statement &quot;This date range will roll&quot; next to the **[!UICONTROL OK]** button.

![](assets/daterange.jpeg)

>[!NOTE] Si necesita ayuda para ejecutar informes preexistentes, comuníquese con su administrador de cuenta.

## Fracciones de datos preexistentes {#concept_53AA34DB3CE647608CAF4B41D6EAF45E}

En el segundo semestre de 2010, Adobe comenzó la migración de grupos de informes a una plataforma de datos unificada para mejorar el procesamiento y el almacenamiento. Los datos existentes antes de la migración se consideran datos heredados (o históricos) que están restringidos por un límite de calendario trimestral o anual.

<!-- 

c_legacy_data.xml

 -->

**Para acceder a fracciones de datos del historial**

1. [Cree](/help/analyze/ad-hoc-analysis/c-getting-started.md) o abra un proyecto.
1. Open the [calendar](/help/analyze/ad-hoc-analysis/c-dates.md), then select **[!UICONTROL Quarter]** or **[!UICONTROL Year]**.

>[!NOTE] Las fracciones de datos históricos están dentro de una restricción trimestral y anual. No es posible realizar vistas de datos que crucen el límite entre los segmentos heredados y la nueva plataforma de procesamiento. Los intervalos de fechas que abarcan ambos resultados dan como resultado un error. Además, los intervalos de fechas solo se aplican al calendario gregoriano, no al calendario personalizado.


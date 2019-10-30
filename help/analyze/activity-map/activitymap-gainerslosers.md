---
description: Las superposiciones permiten configurar la visualización de datos de varias formas para que pueda ver y conocer fácilmente la popularidad que tienen los vínculos en una página.
seo-description: Las superposiciones permiten configurar la visualización de datos de varias formas para que pueda ver y conocer fácilmente la popularidad que tienen los vínculos en una página.
seo-title: Superposiciones personalizables
solution: Analytics
title: Superposiciones personalizables
topic: Activity Map
uuid: c1e56480-c1df-4a81-8a2a-42ea1362175c
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Superposiciones personalizables

Las superposiciones permiten configurar la visualización de datos de varias formas para que pueda ver y conocer fácilmente la popularidad que tienen los vínculos en una página.

Con las superposiciones se pueden ver los datos de clics directamente en la página. This is what separates a visual analysis tool like [!DNL Activity Map] from mostly tabular and graphical tools like Reports &amp; Analytics.

[!DNL Activity Map] ofrece tres tipos de superposiciones:

* Superposición de degradado (mapa de calor)
* Superposición de burbujas
* Superposición de ganadores y perdedores

También puede configurar [la representación de superposiciones en el contenido dinámico](/help/analyze/activity-map/activitymap-link-tracking/activitymap-stl-track-custom-elements.md).

Para hacer cambios en las superposiciones, abra el [panel Configuración de solapamiento](/help/analyze/activity-map/activitymap-overlay-settings.md) y edite las opciones disponibles.

Si coloca el ratón sobre una superposición, se verán los [detalles](/help/analyze/activity-map/activitymap-overlay-details.md).

## Gradient overlay (Heatmap) {#section_06AF13DE05A1454D960176CD0DA921A6}

Con la superposición de degradado, la intensidad del color se basa en la popularidad del vínculo. Esta intensidad se puede normalizar en las 30 primeras clasificaciones o en una función del valor absoluto de la métrica.

Estas métricas se superponen a los vínculos de la página como una especie de “mapa de calor” para responder a cuestiones críticas, incluidas las siguientes:

* ¿Cuál es el valor de una página individual?
* ¿Cuál es el valor de un elemento individual de una página?
* ¿Cuál es el “activo digital” más valioso de la página?

![](assets/gradient.png)

## Bubble overlay {#section_A657AB3F64CB47F881BBFFD72B37D9D4}

La superposición de burbujas muestra el contenido de la superposición (métrica, porcentaje o clasificación) en una pequeña burbuja.

Las superposiciones de burbujas se muestran cuando selecciona en la barra de herramientas esta superposición en Tipo de superposición. Bubble overlays show for all links that match the selection in [[!DNL Activity Map] Settings](/help/analyze/activity-map/activitymap-overlay-settings.md) (top 30, top 50, all...). Si no se selecciona esta opción, se ven las superposiciones de degradado.

![](assets/bubble_overlay.png)

> [!NOTE] Las superposiciones de burbujas para submenús solo se muestran cuando se muestra el submenú:
>
>![](assets/bubbles_submenu.png)&gt;

## Gainers and losers overlays {#section_EE80278E20C14824869BF5A27A4634C8}

**[!UICONTROL Las superposiciones]** de ganadores y perdedores solo están disponibles en el modo Activo. Informan de los cambios en tiempo real que se producen en la actividad de los vínculos comparando las métricas del período actual con las métricas del período anterior. Permiten ver rápidamente las tendencias en tiempo real de una forma visual.

Esta superposición en tiempo real clasifica los clics según los cambios en el valor de la métrica entre los períodos anteriores y el actual.

![](assets/gainers_losers.png)


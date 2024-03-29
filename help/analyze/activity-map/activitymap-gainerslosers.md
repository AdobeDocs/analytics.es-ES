---
description: Las superposiciones permiten configurar la visualización de datos de varias formas para que pueda ver y conocer fácilmente la popularidad que tienen los vínculos en una página.
title: Superposiciones personalizables
feature: Activity Map
role: User, Admin
exl-id: 1e83d470-36e4-47bb-a262-ac12472b21c3
source-git-commit: d173a6c6c9751a86f4218ec842da17da14f8485b
workflow-type: tm+mt
source-wordcount: '337'
ht-degree: 91%

---

# Superposiciones personalizables

Las superposiciones permiten configurar la visualización de datos de varias formas para que pueda ver y conocer fácilmente la popularidad que tienen los vínculos en una página.

Las superposiciones permiten visualizar datos sobre clics directamente en la página.

Activity Map ofrece tres tipos de superposiciones:

* Superposición de degradado (mapa de calor)
* Superposición de burbujas
* Superposición de ganadores y perdedores

También puede configurar [la representación de superposiciones en el contenido dinámico](/help/analyze/activity-map/activitymap-link-tracking/activitymap-stl-track-custom-elements.md).

Para hacer cambios en las superposiciones, abra el [panel Configuración de solapamiento](/help/analyze/activity-map/activitymap-overlay-settings.md) y edite las opciones disponibles.

Si coloca el ratón sobre una superposición, se verán los [detalles](/help/analyze/activity-map/activitymap-overlay-details.md).

## Superposición de degradado (mapa de calor) {#section_06AF13DE05A1454D960176CD0DA921A6}

Con la superposición de degradado, la intensidad del color se basa en la popularidad del vínculo. Esta intensidad se puede normalizar en las 30 primeras clasificaciones o en una función del valor absoluto de la métrica.

Estas métricas se superponen a los vínculos de la página como una especie de “mapa de calor” para responder a cuestiones críticas, incluidas las siguientes:

* ¿Cuál es el valor de una página individual?
* ¿Cuál es el valor de un elemento individual de una página?
* ¿Cuál es el “activo digital” más valioso de la página?

![](assets/gradient.png)

## Superposición de burbujas {#section_A657AB3F64CB47F881BBFFD72B37D9D4}

La superposición de burbujas muestra el contenido de la superposición (métrica, porcentaje o clasificación) en una pequeña burbuja.

Las superposiciones de burbujas se muestran cuando selecciona en la barra de herramientas esta superposición en Tipo de superposición. Las superposiciones de burbujas se ven para todos los vínculos que se ajustan a la selección en [Configuración de Activity Map](/help/analyze/activity-map/activitymap-overlay-settings.md) (30 primeros, 50 primeros, todos...). Si no se selecciona esta opción, se ven las superposiciones de degradado.

![](assets/bubble_overlay.png)

>[!NOTE]
>
>Las superposiciones de burbujas en submenús solo se muestran al mostrar el submenú:
>
>![](assets/bubbles_submenu.png)>

## Superposiciones de ganadores y perdedores {#section_EE80278E20C14824869BF5A27A4634C8}

**[!UICONTROL Las superposiciones de ganadores y perdedores]** solo están disponibles en el modo Activo. Informan de los cambios en tiempo real que se producen en la actividad de los vínculos comparando las métricas del período actual con las métricas del período anterior. Permiten ver rápidamente las tendencias en tiempo real de una forma visual.

Esta superposición en tiempo real clasifica los clics según los cambios en el valor de la métrica entre los períodos anteriores y el actual.

![](assets/gainers_losers.png)

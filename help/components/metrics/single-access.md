---
title: Acceso único
description: Número de veces que un elemento de dimensión no ha cambiado en una visita.
feature: Metrics
exl-id: 973ce835-9d6f-4ead-90c9-0b80aac82cc0
source-git-commit: 6d2c278c5525c89b73c39bbfcedbe644806bf989
workflow-type: tm+mt
source-wordcount: '482'
ht-degree: 15%

---

# Acceso único

La **[!UICONTROL métrica]** Acceso único[ muestra el número de visitas donde la dimensión de informe aplicable solo contenía un valor para una visita completa. ](overview.md) Es la versión más amplia y específica de la dimensión de [[!UICONTROL Visitas de página única]](single-page-visits.md). Esta métrica es útil en el contexto de cualquier dimensión en la que desee ver el valor de una dimensión cuando se estableció solo una vez durante una visita.

## Cálculo de esta métrica

La definición de esta métrica depende de la configuración del proyecto de [[!UICONTROL Contar instancias repetidas]](/help/analyze/analysis-workspace/build-workspace-project/create-projects.md#project-info-settings):

* **Contar instancias repetidas habilitadas**: Cuenta visitas donde la dimensión contiene exactamente un valor en una visita. Si la dimensión persiste, ya no se califica como un acceso único.
* **Recuento de instancias repetidas deshabilitadas**: Cuenta las visitas donde la dimensión contiene un solo valor único. Puede establecer el elemento de dimensión con el mismo valor varias veces o hacer que persista y siga contando como un solo acceso.

Independientemente de &#39;[!UICONTROL Contar instancias repetidas]&#39;, la visita ya no se califica como un acceso único si la dimensión cambia a un segundo valor único. Las llamadas de seguimiento de vínculos se incluyen en este cálculo si la dimensión está establecida en ellas.

## Diferencia entre &#39;[!UICONTROL acceso único]&#39; y &#39;[!UICONTROL visita de página única]&#39;

En el contexto de la dimensión [[!UICONTROL Página]](../dimensions/page.md), &#39;[!UICONTROL Acceso único]&#39; y &#39;[!UICONTROL Visitas de página única]&#39; son siempre exactamente idénticas independientemente de la configuración del proyecto &#39;[!UICONTROL Contar instancias repetidas]&#39;. Sus diferencias surgen cuando se usan otras dimensiones.

* **[!UICONTROL Acceso único]**: Muestra el número de visitas en las que el elemento de dimensión dado estaba presente para una sola visita. Es contextual para la dimensión que se utiliza en el proyecto.
* **[!UICONTROL Visita a una sola página]**: Muestra el número de visitas en las que la dimensión &#39;[!UICONTROL Página]&#39; estaba presente para una sola visita. Aunque utilice otra dimensión en el informe, aún cuenta las visitas que contienen un solo elemento de dimensión &#39;[!UICONTROL Página]&#39; único.

Si [[!UICONTROL Contar instancias repetidas]](/help/analyze/analysis-workspace/build-workspace-project/create-projects.md#project-info-settings) está deshabilitado, las definiciones de métricas cambian ligeramente:

* **Acceso único**: Muestra el número de visitas en las que el elemento de dimensión dado no cambió durante toda la visita.
* **Visita de página única**: Muestra el número de visitas en las que la dimensión &#39;[!UICONTROL Página]&#39; no cambió durante toda la visita.

Veamos el siguiente ejemplo de visitas con dos visitas. La dimensión del informe es [[!UICONTROL Sección del sitio]](../dimensions/site-section.md) y &#39;[!UICONTROL Contar instancias repetidas]&#39; está deshabilitada.

* Un visitante visita dos páginas, pero ambas están en la misma sección del sitio. Dado que la sección del sitio permaneció igual durante la visita, se considera un acceso único. No se cuenta como una visita de página única porque la visita contiene más de un elemento de dimensión [!UICONTROL Página] único.
* Un visitante visita dos páginas en diferentes secciones del sitio, pero ambas páginas tienen el mismo nombre. La visita no cuenta como un acceso único porque había dos valores de sección del sitio únicos. Se cuenta como una visita a una sola página porque había un solo elemento de dimensión [!UICONTROL Página] único.

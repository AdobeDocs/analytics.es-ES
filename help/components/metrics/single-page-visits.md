---
title: Visitas a una sola página (métricas)
description: El número de veces que el elemento de dimensión “Página” no ha cambiado en una visita.
feature: Metrics
exl-id: 086235d0-4542-4e82-96ab-28c47c842ecf
source-git-commit: 6d2c278c5525c89b73c39bbfcedbe644806bf989
workflow-type: tm+mt
source-wordcount: '239'
ht-degree: 33%

---

# Visitas de página única

*En esta página de ayuda se describe cómo funciona “Visitas de página única” como métrica. Consulte la dimensión [Visitas de página única](../dimensions/single-page-visits.md) para obtener más información.*

La **[!UICONTROL métrica]** [visitas de página única](overview.md) muestra el número de visitas donde el elemento de dimensión [Página](../dimensions/page.md) solo contenía un valor para toda la visita. Esta métrica es útil en el contexto de dimensiones en las que desea ver visitas cortas, pero no tiene reglas tan estrictas como [[!UICONTROL Devoluciones]](bounces.md).

## Cálculo de esta métrica

La definición de esta métrica depende de la configuración del proyecto de [[!UICONTROL Contar instancias repetidas]](/help/analyze/analysis-workspace/build-workspace-project/create-projects.md#project-info-settings):

* **[!UICONTROL Contar instancias repetidas] habilitadas**: Cuenta el número de visitas donde la dimensión [!UICONTROL Página] contenía un solo valor para la visita. Si un visitante vuelve a cargar la página, no se califica como una visita a una sola página.
* **[!UICONTROL Contar instancias repetidas] deshabilitadas**: Cuenta el número de visitas donde la dimensión [!UICONTROL Página] contenía un solo valor único para toda la visita.

Independientemente de la configuración del proyecto &#39;[!UICONTROL Contar instancias repetidas]&#39;, esta métrica cumple las siguientes reglas:

* Una visita se considera una visita de página única si un visitante activa las llamadas de seguimiento de vínculos (la dimensión [!UICONTROL Página] se elimina de todas las llamadas de seguimiento de vínculos).
* Tan pronto como la dimensión [!UICONTROL Página] cambie a un segundo valor único, la visita ya no se califica como una visita de página única.

Consulte [Acceso único](single-access.md) para ver una comparación entre métricas.

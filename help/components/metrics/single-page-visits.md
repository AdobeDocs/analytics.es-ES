---
title: Visitas a una sola página (métricas)
description: El número de veces que el elemento de dimensión “Página” no ha cambiado en una visita.
feature: Metrics
exl-id: 086235d0-4542-4e82-96ab-28c47c842ecf
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '191'
ht-degree: 84%

---

# Visitas de página única

*En esta página de ayuda se describe cómo funciona “Visitas de página única” como métrica. Consulte la dimensión [Visitas de página única](../dimensions/single-page-visits.md) para obtener más información.*

La [!UICONTROL métrica](overview.md) [visitas de página única] muestra el número de visitas donde el elemento de dimensión [Página](../dimensions/page.md) solo contenía un valor único para toda la visita. Esta métrica es útil en el contexto de dimensiones en las que desea ver visitas cortas, pero no tiene reglas tan estrictas como [[!UICONTROL Devoluciones]](bounces.md).

## Cálculo de esta métrica

Esta métrica cuenta el número de visitas en las que el elemento de dimensión [!UICONTROL Página] solo contenía un valor único para toda la visita. Si un visitante vuelve a cargar la página o activa las llamadas de seguimiento de vínculos, aún se cuenta como una sola visita a la página. Tan pronto como la dimensión Página cambie a un segundo valor único, la visita ya no se califica como una visita de página única.

Consulte [Acceso único](single-access.md) para ver una comparación entre métricas.

## Contar instancias repetidas

Esta configuración especifica si las instancias repetidas se cuentan en los informes. Para obtener más información, consulte [Recuento de instancias repetidas](/help/components/metrics/count-repeat-instances.md).

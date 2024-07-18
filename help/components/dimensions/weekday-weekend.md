---
title: Día de la semana/Fin de semana
description: Determina si la visita se produjo durante un día entre semana o un fin de semana.
feature: Dimensions
exl-id: c3111cdc-a5f9-4244-a725-b1bb1e72fcff
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '105'
ht-degree: 80%

---

# Día de la semana/Fin de semana

La dimensión &quot;Día de la semana/Fin de semana&quot; [dimension](overview.md) proporciona una perspectiva sobre si la visita se produjo durante un día entre semana (lunes a viernes) o un fin de semana (sábado a domingo). La hora de la visita está basada en la [zona horaria del grupo de informes](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/general-acct-settings-admin.md).

## Rellene esta dimensión con datos

Esta dimensión funciona de forma predeterminada para todas las implementaciones. Si un grupo de informes contiene datos, esta dimensión funciona.

## Elementos de dimensión

Esta dimensión siempre contiene exactamente dos elementos de dimensión: `"Weekday"` y `"Weekend"`. El elemento de dimensión `"Weekday"` se aplica a todas las visitas de lunes a viernes, mientras que el elemento de dimensión `"Weekend"` se aplica a todas las visitas individuales de sábado y domingo.

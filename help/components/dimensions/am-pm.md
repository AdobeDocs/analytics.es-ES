---
title: AM/PM
description: Determina si la visita se produjo durante las horas AM o PM.
feature: Dimensions
exl-id: 93fcdb9f-2ba3-402c-a389-b02ed8c990d2
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '117'
ht-degree: 86%

---

# AM/PM

La dimensión [a.m./p.m.](overview.md) proporciona una perspectiva sobre si la visita se produjo durante las horas AM o PM. La hora de la visita está basada en la [zona horaria del grupo de informes](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/general-acct-settings-admin.md).

## Rellene esta dimensión con datos

Esta dimensión funciona de forma predeterminada. No tiene ninguna configuración para cambiar. Su única dependencia depende del huso horario del grupo de informes, que determina qué horas son AM y cuáles son PM.

## Elementos de dimensión

Esta dimensión siempre contiene exactamente dos elementos de dimensión: `"AM"` y `"PM"`. El elemento de dimensión `"AM"` se aplica a todas las visitas individuales desde las 00:00 h hasta las 11:59 h, mientras que el elemento de dimensión `"PM"` se aplica a todas las visitas individuales desde las 12:00 h hasta las 23:59 h.

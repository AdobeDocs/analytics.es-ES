---
title: AM/PM
description: Determina si la visita se produjo durante las horas AM o PM.
feature: Dimensions
exl-id: 93fcdb9f-2ba3-402c-a389-b02ed8c990d2
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '121'
ht-degree: 64%

---

# AM/PM

La dimensión [a.m./p.m.](overview.md) proporciona insight en caso de que la visita se haya producido durante las horas AM o PM. La hora de la visita está basada en la [zona horaria del grupo de informes](/help/admin/tools/manage-rs/edit-settings/general/general-acct-settings-admin.md).

## Rellene esta dimensión con datos

Esta dimensión funciona de forma predeterminada. No tiene ninguna configuración para cambiar. Su única dependencia depende del huso horario del grupo de informes, que determina qué horas son AM y cuáles son PM.

## Elementos de dimensión

Esta dimensión siempre contiene exactamente dos elementos de dimensión: `"AM"` y `"PM"`. El elemento de dimensión `"AM"` se aplica a todas las visitas individuales desde las 12:00 a las 11:59 a.m., mientras que el elemento de dimensión `"PM"` se aplica a todas las visitas individuales desde las 12:00 p.m. hasta las 11:59 p.m.

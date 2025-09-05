---
title: Día de la semana/Fin de semana
description: Determina si la visita se produjo durante un día entre semana o un fin de semana.
feature: Dimensions
exl-id: c3111cdc-a5f9-4244-a725-b1bb1e72fcff
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '105'
ht-degree: 80%

---

# Día de la semana/Fin de semana

La dimensión [Día de la semana/Fin de semana](overview.md) proporciona insight en caso de que la visita se produzca durante un día entre semana (lunes a viernes) o un fin de semana (sábado a domingo). La hora de la visita está basada en la [zona horaria del grupo de informes](/help/admin/tools/manage-rs/edit-settings/general/general-acct-settings-admin.md).

## Rellene esta dimensión con datos

Esta dimensión funciona de forma predeterminada para todas las implementaciones. Si un grupo de informes contiene datos, esta dimensión funciona.

## Elementos de dimensión

Esta dimensión siempre contiene exactamente dos elementos de dimensión: `"Weekday"` y `"Weekend"`. El elemento de dimensión `"Weekday"` se aplica a todas las visitas de lunes a viernes, mientras que el elemento de dimensión `"Weekend"` se aplica a todas las visitas individuales de sábado y domingo.

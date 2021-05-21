---
title: Día de la semana/Fin de semana
description: Determina si la visita se produjo durante un día entre semana o un fin de semana.
exl-id: c3111cdc-a5f9-4244-a725-b1bb1e72fcff
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '105'
ht-degree: 100%

---

# Día de la semana/Fin de semana

La dimensión “Día de la semana/Fin de semana” proporciona una perspectiva sobre si la visita se produjo durante un día entre semana (lunes a viernes) o un fin de semana (sábado a domingo). La hora de la visita está basada en la [zona horaria del grupo de informes](/help/admin/admin/general-acct-settings-admin.md).

## Rellene esta dimensión con datos

Esta dimensión funciona de forma predeterminada para todas las implementaciones. Si un grupo de informes contiene datos, esta dimensión funciona.

## Elementos de dimensión

Esta dimensión siempre contiene exactamente dos elementos de dimensión: `"Weekday"` y `"Weekend"`. El elemento de dimensión `"Weekday"` se aplica a todas las visitas de lunes a viernes, mientras que el elemento de dimensión `"Weekend"` se aplica a todas las visitas individuales de sábado y domingo.

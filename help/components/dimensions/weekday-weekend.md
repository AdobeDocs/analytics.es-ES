---
title: Día de la semana/Fin de semana
description: Determina si la visita se produjo durante un día de semana o un fin de semana.
translation-type: tm+mt
source-git-commit: 05ea2778cd5cd324c660fd0f1d2ac02373829f0f
workflow-type: tm+mt
source-wordcount: '105'
ht-degree: 3%

---


# Día de la semana/Fin de semana

La dimensión &#39;Día de semana/Fin de semana&#39; proporciona una perspectiva sobre si la visita se produjo durante un día de semana (lunes a viernes) o un fin de semana (sábado a domingo). The time of the hit is based on the [report suite&#39;s time zone](/help/admin/admin/general-acct-settings-admin.md).

## Rellenar esta dimensión con datos

Esta dimensión funciona de forma predeterminada para todas las implementaciones. Si un grupo de informes contiene datos, esta dimensión funciona.

## Valores de dimensión

Esta dimensión siempre contiene exactamente dos valores de dimensión: `"Weekday"` y `"Weekend"`. El valor de dimensión `"Weekday"` se aplica a todas las visitas de lunes a viernes, mientras que el valor de dimensión `"Weekend"` se aplica a todas las visitas individuales de sábado y domingo.

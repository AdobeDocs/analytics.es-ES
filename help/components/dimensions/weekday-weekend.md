---
title: Día de la semana/Fin de semana
description: Determina si la visita se produjo durante un día de semana o un fin de semana.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '105'
ht-degree: 3%

---


# Día de la semana/Fin de semana

La dimensión &#39;Día de semana/Fin de semana&#39; proporciona una perspectiva sobre si la visita se produjo durante un día de semana (lunes a viernes) o un fin de semana (sábado a domingo). The time of the hit is based on the [report suite&#39;s time zone](/help/admin/admin/general-acct-settings-admin.md).

## Rellenar esta dimensión con datos

Esta dimensión funciona de forma predeterminada para todas las implementaciones. Si un grupo de informes contiene datos, esta dimensión funciona.

## Elementos de dimensión

Esta dimensión siempre contiene exactamente dos elementos de dimensión: `"Weekday"` y `"Weekend"`. El elemento de dimensión `"Weekday"` se aplica a todas las visitas individuales de lunes a viernes, mientras que el elemento de dimensión `"Weekend"` se aplica a todas las visitas individuales de sábado y domingo.

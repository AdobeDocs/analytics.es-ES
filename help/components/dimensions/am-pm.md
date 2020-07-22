---
title: AM/PM
description: Determina si la visita se produjo durante las horas AM o PM.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '117'
ht-degree: 3%

---


# AM/PM

La dimensión &#39;AM/PM&#39; proporciona una perspectiva sobre si la visita se produjo durante las horas AM o PM. The time of the hit is based on the [report suite&#39;s time zone](/help/admin/admin/general-acct-settings-admin.md).

## Rellenar esta dimensión con datos

Esta dimensión funciona de forma predeterminada. No tiene ninguna configuración para cambiar. Su única dependencia depende del huso horario del grupo de informes, que determina qué horas son AM y cuáles son PM.

## Elementos de dimensión

Esta dimensión siempre contiene exactamente dos elementos de dimensión: `"AM"` y `"PM"`. El elemento de dimensión `"AM"` se aplica a todas las visitas individuales desde las 12:00 AM hasta las 11:59 AM, mientras que el elemento de dimensión `"PM"` se aplica a todas las visitas individuales desde las 12:00 PM hasta las 11:59 PM.

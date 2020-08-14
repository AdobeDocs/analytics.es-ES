---
title: AM/PM
description: Determina si la visita se produjo durante las horas AM o PM.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '117'
ht-degree: 70%

---


# AM/PM

La dimensión “AM/PM” proporciona una perspectiva sobre si la visita se produjo durante las horas AM o PM. La hora de la visita está basada en la [zona horaria del grupo de informes](/help/admin/admin/general-acct-settings-admin.md).

## Rellene esta dimensión con datos

Esta dimensión funciona de forma predeterminada. No tiene ninguna configuración para cambiar. Su única dependencia depende del huso horario del grupo de informes, que determina qué horas son AM y cuáles son PM.

## Elementos de Dimension

This dimension always contains exactly two dimension items: `"AM"` and `"PM"`. The dimension item `"AM"` applies to all hits from 12:00 AM to 11:59 AM, while the dimension item `"PM"` applies to all hits from 12:00 PM to 11:59 PM.

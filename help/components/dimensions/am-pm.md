---
title: AM/PM
description: Determina si la visita se produjo durante las horas AM o PM.
feature: Dimensions
exl-id: 93fcdb9f-2ba3-402c-a389-b02ed8c990d2
TQID: https://experienceleague.adobe.com/R1syrJ7ylIe2ywH1isX4sjR2O84-8eL-jooYhjUdKhI
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 121
ht-degree: 64%

---

# AM/PM

La dimensión [a.m./p.m.](overview.md) proporciona insight en caso de que la visita se haya producido durante las horas AM o PM. La hora de la visita está basada en la [zona horaria del grupo de informes](/help/admin/tools/manage-rs/edit-settings/general/general-acct-settings-admin.md).

## Rellene esta dimensión con datos

Esta dimensión funciona de forma predeterminada. No tiene ninguna configuración para cambiar. Su única dependencia depende del huso horario del grupo de informes, que determina qué horas son AM y cuáles son PM.

## Elementos de dimensión

Esta dimensión siempre contiene exactamente dos elementos de dimensión: `"AM"` y `"PM"`. El elemento de dimensión `"AM"` se aplica a todas las visitas individuales desde las 12:00 a las 11:59 a.m., mientras que el elemento de dimensión `"PM"` se aplica a todas las visitas individuales desde las 12:00 p.m. hasta las 11:59 p.m.

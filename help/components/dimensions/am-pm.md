---
title: AM/PM
description: Determina si el hit se produjo durante las horas AM o PM.
feature: Dimensions
exl-id: 93fcdb9f-2ba3-402c-a389-b02ed8c990d2
TQID: https://experienceleague.adobe.com/R1syrJ7ylIe2ywH1isX4sjR2O84-8eL-jooYhjUdKhI
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '159'
ht-degree: 33%
---
# AM/PM

La dimensión [a.m./p.m.](overview.md) proporciona insight en caso de que la visita se haya producido durante las horas AM o PM. La hora del hit está basada en la [zona horaria del grupo de informes](/help/admin/tools/manage-rs/edit-settings/general/general-acct-settings-admin.md).

## Rellene esta dimensión con datos

Esta dimensión se deriva de la marca de tiempo de cada visita individual; no hay ninguna variable que establecer. Su única dependencia es la zona horaria del grupo de informes, que determina qué horas son AM y cuáles son PM.

| Propiedad | Valor |
| --- | --- |
| **variable de AppMeasurement** | Ninguno (derivado de la marca de tiempo de la visita) |
| **Campo Web SDK / XDM** | Ninguno (derivado de la marca de tiempo de la visita) |
| **Parámetro de consulta** | n/a |
| **etiqueta XML** | n/a |
| **Límite de bytes** | n/a |
| **Persistencia** | Hit |

## Elementos de dimensión

Esta dimensión siempre contiene exactamente dos elementos de dimensión: `"AM"` y `"PM"`. El elemento de dimensión `"AM"` se aplica a todas las visitas individuales desde las 12:00 a.m. hasta las 11:59 a.m., mientras que el elemento de dimensión `"PM"` se aplica a todas las visitas individuales desde las 12:00 p.m. hasta las 11:59 p.m.

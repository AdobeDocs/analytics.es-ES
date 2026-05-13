---
title: Día de la semana/Fin de semana
description: Determina si la visita se produjo durante un día entre semana o un fin de semana.
feature: Dimensions
exl-id: c3111cdc-a5f9-4244-a725-b1bb1e72fcff
TQID: https://experienceleague.adobe.com/9TJv-49ub1zHsgEGtBeoJVoHhsBktlOr7QhmgLdLRSo
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 105
ht-degree: 80%

---

# Día de la semana/Fin de semana

La dimensión [Día de la semana/Fin de semana](overview.md) proporciona insight en caso de que la visita se produzca durante un día entre semana (lunes a viernes) o un fin de semana (sábado a domingo). La hora de la visita está basada en la [zona horaria del grupo de informes](/help/admin/tools/manage-rs/edit-settings/general/general-acct-settings-admin.md).

## Rellene esta dimensión con datos

Esta dimensión funciona de forma predeterminada para todas las implementaciones. Si un grupo de informes contiene datos, esta dimensión funciona.

## Elementos de dimensión

Esta dimensión siempre contiene exactamente dos elementos de dimensión: `"Weekday"` y `"Weekend"`. El elemento de dimensión `"Weekday"` se aplica a todas las visitas de lunes a viernes, mientras que el elemento de dimensión `"Weekend"` se aplica a todas las visitas individuales de sábado y domingo.

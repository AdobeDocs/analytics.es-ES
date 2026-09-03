---
title: Dirección IP
description: La dirección IP desde la que se envió cada visita, disponible en Data Warehouse.
feature: Dimensions
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: d4db20e3498d54162806b3fdef0b34f45c93a6ff
workflow-type: tm+mt
source-wordcount: 108
ht-degree: 17%

---

# Dirección IP

La &quot;Dirección IP&quot; [dimension](overview.md) enumera la dirección IP desde la que se envió cada visita.

>[!IMPORTANT]
>
>Esta dimensión solo está disponible en Data Warehouse.

## Rellene esta dimensión con datos

AppMeasurement recopila automáticamente la dirección IP del encabezado HTTP de cada solicitud de imagen. Corresponde a la columna `ip` de las fuentes de datos. Consulte [Referencia de columna de datos](../../export/analytics-data-feed/c-df-contents/datafeeds-reference.md) para obtener más información.

Si la [!UICONTROL confusión de IP] está habilitada en la [configuración general de la cuenta](/help/admin/tools/manage-rs/edit-settings/general/general-acct-settings-admin.md) del grupo de informes, las direcciones IP se confunden o eliminan en cualquier lugar de Analytics, incluido Data Warehouse.

## Elementos de dimensión

Los elementos de Dimension incluyen las direcciones IP desde las que se enviaron las visitas.

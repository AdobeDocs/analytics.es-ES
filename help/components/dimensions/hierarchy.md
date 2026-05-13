---
title: Jerarquía
description: (Retirado) Dimensión personalizada que se puede utilizar en la creación de informes.
feature: Dimensions
exl-id: f9bd3ae1-3578-44c5-a540-ea93feac5bef
TQID: https://experienceleague.adobe.com/7WnYvaE3qCfYGWcX6IuvMZiF0MJq50Izz6i2LNg4h6c
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7
subfeature_v2: id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 167
ht-degree: 86%

---

# Jerarquía

>[!IMPORTANT]
>
>Esta dimensión se ha retirado y no es una [dimensión](overview.md) disponible en Analysis Workspace. Adobe recomienda usar [eVars](evar.md) y clasificaciones en su lugar.

Las jerarquías son variables personalizadas que se pueden utilizar como desee. No se mantienen más allá de la visita en la que están configuradas. Hay disponibles hasta 5 jerarquías si su contrato con Adobe lo permite.

## Rellenar jerarquías con datos

Cada jerarquía recopila datos de las cadenas de consulta [`h1` - `h5` ](/help/implement/validate/query-parameters.md) en solicitudes de imagen. Por ejemplo, el parámetro de cadena de consulta `h1` recopila datos para la jerarquía 1, mientras que el parámetro de cadena de consulta `h4` recopila datos para la jerarquía 4.

AppMeasurement, que compila variables JavaScript en una solicitud de imagen para la recopilación de datos, utiliza las variables `hier1` - `hier5`. Consulte [hier](/help/implement/vars/page-vars/hier.md) en la Guía del usuario sobre implementación para ver las directrices de implementación.

## Elementos de dimensión

Dado que las jerarquías contienen cadenas personalizadas en la implementación, la organización determina los elementos de dimensión de cada jerarquía. Asegúrese de registrar el propósito de cada jerarquía y los elementos de dimensión típicos en un [documento de diseño de solución](/help/implement/prepare/solution-design.md).

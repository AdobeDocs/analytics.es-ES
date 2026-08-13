---
title: Canal de último contacto
description: El canal de marketing más reciente dentro de la caducidad de la participación del visitante.
feature: Dimensions
exl-id: 62a47de5-ee1a-4394-aa63-75cdda92ba6a
TQID: https://experienceleague.adobe.com/wUNsv-0snBfk6EE6yeCEuT8-hGvBu9U8tjKDfxhVRA0
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: c80b99d6-98b9-4aeb-b5c4-933ef2ef705cid: f836f655-eebe-4b76-82bc-697955ec1ce3id: fab61dd8-112a-4e5e-ad5f-fb0240b7a60b
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 337
ht-degree: 67%

---

# Canal de último contacto

El &quot;Canal de último contacto&quot; [dimension](overview.md) informa del canal de marketing más reciente con el que coincide un visitante durante el periodo de participación de ese visitante (de forma predeterminada, 30 días). Esta dimensión es valiosa para comprender qué canales de marketing conducen el tráfico al sitio y cuáles resultan en conversiones, lo que permite enfocar los esfuerzos de marketing en las áreas más efectivas.

## Rellene esta dimensión con datos

Esta dimensión hace referencia directamente a los nombres de canales que ha definido en el [administrador de canales de marketing](/help/admin/tools/manage-rs/edit-settings/marketing-channels/c-channels.md).

Cada visita enviada a los servidores de recopilación de datos de Adobe se ejecuta a través de las reglas de procesamiento del canal de marketing del grupo de informes. Se repite por cada regla en orden numérico hasta que encuentra una coincidencia, en la que ese canal de marketing se vincula con la visita. El canal de último contacto persiste con el visitante hasta que no visita el sitio durante más tiempo que el período de participación de visitante (de forma predeterminada, 30 días).

Si desea establecer esta dimensión en un valor específico, se requieren los siguientes pasos:

* Establezca el elemento de dimensión deseado como un canal en el administrador de canales de marketing en la configuración del grupo de informes.
* Establezca una regla de procesamiento de canal de marketing que contenga los criterios deseados para la visita.
* La visita del visitante al sitio debe coincidir con los criterios descritos en la regla de procesamiento del canal de marketing.

>[!TIP]
>
>Si se usa esta dimensión con métricas que usan [atribución de participación](/help/analyze/analysis-workspace/attribution/models.md), se puede atribuir crédito a `None` cuando otros modelos de atribución no lo hacen. Las métricas de participación requieren un canal de marketing [instance](../metrics/instances.md) dentro de la ventana de informes para recibir crédito. Si el canal de marketing se estableció inicialmente fuera de la ventana de informes y solo el valor persistente existe dentro de la ventana de informes, las métricas de participación atribuyen el crédito a `None`. Otros modelos de atribución atribuyen crédito al valor persistente. Si desea evitar la atribución a `None` en este escenario, considere la posibilidad de utilizar un modelo de atribución que no sea de participación.

## Elementos de dimensión

Los elementos de dimensión incluyen cualquier nombre de canal en el administrador de canales de marketing. De forma predeterminada, los valores incluyen `"Paid search"`, `"Natural search"`, `"Display"`, `"Email"`, `"Affiliate"`, `"Direct"`, `"Internal"`, `"Social networks"` y `"Referring domains"`. Puede añadir o eliminar canales en el administrador de canales de marketing, que afectan a los valores de esta dimensión.

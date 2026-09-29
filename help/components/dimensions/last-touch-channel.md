---
title: Canal de último contacto
description: El canal de marketing más reciente dentro de la caducidad de la participación del visitante.
feature: Dimensions
exl-id: 62a47de5-ee1a-4394-aa63-75cdda92ba6a
TQID: 'https://experienceleague.adobe.com/wUNsv-0snBfk6EE6yeCEuT8-hGvBu9U8tjKDfxhVRA0'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
    internal-label: Data configuration and collection
subfeature_v2:
  - id: c80b99d6-98b9-4aeb-b5c4-933ef2ef705c
    internal-label: Marketing Channels
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
  - id: fab61dd8-112a-4e5e-ad5f-fb0240b7a60b
    internal-label: Report Suite settings
  - id: b22bc0f7-b089-4966-95a1-31e7b3b69b79
    internal-label: Dimensions
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: 9a50beeb0aa51cf9f4baf212566947c14029ce8e
workflow-type: tm+mt
source-wordcount: '375'
ht-degree: 49%
---
# Canal de último contacto

El &quot;Canal de último contacto&quot; [dimension](overview.md) informa del canal de marketing más reciente con el que coincide un visitante durante el periodo de participación de ese visitante (de forma predeterminada, 30 días). Esta dimensión es valiosa para comprender qué canales de marketing conducen el tráfico al sitio y cuáles resultan en conversiones, lo que permite enfocar los esfuerzos de marketing en las áreas más efectivas.

## Rellene esta dimensión con datos

Esta dimensión se deriva de las reglas de procesamiento del canal de marketing. Hace referencia directamente a los nombres de canal que ha definido en el [administrador de canales de marketing](/help/admin/tools/manage-rs/edit-settings/marketing-channels/c-channels.md). Cada visita individual se ejecuta a través de las reglas de procesamiento de canal de marketing del grupo de informes en orden numérico hasta que encuentra una coincidencia, que vincula ese canal de marketing con la visita. No hay ninguna variable que establecer.

| Propiedad | Valor |
| --- | --- |
| **variable de AppMeasurement** | Ninguno (derivado por las reglas de procesamiento del canal de marketing) |
| **Campo Web SDK / XDM** | Ninguno (derivado por las reglas de procesamiento del canal de marketing) |
| **Parámetro de consulta** | n/a |
| **etiqueta XML** | n/a |
| **Límite de bytes** | n/a |
| **Persistencia** | Configurable |

El canal de último contacto persiste con el visitante hasta que no visita el sitio durante más tiempo que el período de participación de visitante (de forma predeterminada, 30 días).

Si desea establecer esta dimensión en un valor específico, se requieren los siguientes pasos:

* Establezca el elemento de dimensión deseado como un canal en el administrador de canales de marketing en la configuración del grupo de informes.
* Establezca una regla de procesamiento de canal de marketing que contenga los criterios deseados para el hit.
* El hit del visitante al sitio debe coincidir con los criterios descritos en la regla de procesamiento del canal de marketing.

>[!TIP]
>
>Si se usa esta dimensión con métricas que usan [atribución de participación](/help/analyze/analysis-workspace/attribution/models.md), se puede atribuir crédito a `None` cuando otros modelos de atribución no lo hacen. Las métricas de participación requieren un canal de marketing [instance](../metrics/instances.md) dentro de la ventana de informes para recibir crédito. Si el canal de marketing se estableció inicialmente fuera de la ventana de informes y solo el valor persistente existe dentro de la ventana de informes, las métricas de participación atribuyen el crédito a `None`. Otros modelos de atribución atribuyen crédito al valor persistente. Si desea evitar la atribución a `None` en este escenario, considere la posibilidad de utilizar un modelo de atribución que no sea de participación.

## Elementos de dimensión

Los elementos de dimensión incluyen cualquier nombre de canal en el administrador de canales de marketing. De forma predeterminada, los valores incluyen `"Paid search"`, `"Natural search"`, `"Display"`, `"Email"`, `"Affiliate"`, `"Direct"`, `"Internal"`, `"Social networks"` y `"Referring domains"`. Puede añadir o eliminar canales en el administrador de canales de marketing, que afectan a los valores de esta dimensión.

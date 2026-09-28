---
title: Exclusión en la administración de consentimiento
description: Ver qué configuración de privacidad excluyó un visitante.
exl-id: 2bf4d22c-5b24-47fb-b489-49388fcca5b1
feature: Dimensions
TQID: 'https://experienceleague.adobe.com/tsMhHR84qhEUZIZjPTluCJOHMPc37-JRwLsipAycgJI'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
    internal-label: Data configuration and collection
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
  - id: b22bc0f7-b089-4966-95a1-31e7b3b69b79
    internal-label: Dimensions
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
    internal-label: Data management
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
    internal-label: Privacy
source-git-commit: 9a50beeb0aa51cf9f4baf212566947c14029ce8e
workflow-type: tm+mt
source-wordcount: '278'
ht-degree: 83%
---
# Exclusión en la administración de consentimiento

La dimensión [exclusión de administración de consentimiento](overview.md) muestra qué configuración de privacidad ha excluido explícitamente un visitante. Puede utilizar esta dimensión para filtrar los datos en función de la configuración de privacidad o ver los motivos de exclusión de privacidad más comunes.

## Rellene esta dimensión con datos

Esta dimensión recopila datos de las siguientes [variables de datos de contexto](/help/implement/vars/page-vars/contextdata.md):

* `contextData.['cm.ssf']` cuando se establece como `1`. Si `cm.ssf` es igual a `0` o está en blanco, esta variable no hace nada.
* `contextData.['opt.dmp']` cuando se establece como `N`. Si `opt.dmp` es igual a `Y`, la [Inclusión en la administración de consentimiento](cm-opt-in.md) se rellena en su lugar.
* `contextData.['opt.sell']` cuando se establece como `N`. Si `opt.sell` es igual a `Y`, la [Inclusión en la administración de consentimiento](cm-opt-in.md) se rellena en su lugar.

Su organización determina la lógica para implementar estas variables de datos de contexto. Configure cada variable de datos de contexto en cada página.

| Propiedad | Valor |
| --- | --- |
| **variable de AppMeasurement** | Ninguno (configurado mediante señales de consentimiento) |
| **Campo Web SDK / XDM** | Ninguno |
| **Parámetro de consulta** | n/a |
| **etiqueta XML** | n/a |
| **Límite de bytes** | 100 bytes |
| **Persistencia** | Hit |

## Elementos de dimensión

Los elementos de dimensión incluyen los tres valores siguientes:

* **`SSF`**: el visitante no optó por el [Reenvío del lado del servidor](/help/admin/tools/manage-rs/edit-settings/general/c-server-side-forwarding/ssf.md). Este elemento de dimensión está presente cuando la variable de datos de contexto `cm.ssf` es igual a `1`. Consulte [Información general sobre la privacidad de datos](https://experienceleague.adobe.com/docs/audience-manager/user-guide/overview/data-privacy/data-privacy.html?lang=es) en la guía del usuario de Audience Manager para obtener más información. El hit no se reenvía a Adobe Audience Manager.
* **`DMP`**: el visitante no optó por compartir en plataformas de administración de datos. Este elemento de dimensión está presente cuando la variable de datos de contexto `opt.dmp` es igual a `N`. Similar a `SSF`, el hit no se reenvía a Adobe Audience Manager.
* **`SELL`**: el visitante no optó por el uso compartido o la venta de los datos a terceros. Esta dimensión está presente cuando la variable de datos de contexto `opt.sell` es igual a `N`.

---
title: Usuarios con Experience Cloud ID
description: El número de personas en el análisis entre dispositivos que tienen un ECID.
feature: Metrics
exl-id: 072e7d2b-3a08-49c6-a892-4cea2cc10159
TQID: https://experienceleague.adobe.com/w85poHKHnDYQ0iTItr2r26q1aRpN50AsdYzg6v82Jpk
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
source-git-commit: 0ba418a49e6a226540e0791f0138027566022d6f
workflow-type: tm+mt
source-wordcount: '146'
ht-degree: 28%
---
# Usuarios con Experience Cloud ID

&quot;Personas con Experience Cloud ID&quot; es una métrica de [análisis entre dispositivos](../cda/overview.md) que muestra el número de [personas](people.md) identificadas por Adobe mediante el [servicio de ID de visitante](https://experienceleague.adobe.com/es/docs/id-service/using/home) o [Web SDK](https://experienceleague.adobe.com/en/docs/experience-platform/collection/identity/overview).

## Cálculo de esta métrica

Teniendo en cuenta cada [persona](people.md) (identificada o no identificada), esta [métrica](overview.md) aumenta si la visita contiene la cadena de consulta `mid` (basada en la cookie [`s_ecid`](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/cookies/analytics)).

Puede crear la métrica calculada `[People with ECID] ÷ [People]` para obtener el porcentaje de visitantes del sitio mediante el servicio de ID.

Consulte la métrica equivalente que no es de CDA [Visitantes con Experience Cloud ID](visitors-with-ecid.md) para obtener más información sobre la importancia de ECID y la depuración de la configuración.

---
title: Páginas no encontradas (métricas)
description: Número de hits que contienen un error.
feature: Metrics
exl-id: 71e138b5-69bb-41b0-852c-ca4af22be1f3
TQID: https://experienceleague.adobe.com/V5jVT8wh71qMrchQmmM6c4EMofHPUEI388TmAf7Zf6M
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
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '139'
ht-degree: 35%
---
# Páginas no encontradas

>[!BEGINSHADEBOX]

*En esta página de ayuda se describe cómo funciona &quot;Páginas no encontradas&quot; como métrica. Consulte la página de dimensión [Páginas no encontradas](../dimensions/pages-not-found.md) para obtener más información sobre cómo funciona como dimensión.*

>[!ENDSHADEBOX]

La [métrica](overview.md) &quot;Páginas no encontradas&quot; muestra el número de visitas configurado o en las que persiste una dimensión en el momento en que un visitante encontró un error. Esta métrica es valiosa cuando desea ver qué páginas o direcciones URL contenían mensajes de error (como un 404). A continuación, puede pasar esta información al equipo de desarrollo web, que puede determinar la causa del error y corregirlo.

## Cálculo de esta métrica

Esta métrica cuenta todos los hits en los que la variable [`pageType`](/help/implement/vars/page-vars/pagetype.md) es igual al valor de `"errorPage"`. Es el equivalente de métrica de la dimensión [Páginas no encontradas](../dimensions/pages-not-found.md).

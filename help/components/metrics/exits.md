---
title: Salidas
description: Instancia del último valor de una visita.
feature: Metrics
exl-id: 0997ed1f-29b0-403d-9ed2-644a5ff19aef
TQID: https://experienceleague.adobe.com/KTpLeq4YjWgaFR-xcq1PBENAO5mb-wV-71BODlRGGlM
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
    internal-label: Analysis Workspace
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
    internal-label: Components
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '187'
ht-degree: 88%
---
# Salidas

>[!BEGINSHADEBOX]

*Esta página de ayuda describe cómo funcionan las salidas como una métrica. Para obtener información sobre cómo funcionan las salidas como una dimensión, consulte [Dimensiones de salida](../dimensions/exit-dimensions.md).*

>[!ENDSHADEBOX]

La métrica [Salidas](overview.md) muestra el número de veces que un elemento determinado se captura como el último valor de una visita. Esta métrica es útil cuando desea conocer más sobre lo último que ven los visitantes antes de abandonar el sitio. Ver los últimos valores de una dimensión puede ayudarle a comprender y optimizar la experiencia que obtiene un visitante antes de que se vaya.

## Cálculo de esta métrica

Una vez finalizada una [visita](visits.md), registre el elemento de dimensión más reciente como una salida. Solo existe una salida por dimensión por visita. No es necesariamente el último hit de la visita si la dimensión se estableció en hits anteriores. Es una métrica basada en visitas; se aplica de forma retroactiva a todos los hits de la visita.

>[!TIP]
>
>Si ve esta métrica con una dimensión no siempre establecida en cada visita, puede ocultar el elemento de dimensión “Sin especificar” en Analysis Workspace. Haga clic en el icono de filtro y, a continuación, desmarque [!UICONTROL Incluir sin especificar (Ninguno)].

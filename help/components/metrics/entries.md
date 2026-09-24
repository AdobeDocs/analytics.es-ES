---
title: Entradas
description: Instancia del primer valor de una visita.
feature: Metrics
exl-id: f5d359ce-e6ac-4f80-a30b-ff78cc5fc8dc
TQID: https://experienceleague.adobe.com/H3LE0wm2uDL3-pILbvOXvccAJQdo5o9X3uHJ4xZe7UU
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
source-wordcount: '192'
ht-degree: 89%
---
# Entradas

>[!BEGINSHADEBOX]

*Esta página de ayuda describe cómo funcionan las entradas como una métrica. Para obtener información sobre cómo funcionan las entradas como dimensiones, consulte [Dimensiones de entrada](../dimensions/entry-dimensions.md).*

>[!ENDSHADEBOX]

La [métrica](overview.md) &quot;Entradas&quot; muestra el número de veces que un elemento determinado se captura como el primer valor de una visita. Esta métrica es útil cuando desea conocer mejor las primeras impresiones del sitio en los visitantes. Ver los primeros valores de una dimensión puede ayudarle a comprender y optimizar la experiencia que obtiene un nuevo visitante.

## Cálculo de esta métrica

Para una dimensión determinada, registre el primer elemento de dimensión visto en una visita como una entrada. Solo existe una entrada por dimensión por visita. No es necesariamente el primer hit de la visita si la dimensión no se ha establecido inicialmente. Es una métrica basada en visitas; una vez asociada a un elemento de dimensión, persiste durante el resto de la visita.

>[!TIP]
>
>Si ve esta métrica con una dimensión no siempre establecida en cada visita, puede ocultar el elemento de dimensión “Sin especificar” en Analysis Workspace. Haga clic en el icono de filtro y, a continuación, desmarque [!UICONTROL Incluir sin especificar (Ninguno)].

---
title: Entradas
description: Instancia del primer valor de una visita.
feature: Metrics
exl-id: f5d359ce-e6ac-4f80-a30b-ff78cc5fc8dc
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '191'
ht-degree: 89%

---

# Entradas

*Esta página de ayuda describe cómo funcionan las entradas como una métrica. Para obtener información sobre cómo funcionan las entradas como dimensiones, consulte [Dimensiones de entrada](../dimensions/entry-dimensions.md).*

La [métrica](overview.md) &quot;Entradas&quot; muestra el número de veces que un elemento determinado se captura como el primer valor de una visita. Esta métrica es útil cuando desea conocer mejor las primeras impresiones del sitio en los visitantes. Ver los primeros valores de una dimensión puede ayudarle a comprender y optimizar la experiencia que obtiene un nuevo visitante.

## Cálculo de esta métrica

Para una dimensión determinada, registre el primer elemento de dimensión visto en una visita como una entrada. Solo existe una entrada por dimensión por visita. No es necesariamente la primera visita individual de la visita si la dimensión no se ha establecido inicialmente. Es una métrica basada en visitas; una vez asociada a un elemento de dimensión, persiste durante el resto de la visita.

>[!TIP]
>
>Si ve esta métrica con una dimensión no siempre establecida en cada visita, puede ocultar el elemento de dimensión “Sin especificar” en Analysis Workspace. Haga clic en el icono de filtro y, a continuación, desmarque [!UICONTROL Incluir sin especificar (Ninguno)].

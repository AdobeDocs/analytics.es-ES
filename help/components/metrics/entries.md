---
title: Entradas
description: Instancia del primer valor de una visita.
translation-type: tm+mt
source-git-commit: 554ced510600a4d5866e89806b058b5d2d9a3edf
workflow-type: tm+mt
source-wordcount: '191'
ht-degree: 1%

---


# Entradas

*Esta página de ayuda describe cómo funcionan las entradas como una métrica. Para obtener información sobre cómo funcionan las entradas como dimensiones, consulte Dimensiones[](../dimensions/entry-dimensions.md)de entrada.*

La métrica &quot;Entradas&quot; muestra el número de veces que un valor de dimensión dado se captura como el primer valor de una visita. Esta métrica es útil cuando desea conocer mejor las primeras impresiones que los visitantes tienen en el sitio. Ver los primeros valores de una dimensión puede ayudarle a comprender y optimizar la experiencia que obtiene un nuevo visitante.

## Cómo se calcula esta métrica

Para una dimensión determinada, registre el primer valor de dimensión visto en una visita como una entrada. Solo existe una entrada por dimensión por visita. No es necesariamente la primera visita individual de la visita si la dimensión no se ha establecido inicialmente. Es una métrica basada en visitas; una vez asociado a un valor de dimensión, persiste durante el resto de la visita.

>[!TIP] Si vista esta métrica con una dimensión no siempre establecida en cada visita, puede ocultar el valor de dimensión &#39;No especificado&#39; en Espacio de trabajo de Análisis. Haga clic en el icono de filtro y, a continuación, desmarque [!UICONTROL Incluir sin especificar (Ninguno)].

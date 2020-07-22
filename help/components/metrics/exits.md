---
title: Salidas
description: Instancia del último valor de una visita.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '186'
ht-degree: 1%

---


# Salidas

*Esta página de ayuda describe cómo funcionan las salidas como una métrica. Para obtener información sobre cómo funcionan las salidas como una dimensión, consulte[Dimensiones](../dimensions/exit-dimensions.md)de salida.*

La métrica &#39;Salidas&#39; muestra el número de veces que un elemento de dimensión determinado se captura como el último valor de una visita. Esta métrica es útil cuando desea conocer más sobre lo último que ven los visitantes antes de abandonar el sitio. Ver los últimos valores de una dimensión puede ayudarle a comprender y optimizar la experiencia que obtiene un visitante antes de que se vaya.

## Cómo se calcula esta métrica

Cuando haya finalizado una [visita](visits.md) , registre el elemento de dimensión más reciente como una salida. Solo existe una salida por dimensión por visita. No es necesariamente la última visita individual de la visita si la dimensión se estableció en visitas individuales anteriores. Es una métrica basada en visitas; se aplica de forma retroactiva a todas las visitas.

>[!TIP]
>
>Si vista esta métrica con una dimensión no siempre establecida en cada visita, puede ocultar el elemento de dimensión &#39;No especificado&#39; en Analysis Workspace. Haga clic en el icono de filtro y, a continuación, desmarque [!UICONTROL Incluir sin especificar (Ninguno)].

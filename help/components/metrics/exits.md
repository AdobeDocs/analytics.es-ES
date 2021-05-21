---
title: Salidas
description: Instancia del último valor de una visita.
exl-id: 0997ed1f-29b0-403d-9ed2-644a5ff19aef
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '186'
ht-degree: 100%

---

# Salidas

*Esta página de ayuda describe cómo funcionan las salidas como una métrica. Para obtener información sobre cómo funcionan las salidas como una dimensión, consulte [Dimensiones de salida](../dimensions/exit-dimensions.md).*

La métrica “Salidas” muestra el número de veces que un elemento determinado se captura como el último valor de una visita. Esta métrica es útil cuando desea conocer más sobre lo último que ven los visitantes antes de abandonar el sitio. Ver los últimos valores de una dimensión puede ayudarle a comprender y optimizar la experiencia que obtiene un visitante antes de que se vaya.

## Cálculo de esta métrica

Una vez finalizada una [visita](visits.md), registre el elemento de dimensión más reciente como una salida. Solo existe una salida por dimensión por visita. No es necesariamente la última visita individual de la visita si la dimensión se estableció en visitas individuales anteriores. Es una métrica basada en visitas; se aplica de forma retroactiva a todas las visitas.

>[!TIP]
>
>Si ve esta métrica con una dimensión no siempre establecida en cada visita, puede ocultar el elemento de dimensión “Sin especificar” en Analysis Workspace. Haga clic en el icono de filtro y, a continuación, desmarque [!UICONTROL Incluir sin especificar (Ninguno)].

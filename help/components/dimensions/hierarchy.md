---
title: Jerarquía
description: Dimensión personalizada que se puede utilizar en la creación de informes.
feature: Dimensions
source-git-commit: f435453f655caef89460de42ebecf489b021dc47
workflow-type: ht
source-wordcount: '163'
ht-degree: 100%

---

# Jerarquía

>[!IMPORTANT]
>
>Esta dimensión desaparece y no es una dimensión disponible en Analysis Workspace. Adobe recomienda usar [eVars](evar.md) y clasificaciones en su lugar.

Las jerarquías son variables personalizadas que se pueden utilizar como desee. No se mantienen más allá de la visita en la que están configuradas. Hay disponibles hasta 5 jerarquías si su contrato con Adobe lo permite.

## Rellenar jerarquías con datos

Cada jerarquía recopila datos de las cadenas de consulta [`h1` - `h5` ](/help/implement/validate/query-parameters.md) en solicitudes de imagen. Por ejemplo, el parámetro de cadena de consulta `h1` recopila datos para la jerarquía 1, mientras que el parámetro de cadena de consulta `h4` recopila datos para la jerarquía 4.

AppMeasurement, que compila variables JavaScript en una solicitud de imagen para la recopilación de datos, utiliza las variables `hier1` - `hier5`. Consulte [hier](/help/implement/vars/page-vars/hier.md) en la Guía del usuario sobre implementación para ver las directrices de implementación.

## Elementos de dimensión

Dado que las jerarquías contienen cadenas personalizadas en la implementación, la organización determina los elementos de dimensión de cada jerarquía. Asegúrese de registrar el propósito de cada jerarquía y los elementos de dimensión típicos en un [documento de diseño de solución](/help/implement/prepare/solution-design.md).

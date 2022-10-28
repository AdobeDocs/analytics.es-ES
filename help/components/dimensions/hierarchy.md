---
title: Jerarquía
description: Dimensión personalizada que se puede usar en los informes.
feature: Dimensions
source-git-commit: f435453f655caef89460de42ebecf489b021dc47
workflow-type: tm+mt
source-wordcount: '163'
ht-degree: 22%

---

# Jerarquía

>[!IMPORTANT]
>
>Esta dimensión se ha eliminado y no es una dimensión disponible en Analysis Workspace. Adobe recomienda usar [eVars](evar.md) y clasificaciones en su lugar.

Las jerarquías son variables personalizadas que se pueden utilizar como desee. No se mantienen más allá de la visita en la que están configuradas. Hay disponibles hasta 5 jerarquías si su contrato con Adobe lo admite.

## Rellenar jerarquías con datos

Cada jerarquía recopila datos de la variable [`h1` - `h5` cadena de consulta](/help/implement/validate/query-parameters.md) en solicitudes de imagen. Por ejemplo, la variable `h1` el parámetro de cadena de consulta recopila datos para la jerarquía 1, mientras que la variable `h4` el parámetro de cadena de consulta recopila datos para la jerarquía 4.

AppMeasurement, que compila variables JavaScript en una solicitud de imagen para la recopilación de datos, utiliza las variables `hier1` - `hier5`. Consulte [hier](/help/implement/vars/page-vars/hier.md) en la Guía del usuario de implementación para las directrices de implementación.

## Elementos de dimensión

Dado que las jerarquías contienen cadenas personalizadas en la implementación, su organización determina cuáles son los elementos de dimensión para cada jerarquía. Asegúrese de registrar el propósito de cada jerarquía y los elementos de dimensión típicos en una [documento de diseño de solución](/help/implement/prepare/solution-design.md).

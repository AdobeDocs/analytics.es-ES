---
title: Vínculo de salida
description: Nombre del vínculo de salida.
feature: Dimensions
exl-id: 090d5fee-4b35-4be7-866c-5ef1d1c4c0a6
source-git-commit: a15d2b596c1e8b70e91efb49dd607fdbb0ceec3c
workflow-type: tm+mt
source-wordcount: '165'
ht-degree: 75%

---

# Vínculo de salida

El &quot;Vínculo de salida&quot; [dimension](overview.md) indica los nombres de los vínculos de salida implementados en el sitio. Esta dimensión es útil cuando desea comprender qué vínculos son los más populares y que apuntan a dominios fuera del sitio.

## Rellene esta dimensión con datos

Esta dimensión recopila datos de la [`pev2` cadena de consulta &#x200B;](/help/implement/validate/query-parameters.md) en solicitudes de imagen para visitas individuales que también tienen la cadena de consulta `pe` con el valor de `lnk_e`. Si la cadena de consulta `pe` tiene un valor diferente en la visita, esta dimensión no recopila datos. La longitud máxima de esta dimensión es de 100 bytes.

Si desea enviar datos a esta dimensión mediante AppMeasurement, envíe una solicitud de imagen [`tl()`](/help/implement/vars/functions/tl-method.md) con un argumento de tipo de vínculo de `"e"`. Rellene el argumento del nombre del vínculo con el valor deseado.

## Elementos de dimensión

Dado que esta variable se basa en una cadena personalizada en la implementación, su organización determina cuáles son los elementos de dimensión. Adobe recomienda agrupar los vínculos en categorías significativas en función de sus necesidades de creación de informes.

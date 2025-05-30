---
title: Vínculo personalizado
description: Nombre del vínculo personalizado.
feature: Dimensions
exl-id: c153f710-f03f-4be6-8e18-5ebf2ed80f01
source-git-commit: a15d2b596c1e8b70e91efb49dd607fdbb0ceec3c
workflow-type: tm+mt
source-wordcount: '161'
ht-degree: 75%

---

# Vínculo personalizado

El &quot;Vínculo personalizado&quot; [dimension](overview.md) indica los nombres de los vínculos personalizados implementados en el sitio. Esta dimensión es valiosa cuando desea comprender los tipos de vínculos en los que más hacen clic los visitantes.

## Rellene esta dimensión con datos

Esta dimensión recopila datos de la [`pev2` cadena de consulta ](/help/implement/validate/query-parameters.md) en solicitudes de imagen para visitas individuales que también tienen la cadena de consulta `pe` con el valor de `lnk_o`. Si la cadena de consulta `pe` tiene un valor diferente en la visita, esta dimensión no recopila datos. La longitud máxima de esta dimensión es de 100 bytes.

Si desea enviar datos a esta dimensión mediante AppMeasurement, envíe una solicitud de imagen [`tl()`](/help/implement/vars/functions/tl-method.md) con un argumento de tipo de vínculo de `"o"`. Rellene el argumento del nombre del vínculo con el valor deseado.

## Elementos de dimensión

Dado que esta variable se basa en una cadena personalizada en la implementación, su organización determina cuáles son los elementos de dimensión. Adobe recomienda agrupar los vínculos en categorías significativas en función de sus necesidades de creación de informes.

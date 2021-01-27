---
title: Vínculo personalizado
description: Nombre del vínculo personalizado.
translation-type: tm+mt
source-git-commit: 423e9b753a3b7b1e0a8e8b9748f9694d718abd18
workflow-type: tm+mt
source-wordcount: '152'
ht-degree: 80%

---


# Vínculo personalizado

La dimensión “Vínculo personalizado” indica los nombres de los vínculos personalizados implementados en el sitio. Esta dimensión es valiosa cuando desea comprender los tipos de vínculos en los que más hacen clic los visitantes.

## Rellene esta dimensión con datos

Esta dimensión recopila datos de la [`pev2` cadena de consulta ](/help/implement/validate/query-parameters.md) en solicitudes de imagen para visitas individuales que también tienen la cadena de consulta `pe` con el valor de `lnk_o`. Si la cadena de consulta `pe` tiene un valor diferente en la visita, esta dimensión no recopila datos.

Si desea enviar datos a esta dimensión mediante AppMeasurement, envíe una solicitud de imagen [`tl()`](/help/implement/vars/functions/tl-method.md) con un argumento de tipo de vínculo `"o"`. Rellene el argumento del nombre del vínculo con el valor deseado.

## Elementos de dimensión

Dado que esta variable se basa en una cadena personalizada en la implementación, su organización determina cuáles son los elementos de dimensión. Adobe recomienda agrupar los vínculos en categorías significativas en función de sus necesidades de creación de informes.

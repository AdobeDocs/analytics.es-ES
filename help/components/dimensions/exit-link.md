---
title: Vínculo de salida
description: Nombre del vínculo de salida.
translation-type: ht
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: ht
source-wordcount: '152'
ht-degree: 100%

---


# Vínculo de salida

La dimensión “Vínculo de salida” indica los nombres de los vínculos de salida implementados en el sitio. Esta dimensión es útil cuando desea comprender qué vínculos son los más populares y que apuntan a dominios fuera del sitio.

## Rellene esta dimensión con datos

Esta dimensión recopila datos de la [`pev2`cadena de consulta](/help/implement/validate/query-parameters.md) en solicitudes de imagen para visitas individuales que también tienen la cadena de consulta `pe` con el valor de `lnk_e`. Si la cadena de consulta `pe` tiene un valor diferente en la visita, esta dimensión no recopila datos.

Si desea enviar datos a esta dimensión mediante AppMeasurement:

* Rellene la variable [`linkName`](/help/implement/vars/config-vars/linkname.md) con el valor deseado.
* Configure la variable [`linkType`](/help/implement/vars/config-vars/linktype.md) como `"e"`.
* Envíe una solicitud de imagen [`tl()`](/help/implement/vars/functions/tl-method.md).

## Elementos de dimensión

Dado que esta variable se basa en una cadena personalizada en la implementación, su organización determina cuáles son los elementos de dimensión. Adobe recomienda agrupar los vínculos en categorías significativas en función de sus necesidades de creación de informes.

---
title: Vínculo personalizado
description: Nombre del vínculo personalizado.
translation-type: tm+mt
source-git-commit: c9e696201d0e9ec97dcdd6ff797ca72244dcf366
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 0%

---


# Vínculo personalizado

La dimensión &#39;Vínculo personalizado&#39; informa los nombres de los vínculos personalizados implementados en el sitio. Esta dimensión es valiosa cuando desea comprender los tipos de vínculos en los que más hacen clic los visitantes.

## Rellenar esta dimensión con datos

Esta dimensión recopila datos de la cadena [`pev2` de](/help/implement/validate/query-parameters.md) consulta en solicitudes de imagen para visitas individuales que también tienen la cadena de `pe` consulta con el valor de `lnk_o`. Si la cadena de `pe` consulta tiene un valor diferente en la visita, esta dimensión no recopila datos.

Si desea enviar datos a esta dimensión mediante AppMeasurement:

* Rellene la [`linkName`](/help/implement/vars/config-vars/linkname.md) variable con el valor deseado.
* Set the [`linkType`](/help/implement/vars/config-vars/linktype.md) variable to `"o"`.
* Enviar una solicitud [`tl()`](/help/implement/vars/functions/tl-method.md) de imagen.

## Valores de dimensión

Dado que esta variable se basa en una cadena personalizada en la implementación, su organización determina cuáles son los valores de dimensión. Adobe recomienda agrupar los vínculos en categorías significativas en función de sus necesidades de sistema de informes.

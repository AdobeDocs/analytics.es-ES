---
title: Código de seguimiento
description: Nombre del código de seguimiento o campaña.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '112'
ht-degree: 3%

---


# Código de seguimiento

La dimensión &#39;Código de seguimiento&#39; lista los nombres de los códigos de seguimiento en el sitio. Esta dimensión se recopila generalmente mediante parámetros de cadena de consulta. Puede colocar vínculos con diferentes valores de parámetros de cadena de consulta en diferentes lugares de Internet. Esta dimensión informa qué vínculos fueron los más exitosos en conducir el tráfico al sitio.

## Rellenar esta dimensión con datos

Esta dimensión recupera datos de la cadena [`v0` de](/help/implement/validate/query-parameters.md) consulta en solicitudes de imagen. AppMeasurement recopila estos datos mediante la [`campaign`](/help/implement/vars/page-vars/campaign.md) variable.

## Elementos de dimensión

Los elementos de dimensión incluyen los nombres de los códigos de seguimiento en el sitio. Su organización determina qué elementos de dimensión específicos desea utilizar.

---
title: Número de visita
description: La enésima visita del visitante.
translation-type: tm+mt
source-git-commit: 05ea2778cd5cd324c660fd0f1d2ac02373829f0f
workflow-type: tm+mt
source-wordcount: '162'
ht-degree: 0%

---


# Número de visita

Los informes de dimensión &#39;Número de visita&#39; en los que se encuentra actualmente el visitante. Cuando una nueva visita inicio, este valor de dimensión aumenta en 1. Esta dimensión es útil cuando desea comprender cuán comprometidos son los visitantes al regresar al sitio. Es una dimensión basada en visitas, lo que significa que contiene el mismo valor para toda la visita y no puede cambiar. Se aplica a la duración del visitante, independientemente del intervalo de fechas del proyecto.

## Rellenar esta dimensión con datos

Esta dimensión funciona de forma predeterminada para todas las implementaciones. Si un grupo de informes contiene datos, esta dimensión funciona.

## Valores de dimensión

Los valores de dimensión incluyen la cadena `"Visit number"` seguida de la representación numérica de la visita en la que se encuentra el visitante. Por ejemplo: si el visitante nunca antes había estado en el sitio, su primera visita pertenece al valor de dimensión `"Visit number 1"`. Si esta es la 13ª visita del visitante a su sitio, pertenecen al valor de dimensión `"Visit number 13"`.

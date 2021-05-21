---
title: Número de visita
description: La enésima visita del visitante.
exl-id: daef34b3-c270-476d-a45c-a20be6138c6b
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '162'
ht-degree: 100%

---

# Número de visita

Los informes de dimensión “Número de visita” en los que se encuentra actualmente el visitante. Cuando se inicia una nueva visita, este elemento de dimensión aumenta en 1. Esta dimensión es útil cuando desea comprender el nivel de participación de los visitantes al regresar al sitio. Es una dimensión basada en visitas, lo que significa que contiene el mismo valor para toda la visita y no puede cambiar. Se aplica a la duración del visitante, independientemente del intervalo de fechas del proyecto.

## Rellene esta dimensión con datos

Esta dimensión funciona de forma predeterminada para todas las implementaciones. Si un grupo de informes contiene datos, esta dimensión funciona.

## Elementos de dimensión

Los elementos de dimensión incluyen la cadena `"Visit number"` seguida de la representación numérica de la visita en la que se encuentra el visitante. Por ejemplo, si el visitante nunca antes había estado en el sitio, su primera visita pertenece al elemento de dimensión `"Visit number 1"`. Si esta es la 13.ª visita del visitante a su sitio, pertenecen al elemento de dimensión `"Visit number 13"`.

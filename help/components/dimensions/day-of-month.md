---
title: Día del mes
description: El día numérico del mes, independientemente de qué mes.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '138'
ht-degree: 4%

---


# Día del mes

La dimensión &#39;Día del mes&#39; informa el día numérico de cualquier mes dado como un elemento de dimensión. Por ejemplo: si tiene un informe que abarca del 1 de enero al 31 de marzo, el primero de cada mes se agrupa en el mismo elemento de dimensión. Este informe es valioso si desea que un informe se desglose por día, pero no desea que una fecha estática sea un elemento de dimensión. Es especialmente valiosa como dimensión en los informes programados, ya que esta dimensión se desplaza con el intervalo de fechas seleccionado.

## Rellenar esta dimensión con datos

Esta dimensión funciona de forma predeterminada para todas las implementaciones. Si un grupo de informes contiene datos, esta dimensión funciona.

## Elementos de dimensión

Los elementos de dimensión incluyen los números `1` - `31`, que representan el día del mes en que se produjo la visita.

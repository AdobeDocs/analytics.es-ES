---
description: Número de veces que se captura un valor específico más el número de vistas de página para el que persistió el valor dado. En otras palabras, las ocurrencias son la suma de vistas de página y eventos de página. Las ocurrencias están disponibles en Analysis Workspace y en Ad Hoc Analysis.
title: Ocurrencias
topic: Metrics
uuid: ff999fba-fcb7-4b16-9446-001facd0f15d
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Ocurrencias

Número de veces que se captura un valor específico más el número de vistas de página para el que persistió el valor dado. En otras palabras, las ocurrencias son la suma de vistas de página y eventos de página. Las ocurrencias están disponibles en Analysis Workspace y en Ad Hoc Analysis.

## Comparación de instancias y ocurrencias  {#section_4B0741AC1A78456E98AE0D4D28D70D29}

Se muestran dos métricas que parecen similares:

**[Instancias](/help/components/c-variables/c-metrics/metrics-instance.md)**: el número de veces que se estableció un valor para una variable.

**Ocurrencias**: el número total de veces que se estableció o persistió un valor.

| Situación | Descripción |
|---|---|
| Más ocurrencias que instancias | Es lo esperado para las variables de conversión, ya que las ocurrencias también incluyen el número de veces que se definió la variable (instancias). |
| Más instancias que ocurrencias | No es posible en los informes porque todas las instancias se registran también como ocurrencias. |
| Instancias igual a ocurrencias | Es lo más común en las variables de tráfico ya que por naturaleza no persisten más allá de la solicitud de imagen. |

>[!MORELIKETHIS]
>
>* [Instancias](/help/components/c-variables/c-metrics/metrics-instance.md)


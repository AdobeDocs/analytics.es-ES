---
description: Número de veces que se captura un valor específico más el número de vistas de página para el que persistió el valor dado. En otras palabras, las ocurrencias son la suma de vistas de página y eventos de página. Las ocurrencias están disponibles en Analysis Workspace y en Ad Hoc Analysis.
seo-description: Número de veces que se captura un valor específico más el número de vistas de página para el que persistió el valor dado. En otras palabras, las ocurrencias son la suma de vistas de página y eventos de página. Las ocurrencias están disponibles en Analysis Workspace y en Ad Hoc Analysis.
seo-title: Ocurrencias
solution: Analytics
title: Ocurrencias
topic: Métricas
uuid: ff 999 fba-fcb 7-4 b 16-9446-001 facd 0 f 15 d
translation-type: tm+mt
source-git-commit: ecc762f73f9a303cebf48668b807fef9a2f055c5

---


# Ocurrencias

Número de veces que se captura un valor específico más el número de vistas de página para el que persistió el valor dado. En otras palabras, las ocurrencias son la suma de vistas de página y eventos de página. Las ocurrencias están disponibles en Analysis Workspace y en Ad Hoc Analysis.

## Comparación de instancias y ocurrencias {#section_4B0741AC1A78456E98AE0D4D28D70D29}

Se muestran dos métricas que parecen similares:

**[Instancias](../../../components/c-variables/c-metrics/metrics-instance.md#concept_E3D0FEC81E1F4987B39CC467F19FFCFF)**: el número de veces que se estableció un valor para una variable.

**Ocurrencias**: el número total de veces que se estableció o persistió un valor.

| Situación | Descripción |
|---|---|
| Más ocurrencias que instancias | Es lo esperado para las variables de conversión, ya que las ocurrencias también incluyen el número de veces que se definió la variable (instancias). |
| Más instancias que ocurrencias | No es posible en los informes porque todas las instancias se registran también como ocurrencias. |
| Instancias igual a ocurrencias | Es lo más común en las variables de tráfico ya que por naturaleza no persisten más allá de la solicitud de imagen. |

>[!MORE_LIKE_THIS]
>
>* [Instancias](/help/components/c-variables/c-metrics/metrics-instance.md)


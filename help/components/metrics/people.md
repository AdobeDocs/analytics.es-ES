---
title: Personas
description: Número de individuos únicos, normalmente con varios dispositivos.
exl-id: 0136b843-2a1e-44d5-b5a6-e0fb03b7b995
source-git-commit: 639897682c9a28df7dc642dd7c68ad992fde40a9
workflow-type: tm+mt
source-wordcount: '161'
ht-degree: 80%

---

# Personas

Existen dos versiones de la métrica Personas.

Para los miembros de [Device Co-op](https://experienceleague.adobe.com/docs/device-co-op/using/data/people.html?lang=es) que no utilizan el [análisis entre dispositivos](../cda/overview.md), la métrica Personas es un recuento derivado estadísticamente del número de personas representadas en el informe. Es el número de los ID de visitante que ha identificado Device Co-op, más el número de dispositivos que no ha identificado.

Dentro de un grupo de informes virtuales de [análisis en dispositivos múltiples](../cda/overview.md), la métrica Personas no es una derivación estadística. En cambio, es la suma de los particulares que se identifican en el informe, más el número de dispositivos que no se identifican como pertenecientes a una persona.

Si un visitante se identifica a mitad de la visita, puede contar como 2 personas (1 persona no identificada y 1 persona identificada). [](/help/components/cda/replay.md) Vuelve a mostrar este recuento doble en función de la ventana de informes, la frecuencia de reproducción y la tasa de éxito. Consulte [Dispositivos únicos](unique-devices.md) para obtener más información.

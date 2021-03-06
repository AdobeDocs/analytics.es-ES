---
title: Personas
description: Número de individuos únicos, normalmente con varios dispositivos.
feature: Metrics
exl-id: 0136b843-2a1e-44d5-b5a6-e0fb03b7b995
source-git-commit: 7d5383e1ee3bee189d3dd48bc6b899f4108f7ba8
workflow-type: ht
source-wordcount: '161'
ht-degree: 100%

---

# Personas

Existen dos versiones de la métrica Personas.

Para los miembros de [Device Co-op](https://experienceleague.adobe.com/docs/device-co-op/using/data/people.html?lang=es) que no utilizan el [análisis entre dispositivos](../cda/overview.md), la métrica Personas es un recuento derivado estadísticamente del número de personas representadas en el informe. Es el número de los ID de visitante que ha identificado Device Co-op, más el número de dispositivos que no ha identificado.

Dentro de un grupo de informes virtuales de [análisis en dispositivos múltiples](../cda/overview.md), la métrica Personas no es una derivación estadística. En cambio, es la suma de los particulares que se identifican en el informe, más el número de dispositivos que no se identifican como pertenecientes a una persona.

Si se identifica un visitante a mitad de la visita, ese visitante puede contar como dos personas (una persona no identificada y una identificada). [Reproducir](/help/components/cda/replay.md) mitiga este recuento doble en función de la ventana de informes, la frecuencia de reproducción y la tasa de éxito. Consulte [Dispositivos únicos](unique-devices.md) para obtener más información.

---
title: Personas
description: Número de individuos únicos, normalmente con varios dispositivos.
exl-id: 0136b843-2a1e-44d5-b5a6-e0fb03b7b995
source-git-commit: 7f9442d6be7930b9e040539dc683c62953aba342
workflow-type: tm+mt
source-wordcount: '149'
ht-degree: 53%

---

# Personas

Existen dos versiones de la métrica Personas.

Para los miembros de [Device Co-op](https://experienceleague.adobe.com/docs/device-co-op/using/data/people.html?lang=es) que no utilizan el [análisis entre dispositivos](../cda/overview.md), la métrica Personas es un recuento derivado estadísticamente del número de personas representadas en el informe. Es el número de los ID de visitante que ha identificado Device Co-op, más el número de dispositivos que no ha identificado.

Dentro de un grupo de informes virtuales [Cross-Device analytics](../cda/overview.md) , la métrica &quot;Personas&quot; no es una derivación estadística. En su lugar, es la suma de las personas identificadas en el informe, más el número de dispositivos que no se identifican como pertenecientes a una persona.

Si se identifica un visitante a mitad de la visita, ese visitante puede contar como 2 personas hasta que se ejecute [Reproducir](/help/components/cda/replay.md) (1 persona no identificada y 1 persona identificada). Consulte [Dispositivos únicos](unique-devices.md) para obtener más información.

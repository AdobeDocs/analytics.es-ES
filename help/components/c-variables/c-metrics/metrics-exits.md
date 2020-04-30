---
description: El número de veces que un valor determinado se captura como el último de una visita. Las salidas solo tienen lugar una vez por visita.
title: Salidas
topic: Metrics
uuid: cd5436ef-65d3-431b-a24f-aceff8542c50
translation-type: tm+mt
source-git-commit: 8d6685d241443798be46c19d70d8150d222ab9e8

---


# Salidas

El número de veces que un valor determinado se captura como el último de una visita. Las salidas solo tienen lugar una vez por visita.

Las páginas de salida tienen un alcance de desglose de visitas, lo que significa que persisten a través de todas las visitas. Consulte [Contenedores de segmentación y de desglose](https://docs.adobe.com/content/help/en/analytics/components/segmentation/seg-overview.html) para obtener más información.

Al aplicarse a una dimensión, las Salidas se cuentan en el último valor de una visita, que puede ocurrir en cualquier visita individual durante la visita. Si no existen valores en la última visita individual, la Salida se atribuye al valor más reciente.

Si ocurre una salida fuera del intervalo del informe para una visita dentro del intervalo del informe, se incluirá siempre y cuando no esté a lo largo de un límite de mes (dentro del conjunto de datos).

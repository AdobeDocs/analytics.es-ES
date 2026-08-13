---
title: customerPerspective
description: Especifica si se produjo una visita de una aplicación móvil mientras la aplicación estaba en primer o segundo plano.
feature: Appmeasurement Implementation
role: Admin, Developer
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: d4db20e3498d54162806b3fdef0b34f45c93a6ff
workflow-type: tm+mt
source-wordcount: 199
ht-degree: 0%

---

# customerPerspective

La variable `customerPerspective` especifica si se produjo una visita de una aplicación móvil mientras la aplicación estaba en primer o segundo plano. Se envía a la recopilación de datos de Adobe como parámetro de consulta `cp` y rellena la dimensión [Tipo de visita](/help/components/dimensions/hit-type.md).

## Valores válidos

`customerPerspective` acepta los siguientes valores de cadena:

* `foreground`: la visita se produjo mientras la aplicación estaba en uso activo.
* `background`: la visita se produjo mientras la aplicación se ejecutaba en segundo plano, como una actualización de ubicación o una visita desencadenada por una notificación push.

## Configuración de esta variable

Adobe Mobile SDK (versión 4.13.6 y superior) establece `customerPerspective` automáticamente; normalmente, no lo establece manualmente. Las visitas enviadas desde un explorador a través de AppMeasurement siempre informan como `foreground`. Si la variable está ausente de una visita, esa visita se trata como una visita en primer plano.

## Impacto en los informes

La distinción entre primer plano y segundo plano afecta al modo en que se procesan las visitas:

* Las visitas se cuentan solo cuando contienen al menos una visita en primer plano.
* Las visitas en segundo plano aún pueden atribuirse a eventos de conversión y pueden analizarse a través de [sesiones según el contexto](/help/components/vrs/vrs-mobile-visit-processing.md) en grupos de informes virtuales. Este comportamiento es útil para medir la eficacia de las notificaciones push.

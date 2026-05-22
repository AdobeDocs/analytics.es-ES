---
title: trackingServer
description: Dominio utilizado para enviar datos a Adobe a través de HTTP.
feature: Appmeasurement Implementation
exl-id: bcc23286-4dd5-45ac-ac6f-7b60e95cb798
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/6H8uZ4J-mT8NcC4OiiTgtBnP8eAgaMMzxzUHkS-9kGs'
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 120
ht-degree: 19%

---

# trackingServer

>[!IMPORTANT]
>
>Esta variable está obsoleta. Con la prevalencia de HTTPS, use [`trackingServerSecure`](trackingserversecure.md) en su lugar.

La variable `trackingServer` determina el dominio que utiliza AppMeasurement para enviar datos a Adobe a través de HTTP. Si esta variable no se define correctamente, la implementación puede experimentar una pérdida de datos.

Antes del [servicio de identidad de Adobe Experience Cloud](https://experienceleague.adobe.com/es/docs/id-service/using/home), esta variable también determinaba dónde se configuraban las cookies de terceros. Adobe recomienda encarecidamente utilizar el servicio de ID en todas las implementaciones siempre que sea posible.

AppMeasurement usa `trackingServer` como alternativa si [`trackingServerSecure`](trackingserversecure.md) no está establecido. Muchas implementaciones anteriores no establecen `trackingServerSecure`, por lo que se usa `trackingServer` como alternativa en páginas seguras. Con la prevalencia de HTTPS, Adobe recomienda usar `trackingServerSecure` siempre que sea posible.

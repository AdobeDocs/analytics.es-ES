---
title: trackingServer
description: Dominio utilizado para enviar datos a Adobe a través de HTTP.
feature: Appmeasurement Implementation
exl-id: bcc23286-4dd5-45ac-ac6f-7b60e95cb798
role: Admin, Developer
source-git-commit: 35675c2e65456a175d1516dd421b80d2af809286
workflow-type: tm+mt
source-wordcount: '112'
ht-degree: 13%

---

# trackingServer

>[!IMPORTANT]
>
>Esta variable está obsoleta. Con la prevalencia de HTTPS, use [`trackingServerSecure`](trackingserversecure.md) en su lugar.

La variable `trackingServer` determina el dominio que utiliza AppMeasurement para enviar datos a Adobe a través de HTTP. Si esta variable no se define correctamente, la implementación puede experimentar una pérdida de datos.

Antes del [servicio de identidad de Adobe Experience Cloud](https://experienceleague.adobe.com/es/docs/id-service/using/home), esta variable también determinaba dónde se configuraban las cookies de terceros. Adobe recomienda encarecidamente utilizar el servicio de ID en todas las implementaciones siempre que sea posible.

AppMeasurement usa `trackingServer` como alternativa si [`trackingServerSecure`](trackingserversecure.md) no está establecido. Muchas implementaciones anteriores no establecen `trackingServerSecure`, por lo que se usa `trackingServer` como alternativa en páginas seguras. Con la prevalencia de HTTPS, Adobe recomienda usar `trackingServerSecure` siempre que sea posible.

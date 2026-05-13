---
title: Funciones y métodos
description: Descubra cómo puede utilizar las funciones y los métodos que Adobe ofrece en su implementación.
feature: Appmeasurement Implementation
exl-id: 9ef5bd92-fae1-4fe4-90ea-c735e8ff4b9c
role: Admin, Developer
TQID: https://experienceleague.adobe.com/dKPvTPeRa7-SIFyIDU-7Mlob-3jsrfvhWmKeAveHGEc
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: c069c44e-5426-4c1a-accc-8028662f2fdeid: c8add8f2-4250-4fd9-9cde-9707036c567did: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 142
ht-degree: 100%

---

# Funciones y métodos

Adobe ofrece varias funciones y métodos que puede usar en la implementación. Cuando hace referencia a estas funciones o métodos, realizan tareas comunes con una sola línea de código.

Algunas de estas líneas únicas de código pertenecen a las siguientes categorías:

* **Seguimiento de llamadas**: los métodos más comunes y vitales en muchas implementaciones. Incluyen los métodos [`t()`](t-method.md) y [`tl()`](tl-method.md).
* **Utilidades de AppMeasurement**: en versiones anteriores de AppMeasurement, las implementaciones tenían que escribir su propio código para realizar estas tareas. Adobe proporciona estos métodos de utilidad para racionalizar estas tareas comunes. Las utilidades de AppMeasurement incluyen [`Util.cookieRead()`](util-cookieread.md), [`Util.cookieWrite()`](util-cookiewrite.md) y [`Util.getQueryParam()`](util-getqueryparam.md).
* **Registrar funciones**: puede escribir sus propias funciones y hacer que AppMeasurement las ejecute automáticamente antes o después de enviar una llamada de seguimiento a Adobe. Las variables incluidas en esta categoría son [`doPlugins()`](doplugins.md), [`registerPreTrackCallback()`](registerpretrackcallback.md) y [`registerPostTrackCallback()`](registerposttrackcallback.md).

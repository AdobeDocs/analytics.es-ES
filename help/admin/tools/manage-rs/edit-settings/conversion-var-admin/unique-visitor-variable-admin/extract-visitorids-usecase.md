---
description: Data Warehouse proporciona una función que le permite extraer una lista de ID de visitante. Estos ID no son ID de cookie, sino ID que captura en una de las variables de conversión. Aunque hay otras formas de obtener esta información, el siguiente ejemplo es un método abreviado para generar una solicitud de Data Warehouse.
title: 'Caso de uso: obtención de ID de visitantes'
feature: Admin Tools
role: Admin
exl-id: b1fc41af-31c7-42cd-aab7-0c659577781d
TQID: 'https://experienceleague.adobe.com/CUpKcu-jVNn77bkWM2mJvlLxYMyvfpRt4o-maC7tUBA'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
subfeature_v2:
  - id: f47edbe0-f963-46ff-a667-71011396f5f3
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 399
ht-degree: 6%

---

# Caso de uso: obtención de ID de visitantes

Data Warehouse proporciona una función que le permite extraer una lista de ID de visitante. Estos ID no son ID de cookie, sino ID que captura en una de las variables de conversión. Aunque hay otras formas de obtener esta información, el siguiente ejemplo es un método abreviado para generar una solicitud de Data Warehouse.

Pongamos por ejemplo que su empresa envía correos electrónicos comerciales a clientes y posibles clientes. Cada destinatario de correo electrónico tiene un identificador único en el sistema de correo electrónico (como *`EMAIL Contact ID`*). Configura los correos electrónicos para que, cuando los contactos reciban un mensaje y hagan clic en uno de sus vínculos, el visitante llegue al sitio web con un ID de campaña y un ID de contacto de correo electrónico único. Por ejemplo, el vínculo de correo electrónico puede resolverse como:

```js
https://www.example.com/?cid=springmailblast&mid=1363660158
```

La configuración de estos en variables de conversión (eVars) permite ver el rendimiento de cada correo electrónico (a través del ID de campaña) y la frecuencia con la que cada destinatario de correo electrónico visitó el sitio (a través del ID de contacto de correo electrónico).

Supongamos que está capturando estos ID. La mayoría de los especialistas en marketing desean segmentar el comportamiento de su sitio web y luego ver si pueden volver a enviar marketing a aquellos que cumplen determinados criterios. Por ejemplo: es posible que desee enviar un mensaje de correo electrónico de remarketing a todos los destinatarios de correo electrónico que llegaron al sitio desde el correo electrónico y vieron (o completaron) un formulario del sitio web. Para ello, busque una forma de identificar los ID de contacto de correo electrónico de quienes completan el formulario específico.

Una forma de hacerlo es utilizar un informe de subrelación de conversión para desglosar el valor eVar del ID de formulario por el eVar del ID de contacto de correo electrónico. Sin embargo, hay una función prediseñada disponible para ello con Data Warehouse. Esta función le permite saber qué eVar almacena sus ID de usuario únicos (ID de contacto de correo electrónico en este caso) y extraer fácilmente esos ID mediante Data Warehouse. Con esta función, se puede crear automáticamente una solicitud de Data Warehouse que obtenga los ID únicos de visitante para los que está interesado.

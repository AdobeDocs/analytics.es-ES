---
description: El Data Warehouse ofrece una característica que permite extraer una lista de los ID de visitante. Estos ID no son ID de cookies, sino ID que se capturan en una de las variables de conversión. Aunque hay otros modos de obtener esta información, el ejemplo siguiente es un método abreviado para generar una solicitud del Data Warehouse.
seo-description: El Data Warehouse ofrece una característica que permite extraer una lista de los ID de visitante. Estos ID no son ID de cookies, sino ID que se capturan en una de las variables de conversión. Aunque hay otros modos de obtener esta información, el ejemplo siguiente es un método abreviado para generar una solicitud del Data Warehouse.
seo-title: 'Caso de uso: obtención de ID de visitantes'
solution: Analytics
title: 'Caso de uso: obtención de ID de visitantes'
topic: Herramientas de administración
uuid: ed 228334-619 c -43 d 7-b 781-a 18 af 73 b 00 bb
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Caso de uso: obtención de ID de visitantes

El Data Warehouse ofrece una característica que permite extraer una lista de los ID de visitante. Estos ID no son ID de cookies, sino ID que se capturan en una de las variables de conversión. Aunque hay otros modos de obtener esta información, el ejemplo siguiente es un método abreviado para generar una solicitud del Data Warehouse.

Pongamos por ejemplo que su empresa envía correos electrónicos comerciales a clientes y posibles clientes. Cada destinatario tiene un ID único en el sistema de correo electrónico (por ejemplo, *`EMAIL Contact ID`*). Usted configura los correos electrónicos para que cuando los contactos reciban un correo y hagan clic en uno de sus vínculos, el visitante llegue al sitio web con un ID de campaña y un ID de contacto de correo electrónico única. Por ejemplo, el vínculo incluido en el correo electrónico puede tener como destino:

```js
https://www.test.com/?cid=springmailblast&mid=1363660158
```

Si configura estos valores en las variables de conversión (eVar), podrá ver el rendimiento de cada correo electrónico (mediante el ID de campaña) y la frecuencia con que cada usuario visitó el sitio (mediante el ID de contacto de correo electrónico).

Asumamos que captura estas ID. La mayoría de los especialistas en marketing desean segmentar el comportamiento del sitio web para luego ver si pueden volver a dirigirse a aquellos visitantes que cumplan determinados criterios. Pongamos por caso que desea enviar un nuevo correo comercial a todos los destinatarios de correo electrónico que llegaron al sitio procedentes del correo electrónico y que visualizaron (o completaron) un formulario del sitio web. Para ello, busque un modo de identificar los ID de contacto de correo electrónico de aquellos visitantes que completaron el formulario específico.

Un modo de hacerlo es utilizar un informe de subrelación de conversión con el objetivo de desglosar el valor de eVar de ID de formulario por la eVar de ID de contacto de correo electrónico. No obstante, tiene a su disposición una característica integrada que permite hacer esto utilizando el Data Warehouse. Esta característica permite indicar qué eVar almacena los ID de usuario único (en este caso, ID de contacto de correo electrónico) y permite extraer fácilmente esos ID mediante el almacén de datos. Con esta característica, puede crear automáticamente una solicitud del almacén de datos que obtenga los ID de visitante único que le interesen.

---
description: La política sobre FTP de Adobe deshabilita automáticamente el acceso a las cuentas de FTP que están inactivas durante 90 días seguidos.
keywords: ftp;sftp
title: Eliminación de cuentas y datos de FTP y SFTP
feature: FTP Export
exl-id: accf2f8d-c22c-4684-ba85-73a286325d0c
TQID: 'https://experienceleague.adobe.com/i2jpzTOx-CJzWjHMXT14EE761uGvNjcoW3f1dyF0ZlA'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
subfeature_v2:
  - id: a8bf2e97-0add-4437-b976-1fc5154911a8
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 237
ht-degree: 8%

---

# Eliminación de cuentas y datos de FTP y SFTP

La directiva de FTP y SFTP de Adobe puede deshabilitar el acceso a las cuentas de FTP y SFTP que permanezcan inactivas durante 90 días consecutivos.

Adobe puede eliminar las cuentas de FTP y SFTP deshabilitadas (y eliminar permanentemente todos los datos almacenados en esas cuentas) después de un período de gracia adicional de 90 días. Por ejemplo, una cuenta SFTP que permanece inactiva durante 90 días (del 5 de julio de 2025 al 2 de octubre de 2025) se desactiva el 3 de octubre de 2025. Luego se elimina por completo el 2 de enero de 2026.

No hay cuentas deshabilitadas antes del 5 de octubre de 2025 ni eliminadas antes del 2 de enero de 2026.

Adobe también puede eliminar de forma permanente los datos antiguos de las cuentas activas si no se ha accedido a ellos durante 90 días.

Para ayudarnos en este proceso y garantizar que el entorno FTP o SFTP siga proporcionando una transferencia de datos segura y fiable a nuestros clientes, pedimos a nuestros clientes que hagan lo siguiente:

* Elimine los datos salientes de los sistemas FTP y SFTP una vez que los datos se hayan transferido correctamente al entorno interno. Adobe puede identificar y eliminar cualquier archivo que quede en el sistema después de 90 días.
* Se debe informar a Adobe cuando las cuentas de FTP y SFTP ya no se necesiten para poder desactivarlas y eliminarlas.

---
description: Configure y utilice cuentas de FTP alojadas en Adobe.
keywords: ftp;sftp
title: Resumen de configuración de cuentas de FTP
feature: FTP Export
exl-id: 55f942fe-cb06-43e1-bd3c-57d6786278b7
TQID: https://experienceleague.adobe.com/38oslnk-IS87YU9qpOJyEoqytnrMuK5lp3VtYnTyQOg
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: d095671a-1355-40aa-8b5f-06c33c68080b
source-git-commit: 157cc2bde1047063014aff39319d5cfaa1de9b5c
workflow-type: tm+mt
source-wordcount: 316
ht-degree: 14%

---

# Resumen de configuración de cuentas de FTP o SFTP

Configure y utilice cuentas de FTP o SFTP alojadas en Adobe.

Adobe mantiene clústeres FTP o SFTP de alto rendimiento y disponibilidad, diseñados específicamente para mejorar la fiabilidad de las transferencias de archivos sin dejar de ofrecer un rendimiento excelente.

Como los eventos de mantenimiento están programados, los clientes de Adobe reciben notificaciones de mantenimiento a través del proceso estándar. Para garantizar el correcto funcionamiento de los sistemas FTP o SFTP de Adobe y seguir ofreciendo seguridad, fiabilidad y un alto rendimiento en las transferencias de datos, Adobe exige el cumplimiento de las siguientes normas:

* La mayoría de las cuentas de FTP o SFTP de Adobe (clasificaciones, fuentes de datos y otras) se habilitan automáticamente cuando se configura la característica en cuestión. En el caso de las cuentas de entrega de archivos generales y de fuentes de datos, el servicio de atención al cliente de Adobe puede configurarle una nueva cuenta de FTP o SFTP. Este proceso sirve para garantizar la seguridad y la disponibilidad de espacio en la cuenta FTP o SFTP.
* Los usuarios deben eliminar los datos que Adobe envía a la cuenta FTP o SFTP una vez que los datos se han transferido correctamente a sus sistemas.
* Se debe informar a Adobe cuando las cuentas de FTP o SFTP ya no se necesiten para poder desactivarlas.

El nombre de host del de FTP de Adobe es `ftp://ftp.omniture.com` o `ftp://ftp2.omniture.com`.

Esta información, junto con el nombre de usuario y la contraseña, debe proporcionarse en CX Enterprise (para clasificaciones y fuentes de datos), o por el representante de Adobe responsable de configurar la cuenta a petición suya. Si no sabe qué dirección de FTP o SFTP utilizar, póngase en contacto con el equipo de cuenta de Adobe, que le indicará la dirección correcta. Además, en el caso de las cuentas de clasificaciones y fuentes de datos, Adobe no procesa los archivos de FTP o SFTP a ninguna hora determinada del día. En su lugar, Adobe utiliza un script que sondea constantemente las cuentas de FTP o SFTP en busca de nuevos procesos de archivo. Los archivos cargados en estas cuentas se procesan lo más rápido posible.

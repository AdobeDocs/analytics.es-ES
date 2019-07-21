---
description: Configure y utilice cuentas de FTP alojadas en Adobe.
keywords: ftp; sftp
seo-description: Configure y utilice cuentas de FTP alojadas en Adobe.
seo-title: 'Configuración de cuentas de FTP: información general'
solution: Analytics
title: 'Configuración de cuentas de FTP: información general'
uuid: e 5524619-248 a -4 aae -9 f 64-cd 7 d 33 f 3 c 407
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Configuración de cuentas de FTP: información general

Configure y utilice cuentas de FTP alojadas en Adobe.

Adobe mantiene clústeres de FTP con un alto nivel de disponibilidad y rendimiento que están especialmente diseñados para mejorar la fiabilidad de las transferencias de archivos sin dejar de ofrecer un rendimiento excelente.

Como los eventos de mantenimiento están programados, los clientes de Adobe reciben notificaciones de mantenimiento a través del proceso estándar. Para garantizar el correcto funcionamiento de los sistemas de FTP de Adobe y seguir ofreciendo seguridad, fiabilidad y un alto rendimiento en las transferencias de datos, Adobe exige el cumplimiento de las siguientes normas:

* La mayoría de las cuentas de FTP de Adobe (clasificaciones, fuentes de datos y otras) se habilitan automáticamente cuando se configura la característica en cuestión. En el caso de las cuentas de entrega de archivos generales y de fuentes de datos, el servicio de atención al cliente de Adobe puede configurarle una nueva cuenta de FTP. La finalidad de este proceso es garantizar la seguridad y la disponibilidad de espacio en la cuenta de FTP.
* Después de haberlos transferido correctamente a sus sistemas, los usuarios deben eliminar los datos que Adobe envió a la cuenta de FTP.
* Se debe informar a Adobe cuando las cuentas de FTP ya no se necesiten para proceder a su desactivación.

The Adobe FTP host name is [!DNL ftp.omniture.com] or [!DNL ftp2.omniture.com].

This information, along with a username and password, should be provided either within the [!UICONTROL Experience Cloud] (for classifications and Data Sources), or by the Adobe representative responsible for setting up the account at your request. Si no sabe qué dirección de FTP usar, póngase en contacto con el administrador de cuentas de Adobe, que le indicará la dirección correcta. Además, en el caso de las cuentas de clasificaciones y fuentes de datos, Adobe no procesa los archivos de FTP a ninguna hora determinada del día, sino que utiliza un script que sondea continuamente las cuentas de FTP en busca de nuevos procesos de archivo. Los archivos cargados en estas cuentas se procesan lo más rápido posible.

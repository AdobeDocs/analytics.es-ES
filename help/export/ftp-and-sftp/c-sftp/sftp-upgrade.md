---
title: 'Actualización de servicios SFTP: preguntas frecuentes'
description: Preguntas frecuentes sobre la actualización prevista de los servicios SFTP.
feature: FTP Export
exl-id: e271b545-0769-4a69-9d7f-dc46bc654737
source-git-commit: 266cf18050d60f08f7e170c56453d1e1d805cb7b
workflow-type: tm+mt
source-wordcount: '402'
ht-degree: 100%

---

# Actualización de servicios SFTP: preguntas frecuentes

El 20 de septiembre de 2022, Adobe Analytics actualizará su protocolo seguro de transferencia de archivos ([SFTP]) para proporcionar una seguridad mejorada en las transferencias de archivos. Con este cambio, algunas configuraciones de cliente SFTP ya no serán compatibles. Esto solo afecta a los datos enviados o recuperados de Adobe Analytics mediante SFTP. El protocolo FTP no se verá afectado. Para evitar interrupciones en el servicio, asegúrese de que sus clientes SFTP (código, herramientas y servicios) se ajusten a los cambios detallados a continuación.

## ¿Cómo puedo determinar qué algoritmos, tipos de conexión y protocolos utiliza mi organización actualmente?

El software FTP/SFTP que utilice debe indicar qué configuraciones específicas se están usando en las conexiones configuradas para intercambiar datos con Adobe Analytics. Este software también debe incluir documentación acerca de las diferentes opciones disponibles para las conexiones. Las opciones que se admitirán después de esta actualización son ampliamente compatibles y aceptadas en la industria.

Las opciones de conexión que se eliminarán generalmente se consideran obsoletas y no se utilizan en el software actual. Si ha actualizado el software FTP/SFTP en los últimos tres años, es probable que ya tenga una conexión compatible.

## ¿Qué funciones de Adobe Analytics utilizan SFTP para la ingesta de datos?

Las siguientes funciones proporcionan una opción para cargar datos en Adobe Analytics mediante SFTP.

* [Clasificaciones](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/set-up-ftp-accounts/ftp-saint.html?lang=es)

* [Atributos del cliente](https://experienceleague.adobe.com/docs/core-services/interface/services/customer-attributes/attributes.html?lang=es)

* [Archivos de fuentes de datos](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/set-up-ftp-accounts/ftp-datafeeds.html?lang=es)

* [Fuentes de datos](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/set-up-ftp-accounts/ftp-datasources.html?lang=es)

* [Informes entregados por Data Warehouse](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/set-up-ftp-accounts/ftp-dw-reports.html?lang=es)

* Además, algunas implementaciones personalizadas creadas mediante [Servicios de ingeniería](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/set-up-ftp-accounts/ftp-eng-services.html?lang=es) pueden utilizar SFTP para intercambiar datos con Adobe.

## ¿Qué cambios específicos se incluirán en esta actualización?

A continuación se muestra una lista detallada de las conexiones y algoritmos que se eliminarán y de los que se admitirán:

* Algoritmos mac de protocolo SFTP:

   * Ya no vamos a admitir: hmac-md5, hmac-md5-96, hmac-ripemd160, hmacripemd160@openssh.com, hmac-sha1, hmac-sha1-96, hmac-sha1-etm@openssh.com, umac-64-etm@openssh.com, umac-64@openssh.com

   * Solo admitiremos: hmac-sha2-512-etm@openssh.com, hmac-sha2-256-etm@openssh.com, umac-128-etm@openssh.com, hmac-sha2-512, hmacsha2-256, umac-128@openssh.com

* Algoritmo de cifrado de protocolo SFTP:

   * Ya no vamos a admitir: 3des-cbc, aes128-cbc, aes128-gcm@openssh.com, aes192-cbc, aes256-cbc, aes256-gcm@openssh.com, arcfour, arcfour128, arcfour256, blowfish-cbc, cast128-cbc, rijndael-cbc@lysator.liu.se

   * Solo admitiremos: aes128-ctr, aes192-ctr, aes256-ctr

* Conexiones compatibles con el protocolo SFTP:

   * Ya no admitiremos el uso de comandos o conexiones scp y rsync a través del protocolo sftp

   * Solo se admitirán conexiones de protocolo SFTP puras

* Clientes/protocolos FTP/SFTP admitidos:

   * FTP: vsftpd versión 3.0.2-25 o superior

   * SFTP: openssh versión 7.4p1-21 o superior

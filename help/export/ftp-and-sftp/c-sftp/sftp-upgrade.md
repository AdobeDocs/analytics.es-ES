---
title: 'Actualización de servicios SFTP: preguntas más frecuentes'
description: Preguntas más frecuentes sobre la actualización de los servicios SFTP prevista para mayo de 2022.
source-git-commit: eb9bdcbd99d45afc913c5ade37e8fb5c62a3a456
workflow-type: tm+mt
source-wordcount: '416'
ht-degree: 2%

---


# Actualización de servicios SFTP: preguntas más frecuentes

Activado **2 de mayo de 2022**, Adobe Analytics actualizará su Protocolo seguro de transferencia de archivos [SFTP] para proporcionar una seguridad mejorada para las transferencias de archivos. Con este cambio, algunas configuraciones de cliente SFTP ya no serán compatibles. También agregaremos algunas opciones de conexión que estarán disponibles para **1 de marzo de 2022**. Esto solo afecta a los datos enviados o recuperados de Adobe Analytics mediante SFTP. El protocolo FTP no se verá afectado. Para evitar interrupciones en el servicio, asegúrese de que sus clientes SFTP (código, herramientas y servicios) se ajusten a los cambios detallados a continuación.

## ¿Cómo puedo determinar qué algoritmos, tipos de conexión y protocolos utiliza mi organización actualmente?

El software FTP/SFTP que utilice debe indicar qué configuraciones específicas se están utilizando en las conexiones configuradas para intercambiar datos con Adobe Analytics. Este software también debe incluir documentación sobre las diferentes opciones disponibles para conexiones. Las opciones que se admitirán después de esta actualización son ampliamente compatibles y aceptadas en el sector.

## ¿Qué funciones de Adobe Analytics utilizan SFTP para el consumo de datos?

Las siguientes funciones proporcionan una opción para cargar datos en Adobe Analytics mediante SFTP.

* [Clasificaciones](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/set-up-ftp-accounts/ftp-saint.html)

* [Archivo de fuentes de datos](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/set-up-ftp-accounts/ftp-datafeeds.html)

* [Fuentes de datos](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/set-up-ftp-accounts/ftp-datasources.html)

* [Informes entregados por Data Warehouse](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/set-up-ftp-accounts/ftp-dw-reports.html)

* Además, algunas implementaciones personalizadas creadas mediante [Servicios de ingeniería](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/set-up-ftp-accounts/ftp-eng-services.html) puede utilizar SFTP para intercambiar datos con Adobe.

## ¿Qué cambios específicos se incluirán en esta actualización?

A continuación se muestra una lista detallada de las conexiones y algoritmos que se eliminarán y que serán compatibles:

* Algoritmos mac de protocolo SFTP:

   * Ya no vamos a apoyar: hmac-md5, hmac-md5-96, hmac-ripemd160, hmacripemd160@openssh.com, hmac-sha1, hmac-sha1-96, hmac-sha1-etm@openssh.com, umac-64-etm@openssh.com, umac-64@openssh.com

   * Solo admitiremos: hmac-sha2-512-etm@openssh.com, hmac-sha2-256-etm@openssh.com, umac-128-etm@openssh.com, hmac-sha2-512, hmacsha2-256, umac-128@openssh.com

* Algoritmo de cifrado de protocolo SFTP:

   * Ya no vamos a apoyar: 3des-cbc, aes128-cbc, aes128-gcm@openssh.com, aes192-cbc, aes256-cbc, aes256-gcm@openssh.com, arcfour, arcfour128, arcfour256, blowfish-cbc, cast128-cbc, rijndael-cbc@lysator.liu.se

   * Solo admitiremos: aes128-ctr, aes192-ctr, aes256-ctr

* Conexiones compatibles con el protocolo SFTP:

   * Ya no admitiremos el uso de comandos o conexiones scp y rsync a través del protocolo sftp

   * Solo se admitirán conexiones de protocolo SFTP puras

* Clientes/protocolos FTP/SFTP compatibles:

   * FTP: vsftpd versión 3.0.2-25 o superior

   * SFTP: openssh versión 7.4p1-21 o superior
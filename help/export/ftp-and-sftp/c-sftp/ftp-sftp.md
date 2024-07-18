---
description: SFTP es un protocolo seguro para la transferencia de datos que garantiza que nadie, salvo usted, vea sus datos. Los servicios de ingeniería de Adobe pueden configurar una cuenta de SFTP para conservar los datos de manera segura.
keywords: ftp;sftp
title: Resumen del Protocolo seguro de transferencia de archivos (SFTP)
feature: FTP Export
exl-id: ea0448f9-1685-4a8f-b2f9-49d315c6ab71
source-git-commit: 93099d36a65ca2bf16fbd6342f01bfecdc8c798e
workflow-type: tm+mt
source-wordcount: '219'
ht-degree: 88%

---

# Resumen del Protocolo seguro de transferencia de archivos (SFTP)

SFTP es un protocolo seguro para la transferencia de datos que garantiza que nadie, salvo usted, vea sus datos. Los servicios de ingeniería de Adobe pueden configurar una cuenta de SFTP para conservar los datos de manera segura.

## Entrega mediante inserción {#section_A47831BB1DCA490BB57F0940617AA506}

Esto significa que los servidores de Adobe “insertan” el archivo en sus servidores. Es decir, que lo entregan en su extremo.

[Data Warehouse](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-dw.md) y [la fuente de datos de Analytics](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-overview.html?lang=es) pueden insertar datos mediante un SFTP.

El Report Builder **no puede** insertar datos a través de SFTP.

## Entrega mediante extracción {#section_FA29FAEF02FE40B8B32452146A036F48}

Esto significa que el archivo se envía a uno de los servidores de Adobe usando el FTP normal. Si se quiere que el archivo pase al servidor, hay que extraerlo del servidor de Adobe usando el SFTP del servidor al servidor FTP de Adobe. Esto se puede hacer mediante tres métodos:

* [Conectarse a Adobe a través de un SFTP sin contraseña.](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-cert-auth.md)
* [Conectarse a una cuenta de FTP de Adobe mediante SFTP.](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-connect.md)
* Cualquier informe se puede insertar en las funciones de fuentes de datos/Reports &amp; Analytics/Ad Hoc Analysis y luego extraerlo. Adobe no puede entregar estos informes al servidor SFTP que hayamos configurado.

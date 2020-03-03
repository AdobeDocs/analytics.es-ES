---
description: SFTP es un protocolo seguro para la transferencia de datos que garantiza que nadie, salvo usted, vea sus datos. Los servicios de ingeniería de Adobe pueden configurar una cuenta de SFTP para conservar los datos de manera segura.
keywords: ftp;sftp
title: Resumen del Protocolo seguro de transferencia de archivos (SFTP)
uuid: 7dd1a867-e828-4c7b-bf11-75a81d4c149c
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Resumen del Protocolo seguro de transferencia de archivos (SFTP)

SFTP es un protocolo seguro para la transferencia de datos que garantiza que nadie, salvo usted, vea sus datos. Los servicios de ingeniería de Adobe pueden configurar una cuenta de SFTP para conservar los datos de manera segura.

## Entrega mediante inserción {#section_A47831BB1DCA490BB57F0940617AA506}

Esto significa que los servidores de Adobe “insertan” el archivo en sus servidores. Es decir, que lo entregan en su extremo.

[Data Warehouse](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-dw.md) y [la fuente de datos de Analytics](https://marketing.adobe.com/resources/help/en_US/reference/analytics-data-feed.html) pueden insertar datos mediante un SFTP.

Las siguientes herramientas de Analytics **no pueden** insertar datos por SFTP:

* Reports &amp; Analytics
* Ad Hoc Analysis
* Creador de informes

## Entrega mediante extracción {#section_FA29FAEF02FE40B8B32452146A036F48}

Esto significa que el archivo se envía a uno de los servidores de Adobe usando el FTP normal. Si se quiere que el archivo pase al servidor, hay que extraerlo del servidor de Adobe usando el SFTP del servidor al servidor FTP de Adobe. Esto se puede hacer mediante tres métodos:

* [Conectarse a Adobe a través de un SFTP sin contraseña.](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-cert-auth.md)
* [Conectarse a una cuenta de FTP de Adobe mediante SFTP.](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-connect.md)
* Cualquier informe se puede insertar en las funciones de fuentes de datos/Reports &amp; Analytics/Ad Hoc Analysis y luego extraerlo. Adobe no puede entregar estos informes al servidor SFTP que hayamos configurado.


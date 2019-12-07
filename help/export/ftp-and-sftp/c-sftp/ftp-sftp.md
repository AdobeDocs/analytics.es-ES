---
description: SFTP es un protocolo seguro para la transferencia de datos que garantiza que nadie pueda ver sus datos excepto usted. Los servicios de ingeniería de Adobe pueden configurar una cuenta SFTP para conservar los datos de forma segura.
keywords: ftp;sftp
title: Resumen del Protocolo seguro de transferencia de archivos (SFTP)
uuid: 7dd1a867-e828-4c7b-bf11-75a81d4c149c
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Resumen del Protocolo seguro de transferencia de archivos (SFTP)

SFTP es un protocolo seguro para la transferencia de datos que garantiza que nadie pueda ver sus datos excepto usted. Los servicios de ingeniería de Adobe pueden configurar una cuenta SFTP para conservar los datos de forma segura.

## Entrega mediante inserción {#section_A47831BB1DCA490BB57F0940617AA506}

Esto significa que los servidores de Adobe “insertan” el archivo en sus servidores. Es decir, que lo entregan en su extremo.

[El almacén](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-dw.md) de datos y la fuente de datos [de Analytics](https://marketing.adobe.com/resources/help/en_US/reference/analytics-data-feed.html) pueden insertar datos mediante SFTP.

The following Analytics tools **cannot** push data via SFTP:

* Reports &amp; Analytics
* Ad Hoc Analysis 
* Creador de informes

## Entrega mediante extracción {#section_FA29FAEF02FE40B8B32452146A036F48}

Esto significa que el archivo se envía a uno de los servidores de Adobe usando el FTP normal. Si desea que el archivo esté en el servidor, debe extraerlo del servidor de Adobe mediante SFTP del servidor al servidor FTP de Adobe. Esto se puede hacer mediante tres métodos:

* [Conectarse a Adobe a través de un SFTP sin contraseña.](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-cert-auth.md)
* [Conéctese a una cuenta de FTP de Adobe con SFTP.](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-connect.md)
* Cualquier informe se puede insertar en las funciones de fuentes de datos/informes y análisis/Ad Hoc de Adobe y luego extraerlo. Adobe no puede entregar estos informes al servidor SFTP que ha configurado.


---
description: SFTP es un protocolo seguro para transferir datos que garantiza que nadie vea los datos. Los servicios de ingeniería de Adobe pueden configurar una cuenta SFTP para conservar los datos de forma segura.
keywords: ftp; sftp
seo-description: SFTP es un protocolo seguro para transferir datos que garantiza que nadie vea los datos. Los servicios de ingeniería de Adobe pueden configurar una cuenta SFTP para conservar los datos de forma segura.
seo-title: 'Protocolo seguro de transferencia de archivos: información general'
solution: Analytics
title: 'Protocolo seguro de transferencia de archivos: información general'
uuid: 7 dd 1 a 867-e 828-4 c 7 b-bf 11-75 a 81 d 4 c 149 c
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Protocolo seguro de transferencia de archivos: información general

SFTP es un protocolo seguro para transferir datos que garantiza que nadie vea los datos. Los servicios de ingeniería de Adobe pueden configurar una cuenta SFTP para conservar los datos de forma segura.

## Entrega mediante inserción {#section_A47831BB1DCA490BB57F0940617AA506}

Esto significa que los servidores de Adobe “insertan” el archivo en sus servidores. Es decir, que lo entregan en su extremo.

[El almacén de datos](../../../export/ftp-and-sftp/c-sftp/ftp-sftp-dw.md#concept_904ADB7B4FE04DCCB90EFDB6D0DB1076) y [la fuente](https://marketing.adobe.com/resources/help/en_US/reference/analytics-data-feed.html) de datos de Analytics pueden insertar datos a través de SFTP.

The following Analytics tools **cannot** push data via SFTP:

* Reports &amp; Analytics
* Ad Hoc Analysis
* Creador de informes

## Entrega mediante extracción {#section_FA29FAEF02FE40B8B32452146A036F48}

Esto significa que el archivo se envía a uno de los servidores de Adobe usando el FTP normal. Si desea el archivo en su servidor, debe extraerlo del servidor de Adobe mediante SFTP desde el servidor al servidor FTP de Adobe. Esto se puede hacer mediante tres métodos:

* [Conectarse a Adobe a través de SFTP sin contraseña.](../../../export/ftp-and-sftp/c-sftp/ftp-sftp-cert-auth.md#concept_962A381F42A4472AA366A08CCC962846)
* [Conecte a una cuenta de FTP de Adobe con SFTP.](../../../export/ftp-and-sftp/c-sftp/ftp-sftp-connect.md#concept_01176600188441C6AFB28F5E264D89F8)
* Cualquier informe se puede insertar en las funciones de fuentes de datos/informes y análisis/Ad Hoc de Adobe y luego extraerlo. Adobe no puede entregar estos informes al servidor SFTP que ha configurado.


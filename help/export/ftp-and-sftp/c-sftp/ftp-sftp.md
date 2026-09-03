---
description: SFTP es un protocolo seguro para la transferencia de datos que garantiza que nadie, salvo usted, vea sus datos. Los servicios de ingeniería de Adobe pueden configurar una cuenta de SFTP para conservar los datos de manera segura.
keywords: ftp;sftp
title: Resumen del Protocolo seguro de transferencia de archivos (SFTP)
feature: FTP Export
exl-id: ea0448f9-1685-4a8f-b2f9-49d315c6ab71
TQID: https://experienceleague.adobe.com/kJYtQSuxz-2NMUYqZb01wsr6ltQQbD5itpPYYzsmlCM
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
subfeature_v2:
  - id: ac8a38fa-dec3-4581-8f64-178fde9f64e8
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 220
ht-degree: 80%

---

# Resumen del Protocolo seguro de transferencia de archivos (SFTP)

SFTP es un protocolo seguro para la transferencia de datos que garantiza que nadie, salvo usted, vea sus datos. Los servicios de ingeniería de Adobe pueden configurar una cuenta de SFTP para conservar los datos de manera segura.

## Entrega mediante inserción {#section_A47831BB1DCA490BB57F0940617AA506}

Esto significa que los servidores de Adobe &quot;insertan&quot; el archivo en los servidores. Básicamente, lo entregamos a su punto final.

[Data Warehouse](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-dw.md) y [la fuente de datos de Analytics](/help/export/analytics-data-feed/data-feed-overview.md) pueden insertar datos mediante un SFTP.

Report Builder **no puede** insertar datos a través de un SFTP.

## Entrega mediante extracción {#section_FA29FAEF02FE40B8B32452146A036F48}

Esto significa que el archivo se envía a uno de los servidores de Adobe usando el FTP normal. Si se quiere que el archivo pase al servidor, hay que extraerlo del servidor de Adobe usando el SFTP del servidor al servidor FTP de Adobe. Esto se puede hacer mediante tres métodos:

* [Conectarse a Adobe a través de un SFTP sin contraseña.](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-cert-auth.md)
* [Conectarse a una cuenta de FTP de Adobe mediante SFTP.](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-connect.md)
* Cualquier informe se puede insertar en las funciones de fuentes de datos/Reports &amp; Analytics/Ad Hoc Analysis y luego extraerlo. Adobe no puede entregar estos informes al servidor SFTP que hayamos configurado.

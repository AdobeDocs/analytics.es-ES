---
description: Adobe admite la exportación de solicitudes de Data Warehouse a servidores SFTP.
keywords: ftp;sftp
title: Envío de solicitudes de Data Warehouse a los servidores SFTP
feature: FTP Export
exl-id: 45694647-69ec-45e3-b614-4a936909a338
source-git-commit: d8bfad5d388f906c7c7301a9126813f5c2a5dbaa
workflow-type: tm+mt
source-wordcount: '255'
ht-degree: 52%

---

# Envío de solicitudes de Data Warehouse a los servidores SFTP

Adobe admite la exportación de solicitudes de Data Warehouse a servidores SFTP, tal como se describe en [SFTP](/help/export/data-warehouse/create-request/dw-request-report-destinations.md#sftp) en el artículo [Configurar un destino de informe para una solicitud de Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md).

Asegúrese de que las tareas siguientes se hayan completado:

* Solo se utiliza el puerto 22 al solicitar un informe de Data Warehouse.
* El archivo `authorized_keys` de Adobe se encuentra en el directorio `.ssh`, dentro del directorio raíz del usuario con el que inicia sesión.
* El destino no es `ftp.omniture.com`. No se admite el protocolo SFTP entre los servidores internos de Adobe.
* El destino admite la autenticación de un factor (PKI). Si se exigen dos factores, el informe no se podrá entregar. Asegúrese de que el servidor no esté configurado para intentar la autenticación de doble factor. Adobe Analytics requiere que, al iniciar sesión, solo se utilice la clave.
* Adobe admite el cifrado SSHv2 y regresa a SSHv1 (solo clave RSA).

Para enviar satisfactoriamente una solicitud de Data Warehouse a través de SFTP:

1. Complete los pasos que se describen en [SFTP](/help/export/data-warehouse/create-request/dw-request-report-destinations.md#sftp) en el artículo [Configurar un destino de informe para una solicitud de Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md), incluida la descarga de la clave pública.
1. Inicie sesión en el sitio SFTP con las mismas credenciales que se usan en la solicitud de Data Warehouse.
1. En el directorio raíz, vaya a la carpeta denominada `.ssh` (si todavía no existe, créela) y coloque en ella el archivo `authorized_keys`.

1. Complete la solicitud de Data Warehouse si aún no lo ha hecho, tal como se describe en [Configuración de un destino de informe para una solicitud de Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md).

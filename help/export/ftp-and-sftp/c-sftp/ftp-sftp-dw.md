---
description: Adobe admite la exportación de solicitudes de Data Warehouse a servidores SFTP.
keywords: ftp;sftp
title: Envío de solicitudes de Data Warehouse a los servidores SFTP
feature: FTP Export
exl-id: 45694647-69ec-45e3-b614-4a936909a338
TQID: 'https://experienceleague.adobe.com/gZvqhVFN2WKnk0hs2t8R5fcg5g8Tts1jKZPvMqeGcy4'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
subfeature_v2:
  - id: a8bf2e97-0add-4437-b976-1fc5154911a8
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 258
ht-degree: 53%

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

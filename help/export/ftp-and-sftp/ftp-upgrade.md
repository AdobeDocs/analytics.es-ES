---
description: Las actualizaciones de los servidores FTP de Adobe pueden introducir nuevas configuraciones que afecten a los scripts de automatización (estos suelen utilizarse para descargar o cargar datos periódicamente), que, normalmente, dependen de ciertas opciones del servidor.
keywords: ftp;sftp
title: Actualización de servidores FTP y SFTP de Adobe
feature: FTP Export
exl-id: 442b2d5d-735c-4ece-a456-3a0ac5909c8c
TQID: 'https://experienceleague.adobe.com/RJHgVwgnmCLRuNTyjKx-D6SlOovFYS0T5-7topZkcVY'
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
source-wordcount: 131
ht-degree: 25%

---

# Actualización de servidores FTP y SFTP de Adobe

Las actualizaciones de los servidores FTP y SFTP de Adobe pueden introducir nuevas configuraciones que afecten a los scripts de automatización (estos suelen utilizarse para descargar o cargar datos periódicamente), que, normalmente, dependen de ciertas opciones del servidor.

Por ejemplo, se introduce un nuevo estado de éxito que afecta a un script que utiliza el estado de éxito para almacenar en déclencheur una acción determinada. Adobe notifica activamente a los usuarios de estos cambios de configuración. Si Adobe le notifica que la actualización de un servidor FTP es inminente, compruebe los scripts de automatización para asegurarse de que siguen funcionando correctamente.

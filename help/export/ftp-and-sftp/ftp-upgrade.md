---
description: Las actualizaciones de los servidores FTP de Adobe pueden introducir nuevas configuraciones que afecten a los scripts de automatización (estos suelen utilizarse para descargar o cargar datos periódicamente), que, normalmente, dependen de ciertas opciones del servidor.
keywords: ftp;sftp
title: Actualización de servidores FTP y SFTP de Adobe
feature: FTP Export
exl-id: 442b2d5d-735c-4ece-a456-3a0ac5909c8c
source-git-commit: 6008cd51b86e403668c15bbfb9d50513e46ddf4d
workflow-type: tm+mt
source-wordcount: '130'
ht-degree: 25%

---

# Actualización de servidores FTP y SFTP de Adobe

Las actualizaciones de los servidores FTP y SFTP de Adobe pueden introducir nuevas configuraciones que afecten a los scripts de automatización (estos suelen utilizarse para descargar o cargar datos periódicamente), que, normalmente, dependen de ciertas opciones del servidor.

Por ejemplo, se introduce un nuevo estado de éxito que afecta a un script que utiliza el estado de éxito para almacenar en déclencheur una acción determinada. Adobe notifica activamente a los usuarios de estos cambios de configuración. Si Adobe le notifica que la actualización de un servidor FTP es inminente, compruebe los scripts de automatización para asegurarse de que siguen funcionando correctamente.

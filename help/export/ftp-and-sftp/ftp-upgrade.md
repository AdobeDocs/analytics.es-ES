---
description: Las actualizaciones de los servidores FTP de Adobe pueden introducir nuevas configuraciones que afecten a los scripts de automatización (estos suelen utilizarse para descargar o cargar datos periódicamente), que, normalmente, dependen de ciertas opciones del servidor.
keywords: ftp;sftp
title: Actualización de servidores FTP de Adobe
feature: FTP Export
exl-id: 442b2d5d-735c-4ece-a456-3a0ac5909c8c
source-git-commit: 4daa5c8bdbcb483f23a3b8f75dde9eeb48516db8
workflow-type: ht
source-wordcount: '124'
ht-degree: 100%

---

# Actualización de servidores FTP de Adobe

Las actualizaciones de los servidores FTP de Adobe pueden introducir nuevas configuraciones que afecten a los scripts de automatización (estos suelen utilizarse para descargar o cargar datos periódicamente), que, normalmente, dependen de ciertas opciones del servidor.

Imaginemos, por ejemplo, que se introduce un nuevo estado de éxito y que esto afecta a un script que, a su vez, utiliza el estado de éxito para desencadenar una acción determinada. Adobe notifica estos cambios de configuración a los usuarios de forma proactiva. Si Adobe informa de que una actualización de servidor FTP es inminente, habrá que comprobar los scripts de automatización para cerciorarse de que siguen funcionando correctamente.

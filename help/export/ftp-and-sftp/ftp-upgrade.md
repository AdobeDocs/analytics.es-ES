---
description: Las actualizaciones de los servidores FTP de Adobe pueden introducir nuevas configuraciones que afecten a los scripts de automatización (estos suelen utilizarse para descargar o cargar datos periódicamente), que, normalmente, dependen de ciertas opciones del servidor.
keywords: ftp;sftp
title: Actualización de servidores FTP de Adobe
uuid: cc9e5e13-e213-480f-9ff6-3dbec24baeee
exl-id: 442b2d5d-735c-4ece-a456-3a0ac5909c8c
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '124'
ht-degree: 100%

---

# Actualización de servidores FTP de Adobe

Las actualizaciones de los servidores FTP de Adobe pueden introducir nuevas configuraciones que afecten a los scripts de automatización (estos suelen utilizarse para descargar o cargar datos periódicamente), que, normalmente, dependen de ciertas opciones del servidor.

Imaginemos, por ejemplo, que se introduce un nuevo estado de éxito y que esto afecta a un script que, a su vez, utiliza el estado de éxito para desencadenar una acción determinada. Adobe notifica estos cambios de configuración a los usuarios de forma proactiva. Si Adobe informa de que una actualización de servidor FTP es inminente, habrá que comprobar los scripts de automatización para cerciorarse de que siguen funcionando correctamente.

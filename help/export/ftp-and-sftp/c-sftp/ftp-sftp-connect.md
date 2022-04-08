---
description: Instrucciones para configurar la transferencia segura a través de los servidores FTP de Adobe.
keywords: ftp;sftp
title: Conéctese a una cuenta de FTP de Adobe mediante un SFTP
feature: FTP Export
exl-id: 727d4f7a-d7d1-40cf-bdcd-c783ca47f51c
source-git-commit: 4daa5c8bdbcb483f23a3b8f75dde9eeb48516db8
workflow-type: ht
source-wordcount: '134'
ht-degree: 100%

---

# Conéctese a una cuenta de FTP de Adobe mediante un SFTP

Instrucciones para configurar la transferencia segura a través de los servidores FTP de Adobe.

1. Solicite una cuenta de FTP alojada en Adobe cuota: (50 MB).
1. Cree las claves pública y privada de RSA. En Linux, ejecute:

   ```
   ssh-keygen -t rsa
   ```

   Si está en un entorno de Windows, use puttyGen para crear las claves.

1. Cree un archivo con el nombre [!DNL authorized_keys] (sin extensión).
1. Copie el contenido de la clave pública en [!DNL authorized_keys].
1. Cargue [!DNL authorized_keys] en una cuenta de FTP:

   * Conéctese a la cuenta de FTP de Adobe.
   * Cree un directorio [!DNL .ssh], (si no existe todavía).
   * Cargue el archivo [!DNL authorized_keys] en el directorio [!DNL .ssh].

1. Inicie sesión en la cuenta de FTP usando un SFTP para probar la conexión.

Para obtener más información, consulte [Conexión a Adobe a través de un STFP sin contraseña](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-cert-auth.md).

---
description: Instrucciones para configurar la transferencia segura a través de los servidores FTP de Adobe.
keywords: ftp;sftp
title: Conectarse a una cuenta de FTP de Adobe mediante un SFTP
uuid: 4faf27b8-7276-4c68-87cb-35802b809e27
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Conectarse a una cuenta de FTP de Adobe mediante un SFTP

Instrucciones para configurar la transferencia segura a través de los servidores FTP de Adobe.

1. Solicite una cuenta de FTP alojada en Adobe cuota: (50 MB).
1. Cree las claves pública y privada de RSA. En Linux, ejecute:

   ```
   ssh-keygen -t rsa
   ```

   Si está en un entorno de Windows, use puttyGen para crear las claves.

1. Create a file named [!DNL authorized_keys] (no extension).
1. Copy the contents of the Public key into [!DNL authorized_keys].
1. Upload [!DNL authorized_keys] to an FTP account:

   * Conéctese a la cuenta de FTP de Adobe.
   * Create a [!DNL .ssh] directory (if it does not already exist).
   * Upload the [!DNL authorized_keys] file to the [!DNL .ssh] directory.

1. Compruebe la conexión iniciando sesión en la cuenta de FTP mediante SFTP.

[Para obtener más información, consulte ](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-cert-auth.md)Cómo conectarse a Adobe mediante SFTP sin contraseña....

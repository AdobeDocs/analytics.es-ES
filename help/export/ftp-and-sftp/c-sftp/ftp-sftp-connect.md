---
description: Instrucciones para configurar la transferencia segura a través de los servidores FTP de Adobe.
keywords: ftp; sftp
seo-description: Instrucciones para configurar la transferencia segura a través de los servidores FTP de Adobe.
seo-title: Conexión a una cuenta de FTP de Adobe con SFTP
solution: Analytics
title: Conexión a una cuenta de FTP de Adobe con SFTP
uuid: 4 faf 27 b 8-7276-4 c 68-87 cb -35802 b 809 e 27
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Conexión a una cuenta de FTP de Adobe con SFTP

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

1. Para probar la conexión, inicie sesión en la cuenta de FTP mediante SFTP.

For more detailed information, see [How to Connect to Adobe via sFTP Without a Password_...](../../../export/ftp-and-sftp/c-sftp/ftp-sftp-cert-auth.md#concept_962A381F42A4472AA366A08CCC962846).

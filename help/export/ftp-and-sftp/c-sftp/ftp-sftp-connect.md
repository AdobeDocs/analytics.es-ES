---
description: Instrucciones para configurar la transferencia segura a través de los servidores FTP de Adobe.
keywords: ftp;sftp
title: Conéctese a una cuenta de FTP de Adobe mediante un SFTP
feature: FTP Export
exl-id: 727d4f7a-d7d1-40cf-bdcd-c783ca47f51c
source-git-commit: 62132284ca70f3bdb1a8896e4548b8b63a5c03c8
workflow-type: tm+mt
source-wordcount: '182'
ht-degree: 58%

---

# Conectarse a una cuenta de FTP mediante un SFTP

Para configurar una transferencia segura mediante FTP:

1. (Condicional) Si desea configurar la transferencia segura a través de los servidores FTP de Adobe:

   1. Solicite una cuenta de FTP alojada en Adobe cuota: (50 MB).

   1. Cree las claves pública y privada de RSA.

      * En el entorno Linux, ejecute:

        ```
        ssh-keygen -t rsa
        ```

      * En un entorno Windows, utilice puttyGen.

1. (Condicional) Si desea configurar la transferencia segura con su propia ubicación FTP, debe tener un host SFTP, un nombre de usuario y el sitio de destino que contengan una clave pública RSA o DSA válida. Puede descargar la clave pública adecuada al crear la fuente.

1. Cree un archivo con el nombre [!DNL authorized_keys] (sin extensión).

1. Copie el contenido de la clave pública en [!DNL authorized_keys].

1. Cargue [!DNL authorized_keys] en una cuenta de FTP:

   * Conéctese a la cuenta de FTP de Adobe.
   * Cree un directorio [!DNL .ssh], (si no existe todavía).
   * Cargue el archivo [!DNL authorized_keys] en el directorio [!DNL .ssh].

1. Inicie sesión en la cuenta de FTP usando un SFTP para probar la conexión.

Para obtener más información, consulte [Conexión a Adobe a través de un STFP sin contraseña](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-cert-auth.md).

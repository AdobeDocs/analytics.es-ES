---
description: Instrucciones para configurar la transferencia segura a través de los servidores FTP de Adobe.
keywords: ftp;sftp
title: Conéctese a una cuenta de FTP de Adobe mediante un SFTP
feature: FTP Export
exl-id: 727d4f7a-d7d1-40cf-bdcd-c783ca47f51c
source-git-commit: 26ae4edacbc3591d4d3358afe009bf7831d45efb
workflow-type: tm+mt
source-wordcount: '212'
ht-degree: 39%

---

# Conectarse a una cuenta de FTP mediante un SFTP

Para configurar una transferencia segura mediante FTP:

1. (Condicional) Si desea configurar la transferencia segura a través de los servidores FTP de Adobe:

   1. Solicite una cuenta de FTP alojada en Adobe (cuota de 50 MB).

   1. Cree las claves pública y privada.

      * En el entorno Linux, ejecute:

        ```
        ssh-keygen -t ed25519 -C "your-comment-or-email"
        ```

        Si la directiva no le permite utilizar ed25519, ejecute:

        ```
        ssh-keygen -t rsa -b 4096 -C "your-comment-or-email"
        ```

        **Nota:** Esto suele aplicarse a los clientes que operan bajo FIPS 186-4, ya que ed25519 es compatible por primera vez con el nuevo FIPS 186-5.

      * En un entorno Windows, utilice puttyGen.

1. (Condicional) Si desea configurar la transferencia segura con su propia ubicación FTP, debe tener un host SFTP, un nombre de usuario y el sitio de destino que contengan una clave pública RSA o ed25519 válida. Puede descargar la clave pública adecuada al crear la fuente.

1. Cree un archivo con el nombre [!DNL `authorized_keys`] (sin extensión).

1. Copie el contenido de la clave pública en [!DNL `authorized_keys`].

1. Cargue [!DNL `authorized_keys`] en una cuenta de FTP:

   * Conéctese a la cuenta de FTP de Adobe.
   * Cree un directorio [!DNL .ssh], (si no existe todavía).
   * Cargue el archivo [!DNL `authorized_keys`] en el directorio [!DNL .ssh].

1. Inicie sesión en la cuenta de FTP usando un SFTP para probar la conexión.

Para obtener información más detallada, consulte [Conectarse a Adobe a través de un SFTP sin contraseña](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-cert-auth.md).


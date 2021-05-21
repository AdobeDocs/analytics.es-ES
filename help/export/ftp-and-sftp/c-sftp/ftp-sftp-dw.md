---
description: Adobe admite la exportación de solicitudes de Data Warehouse a servidores SFTP.
keywords: ftp;sftp
title: Envío de solicitudes de Data Warehouse a los servidores SFTP
uuid: 393634a1-0643-4d63-bb6e-fb80f1ba76c1
exl-id: 45694647-69ec-45e3-b614-4a936909a338
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '414'
ht-degree: 100%

---

# Envío de solicitudes de Data Warehouse a los servidores SFTP

Adobe admite la exportación de solicitudes de Data Warehouse a servidores SFTP.

Asegúrese de que las tareas siguientes se hayan completado:

Adobe admite la exporación de solicitudes de Data Warehouse a los servidores SFTP, siempre que se cumplan las condiciones siguientes:

* Cuando el protocolo [!DNL sftp://] se especifica en el campo del host (por ejemplo, [!DNL sftp://ftp.example.com]) y SOLO se utiliza el puerto 22 al solicitar el informe de Data Warehouse.

   También puede utilizar la opción [!DNL sftp+norename://], tal y como se describe a continuación.

* El archivo [!DNL authorized_keys] de Adobe se encuentra en el directorio [!DNL .ssh], dentro del directorio raíz del usuario con el que inicia sesión.

* El destino no es [!DNL ftp.omniture.com]. No se admite el protocolo SFTP entre los servidores internos de Adobe.
* El destino admite la autenticación de un factor (PKI). Si se exigen dos factores, el informe no se podrá entregar. Asegúrese de que el servidor no esté configurado para intentar la autenticación usando dos factores. Adobe Analytics requiere que, al iniciar sesión, solo se utilice la clave.
* Adobe admite el cifrado SSHv2 y regresa a SSHv1 (solo clave RSA).

Para enviar correctamente una solicitud de [!DNL Data Warehouse] a través de SFTP:

1. Pídale a uno de los usuarios de soporte técnico de su compañía que se ponga en contacto con el servicio de atención al cliente para obtener el archivo [!DNL authorized_keys].
1. Cuando haya obtenido el archivo, inicie sesión en el sitio del FTP con las mismas credenciales que utilizó para la solicitud de [!DNL Data Warehouse].
1. En el directorio raíz, vaya a la carpeta denominada [!DNL .ssh] (si todavía no existe, créela) y coloque en ella el archivo [!DNL authorized_keys].

1. Vaya al gestor de solicitudes de [!DNL Data Warehouse]. Configure la solicitud según sus preferencias y luego haga clic en **[!UICONTROL Opciones de envío avanzadas]**.

1. En la ventana emergente, haga clic en **[!UICONTROL FTP]** y después especifique el sitio del FTP (incluido el protocolo [!DNL sftp://], de este modo: [!DNL sftp://ftp.omniture.com]) a través del puerto 22.

   El protocolo [!DNL sftp://] solo se puede incluir cuando se usa un SFTP. El prefijo del protocolo se debe omitir en las solicitudes normales de FTP (es decir, sería [!DNL ftp.omniture.com] en lugar de [!DNL ftp://ftp.omniture.com]).

1. En el campo Carpeta, escriba el nombre de la carpeta donde quiere colocar el archivo. El nombre de la carpeta es obligatorio.
1. Escriba el nombre de usuario y la contraseña que usó en el paso 2.
1. Haga clic en **[!UICONTROL Enviar]**.

El comando PUT de SFTP coloca un archivo temporal con la extensión .part en el directorio especificado. Cuando la carga se termina, la extensión del archivo se cambia por la extensión final. Ahora el archivo ya está listo para su uso.

Otra opción es que [!DNL sftp+norename://] se especifique en lugar de [!DNL sftp://] al cargar el archivo directamente con el nombre final, sin un nombre de archivo temporal [!DNL .part] durante la carga. Este método es adecuado cuando el servidor SFTP gestiona automáticamente el cambio de nombre de archivos durante la carga y no hay posibilidad de que el archivo se procese antes de que se complete la carga.

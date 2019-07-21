---
description: Adobe permite exportar solicitudes del almacén de datos a servidores SFTP.
keywords: ftp; sftp
seo-description: Adobe permite exportar solicitudes del almacén de datos a servidores SFTP.
seo-title: Envío de solicitudes del almacén de datos a servidores SFTP
solution: Analytics
title: Envío de solicitudes del almacén de datos a servidores SFTP
uuid: 393634 a 1-0643-4 d 63-bb 6 e-fb 80 f 1 ba 76 c 1
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Envío de solicitudes del almacén de datos a servidores SFTP

Adobe permite exportar solicitudes del almacén de datos a servidores SFTP.

Asegúrese de que las tareas siguientes se hayan completado:

Adobe permite exportar solicitudes del almacén de datos a servidores SFTP, siempre y cuando se cumplan los siguientes procedimientos:

* [!DNL sftp://] se especifica en el campo host (por ejemplo [!DNL sftp://ftp.example.com],) y SOLO se utiliza el puerto 22 al solicitar un informe de Almacén de datos.

   You can also use the [!DNL sftp+norename://] option, as described below.

* [!DNL authorized_keys] El archivo de Adobe se encuentra en [!DNL .ssh] el directorio del directorio raíz del usuario con el que inicia sesión

* El destino no es [!DNL ftp.omniture.com]. No se admite el protocolo SFTP entre los servidores internos de Adobe.
* El destino admite la autenticación de un factor (PKI). Si se exigen dos factores, el informe no se podrá entregar. Asegúrese de que el servidor no esté configurado para intentar la autenticación usando dos factores. Adobe Analytics requiere que, al iniciar sesión, solo se utilice la clave.
* Adobe admite el cifrado SSHv2 y regresa a SSHv1 (solo clave RSA).

To successfully send a [!DNL Data Warehouse] request via SFTP:

1. Pídale a uno de los usuarios de soporte técnico de su compañía que se ponga en contacto con el servicio de atención al cliente para obtener el archivo [!DNL authorized_keys].
1. After this file is obtained, log in to the FTP site under the same credentials that are used for the [!DNL Data Warehouse] request.
1. In the root directory, navigate to the folder named [!DNL .ssh] (if one does not exist, create one) and place the [!DNL authorized_keys] file there.

1. Go to the [!DNL Data Warehouse] request manager. Configure la solicitud según sus preferencias y luego haga clic en **[!UICONTROL Opciones de envío avanzadas]**.

1. In the pop-up window, click **[!UICONTROL FTP]**, then specify the ftp site (including the [!DNL sftp://] protocol, such as [!DNL sftp://ftp.omniture.com]) via port 22.

   Including the [!DNL sftp://] protocol is only permitted when using SFTP. Regular FTP requests should omit the protocol prefix (such as, [!DNL ftp.omniture.com] instead of [!DNL ftp://ftp.omniture.com]).

1. En el campo Carpeta, escriba el nombre de la carpeta donde quiere colocar el archivo. El nombre de la carpeta es obligatorio.
1. Escriba el nombre de usuario y la contraseña que usó en el paso 2.
1. Haga clic en **[!UICONTROL Enviar]**.

El comando PUT de SFTP coloca un archivo temporal con la extensión .part en el directorio especificado. Cuando la carga se termina, la extensión del archivo se cambia por la extensión final. Ahora el archivo ya está listo para su uso.

Alternatively, [!DNL sftp+norename://] can be specified instead of [!DNL sftp://] to upload the file directly with the final name, without a temporary [!DNL .part] file name during upload. Este método es adecuado cuando el servidor SFTP gestiona el cambio de nombre de archivos durante la carga automáticamente y no existe posibilidad de que el archivo se procese antes de que se complete la carga.

---
description: Adobe admite la exportación de solicitudes del almacén de datos a servidores SFTP.
keywords: ftp;sftp
title: Envío de solicitudes de Data Warehouse a los servidores SFTP
uuid: 393634a1-0643-4d63-bb6e-fb80f1ba76c1
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Envío de solicitudes de Data Warehouse a los servidores SFTP

Adobe admite la exportación de solicitudes del almacén de datos a servidores SFTP.

Asegúrese de que las tareas siguientes se hayan completado:

Adobe admite la exportación de solicitudes del almacén de datos a servidores SFTP, siempre que se cumplan los siguientes requisitos:

* [!DNL sftp://] se especifica en el campo host (por ejemplo, [!DNL sftp://ftp.example.com]) y SOLO se utiliza el puerto 22 al solicitar un informe del almacén de datos.

   También puede utilizar la [!DNL sftp+norename://] opción, como se describe a continuación.

* Adobe's [!DNL authorized_keys] file is in the [!DNL .ssh] directory within the root directory of the user you log in with

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

Alternatively, [!DNL sftp+norename://] can be specified instead of [!DNL sftp://] to upload the file directly with the final name, without a temporary [!DNL .part] file name during upload. Este método es adecuado cuando el servidor SFTP gestiona automáticamente el cambio de nombre de los archivos durante la carga y no hay ninguna posibilidad de que el archivo se procese antes de que la carga se complete.

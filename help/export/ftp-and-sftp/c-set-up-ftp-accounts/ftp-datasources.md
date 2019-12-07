---
description: Puede utilizar Analytics para crear y administrar fuentes de datos basadas en FTP, cosa que permite aprovechar la transferencia de archivos por FTP para importar datos sin conexión o historiales en Experience Cloud.
keywords: ftp;sftp
title: Fuentes de datos
uuid: 41ba2de7-d33d-4394-b7d8-04a116f45419
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Fuentes de datos

Puede utilizar Analytics para crear y administrar fuentes de datos basadas en FTP, cosa que permite aprovechar la transferencia de archivos por FTP para importar datos sin conexión o historiales en Experience Cloud.

Después de crear una instancia de Fuentes de datos, la herramienta proporciona una ubicación de FTP que puede utilizar para cargar archivos de Fuentes de datos. Después de la carga de los archivos, el sistema de Fuentes de datos los encontrará y procesará automáticamente. Una vez procesados los archivos, los datos quedan disponibles para informes de Analytics.

Desde la pestaña [!UICONTROL Crear] del Administrador de fuentes de datos se puede configurar una nueva instancia de fuentes de datos para el grupo de informes seleccionado. El [!UICONTROL Asistente de fuentes de datos] lo acompañará en el proceso de crear una plantilla de fuentes de datos y creará una ubicación de FTP donde cargar los datos.

En la ventana [!UICONTROL Administrar fuentes de datos], busque la fuente de datos y seleccione el vínculo Información de FTP. La información de inicio de sesión en el FTP aparece en la sección [!UICONTROL Información de carga/FTP] de la ventana [!UICONTROL Activar una fuente de datos].

Para obtener información sobre los límites de FTP y la retención de datos, consulte [Límites de FTP y retención de datos](/help/export/ftp-and-sftp/ftp-limits.md).

## Acerca del archivo .fin para cargas de clasificaciones y fuentes de datos {#section_1484719F8A134EAE91212DBD8F15174F}

When you upload a classifications or [!UICONTROL Data Source] file ( [!DNL .tab] or [!DNL .txt]) the upload also requires that you upload an empty file with the exact same name as the data file being imported, but with a [!DNL .fin] extension. This [!DNL .fin] file is a finish file. La función de este archivo es informar al sistema de que el archivo de datos se ha cargado completamente en la cuenta de FTP. The [!DNL .fin] file lets Adobe recognize that you are done with your import. Después de enviarlo, Adobe elimina ambos archivos del FTP y comienza a procesar la importación.
Importar archivo: [!DNL Classifications.tab]

Finalizar archivo: [!DNL Classifications.fin]

If you upload your Data Sources or SAINT file without an accompanying [!DNL .fin] file, Adobe does not add it to the queue for processing. The file remains on the FTP, and is not applied to your data in the [!UICONTROL Experience Cloud]. Solo recibirá un aviso de esto si previamente ha indicado que su dirección de correo electrónico es el [!UICONTROL Destinatario de notificaciones] en la ventana [!UICONTROL Crear cuenta de FTP] de creación de informes. Si no se escribe ninguna dirección de correo electrónico en este campo, no se envían notificaciones.

If you do upload your file with a [!DNL .fin] file, but there is an error in the file, it is submitted for processing, but the error causes the processing to cease and the file to be sent to an error folder. Si esto sucede, se envía una notificación a la dirección de correo electrónico indicada en el campo [!UICONTROL Destinatario de notificaciones] de la ventana [!UICONTROL Crear cuenta de FTP]. Si no se escribe ninguna dirección de correo electrónico, no se envían notificaciones.

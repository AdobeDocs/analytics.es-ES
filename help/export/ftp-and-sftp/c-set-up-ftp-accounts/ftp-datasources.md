---
description: Puede utilizar Analytics para crear y administrar fuentes de datos basadas en FTP, cosa que permite aprovechar la transferencia de archivos por FTP para importar datos sin conexión o historiales en Experience Cloud.
keywords: ftp; sftp
seo-description: Puede utilizar Analytics para crear y administrar fuentes de datos basadas en FTP, cosa que permite aprovechar la transferencia de archivos por FTP para importar datos sin conexión o historiales en Experience Cloud.
seo-title: Fuentes de datos
solution: Analytics
title: Fuentes de datos
uuid: 41 ba 2 de 7-d 33 d -4394-b 7 d 8-04 a 116 f 45419
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Fuentes de datos

Puede utilizar Analytics para crear y administrar fuentes de datos basadas en FTP, cosa que permite aprovechar la transferencia de archivos por FTP para importar datos sin conexión o historiales en Experience Cloud.

Después de crear una instancia de Fuentes de datos, la herramienta proporciona una ubicación de FTP que puede utilizar para cargar archivos de Fuentes de datos. Después de la carga de los archivos, el sistema de Fuentes de datos los encontrará y procesará automáticamente. Una vez procesados los archivos, los datos quedan disponibles para informes de Analytics.

Desde la pestaña [!UICONTROL Crear] del Administrador de fuentes de datos se puede configurar una nueva instancia de fuentes de datos para el grupo de informes seleccionado. El [!UICONTROL Asistente de fuentes de datos] lo acompañará en el proceso de crear una plantilla de fuentes de datos y creará una ubicación de FTP donde cargar los datos.

En la ventana [!UICONTROL Administrar fuentes de datos], busque la fuente de datos y seleccione el vínculo Información de FTP. La información de inicio de sesión en el FTP aparece en la sección [!UICONTROL Información de carga/FTP] de la ventana [!UICONTROL Activar una fuente de datos].

Para obtener información sobre los límites de FTP y la retención de datos, consulte [Límites de FTP y retención de datos](../../../export/ftp-and-sftp/ftp-limits.md#concept_8CAA1D8F27B3411AB902520AD6C9A70E).

## Acerca del archivo .fin para cargas de clasificaciones y fuentes de datos {#section_1484719F8A134EAE91212DBD8F15174F}

When you upload a classifications or [!UICONTROL Data Source] file ( [!DNL .tab] or [!DNL .txt]) the upload also requires that you upload an empty file with the exact same name as the data file being imported, but with a [!DNL .fin] extension. [!DNL .fin] Este archivo es un archivo de finalización. La función de este archivo es informar al sistema de que el archivo de datos se ha cargado completamente en la cuenta de FTP. The [!DNL .fin] file lets Adobe recognize that you are done with your import. Después de enviarlo, Adobe elimina ambos archivos del FTP y comienza a procesar la importación.
Importar archivo: [!DNL Classifications.tab]

Finish File: [!DNL Classifications.fin]

If you upload your Data Sources or SAINT file without an accompanying [!DNL .fin] file, Adobe does not add it to the queue for processing. The file remains on the FTP, and is not applied to your data in the [!UICONTROL Experience Cloud]. Solo recibirá un aviso de esto si previamente ha indicado que su dirección de correo electrónico es el [!UICONTROL Destinatario de notificaciones] en la ventana [!UICONTROL Crear cuenta de FTP] de creación de informes. Si no se escribe ninguna dirección de correo electrónico en este campo, no se envían notificaciones.

If you do upload your file with a [!DNL .fin] file, but there is an error in the file, it is submitted for processing, but the error causes the processing to cease and the file to be sent to an error folder. Si esto sucede, se envía una notificación a la dirección de correo electrónico indicada en el campo [!UICONTROL Destinatario de notificaciones] de la ventana [!UICONTROL Crear cuenta de FTP]. Si no se escribe ninguna dirección de correo electrónico, no se envían notificaciones.

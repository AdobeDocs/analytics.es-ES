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

Después de crear una instancia de Fuentes de datos, la herramienta proporciona una ubicación de FTP que puede utilizar para cargar archivos de Fuentes de datos. Después de la carga de los archivos, el sistema de fuentes de datos los encontrará y procesará automáticamente. Una vez procesados los archivos, los datos quedan disponibles para informes de Analytics.

The [!UICONTROL Create] tab in the Data Sources Manager lets you configure a new Data Sources instance for the selected report suite. The [!UICONTROL Data Sources Wizard] guides you through the process of creating a Data Sources template, and creates an FTP location for uploading data.

In the [!UICONTROL Manage Data Sources] window, find your data source and select the FTP Info link. La información de inicio de sesión de FTP se muestra en la [!UICONTROL Activate a Data Source] ventana de la [!UICONTROL Upload/FTP Information] sección .

Para obtener información sobre los límites de FTP y la retención de datos, consulte Límites de [FTP y Retención](/help/export/ftp-and-sftp/ftp-limits.md)de datos.

## Acerca del archivo .fin para cargas de clasificaciones y fuentes de datos {#section_1484719F8A134EAE91212DBD8F15174F}

When you upload a classifications or [!UICONTROL Data Source] file ( [!DNL .tab] or [!DNL .txt]) the upload also requires that you upload an empty file with the exact same name as the data file being imported, but with a [!DNL .fin] extension. El archivo [!DNL .fin] es un archivo de finalización. La función de este archivo es informar al sistema de que el archivo de datos se ha cargado completamente en la cuenta de FTP. El archivo [!DNL .fin] permite a Adobe saber que la importación ha finalizado. Después de enviarlo, Adobe elimina ambos archivos del FTP y comienza a procesar la importación.
Importar archivo: [!DNL Classifications.tab]

Finalizar archivo: [!DNL Classifications.fin]

Si se carga el archivo de fuentes de datos o SAINT sin el archivo [!DNL .fin] correspondiente, Adobe no lo añadirá a la cola para su procesamiento. El archivo permanece en el FTP y no se aplica a los datos que haya en [!UICONTROL Experience Cloud]. You are notified of this only if you have entered your email address as the [!UICONTROL Notification Recipient] in the [!UICONTROL Create FTP Account] window of reporting. Si no se escribe ninguna dirección de correo electrónico en este campo, no se envían notificaciones.

Si el archivo que se carga con un archivo [!DNL .fin] tiene algún error, se envía para su procesamiento, pero el error interrumpe el procesamiento y el archivo se envía a una carpeta de errores. If this occurs, a notification is sent to the email address listed in the [!UICONTROL Notification Recipient] field in the [!UICONTROL Create FTP Account] window. Si no se escribe ninguna dirección de correo electrónico, no se envían notificaciones.

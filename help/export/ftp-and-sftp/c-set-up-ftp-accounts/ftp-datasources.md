---
description: Puede utilizar Analytics para crear y administrar fuentes de datos basadas en FTP, cosa que permite aprovechar la transferencia de archivos por FTP para importar datos sin conexión o historiales en Experience Cloud.
keywords: ftp;sftp
title: Fuentes de datos
uuid: 41ba2de7-d33d-4394-b7d8-04a116f45419
exl-id: 777917bd-bd11-4360-a149-e4fd0bb2f99e
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '450'
ht-degree: 100%

---

# Fuentes de datos

Puede utilizar Analytics para crear y administrar fuentes de datos basadas en FTP, cosa que permite aprovechar la transferencia de archivos por FTP para importar datos sin conexión o historiales en Experience Cloud.

Después de crear una instancia de Fuentes de datos, la herramienta proporciona una ubicación de FTP que puede utilizar para cargar archivos de Fuentes de datos. Después de la carga de los archivos, el sistema de fuentes de datos los encontrará y procesará automáticamente. Una vez procesados los archivos, los datos quedan disponibles para informes de Analytics.

Desde la pestaña [!UICONTROL Crear] del Administrador de fuentes de datos se puede configurar una nueva instancia de fuentes de datos para el grupo de informes seleccionado. El [!UICONTROL Asistente de fuentes de datos] lo acompañará en el proceso de crear una plantilla de fuentes de datos y creará una ubicación de FTP donde cargar los datos.

En la ventana [!UICONTROL Administrar fuentes de datos], busque la fuente de datos y seleccione el vínculo Información de FTP. La información de inicio de sesión en el FTP aparece en la sección [!UICONTROL Información de carga/FTP] de la ventana [!UICONTROL Activar una fuente de datos].

Para obtener información sobre los límites de FTP y la retención de datos, consulte [Límites de FTP y retención de datos](/help/export/ftp-and-sftp/ftp-limits.md).

## Acerca del archivo .fin para cargas de clasificaciones y fuentes de datos {#section_1484719F8A134EAE91212DBD8F15174F}

Al cargar un archivo de clasificaciones o [!UICONTROL fuente de datos] ([!DNL .tab] o [!DNL .txt]), también hay que cargar un archivo vacío que tenga el mismo nombre que el archivo de datos que se va a importar, pero con una extensión [!DNL .fin]. El archivo [!DNL .fin] es un archivo de finalización. La función de este archivo es informar al sistema de que el archivo de datos se ha cargado completamente en la cuenta de FTP. El archivo [!DNL .fin] permite a Adobe saber que la importación ha finalizado. Después de enviarlo, Adobe elimina ambos archivos del FTP y comienza a procesar la importación.
Importar archivo: [!DNL Classifications.tab]

Finalizar archivo: [!DNL Classifications.fin]

Si se carga el archivo de fuentes de datos o SAINT sin el archivo [!DNL .fin] correspondiente, Adobe no lo añadirá a la cola para su procesamiento. El archivo permanece en el FTP y no se aplica a los datos que haya en [!UICONTROL Experience Cloud]. Solo recibirá un aviso de esto si previamente ha indicado que su dirección de correo electrónico es el [!UICONTROL Destinatario de notificaciones] en la ventana [!UICONTROL Crear cuenta de FTP] de creación de informes. Si no se escribe ninguna dirección de correo electrónico en este campo, no se envían notificaciones.

Si el archivo que se carga con un archivo [!DNL .fin] tiene algún error, se envía para su procesamiento, pero el error interrumpe el procesamiento y el archivo se envía a una carpeta de errores. Si esto sucede, se envía una notificación a la dirección de correo electrónico indicada en el campo [!UICONTROL Destinatario de notificaciones] de la ventana [!UICONTROL Crear cuenta de FTP]. Si no se escribe ninguna dirección de correo electrónico, no se envían notificaciones.

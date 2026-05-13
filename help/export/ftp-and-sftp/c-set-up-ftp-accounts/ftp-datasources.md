---
description: Puede utilizar Analytics para crear y administrar fuentes de datos basadas en FTP, cosa que permite aprovechar la transferencia de archivos por FTP para importar datos sin conexión o historiales en Experience Cloud.
keywords: ftp;sftp
title: Resumen de las fuentes de datos
feature: FTP Export
exl-id: 777917bd-bd11-4360-a149-e4fd0bb2f99e
TQID: https://experienceleague.adobe.com/Mq4r5p1872tIxfjts7HOq50XWky12Oy4fTi9ajzbAsc
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 455
ht-degree: 60%

---

# Fuentes de datos basadas en FTP

Puede utilizar Analytics para crear y administrar fuentes de datos basadas en FTP, cosa que permite aprovechar la transferencia de archivos por FTP para importar datos sin conexión o historiales en Experience Cloud.

Después de crear una instancia de fuente de datos, la herramienta proporciona una ubicación de FTP que se puede utilizar para cargar los archivos de fuente de datos. Después de la carga de los archivos, el sistema de fuentes de datos los encontrará y procesará automáticamente. Una vez procesados los archivos, los datos estarán disponibles para los informes de Analytics.

La ficha [!UICONTROL Crear] del Administrador de fuentes de datos le permite configurar una nueva instancia de fuente de datos para el grupo de informes seleccionado. El [!UICONTROL Asistente para fuentes de datos] le guiará a través del proceso de creación de una plantilla de fuentes de datos y creará una ubicación FTP para cargar los datos.

En la ventana [!UICONTROL Administrar fuentes de datos], busque la fuente de datos y seleccione el vínculo Información de FTP. Su información de inicio de sesión en FTP se muestra en la ventana [!UICONTROL Activar un Source de datos] de la sección [!UICONTROL Cargar información del FTP].

Para obtener información sobre los límites de FTP y la retención de datos, consulte [Límites de FTP y retención de datos](/help/export/ftp-and-sftp/ftp-limits.md).

## Acerca del archivo .fin para cargas de clasificaciones y fuentes de datos {#section_1484719F8A134EAE91212DBD8F15174F}

Al cargar un archivo de clasificaciones o [!UICONTROL fuente de datos] ([!DNL .tab] o [!DNL .txt]), también hay que cargar un archivo vacío que tenga el mismo nombre que el archivo de datos que se va a importar, pero con una extensión [!DNL .fin]. El archivo [!DNL .fin] es un archivo de finalización. La función de este archivo es informar al sistema de que el archivo de datos se ha cargado completamente en la cuenta de FTP. El archivo [!DNL .fin] permite a Adobe saber que la importación ha finalizado. Después de enviarlo, Adobe elimina ambos archivos del FTP y comienza a procesar la importación.
Importar archivo: [!DNL Classifications.tab]

Finalizar archivo: [!DNL Classifications.fin]

Si se carga el archivo de fuentes de datos o SAINT sin el archivo [!DNL .fin] correspondiente, Adobe no lo añadirá a la cola para su procesamiento. El archivo permanece en el FTP y no se aplica a los datos que haya en [!UICONTROL Experience Cloud]. Se le notificará esto solamente si ha ingresado su dirección de correo electrónico como [!UICONTROL Destinatario de notificación] en la ventana de informes [!UICONTROL Crear cuenta de FTP]. Si no se introduce ninguna dirección de correo electrónico en este campo, no se envía ninguna notificación.

Si el archivo que se carga con un archivo [!DNL .fin] tiene algún error, se envía para su procesamiento, pero el error interrumpe el procesamiento y el archivo se envía a una carpeta de errores. Si esto sucede, se envía una notificación a la dirección de correo electrónico indicada en el campo [!UICONTROL Destinatario de notificaciones] de la ventana [!UICONTROL Crear cuenta de FTP]. Si no se introduce ninguna dirección de correo electrónico, no se envía ninguna notificación.

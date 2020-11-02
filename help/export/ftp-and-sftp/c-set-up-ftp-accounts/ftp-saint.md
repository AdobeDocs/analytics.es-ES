---
description: La opción de FTP (SAINT) de las clasificaciones ofrece más flexibilidad a la hora de cargar grandes conjuntos de datos de clasificación, incluida la capacidad de cargar datos en varios grupos de informes, así como cargar conjuntos de datos con más de 50 000 filas.
keywords: ftp;sftp
title: Clasificaciones
uuid: 35936c98-b785-43eb-89f4-ab42a10db256
translation-type: tm+mt
source-git-commit: 7a70a5185b768dbc09deca5c8989693501af0cca
workflow-type: tm+mt
source-wordcount: '483'
ht-degree: 68%

---


# Clasificaciones

La opción de FTP de las clasificaciones ofrece más flexibilidad a la hora de cargar grandes conjuntos de datos de clasificación, incluida la capacidad de cargar datos en varios grupos de informes, así como cargar conjuntos de datos con más de 50 000 filas.

Consulte las [clasificaciones](https://docs.adobe.com/content/help/es-ES/analytics/components/classifications/classifications-importer/c-working-with-saint.html) si quiere conocer los pasos para descargar datos de clasificación por FTP y para cargar archivos de datos a través de FTP (incluidos los pasos de creación de una cuenta de FTP).

La cantidad de tiempo que el sistema necesita para importar estos archivos varía en función de diversos factores. Si hay un archivo cargado en el servidor FTP durante más de tres días, trabaje con los usuarios de asistencia técnica de su organización para ponerse en contacto con el Servicio de atención al cliente de Adobe.

Las importaciones que se llevan a cabo correctamente enseguida muestran los cambios correspondientes en una exportación, mientras que los cambios de datos en Analytics pueden tardar hasta cuatro horas con una importación por navegador y hasta 24 horas con una importación por FTP.

Para obtener información sobre los límites de FTP y la retención de datos, consulte [Límites de FTP y retención de datos](/help/export/ftp-and-sftp/ftp-limits.md).

## About the `.fin` file for Classifications and Data Sources Uploads {#section_1484719F8A134EAE91212DBD8F15174F}

When you upload a Classification or Data Source file (`.tab` or `.txt`), the upload also requires that you upload an empty file with the exact same name as the data file being imported, but with a .`.fin` extension. El archivo `.fin` es un archivo de finalización. La función de este archivo es informar al sistema de que el archivo de datos se ha cargado completamente en la cuenta de FTP. El archivo `.fin` permite a Adobe saber que la importación ha finalizado.

Después de enviar el archivo de origen y el `.fin` archivo, es importante cerrar la sesión en el sitio FTP. El motivo es que Adobe Analytics utiliza eventos de cierre de sesión como activador para que los archivos estén listos para su procesamiento. Una vez completada la importación, Adobe elimina ambos archivos de la ubicación FTP.

Finalizar archivo: [!DNL Classifications.fin]

If you upload your Data Sources or Classification file without an accompanying `.fin` file, Adobe does not add it to the queue for processing. El archivo permanece en el FTP y no se aplica a los datos de [!UICONTROL Experience Cloud]. Solo recibirá un aviso de esto si previamente ha indicado que su dirección de correo electrónico es el [!UICONTROL Destinatario de notificaciones] en la ventana [!UICONTROL Crear cuenta de FTP] de Analytics. Si no se escribe ninguna dirección de correo electrónico en este campo, no se envían notificaciones.

Si el archivo que se carga con un archivo `.fin` tiene algún error, se envía para su procesamiento, pero el error interrumpe el procesamiento y el archivo se envía a una carpeta de errores. Si esto sucede, se envía una notificación a la dirección de correo electrónico indicada en el campo [!UICONTROL Destinatario de notificaciones] de la ventana [!UICONTROL Crear cuenta de FTP]. Si no se especificó ninguna dirección de correo electrónico, no se enviará ninguna notificación.

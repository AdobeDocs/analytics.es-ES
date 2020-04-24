---
description: La opción de FTP (SAINT) de las clasificaciones ofrece más flexibilidad a la hora de cargar grandes conjuntos de datos de clasificación, incluida la capacidad de cargar datos en varios grupos de informes, así como cargar conjuntos de datos con más de 50 000 filas.
keywords: ftp;sftp
title: Clasificaciones
uuid: 35936c98-b785-43eb-89f4-ab42a10db256
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Clasificaciones

La opción de FTP de las clasificaciones ofrece más flexibilidad a la hora de cargar grandes conjuntos de datos de clasificación, incluida la capacidad de cargar datos en varios grupos de informes, así como cargar conjuntos de datos con más de 50 000 filas.

Consulte las [clasificaciones](https://marketing.adobe.com/resources/help/es_ES/reference/c_working_with_saint.html) si quiere conocer los pasos para descargar datos de clasificación por FTP y para cargar archivos de datos a través de FTP (incluidos los pasos de creación de una cuenta de FTP).

La cantidad de tiempo que el sistema necesita para importar estos archivos varía en función de diversos factores. Si un archivo cargado sigue estando en el servidor FTP pasadas seis horas, trabaje con los usuarios de soporte técnico de su compañía para ponerse en contacto con el servicio de atención al cliente de Adobe.

Las importaciones que se llevan a cabo correctamente enseguida muestran los cambios correspondientes en una exportación, mientras que los cambios de datos en Analytics pueden tardar hasta cuatro horas con una importación por navegador y hasta 24 horas con una importación por FTP.

Para obtener información sobre los límites de FTP y la retención de datos, consulte [Límites de FTP y retención de datos](/help/export/ftp-and-sftp/ftp-limits.md).

## Acerca del archivo .fin para cargas de clasificaciones y fuentes de datos {#section_1484719F8A134EAE91212DBD8F15174F}

When you upload a classification or [!UICONTROL Data Source] file ( [!DNL .tab]or [!DNL .txt]) the upload also requires that you upload an empty file with the exact same name as the data file being imported, but with a [!DNL .fin] extension. El archivo [!DNL .fin] es un archivo de finalización. La función de este archivo es informar al sistema de que el archivo de datos se ha cargado completamente en la cuenta de FTP. El archivo [!DNL .fin] permite a Adobe saber que la importación ha finalizado. Después de enviarlo, Adobe elimina ambos archivos del FTP y comienza a procesar la importación.
Archivo de importación: [!DNL Classifications.tab]

Archivo de finalización: [!DNL Classifications.fin]

Si se carga el archivo de fuentes de datos o de clasificación sin el archivo [!DNL .fin] correspondiente, Adobe no lo añadirá a la cola para su procesamiento. El archivo permanece en el FTP y no se aplica a los datos que haya en [!UICONTROL Experience Cloud]. You are notified of this only if you have entered your email address as the [!UICONTROL Notification Recipient] in the [!UICONTROL Create FTP Account] window of Analytics. Si no se escribe ninguna dirección de correo electrónico en este campo, no se envían notificaciones.

Si el archivo que se carga con un archivo [!DNL .fin] tiene algún error, se envía para su procesamiento, pero el error interrumpe el procesamiento y el archivo se envía a una carpeta de errores. If this occurs, a notification is sent to the email address listed in the [!UICONTROL Notification Recipient] field in the [!UICONTROL Create FTP Account] window. Si no se escribe ninguna dirección de correo electrónico, no se envían notificaciones.

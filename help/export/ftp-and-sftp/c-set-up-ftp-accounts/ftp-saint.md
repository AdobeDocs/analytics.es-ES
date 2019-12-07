---
description: La opción de FTP (SAINT) de las clasificaciones ofrece más flexibilidad a la hora de cargar grandes conjuntos de datos de clasificación, incluida la capacidad de cargar datos en varios grupos de informes, así como cargar conjuntos de datos con más de 50 000 filas.
keywords: ftp;sftp
title: Clasificaciones
uuid: 35936c98-b785-43eb-89f4-ab42a10db256
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Clasificaciones

La opción de FTP de clasificaciones proporciona más flexibilidad para cargar grandes conjuntos de datos de clasificación, incluida la capacidad de cargar datos en varios grupos de informes y cargar conjuntos de datos de más de 50.000 filas.

Consulte las [clasificaciones](https://marketing.adobe.com/resources/help/en_US/reference/c_working_with_saint.html) si quiere conocer los pasos para descargar datos de clasificación por FTP y para cargar archivos de datos a través de FTP (incluidos los pasos de creación de una cuenta de FTP).

La cantidad de tiempo que el sistema necesita para importar estos archivos varía en función de diversos factores. Si un archivo cargado sigue estando en el servidor FTP pasadas seis horas, trabaje con los usuarios de soporte técnico de su compañía para ponerse en contacto con el servicio de atención al cliente de Adobe.

Las importaciones que se llevan a cabo correctamente enseguida muestran los cambios correspondientes en una exportación, mientras que los cambios de datos en Analytics pueden tardar hasta cuatro horas con una importación por navegador y hasta 24 horas con una importación por FTP.

Para obtener información sobre los límites de FTP y la retención de datos, consulte [Límites de FTP y retención de datos](/help/export/ftp-and-sftp/ftp-limits.md).

## Acerca del archivo .fin para cargas de clasificaciones y fuentes de datos {#section_1484719F8A134EAE91212DBD8F15174F}

When you upload a classification or [!UICONTROL Data Source] file ( [!DNL .tab]or [!DNL .txt]) the upload also requires that you upload an empty file with the exact same name as the data file being imported, but with a [!DNL .fin] extension. This [!DNL .fin] file is a finish file. La función de este archivo es informar al sistema de que el archivo de datos se ha cargado completamente en la cuenta de FTP. The [!DNL .fin] file lets Adobe recognize that you are done with your import. Después de enviarlo, Adobe elimina ambos archivos del FTP y comienza a procesar la importación.
Importar archivo: [!DNL Classifications.tab]

Finalizar archivo: [!DNL Classifications.fin]

If you upload your Data Sources or classification file without an accompanying [!DNL .fin] file, Adobe does not add it to the queue for processing. The file remains on the FTP, and is not applied to your data in the [!UICONTROL Experience Cloud]. Solo recibirá un aviso de esto si previamente ha indicado que su dirección de correo electrónico es el [!UICONTROL Destinatario de notificaciones] en la ventana [!UICONTROL Crear cuenta de FTP] de Analytics. Si no se escribe ninguna dirección de correo electrónico en este campo, no se envían notificaciones.

If you do upload your file with a [!DNL .fin] file, but there is an error in the file, it is submitted for processing, but the error causes the processing to cease and the file to be sent to an error folder. Si esto sucede, se envía una notificación a la dirección de correo electrónico indicada en el campo [!UICONTROL Destinatario de notificaciones] de la ventana [!UICONTROL Crear cuenta de FTP]. Si no se escribe ninguna dirección de correo electrónico, no se envían notificaciones.

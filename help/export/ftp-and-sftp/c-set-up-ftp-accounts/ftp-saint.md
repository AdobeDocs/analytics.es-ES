---
description: La opción de FTP (SAINT) de las clasificaciones ofrece más flexibilidad a la hora de cargar grandes conjuntos de datos de clasificación, incluida la capacidad de cargar datos en varios grupos de informes, así como cargar conjuntos de datos con más de 50 000 filas.
keywords: ftp;sftp
title: Clasificaciones
uuid: 35936c98-b785-43eb-89f4-ab42a10db256
exl-id: fc783328-a70b-4af3-b3d3-c59ab79d6b8f
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '483'
ht-degree: 98%

---

# Clasificaciones

La opción de FTP de las clasificaciones ofrece más flexibilidad a la hora de cargar grandes conjuntos de datos de clasificación, incluida la capacidad de cargar datos en varios grupos de informes, así como cargar conjuntos de datos con más de 50 000 filas.

Consulte las [clasificaciones](https://experienceleague.adobe.com/docs/analytics/components/classifications/classifications-importer/c-working-with-saint.html) si quiere conocer los pasos para descargar datos de clasificación por FTP y para cargar archivos de datos a través de FTP (incluidos los pasos de creación de una cuenta de FTP).

La cantidad de tiempo que el sistema necesita para importar estos archivos varía en función de diversos factores. Si un archivo cargado está en el servidor FTP pasados más de tres días, colabore con los usuarios de soporte técnico de su compañía para ponerse en contacto con el Servicio de atención al cliente de Adobe.

Las importaciones que se llevan a cabo correctamente enseguida muestran los cambios correspondientes en una exportación, mientras que los cambios de datos en Analytics pueden tardar hasta cuatro horas con una importación por navegador y hasta 24 horas con una importación por FTP.

Para obtener información sobre los límites de FTP y la retención de datos, consulte [Límites de FTP y retención de datos](/help/export/ftp-and-sftp/ftp-limits.md).

## Acerca del archivo `.fin` para cargas de clasificaciones y fuentes de datos {#section_1484719F8A134EAE91212DBD8F15174F}

Al cargar un archivo de clasificación o fuente de datos (`.tab` o `.txt`), también hay que cargar un archivo vacío que tenga el mismo nombre que el archivo de datos que se va a importar, pero con una extensión `.fin`. El archivo `.fin` es un archivo de finalización. La función de este archivo es informar al sistema de que el archivo de datos se ha cargado completamente en la cuenta de FTP. El archivo `.fin` permite a Adobe saber que la importación ha finalizado.

Después de enviar el archivo de origen y el archivo `.fin`, es importante cerrar la sesión en el sitio FTP. El motivo es que Adobe Analytics utiliza eventos de cierre de sesión como un activador de que los archivos están listos para procesarse. Una vez completada la importación, Adobe elimina ambos archivos de la ubicación FTP.

Finalizar archivo: [!DNL Classifications.fin]

Si se carga el archivo de fuentes de datos o de clasificación sin el archivo `.fin` correspondiente, Adobe no lo añadirá a la cola para su procesamiento. El archivo permanece en el FTP y no se aplica a los datos de [!UICONTROL Experience Cloud]. Solo recibirá un aviso de esto si previamente ha indicado que su dirección de correo electrónico es el [!UICONTROL Destinatario de notificaciones] en la ventana [!UICONTROL Crear cuenta de FTP] de Analytics. Si no se escribe ninguna dirección de correo electrónico en este campo, no se envían notificaciones.

Si el archivo que se carga con un archivo `.fin` tiene algún error, se envía para su procesamiento, pero el error interrumpe el procesamiento y el archivo se envía a una carpeta de errores. Si esto sucede, se envía una notificación a la dirección de correo electrónico indicada en el campo [!UICONTROL Destinatario de notificaciones] de la ventana [!UICONTROL Crear cuenta de FTP]. Si no se escribe ninguna dirección de correo electrónico, no se envían notificaciones.

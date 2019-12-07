---
description: Pasos que describen cómo cargar un archivo de fuente de datos.
subtopic: Data sources
title: Cargar un archivo de fuente de datos
topic: Developer and implementation
uuid: 5a9dde91-1297-47e5-9393-611b40413c17
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Cargar un archivo de fuente de datos

Pasos que describen cómo cargar un archivo de fuente de datos.

Después de preparar un archivo de fuente de datos, debe enviarlo al sistema de fuentes de datos para que lo procese. Adobe mantiene varios servidores FTP donde se pueden cargar archivos de fuente de datos. Tenga en cuenta lo siguiente en relación con estos servidores FTP:

* Select FTP Info next to the Data Source entry in the [!UICONTROL Data Sources Manage] tab to see the FTP Host, Login, and Password information for the data source's FTP account. Cualquier persona que tenga acceso a esta información podrá cargar datos en el grupo de informes.
* Por razones de seguridad, las cuentas FTP se cierran después de 30 días de inactividad.
* Cada cuenta FTP es exclusiva de una fuente de datos. No se puede usar una misma cuenta FTP para cargar archivos de varias fuentes de datos.

**Para cargar un archivo de fuente de datos**

1. Utilice un cliente FTP para enviar los datos a su sitio de fuentes de datos del FTP.

   (Está disponible en el vínculo Información de FTP del Administrador de fuentes de datos).

1. Upload a [!DNL .fin] file to notify Adobe that the Data Sources file upload is complete.

   The [!DNL .fin] file must have the exact same name as the Data Sources file, except for the file extension. Adobe does not queue the Data Sources file for processing until you upload the [!DNL .fin] file.

   No cargue el archivo hasta que se acaben de cargar todos los archivos de fuente de datos. Si no espera, puede que las fuentes de datos intenten procesar un archivo incompleto.
1. Durante el procesamiento del archivo de fuente de datos, observe si aparece algún mensaje del sistema.

   Si durante el procesamiento del archivo se producen errores, el Administrador de fuentes de datos mostrará un mensaje relacionado.


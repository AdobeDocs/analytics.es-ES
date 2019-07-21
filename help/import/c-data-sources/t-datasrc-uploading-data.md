---
description: Pasos que describen cómo cargar un archivo de fuente de datos.
seo-description: Pasos que describen cómo cargar un archivo de fuente de datos.
seo-title: Carga de un archivo de fuente de datos
solution: Analytics
subtopic: Fuentes de datos
title: Carga de un archivo de fuente de datos
topic: Desarrollador e implementación
uuid: 5 a 9 dde 91-1297-47 e 5-9393-611 b 40413 c 17
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Carga de un archivo de fuente de datos

Pasos que describen cómo cargar un archivo de fuente de datos.

Después de preparar un archivo de fuente de datos, debe enviarlo al sistema de fuentes de datos para que lo procese. Adobe mantiene varios servidores FTP donde se pueden cargar archivos de fuente de datos. Tenga en cuenta lo siguiente en relación con estos servidores FTP:

* Seleccione Información de FTP al lado de la fuente de datos en la ficha [!UICONTROL Administrar fuentes de datos] para ver el servidor FTP, el usuario y la contraseña correspondientes a la cuenta FTP de la fuente de datos. Cualquier persona que tenga acceso a esta información podrá cargar datos en el grupo de informes.
* Por razones de seguridad, las cuentas FTP se cierran después de 30 días de inactividad.
* Cada cuenta FTP es exclusiva de una fuente de datos. No se puede usar una misma cuenta FTP para cargar archivos de varias fuentes de datos.

**Para cargar un archivo de fuente de datos**

1. Utilice un cliente FTP para enviar los datos a su sitio de fuentes de datos del FTP.

   (Está disponible en el vínculo Información de FTP del Administrador de fuentes de datos).

1. Upload a [!DNL .fin] file to notify Adobe that the Data Sources file upload is complete.

   [!DNL .fin] El archivo debe tener el mismo nombre que el archivo de fuente de datos, excepto la extensión del archivo. Adobe does not queue the Data Sources file for processing until you upload the [!DNL .fin] file.

   No cargue el archivo hasta que se acaben de cargar todos los archivos de fuente de datos. Si no espera, puede que las fuentes de datos intenten procesar un archivo incompleto.
1. Durante el procesamiento del archivo de fuente de datos, observe si aparece algún mensaje del sistema.

   Si durante el procesamiento del archivo se producen errores, el Administrador de fuentes de datos mostrará un mensaje relacionado.


---
description: Pasos que describen cómo cargar un archivo de fuente de datos.
subtopic: Data sources
title: Cargar un archivo de fuente de datos
topic-fix: Developer and implementation
uuid: 5a9dde91-1297-47e5-9393-611b40413c17
exl-id: 8b7fa32c-01f2-452b-bf8e-8a81da266926
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '293'
ht-degree: 87%

---

# Cargar un archivo de fuente de datos

Después de preparar un archivo de fuente de datos, debe enviarlo al sistema de fuentes de datos para que lo procese. Adobe mantiene varios servidores FTP donde se pueden cargar archivos de fuente de datos. Tenga en cuenta lo siguiente en relación con estos servidores FTP:

* Seleccione Información de FTP al lado de la fuente de datos en la pestaña [!UICONTROL Administrar fuentes de datos] para ver el servidor FTP, el usuario y la contraseña correspondientes a la cuenta FTP de la fuente de datos. Cualquier persona que tenga acceso a esta información podrá cargar datos en el grupo de informes.
* Por razones de seguridad, las cuentas FTP se cierran después de 30 días de inactividad.
* Cada cuenta FTP es exclusiva de una fuente de datos. No se puede usar una misma cuenta FTP para cargar archivos de varias fuentes de datos.

**Para cargar un archivo de fuente de datos**

1. Utilice un cliente FTP para enviar los datos a su sitio de fuentes de datos del FTP.

   (Está disponible en el vínculo Información de FTP del Administrador de fuentes de datos).

1. Cuando la carga del archivo de fuente de datos esté completa, cargue un archivo [!DNL .fin] para informar a Adobe.

   El archivo [!DNL .fin] debe tener el mismo nombre que el archivo de fuente de datos, a excepción de la extensión de archivo. Adobe solamente colocará el archivo de fuente de datos en la cola de procesamiento cuando se cargue el archivo [!DNL .fin].

   No cargue el archivo hasta que se acaben de cargar todos los archivos de fuente de datos. Si no espera, puede que las fuentes de datos intenten procesar un archivo incompleto.
1. Una vez cargado el archivo .fin, es importante que cierre la sesión del sitio FTP de fuentes de datos. El motivo es que Analytics utiliza eventos de cierre de sesión como déclencheur para indicar que los archivos están listos para procesarse.
1. Durante el procesamiento del archivo de fuente de datos, observe si aparece algún mensaje del sistema.

   Si durante el procesamiento del archivo se producen errores, el Administrador de fuentes de datos mostrará un mensaje relacionado.

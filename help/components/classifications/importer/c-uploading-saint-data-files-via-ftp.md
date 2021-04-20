---
description: Instrucciones sobre cómo cargar archivos de datos a través de FTP.
subtopic: Classifications
title: Importación de FTP
feature: Admin Tools
uuid: a914970d-ba02-4111-9dcf-06448f71b9f3
exl-id: 3e93b35c-6f65-4a93-887d-d94e4d359bdc
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '723'
ht-degree: 100%

---

# Importación de FTP

Instrucciones sobre cómo cargar archivos de datos a través de FTP.

## Importación de FTP {#concept_2F965BE873254546A61FB755F25299FD}

Instrucciones sobre cómo cargar archivos de datos a través de FTP.

**[!UICONTROL Administración]** > **[!UICONTROL Importador de clasificaciones]**.

Es importante tener en cuenta los límites recomendados siguientes:

* Muchos archivos de pequeño tamaño resultarán en un procesamiento más lento que pocos archivos de gran tamaño. Esto es debido a la cantidad de cola y priorización necesaria para estas tareas de menor tamaño.
* Divida los archivos de gran tamaño en partes de 50 MB. Esto no es necesario, pero es recomendable ya que proporciona una mejor visibilidad del progreso en segundo plano. Además, si se producen errores mientras procesa su trabajo, el trabajo se reiniciará y, este caso, los archivos de gran tamaño provocarán la repetición de una gran cantidad de trabajo.

En lugar de agregar filas o reclasificar solo algunas de ellas, la configuración inicial rellena la base de datos con un gran conjunto de datos originales o reestructura las clasificaciones.

Después de realizar una carga inicial en un grupo de informes (de un informe o una variable en concreto), Adobe recomienda cargar solamente las filas nuevas y las actualizadas en las importaciones subsiguientes. Las filas que no se cambien en absoluto deben omitirse de las cargas futuras.

Cada nuevo valor clave que cargue se restará a los únicos de esa variable para el mes.

Si ha superado las únicas del mes, no verá los datos de clasificación correspondientes a los valores únicos superados en los informes. Puede ver dichas clasificaciones en Data Warehouse.

>[!NOTE]
>
>El tiempo necesario para procesar un archivo de datos de clasificación varía según el tamaño del archivo y la cantidad de archivos que estén procesando los servidores de Adobe en ese momento. El procesamiento de los archivos no suele tardar más de 72 horas.

Antes de cargar datos a través de FTP, se debe crear una cuenta de FTP. Para obtener más información, consulte [Crear una cuenta FTP](/help/components/classifications/importer/c-uploading-saint-data-files-via-ftp.md#task_C019268E6C934C7C95F4326F42A22CCF).

## Importar clasificaciones a través del FTP {#task_132C36830B69418B8C929E39838EF01D}

<!-- 

t_upload_a_saint_data_file_via_ftp.xml

 -->

Instrucciones sobre cómo utilizar una cuenta de FTP para importar clasificaciones en Adobe Analytics.

Para obtener más información acerca de cómo crear una cuenta de FTP, consulte [Crear una cuenta de FTP](/help/components/classifications/importer/c-uploading-saint-data-files-via-ftp.md#task_C019268E6C934C7C95F4326F42A22CCF).

1. Haga clic en **[!UICONTROL Administración]** > **[!UICONTROL Importador de clasificaciones]**.
1. Haga clic en **[!UICONTROL Importar archivo]** y, a continuación, seleccione **[!UICONTROL Importar FTP]**.
1. Junto a la cuenta de FTP que desea utilizar, haga clic en **[!UICONTROL Ver]**.
1. Utilice la información de acceso al FTP (host, nombre de usuario y contraseña) para acceder al servidor FTP con un cliente FTP de su elección.
1. Cargue el archivo de datos ( [!DNL .tab] o [!DNL .txt]) al servidor FTP.
1. Una vez cargado el archivo de datos, cargue un archivo FIN que indique el archivo está listo para ser procesado.

   El archivo FIN es un archivo vacío que tiene el mismo nombre que su archivo de datos, con la extensión de nombre de archivo [!DNL .fin]. Por ejemplo, si su archivo de datos es [!DNL classdata1.tab], el nombre del archivo es [!DNL classdata1.fin] .fin.

A intervalos periódicos, Adobe recupera los archivos de datos cargados que tienen un archivo FIN asociado. Adobe los importa en los grupos de informes y conjuntos de datos indicados en la configuración de la cuenta FTP.

## Crear una cuenta de FTP {#task_C019268E6C934C7C95F4326F42A22CCF}

Antes de cargar datos a través de FTP, se debe crear una cuenta de FTP. >

<!-- 

t_create_an_ftp_account.xml

 -->

Consulte [FTP y sFTP](https://docs.adobe.com/content/help/es-ES/analytics/export/ftp-and-sftp/ftp-overview.html) para obtener más información sobre los servidores FTP de Adobe.

1. Haga clic en **[!UICONTROL Administración]** > **[!UICONTROL Importador de clasificaciones]**.
1. Haga clic en **[!UICONTROL Importar archivo]** y, a continuación, seleccione **[!UICONTROL Importar FTP]**.
1. En la pestaña **[!UICONTROL Importar archivo]**, haga clic en **[!UICONTROL Añadir nuevo]**.
1. Indique los detalles de la cuenta de FTP:

   | Elemento | Descripción |
   |---|---|
   | Nombre | El nombre de la cuenta de FTP. |
   | Conjunto de datos a clasificar | En la lista desplegable, seleccione el conjunto de datos (variable de informes de marketing) que desee clasificar. |
   | Seleccionar grupos de informes | Permite seleccionar los grupos de informes en los que se debe clasificar el conjunto de datos seleccionado. Para seleccionar varios grupos de informes, las clasificaciones de cada uno de los grupos de informes seleccionados deben ser idénticas. |
   | Sobrescribir datos sobre conflictos | Permite sobrescribir los datos duplicados. Esta opción resulta útil si está actualizando clasificaciones existentes. Si está añadiendo clasificaciones adicionales, no se recomienda utilizar esta opción. |
   | Una vez completada la importación | Seleccione esta opción si desea exportar automáticamente el conjunto de datos actualizado a la misma cuenta de FTP, tras especificar la dirección de correo electrónico para recibir notificaciones sobre la cuenta de FTP una vez completada la importación. |
   | Destinatario de la notificación | Especifica la dirección de correo electrónico donde se recibirán las notificaciones sobre esta cuenta de FTP. |
   | Autorización | (Obligatorio) Autoriza a Adobe para que importe automáticamente todos los archivos de datos enviados a la nueva cuenta de FTP. |

1. Haga clic en **[!UICONTROL Guardar]**.

Una vez creadas, puede editar o eliminar las cuentas de FTP haciendo clic en el vínculo correspondiente junto a la cuenta de FTP específica.

>[!NOTE]
>
>Las notificaciones no se envían si una importación no introduce cambios en una clasificación. Un correo electrónico solo se envía si se hace correctamente y provoca cambios en una clasificación.

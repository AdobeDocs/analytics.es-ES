---
description: Instrucciones sobre cómo cargar archivos de datos a través de FTP.
subtopic: Classifications
title: Importación de FTP
topic: Admin tools
uuid: a914970d-ba02-4111-9dcf-06448f71b9f3
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Importación de FTP

Instrucciones sobre cómo cargar archivos de datos a través de FTP.

## Importación de FTP {#concept_2F965BE873254546A61FB755F25299FD}

Instrucciones sobre cómo cargar archivos de datos a través de FTP.

**[!UICONTROL Admin]** > **[!UICONTROL Classification Importer]**.

Los siguientes límites recomendados son importantes:

* Muchos archivos pequeños resultarán en un procesamiento más lento que unos pocos archivos grandes. Esto se debe a la cantidad de colas y priorización necesarias para los trabajos más pequeños.
* Por favor, divida los archivos grandes en fragmentos de 50 MB. Esto no es necesario, pero se recomienda porque proporciona una mejor visibilidad del progreso en el back-end. Además, si se producen errores mientras procesamos su trabajo, se reiniciará el trabajo; los archivos de gran tamaño resultan en una gran cantidad de trabajo rehecho en este escenario.

La configuración inicial rellena la base de datos de clasificaciones con un gran conjunto de datos originales o reestructura las clasificaciones, en lugar de reclasificar unas pocas filas o agregar filas.

Después de una carga inicial en un grupo de informes (para una variable o informe determinado), Adobe recomienda cargar solo las filas nuevas y actualizadas en importaciones posteriores. Las filas que no se estén modificando deben omitirse de las cargas futuras.

Cada nuevo valor clave que cargue se cuenta con las únicas de esa variable para el mes.

Si ha superado las únicas del mes, no verá los datos de clasificación correspondientes para los valores únicos excedidos en sistema de informes. Puede ver dichas clasificaciones en el almacén de datos o en la análisis ad hoc.

>[!NOTE] El tiempo necesario para procesar un archivo de datos de clasificación varía según el tamaño del archivo y la cantidad de archivos que estén procesando los servidores de Adobe en ese momento. El procesamiento de los archivos de datos no suele tardar más de 72 horas.

Antes de cargar datos a través de FTP, se debe crear una cuenta de FTP. Para obtener más información, consulte [Crear una cuenta FTP](/help/components/c-classifications2/c-classifications-importer/c-uploading-saint-data-files-via-ftp.md#task_C019268E6C934C7C95F4326F42A22CCF).

## Importar clasificaciones a través del FTP {#task_132C36830B69418B8C929E39838EF01D}

<!-- 

t_upload_a_saint_data_file_via_ftp.xml

 -->

Instrucciones sobre cómo utilizar una cuenta de FTP para importar clasificaciones en Adobe Analytics.

Para obtener más información acerca de cómo crear una cuenta de FTP, consulte  [Crear una cuenta de FTP](/help/components/c-classifications2/c-classifications-importer/c-uploading-saint-data-files-via-ftp.md#task_C019268E6C934C7C95F4326F42A22CCF).

1. Haga clic **[!UICONTROL Admin]** > **[!UICONTROL Classification Importer]**.
1. Haga clic en **[!UICONTROL Import File]** y luego en **[!UICONTROL FTP Import]**.
1. Next to the FTP account that you want to use, click **[!UICONTROL View]**.
1. Utilice la información de acceso al FTP (host, nombre de usuario y contraseña) para acceder al servidor FTP con un cliente FTP de su elección.
1. Cargue el archivo de datos ( [!DNL .tab] o [!DNL .txt]) al servidor FTP.
1. Una vez cargado el archivo de datos, cargue un archivo FIN que indique el archivo está listo para ser procesado.

   El archivo FIN es un archivo vacío que tiene el mismo nombre que su archivo de datos, con la extensión de nombre de archivo [!DNL .fin]. Por ejemplo, si su archivo de datos es [!DNL classdata1.tab], el nombre del archivo es [!DNL classdata1.fin].fin.

A intervalos regulares, Adobe recupera los archivos de datos cargados que tienen un archivo FIN asociado. Adobe los importa en los grupos de informes y conjuntos de datos especificados en la configuración de la cuenta de FTP.

## Crear una cuenta de FTP {#task_C019268E6C934C7C95F4326F42A22CCF}

Antes de cargar datos a través de FTP, se debe crear una cuenta de FTP. >

<!-- 

t_create_an_ftp_account.xml

 -->

Consulte [FTP y sFTP](https://marketing.adobe.com/resources/help/es_ES/whitepapers/ftp/) para obtener más información sobre los servidores FTP de Adobe.

1. Haga clic **[!UICONTROL Admin]** > **[!UICONTROL Classification Importer]**.
1. Haga clic en **[!UICONTROL Import File]** y luego en **[!UICONTROL FTP Import]**.
1. En la **[!UICONTROL Import File]** ficha, haga clic en **[!UICONTROL Add New]**.
1. Indique los detalles de la cuenta de FTP:

   | Elemento | Descripción |
   |---|---|
   | Nombre | El nombre de la cuenta de FTP. |
   | Conjunto de datos para clasificar | En la lista desplegable, seleccione el conjunto de datos (variable de informe de marketing) que desee clasificar. |
   | Seleccionar grupos de informes | Seleccione los grupos de informes donde desee clasificar el conjunto de datos seleccionado. Para seleccionar varios grupos de informes, las clasificaciones de cada uno de los grupos de informes seleccionados deben ser idénticas. |
   | Sobrescribir datos en caso de conflicto | Seleccione esta opción para sobrescribir los datos de duplicado. Esta opción resulta útil si está actualizando clasificaciones existentes. Si va a agregar clasificaciones adicionales, no se recomienda esta opción. |
   | Una vez completada la importación | Seleccione esta opción para exportar automáticamente el conjunto de datos actualizado a la misma cuenta de FTP una vez que especifique la dirección de correo electrónico para recibir notificaciones sobre esta cuenta de FTP una vez completada la importación. |
   | Destinatario de la notificación | Especifique la dirección de correo electrónico para recibir notificaciones sobre esta cuenta de FTP. |
   | Autorizar | (Requerido) Autoriza a Adobe a importar automáticamente todos los archivos de datos enviados a la nueva cuenta de FTP. |

1. Haga clic en **[!UICONTROL Save]**.

Una vez creadas, puede editar o eliminar las cuentas de FTP haciendo clic en el vínculo correspondiente junto a la cuenta de FTP específica.

---
description: Cómo cargar archivos de datos a través de FTP.
title: Importación de FTP
feature: Classifications
exl-id: 3e93b35c-6f65-4a93-887d-d94e4d359bdc
TQID: https://experienceleague.adobe.com/CMHQpWtGl14Z7kHaZ7ufp6-tDIfQ-pCEzSI47XMi-pA
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 727
ht-degree: 39%

---

# Importación de FTP (heredada)

{{classification-importer-deprecation}}

>[!IMPORTANT]
>
>Adobe ya no recomienda utilizar FTP para las importaciones, tal como se describe en esta página.
>
>No se recomienda utilizar FTP porque es un método no cifrado para compartir archivos, lo que significa que cualquiera puede interceptar el contenido del archivo, así como el nombre de usuario y la contraseña utilizados para la cuenta.
>
>En su lugar, configure una cuenta en la nube tal como se describe en [Configurar cuentas de importación y exportación en la nube](/help/components/locations/configure-import-accounts.md).

Instrucciones sobre cómo cargar archivos de datos a través de FTP.

## Importación de FTP {#concept_2F965BE873254546A61FB755F25299FD}

Para cargar archivos de datos a través del FTP:

1. **[!UICONTROL Administración]** > **[!UICONTROL Importador de clasificaciones]**.

Los siguientes límites recomendados son importantes.

>[!IMPORTANT]
>
>Tener demasiados archivos pequeños o archivos grandes únicos puede crear una carga de procesamiento innecesaria en los servidores de procesamiento. Adobe recomienda dividir los archivos grandes en fragmentos de 50 MB y combinar archivos pequeños.

La configuración inicial rellena la base de datos de clasificaciones con un gran conjunto de datos originales o reestructura las clasificaciones, en lugar de volver a clasificar algunas filas o agregar filas.

Después de una carga inicial en un grupo de informes (para una variable o informe determinado), Adobe recomienda cargar solo filas nuevas y actualizadas en importaciones posteriores. Las filas que no se cambien se deben omitir de las cargas futuras.

Cada nuevo valor clave que cargue se contabilizará en los valores exclusivos de esa variable durante el mes.

Si ha superado los valores exclusivos del mes, no verá en los informes los datos de clasificaciones correspondientes para los valores únicos excedidos. Puede ver dichas clasificaciones en Data Warehouse.

>[!NOTE]
>
>El tiempo necesario para procesar un archivo de datos de clasificación varía según el tamaño del archivo y la cantidad de archivos que estén procesando los servidores de Adobe en ese momento. El procesamiento de los archivos de datos no suele durar más de 72 horas.

## Crear una cuenta de FTP

Antes de cargar datos a través de FTP, se debe crear una cuenta de FTP. >

Consulte [FTP y sFTP](/help/export/ftp-and-sftp/ftp-overview.md) para obtener más información sobre los servidores FTP de Adobe.

1. Haga clic en **[!UICONTROL Administración]** > **[!UICONTROL Importador de clasificaciones]**.
1. Haga clic en **[!UICONTROL Importar archivo]** y, a continuación, seleccione **[!UICONTROL Importar FTP]**.
1. En la pestaña **[!UICONTROL Importar archivo]**, haga clic en **[!UICONTROL Añadir nuevo]**.
1. Indique los detalles de la cuenta de FTP:

   | Elemento | Descripción |
   |---|---|
   | **Nombre** | Nombre de la cuenta de FTP. |
   | **Conjunto de datos a clasificar** | En la lista desplegable, seleccione el conjunto de datos (variable de informe de marketing) que desee clasificar. |
   | **Seleccionar grupos de informes** | Seleccione los grupos de informes en los que desea clasificar el conjunto de datos seleccionado. Para seleccionar varios grupos de informes, las clasificaciones de cada uno de ellos deben ser idénticas. |
   | **Sobrescribir datos sobre conflictos** | Seleccione esta opción para sobrescribir los datos duplicados. Esta opción es útil si va a actualizar clasificaciones existentes. Si se encuentra en la [arquitectura de clasificación más reciente](../sets/overview.md), esta configuración siempre estará habilitada. |
   | **Una vez completada la importación** | Seleccione esta opción para exportar automáticamente el conjunto de datos actualizado a la misma cuenta de FTP una vez. Especifique la dirección de correo electrónico para recibir notificaciones sobre esta cuenta de FTP una vez completada la importación. Si se encuentra en la [arquitectura de clasificación más reciente](../sets/overview.md), esta opción no está disponible. |
   | **Destinatario de notificación** | Especifique la dirección de correo electrónico donde desea recibir las notificaciones sobre esta cuenta de FTP. |
   | **Autorizar** | (Obligatorio) Autoriza a Adobe a importar automáticamente todos los archivos de datos enviados a la nueva cuenta de FTP. |

1. Haga clic en **[!UICONTROL Guardar]**.

Una vez creadas, puede editar o eliminar las cuentas de FTP haciendo clic en el vínculo correspondiente junto a la cuenta de FTP específica.

>[!NOTE]
>
>Las notificaciones no se envían si una importación no introduce cambios en una clasificación. Un correo electrónico solo se envía si se hace correctamente y provoca cambios en una clasificación.

## Importar clasificaciones a través del FTP

Puede usar una cuenta de FTP para importar clasificaciones a Adobe Analytics.

Para importar clasificaciones a través del FTP:

1. Haga clic en **[!UICONTROL Administración]** > **[!UICONTROL Importador de clasificaciones]**.
1. Haga clic en **[!UICONTROL Importar archivo]** y, a continuación, seleccione **[!UICONTROL Importar FTP]**.
1. Junto a la cuenta de FTP que desea utilizar, haga clic en **[!UICONTROL Ver]**.
1. Utilice la información de acceso al FTP (host, nombre de usuario y contraseña) para acceder al servidor FTP con un cliente FTP de su elección.
1. Cargue el archivo de datos ( `.tab` o `.txt`) al servidor FTP.
1. Una vez cargado el archivo de datos, cargue un archivo FIN que indique el archivo está listo para ser procesado.

   El archivo FIN es un archivo vacío que tiene el mismo nombre que su archivo de datos, con la extensión de nombre de archivo `.fin`. Por ejemplo, si su archivo de datos es `classdata1.tab`, el nombre del archivo es `classdata1.fin`.fin.

A intervalos regulares, Adobe recupera los archivos de datos cargados que tienen asociado un archivo FIN. Adobe los importa a los grupos de informes y conjuntos de datos especificados en la configuración de la cuenta de FTP.

Una vez que Adobe Analytics ha leído y procesado los archivos cargados en la carpeta FTP, estos se eliminan automáticamente del sitio FTP.

---
description: Cómo cargar archivos de datos a través de FTP.
title: Importación de FTP
feature: Classifications
exl-id: 3e93b35c-6f65-4a93-887d-d94e4d359bdc
source-git-commit: c36cc9884b2de3cddf03b505d9c4883dcac846af
workflow-type: tm+mt
source-wordcount: '721'
ht-degree: 81%

---

# Importación de FTP

>[!IMPORTANT]
>
>Ya no se recomienda utilizar FTP para la importación, tal como se describe en esta página.
>
>No se recomienda utilizar FTP porque es un método no cifrado para compartir archivos, lo que significa que cualquiera puede interceptar el contenido del archivo, así como el nombre de usuario y la contraseña utilizados para la cuenta.
>
>En su lugar, configure una cuenta en la nube como se describe en [Configurar ubicaciones de importación en la nube](/help/components/classifications/importer/configure-import-accounts.md).

Instrucciones sobre cómo cargar archivos de datos a través de FTP.

## Importación de FTP {#concept_2F965BE873254546A61FB755F25299FD}

Para cargar archivos de datos a través del FTP:

1. **[!UICONTROL Administración]** > **[!UICONTROL Importador de clasificaciones]**.

Es importante tener en cuenta los límites recomendados siguientes.

>[!IMPORTANT]
>
>Tener demasiados archivos pequeños o archivos grandes únicos puede crear una carga de procesamiento innecesaria en los servidores de procesamiento. Adobe recomienda dividir los archivos grandes en fragmentos de 50 MB y combinar archivos pequeños.

En lugar de agregar filas o reclasificar solo algunas de ellas, la configuración inicial rellena la base de datos con un gran conjunto de datos originales o reestructura las clasificaciones.

Después de realizar una carga inicial en un grupo de informes (de un informe o una variable en concreto), Adobe recomienda cargar solamente las filas nuevas y las actualizadas en las importaciones subsiguientes. Las filas que no se cambien en absoluto deben omitirse de las cargas futuras.

Cada nuevo valor clave que cargue se restará a los únicos de esa variable para el mes.

Si ha superado las únicas del mes, no verá los datos de clasificación correspondientes a los valores únicos superados en los informes. Puede ver dichas clasificaciones en Data Warehouse.

>[!NOTE]
>
>El tiempo necesario para procesar un archivo de datos de clasificación varía según el tamaño del archivo y la cantidad de archivos que estén procesando los servidores de Adobe en ese momento. El procesamiento de los archivos no suele tardar más de 72 horas.

## Crear una cuenta de FTP

Antes de cargar datos a través de FTP, se debe crear una cuenta de FTP. >

Consulte [FTP y sFTP](/help/export/ftp-and-sftp/ftp-overview.md) para obtener más información sobre los servidores FTP de Adobe.

1. Haga clic en **[!UICONTROL Administración]** > **[!UICONTROL Importador de clasificaciones]**.
1. Haga clic en **[!UICONTROL Importar archivo]** y, a continuación, seleccione **[!UICONTROL Importar FTP]**.
1. En la pestaña **[!UICONTROL Importar archivo]**, haga clic en **[!UICONTROL Añadir nuevo]**.
1. Indique los detalles de la cuenta de FTP:

   | Elemento | Descripción |
   |---|---|
   | **Nombre** | El nombre de la cuenta de FTP. |
   | **Conjunto de datos a clasificar** | En la lista desplegable, seleccione el conjunto de datos (variable de informes de marketing) que desee clasificar. |
   | **Seleccionar grupos de informes** | Permite seleccionar los grupos de informes en los que se debe clasificar el conjunto de datos seleccionado. Para seleccionar varios grupos de informes, las clasificaciones de cada uno de los grupos de informes seleccionados deben ser idénticas. |
   | **Sobrescribir datos sobre conflictos** | Permite sobrescribir los datos duplicados. Esta opción resulta útil si está actualizando clasificaciones existentes. Si está en la [arquitectura de clasificación más reciente](../sets/overview.md), esta configuración siempre está habilitada. |
   | **Una vez completada la importación** | Seleccione esta opción si desea exportar automáticamente el conjunto de datos actualizado a la misma cuenta de FTP, tras especificar la dirección de correo electrónico para recibir notificaciones sobre la cuenta de FTP una vez completada la importación. Si está en la [arquitectura de clasificación más reciente](../sets/overview.md), esta opción no está disponible. |
   | **Destinatario de la notificación** | Especifica la dirección de correo electrónico donde se recibirán las notificaciones sobre esta cuenta de FTP. |
   | **Autorización** | (Obligatorio) Autoriza a Adobe para que importe automáticamente todos los archivos de datos enviados a la nueva cuenta de FTP. |

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

A intervalos periódicos, Adobe recupera los archivos de datos cargados que tienen un archivo FIN asociado. Adobe los importa en los grupos de informes y conjuntos de datos indicados en la configuración de la cuenta FTP.

Una vez que Adobe Analytics ha leído y procesado los archivos cargados en la carpeta FTP, estos se eliminan automáticamente del sitio FTP.

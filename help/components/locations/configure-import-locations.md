---
description: Configure la cuenta de importación y la ubicación de la nube en la que se pueden cargar los datos de clasificación
keywords: Analysis Workspace
title: Configurar ubicaciones de importación y exportación de la nube
feature: Classifications
exl-id: 55179868-6228-44ff-835c-f4a7b38e929b
source-git-commit: 66c846dd64ee3ed8f421c834ab82b53b1f0f00a5
workflow-type: tm+mt
source-wordcount: '1450'
ht-degree: 37%

---

# Configurar ubicaciones de importación y exportación de la nube

<!-- This page is almost duplicated with the "Configure cloud export locations" article in CJA. Differences are that Snowflake isn't supported here and there is a Suffix field for each account type. -->

Puede configurar una cuenta de la nube (y una ubicación en esa cuenta). Una sola ubicación se puede utilizar para cualquiera de los siguientes fines (una sola ubicación no se puede asociar con varios fines, como fuentes de datos y Data Warehouse, o conjuntos de Data Warehouse y clasificación):

* Exportación de archivos mediante [Fuentes de datos](/help/export/analytics-data-feed/create-feed.md)
* Exportación de informes mediante [Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md)
* Importación de esquemas mediante [Conjuntos de clasificaciones](/help/components/classifications/sets/overview.md)

Debe configurar Adobe Analytics con la información necesaria para acceder a su cuenta de Cloud. Este proceso consiste en añadir y configurar la cuenta (como ARN de la función de Amazon S3, Google Cloud Platform, etc.) tal como se describe en [Configuración de cuentas de importación y exportación de nube](/help/components/locations/configure-import-accounts.md)y, a continuación, agregue y configure la ubicación dentro de esa cuenta (tal como se describe en este artículo).

Para obtener información sobre cómo administrar ubicaciones existentes, incluida la visualización, edición y eliminación de ubicaciones, consulte [Administrador de ubicaciones](/help/components/locations/locations-manager.md).

## Comience a crear una ubicación de exportación de nube

1. En Adobe Analytics, seleccione [!UICONTROL **Componentes**] > [!UICONTROL **Ubicaciones**].
1. En el [!UICONTROL Ubicaciones] , seleccione la [!UICONTROL **Ubicaciones**] pestaña.
1. Seleccionar [!UICONTROL **Añadir ubicación**]. (Si aún no ha agregado una cuenta, agréguela tal como se describe en [Configuración de cuentas de importación y exportación de nube](/help/components/locations/configure-import-accounts.md).)

   Se muestra el cuadro de diálogo Ubicación.

1. Especifique la siguiente información: |Campo | Función | |---------|----------| | [!UICONTROL **Nombre**] | El nombre de la ubicación.  |
| [!UICONTROL **Descripción**] | Proporcione una breve descripción de la cuenta para diferenciarla de otras cuentas del mismo tipo de cuenta. | | [!UICONTROL **Uso con**] | Seleccione si desea utilizar esta ubicación con [!UICONTROL **Fuentes de datos**], [!UICONTROL **Data Warehouse**], o [!UICONTROL **Conjuntos de clasificaciones**]. <p>Tenga en cuenta lo siguiente al realizar una selección:</p><ul><li>Una sola ubicación no se puede usar con varios fines. Por ejemplo, una ubicación que se usa para fuentes de datos no se puede usar también para conjuntos de Datas Warehouse o clasificaciones.</li><li>Para evitar conflictos de archivos dentro de una ubicación, no cambie el valor del [!UICONTROL **Uso con**] después de utilizar la ubicación.</li></ul> | | [!UICONTROL **Cuenta de ubicación**] | Seleccione la cuenta de ubicación donde desea crear esta ubicación. Para obtener información sobre cómo crear una cuenta, consulte [Agregar una cuenta](#add-an-account). |

1. En la sección [!UICONTROL **Propiedades de ubicación**], especifique información específica para el tipo de cuenta de su cuenta de ubicación.

   Continúe con la sección siguiente que corresponde al tipo de cuenta seleccionado en la [!UICONTROL **Cuentas de ubicación**] field. (También están disponibles otros tipos de cuentas heredadas, pero no se recomiendan).



### Amazon S3 Role ARN

Para configurar una ubicación ARN de la función Amazon S3, especifique la siguiente información:

1. [Empezar a crear o editar una ubicación de exportación de nube](#begin-creating-or-editing-a-cloud-export-location), tal como se ha descrito anteriormente.

   | Campo | Función |
   |---------|----------|
   | [!UICONTROL **Nombre del bloque**] | El bloque de su cuenta de Amazon S3 al que quiere enviar los datos de Adobe Analytics. <p>Asegúrese de que el ARN del usuario proporcionado por el Adobe tiene el `S3:PutObject` para cargar archivos en este bloque. </p><p>Los nombres de bloques deben cumplir reglas de nomenclatura específicas. Los nombres bloques deben tener entre 3 y 63 caracteres de longitud, solo pueden constar de letras minúsculas, números, puntos (.) y guiones (-), y deben empezar y terminar con una letra o un número. [En la documentación de AWS encontrará una lista completa de las reglas de nomenclatura](https://docs.aws.amazon.com/AmazonS3/latest/userguide/bucketnamingrules.html). </p> |
   | [!UICONTROL **Prefijo de clave**] | La carpeta dentro del bloque en el que quiere colocar los datos. Especifique un nombre de carpeta y, a continuación, añada una barra invertida después del nombre para crear la carpeta. Por ejemplo, folder_name/ |

   {style="table-layout:auto"}

1. Seleccione [!UICONTROL **Guardar**].

   Ahora puede importar o exportar datos desde o hacia la cuenta y la ubicación configuradas. Para exportar datos, utilice [Fuentes de datos](/help/export/analytics-data-feed/create-feed.md) o [Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md). Para importar datos, utilice [Conjuntos de clasificaciones](/help/components/classifications/sets/overview.md).

   Los datos importados no se eliminan del destino de nube una vez importados.

   >[!NOTE]
   >
   >   Si ha utilizado anteriormente [FTP para importar clasificaciones](/help/components/classifications/importer/c-uploading-saint-data-files-via-ftp.md) a Adobe Analytics, tenía que cargar un archivo FIN. Este archivo FIN no es necesario al importar desde cuentas en la nube.


### Google Cloud Platform

Para configurar una ubicación de Google Cloud Platform, especifique la siguiente información:

1. [Empezar a crear o editar una ubicación de exportación de nube](#begin-creating-or-editing-a-cloud-export-location), tal como se ha descrito anteriormente.

   | Campo | Función |
   |---------|----------|
   | [!UICONTROL **Nombre del bloque**] | El bloque de su cuenta de GCP al que desea enviar los datos de Adobe Analytics. Asegúrese de haber concedido permiso al principal proporcionado por el Adobe para cargar archivos en este bloque. |
   | [!UICONTROL **Prefijo de clave**] | La carpeta dentro del bloque en el que quiere colocar los datos. Especifique un nombre de carpeta y, a continuación, añada una barra invertida después del nombre para crear la carpeta. Por ejemplo, folder_name/ |

   {style="table-layout:auto"}

1. Seleccione [!UICONTROL **Guardar**].

   Ahora puede importar o exportar datos desde o hacia la cuenta y la ubicación configuradas. Para exportar datos, utilice [Fuentes de datos](/help/export/analytics-data-feed/create-feed.md) o [Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md). Para importar datos, utilice [Conjuntos de clasificaciones](/help/components/classifications/sets/overview.md).

   Los datos importados no se eliminan del destino de nube una vez importados.

   >[!NOTE]
   >
   >   Si ha utilizado anteriormente [FTP para importar clasificaciones](/help/components/classifications/importer/c-uploading-saint-data-files-via-ftp.md) a Adobe Analytics, tenía que cargar un archivo FIN. Este archivo FIN no es necesario al importar desde cuentas en la nube.


### Azure SAS

Para configurar una ubicación SAS de Azure, especifique la siguiente información:

1. [Empezar a crear o editar una ubicación de exportación de nube](#begin-creating-or-editing-a-cloud-export-location), tal como se ha descrito anteriormente.

   | Campo | Función |
   |---------|----------|
   | [!UICONTROL **Nombre de contenedor**] | El contenedor de la cuenta que especificó dónde desea que se envíen los datos de Adobe Analytics. |
   | [!UICONTROL **Prefijo clave**] | La carpeta dentro del contenedor en la que desea colocar los datos. Especifique un nombre de carpeta y, a continuación, añada una barra invertida después del nombre para crear la carpeta. Por ejemplo, `folder_name/` |

   {style="table-layout:auto"}

1. Seleccione [!UICONTROL **Guardar**].

   Ahora puede importar o exportar datos desde o hacia la cuenta y la ubicación configuradas. Para exportar datos, utilice [Fuentes de datos](/help/export/analytics-data-feed/create-feed.md) o [Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md). Para importar datos, utilice [Conjuntos de clasificaciones](/help/components/classifications/sets/overview.md).

   Los datos importados no se eliminan del destino de nube una vez importados.

   >[!NOTE]
   >
   >   Si ha utilizado anteriormente [FTP para importar clasificaciones](/help/components/classifications/importer/c-uploading-saint-data-files-via-ftp.md) a Adobe Analytics, tenía que cargar un archivo FIN. Este archivo FIN no es necesario al importar desde cuentas en la nube.


### Azure RBAC

Para configurar una ubicación RBAC de Azure, especifique la siguiente información:

1. [Empezar a crear o editar una ubicación de exportación de nube](#begin-creating-or-editing-a-cloud-export-location), tal como se ha descrito anteriormente.

   | Campo | Función |
   |---------|----------|
   | [!UICONTROL **Nombre de contenedor**] | El contenedor de la cuenta que especificó dónde desea que se envíen los datos de Adobe Analytics. Asegúrese de conceder permisos para cargar archivos en la aplicación de Azure que creó anteriormente. |
   | [!UICONTROL **Prefijo clave**] | La carpeta dentro del contenedor en la que desea colocar los datos. Especifique un nombre de carpeta y, a continuación, añada una barra invertida después del nombre para crear la carpeta. Por ejemplo, `folder_name/` |
   | [!UICONTROL **Nombre de la cuenta**] | La cuenta de almacenamiento de Azure. |

   {style="table-layout:auto"}

1. Seleccione [!UICONTROL **Guardar**].

   Ahora puede importar o exportar datos desde o hacia la cuenta y la ubicación configuradas. Para exportar datos, utilice [Fuentes de datos](/help/export/analytics-data-feed/create-feed.md) o [Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md). Para importar datos, utilice [Conjuntos de clasificaciones](/help/components/classifications/sets/overview.md).

   Los datos importados no se eliminan del destino de nube una vez importados.

   >[!NOTE]
   >
   >   Si ha utilizado anteriormente [FTP para importar clasificaciones](/help/components/classifications/importer/c-uploading-saint-data-files-via-ftp.md) a Adobe Analytics, tenía que cargar un archivo FIN. Este archivo FIN no es necesario al importar desde cuentas en la nube.

### Tipos de cuentas heredadas

Estos tipos de cuentas heredadas solo están disponibles al exportar datos con [Fuentes de datos](/help/export/analytics-data-feed/create-feed.md) y [Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md). Estas opciones no están disponibles al importar datos con [Conjuntos de clasificaciones](/help/components/classifications/sets/manage/schema.md).

+++FTP

Los datos de las fuentes de datos se pueden entregar en un Adobe o en una ubicación FTP alojada por el cliente. Especifique el directorio Utilice el campo de ruta para colocar los archivos de fuente en una carpeta.

| Campo | Función |
|---------|----------|
| [!UICONTROL **Ruta de directorio**] | Introduzca la ruta al directorio en el servidor FTP. Las carpetas ya deben existir, las fuentes generan un error si la ruta especificada no existe. </br>Por ejemplo, `/folder_name/folder_name`. |

{style="table-layout:auto"}

+++

+++SFTP

Los datos de las fuentes de datos se pueden entregar en un Adobe o en una ubicación SFTP alojada por el cliente. El sitio de destino debe contener una clave pública RSA o DSA válida. Puede descargar la clave pública adecuada al crear la fuente.

| Campo | Función |
|---------|----------|
| [!UICONTROL **Ruta de directorio**] | Introduzca la ruta al directorio en el servidor FTP. Las carpetas ya deben existir, las fuentes generan un error si la ruta especificada no existe. </br>Por ejemplo, `/folder_name/folder_name`. |

{style="table-layout:auto"}

+++

+++S3

Puede enviar datos del almacén de datos directamente a los bloques de Amazon S3. Este tipo de destino requiere un nombre de contenedor, un ID de clave de acceso y una clave secreta. Consulte los [requisitos de nomenclatura de contenedor de Amazon S3](https://docs.aws.amazon.com/es_es/awscloudtrail/latest/userguide/cloudtrail-s3-bucket-naming-requirements.html) en los documentos de Amazon S3 para obtener más información.

El usuario que proporcione para cargar el almacén de datos debe tener los siguientes [permisos](https://docs.aws.amazon.com/es_es/AmazonS3/latest/API/API_Operations_Amazon_Simple_Storage_Service.html):

* s3:GetObject
* s3:PutObject
* s3:PutObjectAcl

Se admiten las 16 regiones de AWS estándar siguientes (utilizando el algoritmo de firma adecuado cuando sea necesario):

* us-east-2
* us-east-1
* us-west-1
* us-west-2
* ap-south-1
* ap-northeast-2
* ap-southeast-1
* ap-southeast-2
* ap-northeast-1
* ca-central-1
* eu-central-1
* eu-west-1
* eu-west-2
* eu-west-3
* eu-north-1
* sa-east-1

>[!NOTE]
>
>No se admite la región cn-north-1.

+++

+++blob de Azure

El almacén de datos admite destinos de Azure Blob. Se necesita un contenedor, una cuenta y una clave. Amazon cifra automáticamente los datos en reposo. Cuando se descarguen los datos, estos se descifrarán automáticamente. Consulte [Creación de una cuenta de almacenamiento](https://docs.microsoft.com/es-es/azure/storage/common/storage-quickstart-create-account?tabs=azure-portal#view-and-copy-storage-access-keys) en los documentos de Microsoft Azure para obtener más información.

>[!NOTE]
>
>Debe implementar su propio proceso para administrar el espacio en disco en el destino del almacén de datos. Adobe no elimina ningún dato del servidor.

+++



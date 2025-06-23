---
description: Configure la cuenta de importación y la ubicación de la nube en la que se pueden cargar los datos de clasificación
keywords: Analysis Workspace
title: Configuración de cuentas de importación y exportación de nube
feature: Classifications
exl-id: 40d3d3f1-1047-4c37-8caf-6b0aabaa590a
source-git-commit: 5c02b46a7757e07a23505dc8e3dc21b6353aa9e2
workflow-type: tm+mt
source-wordcount: '1476'
ht-degree: 56%

---

# Configuración de cuentas de importación y exportación de nube

<!-- This page is almost duplicated with the "Configure cloud export locations" article in CJA. Differences are that Snowflake isn't supported here and there is a Suffix field for each account type. -->

>[!NOTE]
>
>Tenga en cuenta lo siguiente al crear y editar cuentas: <ul><li>Los administradores del sistema pueden impedir que los usuarios creen cuentas, tal como se describe en [Configurar si los usuarios pueden crear cuentas](/help/components/locations/locations-manager.md#configure-whether-users-can-create-accounts). Si no puede crear cuentas como se describe en esta sección, póngase en contacto con el administrador del sistema.</li><li>Solamente el usuario que la creó o un administrador del sistema pueden editar una cuenta.</li></ul>

Puede configurar una cuenta de nube que se utilice para uno o todos los fines siguientes:

* Exportando archivos mediante [fuentes de datos](/help/export/analytics-data-feed/create-feed.md)
* Exportando informes con [Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md)
* Exportando archivos al usar [Report Builder](/help/analyze/report-builder/report-builder-export.md)
* Importando esquemas utilizando [conjuntos de clasificaciones](/help/components/classifications/sets/overview.md)

Debe configurar Adobe Analytics con la información necesaria para acceder a su cuenta de la nube. Este proceso consiste en agregar y configurar la cuenta (como el ARN de la función de Amazon S3, Google Cloud Platform, etc.) tal como se describe en este artículo y, a continuación, agregar y configurar la ubicación dentro de esa cuenta (como una carpeta dentro de la cuenta) tal como se describe en [Configurar ubicaciones de importación y exportación en la nube](/help/components/locations/configure-import-locations.md).

Para obtener información sobre cómo ver y eliminar cuentas existentes, consulte [Administrador de ubicaciones](/help/components/locations/locations-manager.md).

Para configurar una cuenta de importación o exportación de nube:

1. En Adobe Analytics, seleccione [!UICONTROL **Componentes**] > [!UICONTROL **Ubicaciones**].
1. En la página [!UICONTROL Ubicaciones], seleccione la ficha [!UICONTROL **Cuentas de ubicación**].
1. (Condicional) Si es administrador del sistema, puede habilitar la opción [!UICONTROL **Ver cuentas de todos los usuarios**] para ver las cuentas creadas por todos los usuarios de su organización.
   ![ver cuentas de todos los usuarios](assets/accounts-all-users.png)
1. Para crear una cuenta nueva, seleccione [!UICONTROL **Agregar cuenta**].

   Se muestra el cuadro de diálogo [!UICONTROL **Detalles de cuenta de ubicación**].

   O bien

   Para editar una cuenta existente, localice la cuenta que desee editar y luego seleccione el botón [!UICONTROL **Editar detalles**].

   Se muestra el cuadro de diálogo [!UICONTROL **Agregar cuenta**].

1. Especifique la siguiente información:

   | Campo | Función |
   |---------|----------|
   | [!UICONTROL **Nombre de cuenta de ubicación**] | El nombre de la cuenta de ubicación. Este nombre aparece al crear una ubicación  |
   | [!UICONTROL **Descripción de cuenta de ubicación**] | Proporcione una breve descripción de la cuenta para diferenciarla de otras cuentas del mismo tipo de cuenta. |
   | [!UICONTROL **Poner la cuenta a disposición de todos los usuarios de su organización**] | Active esta opción para permitir que otros usuarios de su organización utilicen la cuenta.<p>Tenga en cuenta lo siguiente al compartir cuentas:</p><ul><li>Las cuentas que comparta no se pueden dejar de compartir.</li><li>Solo el propietario de la cuenta puede editar las cuentas compartidas.</li><li>Cualquiera puede crear una ubicación para la cuenta compartida.</li></ul> |
   | [!UICONTROL **Tipo de cuenta**] | Seleccione el tipo de cuenta en la nube. Le recomendamos que tenga una sola cuenta para cada tipo de cuenta, con varias ubicaciones según sea necesario dentro de esa cuenta.<p>Los administradores del sistema pueden limitar los tipos de cuentas que los usuarios pueden crear, tal como se describe en [Configurar si los usuarios pueden crear cuentas](/help/components/locations/locations-manager.md#configure-whether-users-can-create-accounts). Si no puede crear cuentas como se describe en esta sección, póngase en contacto con el administrador del sistema.</p> |

1. En la sección [!UICONTROL **Propiedades de la cuenta**], especifique información específica para el tipo de cuenta que seleccionó.

   Para obtener instrucciones de configuración, expanda la sección siguiente que corresponde al [!UICONTROL **tipo de cuenta**] que seleccionó. (También están disponibles otros tipos de cuentas heredadas, pero no se recomiendan).

   **Tipos de cuenta**

   +++ARN de la función Amazon S3

   Para configurar una cuenta ARN de la función Amazon S3, especifique la siguiente información:

   | Campo | Función |
   |---------|----------|
   | [!UICONTROL **ARN de función**] | Debe proporcionar un ARN de función (nombre de recurso de Amazon) que Adobe pueda utilizar para obtener acceso a la cuenta de Amazon S3. Para ello, se crea una directiva de permisos de IAM para la cuenta de origen, se adjunta la directiva a un usuario y, a continuación, se crea una función para la cuenta de destino. Para obtener información específica, consulte [esta documentación de AWS](https://aws.amazon.com/premiumsupport/knowledge-center/cross-account-access-iam/). |

   {style="table-layout:auto"}

   +++

   +++Google Cloud Platform

   Para configurar una cuenta de Google Cloud Platform, especifique la siguiente información:

   | Campo | Función |
   |---------|----------|
   | [!UICONTROL **ID del proyecto**] | Su ID del proyecto de Google Cloud. Consulte la [documentación de Google Cloud sobre cómo obtener un ID de proyecto](https://cloud.google.com/resource-manager/docs/creating-managing-projects#identifying_projects). |

   {style="table-layout:auto"}

   +++

   +++Azure SAS

   Para configurar una cuenta SAS de Azure, especifique la siguiente información:

   | Campo | Función |
   |---------|----------|
   | [!UICONTROL **ID de aplicación**] | Copie este ID de la aplicación de Azure que ha creado. En Microsoft Azure, esta información se encuentra en la pestaña **Información general** dentro de la aplicación. Para obtener más información, consulte la [documentación de Microsoft Azure sobre cómo registrar una aplicación con la plataforma de identidad de Microsoft](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
   | [!UICONTROL **ID de inquilino**] | Copie este ID de la aplicación de Azure que ha creado. En Microsoft Azure, esta información se encuentra en la pestaña **Información general** dentro de la aplicación. Para obtener más información, consulte la [documentación de Microsoft Azure sobre cómo registrar una aplicación con la plataforma de identidad de Microsoft](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
   | [!UICONTROL **URI de almacén de claves**] | <p>Ruta al token SAS en Azure Key Vault.  Para configurar Azure SAS, debe almacenar un token SAS como secreto mediante Azure Key Vault. Para obtener más información, consulte la [documentación de Microsoft Azure sobre cómo establecer y recuperar un secreto de Azure Key Vault](https://learn.microsoft.com/en-us/azure/key-vault/secrets/quick-create-portal?source=recommendations).</p><p>Una vez creado el URI del almacén de claves, agregue una directiva de acceso en el almacén de claves para conceder permiso a la aplicación de Azure que ha creado. Para obtener más información, consulte [Documentación de Microsoft Azure sobre cómo asignar una directiva de acceso de almacén de claves](https://learn.microsoft.com/en-us/azure/key-vault/general/assign-access-policy?tabs=azure-portal).</p> |
   | [!UICONTROL **Nombre secreto del almacén de claves**] | El nombre secreto que creó al agregar el secreto a Azure Key Vault. En Microsoft Azure, esta información se encuentra en el almacén de claves que creó, en la página de configuración de **almacén de claves**. Para obtener más información, consulte la [documentación de Microsoft Azure sobre cómo establecer y recuperar un secreto de Azure Key Vault](https://learn.microsoft.com/en-us/azure/key-vault/secrets/quick-create-portal?source=recommendations). |
   | [!UICONTROL **Secreto de cuenta de ubicación**] | Copie el secreto de la aplicación de Azure que ha creado. En Microsoft Azure, esta información se encuentra en la pestaña **Certificados y secretos** dentro de la aplicación. Para obtener más información, consulte la [Documentación de Microsoft Azure sobre cómo registrar una aplicación con la plataforma de identidad de Microsoft](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |

   {style="table-layout:auto"}

   +++

   +++Azure RBAC

   Para configurar una cuenta RBAC de Azure, especifique la siguiente información:

   | Campo | Función |
   |---------|----------|
   | [!UICONTROL **ID de aplicación**] | Copie este ID de la aplicación de Azure que ha creado. En Microsoft Azure, esta información se encuentra en la pestaña **Información general** dentro de la aplicación. Para obtener más información, consulte la [documentación de Microsoft Azure sobre cómo registrar una aplicación con la plataforma de identidad de Microsoft](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
   | [!UICONTROL **ID de inquilino**] | Copie este ID de la aplicación de Azure que ha creado. En Microsoft Azure, esta información se encuentra en la pestaña **Información general** dentro de la aplicación. Para obtener más información, consulte la [documentación de Microsoft Azure sobre cómo registrar una aplicación con la plataforma de identidad de Microsoft](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
   | [!UICONTROL **Secreto de cuenta de ubicación**] | Copie el secreto de la aplicación de Azure que ha creado. En Microsoft Azure, esta información se encuentra en la pestaña **Certificados y secretos** dentro de la aplicación. Para obtener más información, consulte la [Documentación de Microsoft Azure sobre cómo registrar una aplicación con la plataforma de identidad de Microsoft](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |

   {style="table-layout:auto"}

   +++

   +++Correo electrónico

   >[!NOTE]
   >
   >Las cuentas de correo electrónico solo se pueden usar con [Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md). (Las cuentas de correo electrónico no son compatibles con [Fuentes de datos](/help/export/analytics-data-feed/create-feed.md) o [Conjuntos de clasificación](/help/components/classifications/sets/overview.md)).

   Para configurar una cuenta RBAC de Azure, especifique la siguiente información:

   | Campo | Función |
   |---------|----------|
   | [!UICONTROL **Destinatarios**] | Se pueden enviar notificaciones por correo electrónico a personas específicas cuando se envía el informe. Especifique una única dirección de correo electrónico o una lista de direcciones de correo electrónico separadas por comas. |

   {style="table-layout:auto"}

   +++

   **Tipos de cuentas heredadas**

   Estos tipos de cuentas heredadas solo están disponibles al exportar datos con [Fuentes de datos](/help/export/analytics-data-feed/create-feed.md) y [Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md). Estas opciones no están disponibles al importar datos con [conjuntos de clasificaciones](/help/components/classifications/sets/manage/schema.md).

   +++FTP

   Los datos de las fuentes de datos se pueden entregar en una ubicación de Adobe o de FTP alojado por el cliente. Se necesita un host FTP, un nombre de usuario y una contraseña. Utilice el campo de ruta para colocar los archivos de fuente en una carpeta. Las carpetas ya deben existir, las fuentes generan un error si la ruta de acceso especificada no existe.

   | Campo | Función |
   |---------|----------|
   | [!UICONTROL **Host**] | Introduzca la dirección URL de destino de FTP que desee. Por ejemplo, `ftp.adobe.com`. |
   | [!UICONTROL **Ruta**] | Se puede dejar en blanco. |
   | [!UICONTROL **Nombre de usuario**] | Introduzca el nombre de usuario para iniciar sesión en el sitio FTP. |
   | [!UICONTROL **Contraseña y confirmar contraseña**] | Introduzca la contraseña para iniciar sesión en el sitio FTP. |

   {style="table-layout:auto"}

   +++

   +++SFTP

   La compatibilidad con SFTP para fuentes de datos está disponible. Se necesita un host SFTP, un nombre de usuario y el sitio de destino para contener una clave pública RSA o DSA válida. Puede descargar la clave pública adecuada al crear la fuente.

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

   Data Warehouse admite destinos de Azure Blob. Se necesita un contenedor, una cuenta y una clave. Amazon cifra automáticamente los datos en reposo. Cuando se descarguen los datos, estos se descifrarán automáticamente. Consulte [Creación de una cuenta de almacenamiento](https://docs.microsoft.com/es-es/azure/storage/common/storage-quickstart-create-account?tabs=azure-portal#view-and-copy-storage-access-keys) en los documentos de Microsoft Azure para obtener más información.

   >[!NOTE]
   >
   >Debe implementar su propio proceso para administrar el espacio en disco en el destino del almacén de datos. Adobe no elimina ningún dato del servidor.

   +++

1. Seleccione [!UICONTROL **Guardar**].

1. Continúe con [Configurar ubicaciones de importación y exportación en la nube](/help/components/locations/configure-import-locations.md).

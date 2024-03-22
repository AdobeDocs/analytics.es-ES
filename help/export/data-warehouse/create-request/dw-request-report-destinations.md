---
description: Instrucciones sobre cómo crear una solicitud de Data Warehouse.
title: Configuración del destino de un informe para una solicitud de Data Warehouse
feature: Data Warehouse
exl-id: 3c7faea3-4d90-4274-88f3-e9337c94155f
source-git-commit: 4e4b5e1c362778223be01f78b173a698c53f9b32
workflow-type: tm+mt
source-wordcount: '2430'
ht-degree: 99%

---

# Configuración del destino de un informe para una solicitud de Data Warehouse

Hay varias opciones de configuración disponibles al crear una solicitud de Data Warehouse. En la siguiente información se describe cómo configurar un destino de informe para la solicitud.

Para obtener información sobre cómo empezar a crear una solicitud, así como vínculos a otras opciones de configuración importantes, consulte [Crear una solicitud de Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md).

>[!NOTE]
>
>Al configurar un destino de informe, tenga en cuenta lo siguiente:
>
>* Recomendamos utilizar una cuenta en la nube o un correo electrónico para el destino del informe. Las cuentas heredadas de FTP y SFTP están disponibles, pero no se recomiendan.
>
>* Cualquier cuenta en la nube que haya configurado anteriormente para [Fuentes de datos](/help/export/analytics-data-feed/create-feed.md) o para [importación de datos de clasificación de Adobe Analytics](/help/components/locations/locations-manager.md) está disponible para su uso en Data Warehouse. Sin embargo, no se puede utilizar ninguna ubicación configurada para importar datos de clasificación.
>
>* Las cuentas en la nube están asociadas a su cuenta de usuario de Adobe Analytics. Otros usuarios no pueden usar ni ver las cuentas en la nube que configure.
>

Para configurar el destino al que se envían los informes de Data Warehouse:

1. Si aún no lo ha hecho, comience a crear una solicitud en Adobe Analytics seleccionando **[!UICONTROL Herramientas]** > **[!UICONTROL Data Warehouse]** > [!UICONTROL **Añadir**].

   Para obtener más información, consulte [Crear una solicitud de Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md).

1. En la página Nueva solicitud de Data Warehouse, seleccione la pestaña [!UICONTROL **Destino del informe**].

   ![Pestaña Destino del informe](assets/dw-report-destination.png)

1. (Condicional) Si ya se ha configurado una cuenta (y un destino de esa cuenta) que quiere usar como destino del informe:

   1. (Opcional) Si es administrador del sistema, la opción [!UICONTROL **Mostrar todos los destinos**] está disponible. Active esta opción si quiere tener acceso a todas las cuentas y ubicaciones creadas por cualquier usuario de la organización.

   1. Seleccione la cuenta del menú desplegable [!UICONTROL **Seleccionar cuenta**].

      Cualquier cuenta en la nube que haya configurado para [importación de datos de clasificación de Adobe Analytics](/help/components/locations/locations-manager.md) desde un destino en la nube se muestran aquí y se puede utilizar. Sin embargo, no se puede utilizar ninguna ubicación configurada para importar datos de clasificación. En su lugar, añada un nuevo destino tal como se describe a continuación.

   1. Seleccione el destino asociado a la cuenta en el menú desplegable [!UICONTROL **Seleccionar destino**]. <!-- Is this correct? -->

1. (Condicional) Si no ha configurado una cuenta anteriormente:

   1. Seleccione [!UICONTROL **Añadir cuenta**] y, a continuación, especifique la siguiente información:

      | Campo | Función |
      |---------|----------|
      | [!UICONTROL **Tipo de cuenta**] | Seleccione el tipo de cuenta en la nube. Le recomendamos que tenga una sola cuenta para cada tipo de cuenta, con varias ubicaciones según sea necesario dentro de esa cuenta. <p>Después de elegir un tipo de cuenta, aparecen campos específicos de ese tipo de cuenta. </p> |
      | [!UICONTROL **Nombre de la cuenta**] | Especifique un nombre para la cuenta. Este nombre aparece al crear una ubicación. <!-- true? --> |
      | [!UICONTROL **Descripción de la cuenta**] | Proporcione una breve descripción de la cuenta para diferenciarla de otras cuentas del mismo tipo de cuenta. |

      Para obtener instrucciones de configuración, expanda la sección siguiente que corresponde al [!UICONTROL **Tipo de cuenta**] que ha seleccionado.

      Utilice cualquiera de los siguientes tipos de cuentas al configurar un destino de informe. Para obtener instrucciones de configuración, expanda el tipo de cuenta. (También están disponibles otros [destinos heredados](#legacy-destinations), pero no se recomiendan).

      +++Amazon S3

      Especifique la siguiente información para configurar una cuenta ARN de la función Amazon S3:

      | Campo | Función |
      |---------|----------|
      | [!UICONTROL **ARN de función**] | Debe proporcionar un ARN de función (nombre de recurso de Amazon) que Adobe pueda utilizar para obtener acceso a la cuenta de Amazon S3. Para ello, se crea una directiva de permisos de IAM para la cuenta de origen, se adjunta la directiva a un usuario y, a continuación, se crea una función para la cuenta de destino. Para obtener información específica, consulte [esta documentación de AWS](https://aws.amazon.com/premiumsupport/knowledge-center/cross-account-access-iam/).<p>Para obtener información sobre cómo configurar el permiso del cubo, consulte el artículo [¿Cómo puedo proporcionar acceso entre cuentas a los objetos que están en bloques de Amazon S3?](https://repost.aws/knowledge-center/cross-account-access-s3) en el centro de conocimientos de Amazon. |
      | [!UICONTROL **ARN de usuario**] | El ARN (nombre del recurso de Amazon) del usuario lo proporciona Adobe. Debe adjuntar este usuario a la directiva que ha creado. |

      {style="table-layout:auto"}

+++

      +++Google Cloud Platform

      Especifique la siguiente información para configurar una cuenta de Google Cloud Platform:

      | Campo | Función |
      |---------|----------|
      | [!UICONTROL **ID del proyecto**] | Su ID del proyecto de Google Cloud. Consulte la [documentación de Google Cloud sobre cómo obtener un ID de proyecto](https://cloud.google.com/resource-manager/docs/creating-managing-projects#identifying_projects). |

      {style="table-layout:auto"}

+++

      +++Azure SAS

      Especifique la siguiente información para configurar una cuenta SAS de Azure:

      | Campo | Función |
      |---------|----------|
      | [!UICONTROL **ID de aplicación**] | Copie este ID de la aplicación de Azure que ha creado. En Microsoft Azure, esta información se encuentra en la pestaña **Información general** dentro de la aplicación. Para obtener más información, consulte la [documentación de Microsoft Azure sobre cómo registrar una aplicación con la plataforma de identidad de Microsoft](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
      | [!UICONTROL **ID de inquilino**] | Copie este ID de la aplicación de Azure que ha creado. En Microsoft Azure, esta información se encuentra en la pestaña **Información general** dentro de la aplicación. Para obtener más información, consulte la [documentación de Microsoft Azure sobre cómo registrar una aplicación con la plataforma de identidad de Microsoft](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
      | [!UICONTROL **URI de almacén de claves**] | <p>Ruta al token SAS en Azure Key Vault.  Para configurar Azure SAS, debe almacenar un token SAS como un secreto mediante Azure Key Vault. Para obtener más información, consulte la [documentación de Microsoft Azure sobre cómo establecer y recuperar un secreto de Azure Key Vault](https://learn.microsoft.com/en-us/azure/key-vault/secrets/quick-create-portal?source=recommendations).</p><p>Una vez creado el URI del almacén de claves:<ul><li>Añada una directiva de acceso en el almacén de claves para poder conceder permiso a la aplicación de Azure que ha creado.</li><li>Asegúrese de que al ID de aplicación se le haya concedido la `Key Vault Certificate User` función integrada para acceder al URI de almacén de claves.</br><p>Para obtener más información, consulte [Funciones integradas de Azure](https://learn.microsoft.com/en-us/azure/role-based-access-control/built-in-roles).</p></li></ul><p>Para obtener más información, consulte [Documentación de Microsoft Azure sobre cómo asignar una directiva de acceso de Key Vault](https://learn.microsoft.com/en-us/azure/key-vault/general/assign-access-policy?tabs=azure-portal).</p> |
      | [!UICONTROL **Nombre secreto del almacén de claves**] | El nombre secreto que creó al añadir el secreto a Azure Key Vault. En Microsoft Azure, esta información se encuentra en el almacén de claves que ha creado, en las páginas de configuración del **Almacén de claves**. Para obtener más información, consulte [Documentación de Microsoft Azure sobre cómo establecer y recuperar un secreto de Azure Key Vault](https://learn.microsoft.com/en-us/azure/key-vault/secrets/quick-create-portal?source=recommendations). |
      | [!UICONTROL **Secreto**] | Copie el secreto de la aplicación de Azure que ha creado. En Microsoft Azure, esta información se encuentra en la pestaña **Certificados y secretos** dentro de la aplicación. Para obtener más información, consulte la [Documentación de Microsoft Azure sobre cómo registrar una aplicación con la plataforma de identidad de Microsoft](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |

      {style="table-layout:auto"}

+++

      +++Azure RBAC

      Especifique la siguiente información para configurar una cuenta RBAC de Azure:

      | Campo | Función |
      |---------|----------|
      | [!UICONTROL **ID de aplicación**] | Copie este ID de la aplicación de Azure que ha creado. En Microsoft Azure, esta información se encuentra en la pestaña **Información general** dentro de la aplicación. Para obtener más información, consulte la [documentación de Microsoft Azure sobre cómo registrar una aplicación con la plataforma de identidad de Microsoft](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
      | [!UICONTROL **ID de inquilino**] | Copie este ID de la aplicación de Azure que ha creado. En Microsoft Azure, esta información se encuentra en la pestaña **Información general** dentro de la aplicación. Para obtener más información, consulte la [Documentación de Microsoft Azure sobre cómo registrar una aplicación con la plataforma de identidad de Microsoft](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
      | [!UICONTROL **Secreto**] | Copie el secreto de la aplicación de Azure que ha creado. En Microsoft Azure, esta información se encuentra en la pestaña **Certificados y secretos** dentro de la aplicación. Para obtener más información, consulte la [Documentación de Microsoft Azure sobre cómo registrar una aplicación con la plataforma de identidad de Microsoft](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |

      {style="table-layout:auto"}

+++

      +++Correo electrónico

      Especifique la siguiente información para configurar una cuenta de correo electrónico:

      | Campo | Función |
      |---------|----------|
      | [!UICONTROL **Destinatarios**] | Se pueden enviar notificaciones por correo electrónico a personas específicas cuando se envía el informe. Especifique una única dirección de correo electrónico o una lista de direcciones de correo electrónico separadas por comas.<!-- How does this differ from the Notification email tab? --> |

   1. Seleccione [!UICONTROL **Añadir ubicación**] y, a continuación, especifique la siguiente información: 
|Campo | Función |
|---------|----------|
| [!UICONTROL **Nombre**] | el nombre de la ubicación.    |
| [!UICONTROL **Descripción**] | Proporcione una breve descripción de la cuenta para diferenciarla de otras cuentas del mismo tipo de cuenta. |
| [!UICONTROL **Cuenta de ubicación**] | Seleccione la cuenta de ubicación que ha creado en [Añadir una cuenta](#add-an-account). |

   1. En la sección [!UICONTROL **Propiedades de ubicación**], especifique información específica para el tipo de cuenta de su cuenta de ubicación.

      Para obtener instrucciones de configuración, expanda la sección siguiente que corresponde al [!UICONTROL **Tipo de cuenta**] que ha seleccionado anteriormente.

      +++Amazon S3

      Especifique la siguiente información para configurar una ubicación de Amazon S3:

      | Campo | Función |
      |---------|----------|
      | [!UICONTROL **Nombre del bloque**] | El bloque de su cuenta de Amazon S3 al que quiere enviar los datos de Adobe Analytics. <p>Asegúrese de que el ARN del usuario proporcionado por Adobe tiene el permiso `S3:PutObject` para cargar archivos en este bloque. Este permiso permite al ARN del usuario cargar archivos iniciales y sobrescribir archivos para cargas posteriores.</p> |
      | [!UICONTROL **Prefijo de clave**] | La carpeta dentro del bloque en el que quiere colocar los datos. Especifique un nombre de carpeta y, a continuación, añada una barra invertida después del nombre para crear la carpeta. Por ejemplo, folder_name/ |

      {style="table-layout:auto"}

+++

      +++Google Cloud Platform

      Especifique la siguiente información para configurar una ubicación de Google Cloud Platform:

      | Campo | Función |
      |---------|----------|
      | [!UICONTROL **Nombre de bloque**] | El bloque de su cuenta de GCP al que desea enviar los datos de Adobe Analytics. <p>Asegúrese de que ha concedido cualquiera de los siguientes permisos al principal proporcionado por Adobe:<ul><li>`roles/storage.objectCreator`: utilice este permiso si desea limitar el principal para que solo cree archivos en la cuenta de GCP. </br>**Importante:** si utiliza este permiso con informes programados, debe utilizar un nombre de archivo único para cada nueva exportación programada. De lo contrario, la generación del informe no se realizará porque el principal no tiene acceso para sobrescribir los archivos existentes.</li><li>`roles/storage.objectUser`: utilice este permiso si desea que el principal tenga acceso para ver, enumerar, actualizar y eliminar archivos de su cuenta de GCP.</br>Este permiso permite al principal sobrescribir los archivos existentes para cargas posteriores, sin necesidad de generar automáticamente nombres de archivo únicos para cada nueva exportación programada.</li></ul><p>Para obtener información sobre la concesión de permisos, consulte [Adición de un principal a una política de nivel de bloque](https://cloud.google.com/storage/docs/access-control/using-iam-permissions#bucket-add) en la documentación de Google Cloud.</p> |
      | [!UICONTROL **Prefijo clave**] | La carpeta dentro del bloque en el que quiere colocar los datos. Especifique un nombre de carpeta y, a continuación, añada una barra invertida después del nombre para crear la carpeta. Por ejemplo, folder_name/ |

      {style="table-layout:auto"}

+++

      +++Azure SAS

      Especifique la siguiente información para configurar una ubicación SAS de Azure:

      | Campo | Función |
      |---------|----------|
      | [!UICONTROL **Nombre de contenedor**] | El contenedor de la cuenta que especificó dónde desea que se envíen los datos de Adobe Analytics. |
      | [!UICONTROL **Prefijo clave**] | La carpeta dentro del contenedor en la que desea colocar los datos. Especifique un nombre de carpeta y, a continuación, añada una barra invertida después del nombre para crear la carpeta. Por ejemplo, `folder_name/`<p>Asegúrese de que el almacén de tokens SAS que especificó en el campo Nombre secreto del almacén de claves al configurar la cuenta SAS de Azure tenga el permiso `Write`. Esto permite que el token de SAS cree archivos en el contenedor de Azure. <p>Si desea que el token de SAS sobrescriba también los archivos, asegúrese de que el almacén de tokens SAS tenga el permiso `Delete`.</p><p>Para obtener más información, consulte [Recursos de almacenamiento de blob](https://learn.microsoft.com/en-us/azure/storage/blobs/storage-blobs-introduction#blob-storage-resources) en la documentación de almacenamiento de Azure Blob.</p> |

      {style="table-layout:auto"}

+++

      +++Azure RBAC

      Especifique la siguiente información para configurar una ubicación RBAC de Azure:

      | Campo | Función |
      |---------|----------|
      | [!UICONTROL **Nombre de contenedor**] | El contenedor de la cuenta que especificó dónde desea que se envíen los datos de Adobe Analytics. Asegúrese de conceder permisos para cargar archivos en la aplicación de Azure que creó anteriormente. |
      | [!UICONTROL **Prefijo clave**] | La carpeta dentro del contenedor en la que desea colocar los datos. Especifique un nombre de carpeta y, a continuación, añada una barra invertida después del nombre para crear la carpeta. Por ejemplo, `folder_name/`<p>Asegúrese de que el ID de aplicación que especificó al configurar la cuenta de Azure RBAC tenga concedida la función `Storage Blob Data Contributor` para acceder al contenedor (carpeta).</p> <p>Para obtener más información, consulte [Funciones integradas de Azure](https://learn.microsoft.com/en-us/azure/role-based-access-control/built-in-roles).</p> |
      | [!UICONTROL **Nombre de la cuenta**] | La cuenta de almacenamiento de Azure. |

      {style="table-layout:auto"}

+++

1. Siga configurando la solicitud de Data Warehouse en la pestaña [!UICONTROL **Opciones de informe**]. Para obtener más información, consulte [Configuración de las opciones de un informe para una solicitud de Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-options.md).

## Destinos heredados

>[!IMPORTANT]
>
>Los destinos descritos en esta sección son heredados y no se recomiendan. En su lugar, utilice uno de los siguientes destinos al crear un destino de data warehouse: Amazon S3, Google Cloud Platform, Azure RBAC, Azure SAS o Correo electrónico. Consulte la información anterior para obtener detalles sobre cada uno de estos destinos recomendados.

La siguiente información proporciona información de configuración para cada uno de los destinos heredados:

### FTP

Los datos del almacén de datos se pueden entregar en una ubicación de Adobe o de FTP alojada por el cliente. Se necesita un host FTP, un nombre de usuario y una contraseña. Utilice el campo de ruta para colocar los archivos de fuente en una carpeta. Las carpetas ya deben existir, las fuentes generan un error si la ruta de acceso especificada no existe.

Utilice la siguiente información al completar los campos disponibles:

#### Campos de cuenta

* [!UICONTROL **Nombre de cuenta**]: nombre de la cuenta de FTP.

* [!UICONTROL **Descripción de cuenta**]: descripción de la cuenta de FTP.

* [!UICONTROL **Nombre de host**]: introduzca la dirección URL de destino de FTP que quiera. Por ejemplo, `ftp.company.com`.

  >[!NOTE]
  >
  >  No incluya `ftp://` al principio de la dirección URL.

* [!UICONTROL **Nombre de usuario**]: introduzca el nombre de usuario para iniciar sesión en el sitio FTP.

* [!UICONTROL **Contraseña y confirmar contraseña**]: introduzca la contraseña para iniciar sesión en el sitio FTP.

#### Campos de ubicación

* [!UICONTROL **Nombre de ubicación**]: nombre de la ubicación de la cuenta de FTP a la que quiere enviar los archivos.

* [!UICONTROL **Descripción de ubicación**]: descripción de la ubicación en la cuenta de FTP.

* [!UICONTROL **Ruta de directorio**]: ruta a la ubicación en la cuenta de FTP.

### SFTP

La compatibilidad con SFTP para el almacén de datos está disponible. Se necesita un host SFTP, un nombre de usuario y el sitio de destino para contener una clave pública RSA o DSA válida. Puede descargar la clave pública adecuada al crear el destino del almacén de datos.

Utilice la siguiente información al completar los campos disponibles:

#### Campos de cuenta

* [!UICONTROL **Nombre de cuenta**]: nombre de la cuenta de FTP.

* [!UICONTROL **Descripción de cuenta**]: descripción de la cuenta de FTP.

* [!UICONTROL **Nombre de host**]: introduzca la dirección URL del destino de SFTP Por ejemplo, `sftp.company.com`.

  >[!NOTE]
  >
  >  No incluya `sftp://` al principio de la dirección URL.

* [!UICONTROL **Nombre de usuario**]: introduzca el nombre de usuario para iniciar sesión en el sitio de SFTP.

* [!UICONTROL **Usar extensiones de archivos temporales durante la carga**]: cuando está activada, la extensión de archivo `.part` se utiliza durante el proceso de carga. Mantenga esta opción habilitada a menos que el servidor SFTP restrinja que los nombres de archivo cambien una vez completada la carga.

* [!UICONTROL **Claves públicas**]: descargue la clave pública adecuada al crear el destino del almacén de datos.

#### Campos de ubicación

* [!UICONTROL **Nombre de ubicación**]: nombre de la ubicación de la cuenta SFTP a la que quiere enviar los archivos.

* [!UICONTROL **Descripción de ubicación**]: descripción de la ubicación en la cuenta SFTP.

* [!UICONTROL **Ruta de directorio**]: ruta a la ubicación en la cuenta de SFTP.

Para obtener más información sobre la configuración de SFTP, consulte [Envío de solicitudes de Data Warehouse a servidores SFTP](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-dw.md).

### S3

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

### Azure Blob

El almacén de datos admite destinos de Azure Blob. Se necesita un contenedor, una cuenta y una clave. Amazon cifra automáticamente los datos en reposo. Cuando se descarguen los datos, estos se descifrarán automáticamente. Consulte [Creación de una cuenta de almacenamiento](https://docs.microsoft.com/es-es/azure/storage/common/storage-quickstart-create-account?tabs=azure-portal#view-and-copy-storage-access-keys) en los documentos de Microsoft Azure para obtener más información.

>[!NOTE]
>
>Debe implementar su propio proceso para administrar el espacio en disco en el destino del almacén de datos. Adobe no elimina ningún dato del servidor.

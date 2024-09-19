---
description: Instrucciones sobre cómo crear una solicitud de Data Warehouse.
title: Configuración del destino de un informe para una solicitud de Data Warehouse
feature: Data Warehouse
exl-id: 3c7faea3-4d90-4274-88f3-e9337c94155f
source-git-commit: d213befd0fd8d530d95b8d3ac3c4f3b808558244
workflow-type: tm+mt
source-wordcount: '1970'
ht-degree: 83%

---

# Configuración del destino de un informe para una solicitud de Data Warehouse

Hay varias opciones de configuración disponibles al crear una solicitud de Data Warehouse. En la siguiente información se describe cómo configurar un destino de informe para la solicitud.

Para obtener información sobre cómo empezar a crear una solicitud, así como vínculos a otras opciones de configuración importantes, consulte [Crear una solicitud de Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md).

>[!NOTE]
>
>Al configurar un destino de informe, tenga en cuenta lo siguiente:
>
>* Recomendamos utilizar una cuenta en la nube o un correo electrónico para el destino del informe. Las [cuentas heredadas de FTP y SFTP](#legacy-destinations) están disponibles, pero no se recomiendan.
>
>* Todas las cuentas en la nube que configuró anteriormente están disponibles para Data Warehouse. Puede configurar cuentas en la nube de cualquiera de estas formas:
>
>   * Al configurar [Fuentes de datos](/help/export/analytics-data-feed/create-feed.md)
>   
>   * Al [importar datos de clasificación de Adobe Analytics](/help/components/locations/locations-manager.md) (Las cuentas se pueden usar, pero no se pueden usar las ubicaciones configuradas en ellas).
>   
>   * Desde el administrador de Ubicaciones, en [Componentes > Ubicaciones](/help/components/locations/configure-import-accounts.md).
>
>* Las cuentas en la nube están asociadas a su cuenta de usuario de Adobe Analytics. Otros usuarios no pueden usar ni ver las cuentas en la nube que configure.
>
>* Puede editar cualquier ubicación que cree desde el Administrador de ubicaciones en [Componentes > Ubicaciones](/help/components/locations/configure-import-accounts.md)

Para configurar el destino al que se envían los informes de Data Warehouse:

1. Si aún no lo ha hecho, empiece a crear una solicitud en Adobe Analytics seleccionando **[!UICONTROL Herramientas]** > **[!UICONTROL Data Warehouse]** > [!UICONTROL **Añadir**].

   Para obtener más información, consulte [Crear una solicitud de Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md).

1. En la página Nueva solicitud de Data Warehouse, seleccione la pestaña [!UICONTROL **Destino del informe**].

   ![Pestaña Destino del informe](assets/dw-report-destination.png)

1. (Condicional) Si ya se ha configurado una cuenta en la nube (y un destino en esa cuenta) en Adobe Analytics, puede utilizarla como destino del informe:

   >[!NOTE]
   >
   >Las cuentas solo están disponibles si las configuró o si se compartieron con una organización de la que forma parte.
   >
   >(Opcional) Si es administrador del sistema, la opción [!UICONTROL **Mostrar todos los destinos**] está disponible. Active esta opción si quiere tener acceso a todas las cuentas y ubicaciones creadas por cualquier usuario de la organización.

   1. Seleccione la cuenta del menú desplegable [!UICONTROL **Cuenta**].

      Puede utilizar cualquier cuenta en la nube que haya configurado en cualquiera de las siguientes áreas de Adobe Analytics:

      * Al importar datos de clasificación de Adobe Analytics, tal como se describe en [Esquema](/help/components/classifications/sets/manage/schema.md).

        Sin embargo, no se puede utilizar ninguna ubicación configurada para importar datos de clasificación. En su lugar, añada un nuevo destino tal como se describe a continuación.

      * Al configurar cuentas y ubicaciones en el área Ubicaciones, tal como se describe en [Configuración de cuentas de importación y exportación en la nube](/help/components/locations/configure-import-accounts.md) y [Configuración de ubicaciones de importación y exportación en la nube](/help/components/locations/configure-import-locations.md).

   1. Seleccione el destino asociado a la cuenta en el menú desplegable [!UICONTROL **Seleccionar destino**]. <!-- Is this correct? -->

1. (Condicional) Si no tiene acceso a una cuenta en la nube que ya esté configurada en Adobe Analytics, puede configurar una:

   1. Seleccione el menú desplegable [!UICONTROL **Cuenta**] y luego seleccione [!UICONTROL **Agregar cuenta**].

   1. En el cuadro de diálogo Agregar cuenta, especifique la siguiente información:

      | Campo | Función |
      |---------|----------|
      | [!UICONTROL **Nombre de cuenta de ubicación**] | El nombre de la cuenta de ubicación. Este nombre aparece al crear una ubicación |
      | [!UICONTROL **Descripción de cuenta de ubicación**] | Proporcione una breve descripción de la cuenta para diferenciarla de otras cuentas del mismo tipo de cuenta. |
      | [!UICONTROL **Poner la cuenta a disposición de todos los usuarios de su organización**] | Active esta opción para permitir que otros usuarios de su organización utilicen la cuenta.<p>Tenga en cuenta lo siguiente al compartir cuentas:</p><ul><li>Las cuentas que comparta no se pueden dejar de compartir.</li><li>Solo el propietario de la cuenta puede editar las cuentas compartidas.</li><li>Cualquiera puede crear una ubicación para la cuenta compartida.</li></ul> |
      | [!UICONTROL **Tipo de cuenta**] | Seleccione el tipo de cuenta en la nube. Le recomendamos que tenga una sola cuenta para cada tipo de cuenta, con varias ubicaciones según sea necesario dentro de esa cuenta.<p>Los administradores del sistema pueden limitar los tipos de cuentas que los usuarios pueden crear, tal como se describe en [Configurar si los usuarios pueden crear cuentas](/help/components/locations/locations-manager.md#configure-whether-users-can-create-accounts). Si no puede crear cuentas como se describe en esta sección, póngase en contacto con el administrador del sistema.</p> |

   1. En la sección [!UICONTROL **Propiedades de la cuenta**], especifique información específica para el tipo de cuenta que seleccionó.

      Para obtener instrucciones de configuración, expanda la sección siguiente que corresponde al [!UICONTROL **tipo de cuenta**] que seleccionó. (También están disponibles otros tipos de cuentas heredadas, pero no se recomiendan).

      **Tipos de cuenta**

      ARN de la función +++Amazon S3

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
      | [!UICONTROL **URI de almacén de claves**] | <p>Ruta al token SAS en Azure Key Vault.  Para configurar Azure SAS, debe almacenar un token SAS como secreto mediante Azure Key Vault. Para obtener más información, consulte la [documentación de Microsoft Azure sobre cómo establecer y recuperar un secreto de Azure Key Vault](https://learn.microsoft.com/en-us/azure/key-vault/secrets/quick-create-portal?source=recommendations).</p><p>Una vez creado el URI del almacén de claves, agregue una directiva de acceso en el almacén de claves para conceder permiso a la aplicación de Azure que ha creado. Para obtener más información, consulte [Documentación de Microsoft Azure sobre cómo asignar una directiva de acceso de Key Vault](https://learn.microsoft.com/en-us/azure/key-vault/general/assign-access-policy?tabs=azure-portal).</p><p>O</p><p>Si desea conceder un rol de acceso directamente sin crear una directiva de acceso, consulte la [documentación de Microsoft Azure sobre cómo asignar roles de Azure mediante Azure Portal](https://learn.microsoft.com/en-us/azure/role-based-access-control/role-assignments-portal). Esto agrega la asignación de funciones para que el ID de aplicación acceda al URI del almacén de claves. </p> |
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
      >Las cuentas de correo electrónico solo se pueden usar con [Fuentes de datos](/help/export/analytics-data-feed/create-feed.md). (Las cuentas de correo electrónico no son compatibles con [Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md) o [conjuntos de clasificaciones](/help/components/classifications/sets/overview.md)).

      Para configurar una cuenta RBAC de Azure, especifique la siguiente información:

      | Campo | Función |
      |---------|----------|
      | [!UICONTROL **Destinatarios**] | Se pueden enviar notificaciones por correo electrónico a personas específicas cuando se envía el informe. Especifique una única dirección de correo electrónico o una lista de direcciones de correo electrónico separadas por comas. |

      {style="table-layout:auto"}

+++

1. Siga configurando la solicitud de Data Warehouse en la pestaña [!UICONTROL **Opciones de informe**]. Para obtener más información, consulte [Configuración de las opciones de un informe para una solicitud de Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-options.md).

## Tipos de cuentas heredadas

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

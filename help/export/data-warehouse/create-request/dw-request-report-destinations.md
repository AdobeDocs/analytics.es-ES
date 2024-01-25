---
description: Instrucciones sobre cómo crear una solicitud de Data Warehouse.
title: Configuración del destino de un informe para una solicitud de Data Warehouse
feature: Data Warehouse
exl-id: 3c7faea3-4d90-4274-88f3-e9337c94155f
source-git-commit: 7edee01a5a5399762f10037cf920863af35cc4d7
workflow-type: tm+mt
source-wordcount: '2235'
ht-degree: 10%

---

# Configuración del destino de un informe para una solicitud de Data Warehouse

Hay varias opciones de configuración disponibles al crear una solicitud de Data Warehouse. En la siguiente información se describe cómo configurar un destino de informe para la solicitud.

Para obtener información sobre cómo empezar a crear una solicitud, así como vínculos a otras opciones de configuración importantes, consulte [Creación de una solicitud de Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md).

>[!NOTE]
>
>Tenga en cuenta lo siguiente al configurar un destino de informe:
>
>* Recomendamos utilizar una cuenta en la nube o un correo electrónico para el destino del informe. Las cuentas heredadas de FTP y SFTP están disponibles, pero no se recomiendan.
>
>* Las solicitudes de Data Warehouse están asociadas a su cuenta de usuario de Adobe Analytics. De forma predeterminada, otros usuarios no pueden utilizar ni ver las solicitudes configuradas. Puede poner las solicitudes de Data Warehouse a disposición de otros usuarios de su organización activando la variable **Mostrar todos los destinos** alternar, tal como se describe en [Configuración general de solicitudes de Data Warehouse](/help/export/data-warehouse/create-request/dw-general-settings.md).
>
>* Cualquier cuenta de la nube que haya creado anteriormente [configurado para fuentes de datos](/help/export/analytics-data-feed/create-feed.md) están disponibles para su uso en la Data Warehouse.
>
>* Cuentas en la nube configuradas para [importación de datos de clasificación de Adobe Analytics](/help/components/locations/locations-manager.md) desde un destino en la nube se puede utilizar al configurar un destino de informe. Sin embargo, no se puede utilizar ninguna ubicación configurada para importar datos de clasificación.

Para configurar el destino al que se envían los informes de Data Warehouse:

1. Comience a crear una solicitud en Adobe Analytics seleccionando **[!UICONTROL Herramientas]** > **[!UICONTROL Data Warehouse]** > [!UICONTROL **Añadir**].

   Para obtener más información, consulte [Creación de una solicitud de Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md).

1. En la página Nueva solicitud de Data Warehouse, seleccione [!UICONTROL **Destino del informe**] pestaña.

   ![Pestaña Destino del informe](assets/dw-report-destination.png)

1. (Condicional) Si ya se ha configurado una cuenta (y un destino de esa cuenta) que desee usar como destino del informe:

   1. (Opcional) Si es administrador del sistema, la variable [!UICONTROL **Mostrar todos los destinos**] está disponible. Active esta opción si desea tener acceso a todas las cuentas y ubicaciones creadas por cualquier usuario de la organización.

   1. Seleccione la cuenta de la [!UICONTROL **Seleccionar cuenta**] menú desplegable.

      Cualquier cuenta de nube para la que haya configurado [importación de datos de clasificación de Adobe Analytics](/help/components/locations/locations-manager.md) desde un destino en la nube se muestran aquí y se pueden utilizar. Sin embargo, no se puede utilizar ninguna ubicación configurada para importar datos de clasificación. En su lugar, añada un nuevo destino como se describe a continuación.

   1. Seleccione el destino asociado a la cuenta en [!UICONTROL **Seleccionar destino**] menú desplegable. <!-- Is this correct? -->

1. (Condicional) Si no ha configurado una cuenta anteriormente:

   1. Seleccionar [!UICONTROL **Añadir cuenta**] y, a continuación, especifique la siguiente información:

      | Campo | Función |
      |---------|----------|
      | [!UICONTROL **Tipo de cuenta**] | Seleccione el tipo de cuenta en la nube. Recomendamos tener una sola cuenta para cada tipo de cuenta, con varias ubicaciones según sea necesario dentro de esa cuenta. <p>Después de elegir un tipo de cuenta, aparecen campos específicos de ese tipo de cuenta. </p> |
      | [!UICONTROL **Nombre de cuenta**] | Especifique un nombre para la cuenta. Este nombre aparece al crear una ubicación. <!-- true? --> |
      | [!UICONTROL **Descripción de cuenta**] | Proporcione una breve descripción de la cuenta para diferenciarla de otras cuentas del mismo tipo de cuenta. |

      Para obtener instrucciones de configuración, expanda la sección siguiente que corresponde a la variable [!UICONTROL **Tipo de cuenta**] que ha seleccionado.

      Utilice cualquiera de los siguientes tipos de cuentas al configurar un destino de informe. Para obtener instrucciones de configuración, expanda el tipo de cuenta. (adicional) [destinos heredados](#legacy-destinations) también están disponibles, pero no se recomiendan).

      +++Amazon S3

      Especifique la siguiente información para configurar una cuenta ARN de la función Amazon S3:

      | Campo | Función |
      |---------|----------|
      | [!UICONTROL **ARN de la función**] | Debe proporcionar un ARN de la función (nombre de recurso de Amazon) que el Adobe pueda utilizar para obtener acceso a la cuenta de Amazon S3. Para ello, se crea una directiva de permisos de IAM para la cuenta de origen, se adjunta la directiva a un usuario y, a continuación, se crea un rol para la cuenta de destino. Para obtener información específica, consulte [esta documentación de AWS](https://aws.amazon.com/premiumsupport/knowledge-center/cross-account-access-iam/).<p>Para obtener información sobre cómo configurar el permiso del bloque, consulte el artículo [¿Cómo puedo proporcionar acceso entre cuentas a los objetos que están en bloques de Amazon S3?](https://repost.aws/knowledge-center/cross-account-access-s3) en el centro de conocimientos de Amazon. |
      | [!UICONTROL **ARN del usuario**] | El ARN del usuario (nombre del recurso de Amazon) lo proporciona Adobe. Debe adjuntar este usuario a la directiva que ha creado. |

      {style="table-layout:auto"}

+++

      +++Google Cloud Platform

      Especifique la siguiente información para configurar una cuenta de Google Cloud Platform:

      | Campo | Función |
      |---------|----------|
      | [!UICONTROL **ID del proyecto**] | Su ID del proyecto de Google Cloud. Consulte la [Documentación de Google Cloud sobre la obtención de un ID de proyecto](https://cloud.google.com/resource-manager/docs/creating-managing-projects#identifying_projects). |

      {style="table-layout:auto"}

+++

      +++Azure SAS

      Especifique la siguiente información para configurar una cuenta SAS de Azure:

      | Campo | Función |
      |---------|----------|
      | [!UICONTROL **ID de aplicación**] | Copie este ID de la aplicación de Azure que ha creado. En Microsoft Azure, esta información se encuentra en **Información general** dentro de la aplicación. Para obtener más información, consulte la [Documentación de Microsoft Azure sobre cómo registrar una aplicación con Microsoft identity platform](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
      | [!UICONTROL **ID de inquilino**] | Copie este ID de la aplicación de Azure que ha creado. En Microsoft Azure, esta información se encuentra en **Información general** dentro de la aplicación. Para obtener más información, consulte la [Documentación de Microsoft Azure sobre cómo registrar una aplicación con Microsoft identity platform](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
      | [!UICONTROL **URI de Key Vault**] | <p>Ruta al token SAS en Azure Key Vault.  Para configurar Azure SAS, debe almacenar un token SAS como secreto mediante Azure Key Vault. Para obtener más información, consulte [Documentación de Microsoft Azure sobre cómo establecer y recuperar un secreto de Azure Key Vault](https://learn.microsoft.com/en-us/azure/key-vault/secrets/quick-create-portal?source=recommendations).</p><p>Una vez creado el URI del almacén de claves, agregue una directiva de acceso en el almacén de claves para conceder permiso a la aplicación de Azure que ha creado. Para obtener más información, consulte [Documentación de Microsoft Azure sobre cómo asignar una directiva de acceso de Key Vault](https://learn.microsoft.com/en-us/azure/key-vault/general/assign-access-policy?tabs=azure-portal).</p> |
      | [!UICONTROL **Nombre secreto de almacén de claves**] | El nombre secreto que creó al agregar el secreto a Azure Key Vault. En Microsoft Azure, esta información se encuentra en Key Vault que ha creado, en **Key Vault** páginas de configuración. Para obtener más información, consulte [Documentación de Microsoft Azure sobre cómo establecer y recuperar un secreto de Azure Key Vault](https://learn.microsoft.com/en-us/azure/key-vault/secrets/quick-create-portal?source=recommendations). |
      | [!UICONTROL **Secreto**] | Copie el secreto de la aplicación de Azure que ha creado. En Microsoft Azure, esta información se encuentra en **Certificados y secretos** dentro de la aplicación. Para obtener más información, consulte la [Documentación de Microsoft Azure sobre cómo registrar una aplicación con Microsoft identity platform](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |

      {style="table-layout:auto"}

+++

      +++Azure RBAC

      Especifique la siguiente información para configurar una cuenta RBAC de Azure:

      | Campo | Función |
      |---------|----------|
      | [!UICONTROL **ID de aplicación**] | Copie este ID de la aplicación de Azure que ha creado. En Microsoft Azure, esta información se encuentra en **Información general** dentro de la aplicación. Para obtener más información, consulte la [Documentación de Microsoft Azure sobre cómo registrar una aplicación con Microsoft identity platform](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
      | [!UICONTROL **ID de inquilino**] | Copie este ID de la aplicación de Azure que ha creado. En Microsoft Azure, esta información se encuentra en **Información general** dentro de la aplicación. Para obtener más información, consulte la [Documentación de Microsoft Azure sobre cómo registrar una aplicación con Microsoft identity platform](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
      | [!UICONTROL **Secreto**] | Copie el secreto de la aplicación de Azure que ha creado. En Microsoft Azure, esta información se encuentra en **Certificados y secretos** dentro de la aplicación. Para obtener más información, consulte la [Documentación de Microsoft Azure sobre cómo registrar una aplicación con Microsoft identity platform](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |

      {style="table-layout:auto"}

+++

      +++Correo electrónico

      Especifique la siguiente información para configurar una cuenta de correo electrónico:

      | Campo | Función |
      |---------|----------|
      | [!UICONTROL **Destinatarios**] | Las notificaciones por correo electrónico se pueden enviar a usuarios específicos cuando se envía el informe. Especifique una sola dirección de correo electrónico o una lista de direcciones de correo electrónico separadas por coma. <!-- How does this differ from the Notification email tab? --> |

   1. Seleccionar [!UICONTROL **Añadir ubicación**] y, a continuación, especifique la siguiente información: |Campo | Función | |---------|----------| | [!UICONTROL **Nombre**] | El nombre de la ubicación.  | | [!UICONTROL **Descripción**] | Proporcione una breve descripción de la cuenta para diferenciarla de otras cuentas del mismo tipo de cuenta. | | [!UICONTROL **Cuenta de ubicación**] | Seleccione la cuenta de ubicación que creó en [Agregar una cuenta](#add-an-account). |

   1. En el [!UICONTROL **Propiedades de ubicación**] , especifique información específica para el tipo de cuenta de su cuenta de ubicación.

      Para obtener instrucciones de configuración, expanda la sección siguiente que corresponde a la variable [!UICONTROL **Tipo de cuenta**] que seleccionó anteriormente.

      +++Amazon S3

      Especifique la siguiente información para configurar una ubicación de Amazon S3:

      | Campo | Función |
      |---------|----------|
      | [!UICONTROL **Nombre del cubo**] | El bloque de su cuenta de Amazon S3 al que desea enviar los datos de Adobe Analytics. Asegúrese de que el ARN del usuario proporcionado por el Adobe tiene acceso para cargar archivos en este bloque. |
      | [!UICONTROL **Prefijo de clave**] | La carpeta dentro del bloque en el que desea colocar los datos. Especifique un nombre de carpeta y, a continuación, agregue una barra invertida después del nombre para crear la carpeta. Por ejemplo, folder_name/ |

      {style="table-layout:auto"}

+++

      +++Google Cloud Platform

      Especifique la siguiente información para configurar una ubicación de Google Cloud Platform:

      | Campo | Función |
      |---------|----------|
      | [!UICONTROL **Nombre del cubo**] | El bloque de su cuenta de GCP al que desea enviar los datos de Adobe Analytics. Asegúrese de haber concedido permiso al principal proporcionado por el Adobe para cargar archivos en este bloque. Para obtener información sobre la concesión de permisos, consulte [Añadir un principal a una política de nivel de bloque](https://cloud.google.com/storage/docs/access-control/using-iam-permissions#bucket-add) en la documentación de Google Cloud. |
      | [!UICONTROL **Prefijo de clave**] | La carpeta dentro del bloque en el que desea colocar los datos. Especifique un nombre de carpeta y, a continuación, agregue una barra invertida después del nombre para crear la carpeta. Por ejemplo, folder_name/ |

      {style="table-layout:auto"}

+++

      +++Azure SAS

      Especifique la siguiente información para configurar una ubicación SAS de Azure:

      | Campo | Función |
      |---------|----------|
      | [!UICONTROL **Nombre del contenedor**] | El contenedor de la cuenta que especificó a donde desea enviar los datos de Adobe Analytics. |
      | [!UICONTROL **Prefijo de clave**] | Carpeta dentro del contenedor en la que desea colocar los datos. Especifique un nombre de carpeta y, a continuación, agregue una barra invertida después del nombre para crear la carpeta. Por ejemplo, `folder_name/` |

      {style="table-layout:auto"}

+++

      +++Azure RBAC

      Especifique la siguiente información para configurar una ubicación RBAC de Azure:

      | Campo | Función |
      |---------|----------|
      | [!UICONTROL **Nombre del contenedor**] | El contenedor de la cuenta que especificó a donde desea enviar los datos de Adobe Analytics. Asegúrese de conceder permisos para cargar archivos en la aplicación de Azure que creó anteriormente. |
      | [!UICONTROL **Prefijo de clave**] | Carpeta dentro del contenedor en la que desea colocar los datos. Especifique un nombre de carpeta y, a continuación, agregue una barra invertida después del nombre para crear la carpeta. Por ejemplo, `folder_name/` |
      | [!UICONTROL **Nombre de cuenta**] | La cuenta de almacenamiento de Azure. |

      {style="table-layout:auto"}

+++

   1. Seleccione [!UICONTROL **Guardar**].

      Ahora puede importar datos a la cuenta y la ubicación configuradas.

1. Siga configurando la solicitud de Data Warehouse en [!UICONTROL **Opciones de informe**] pestaña. Para obtener más información, consulte [Configuración de las opciones de informes de una solicitud de Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-options.md).

## Destinos heredados

>[!IMPORTANT]
>
>Los destinos descritos en esta sección son heredados y no se recomiendan. En su lugar, utilice uno de los siguientes destinos al crear un destino de Data Warehouse: Amazon S3, Google Cloud Platform, Azure RBAC, Azure SAS o correo electrónico. Consulte la información anterior para obtener detalles sobre cada uno de estos destinos recomendados.

La siguiente información proporciona información de configuración para cada uno de los destinos heredados:

### FTP

Los datos del Data Warehouse se pueden entregar en un Adobe o en una ubicación FTP alojada por el cliente. Se necesita un host FTP, un nombre de usuario y una contraseña. Utilice el campo de ruta para colocar los archivos de fuente en una carpeta. Las carpetas ya deben existir, las fuentes generan un error si la ruta de acceso especificada no existe.

Utilice la siguiente información al completar los campos disponibles:

#### Campos de cuenta

* [!UICONTROL **Nombre de cuenta**]: nombre de la cuenta de FTP.

* [!UICONTROL **Descripción de cuenta**]: una descripción de la cuenta de FTP.

* [!UICONTROL **Hostname**]: introduzca la dirección URL de destino de FTP que desee. Por ejemplo, `ftp.company.com`.

  >[!NOTE]
  >
  >  No incluir `ftp://` al principio de la dirección URL.

* [!UICONTROL **Nombre de usuario**]: introduzca el nombre de usuario para iniciar sesión en el sitio FTP.

* [!UICONTROL **Contraseña y confirmar contraseña**]: introduzca la contraseña para iniciar sesión en el sitio FTP.

#### Campos de ubicación

* [!UICONTROL **Nombre de ubicación**]: nombre de la ubicación de la cuenta de FTP a la que desea enviar los archivos.

* [!UICONTROL **Descripción de ubicación**]: una descripción de la ubicación en la cuenta de FTP.

* [!UICONTROL **Ruta de directorio**]: Ruta a la ubicación en la cuenta de FTP.

### SFTP

La compatibilidad con SFTP para Data Warehouse está disponible. Se necesita un host SFTP, un nombre de usuario y el sitio de destino para contener una clave pública RSA o DSA válida. Puede descargar la clave pública adecuada al crear el destino de Data Warehouse.

Utilice la siguiente información al completar los campos disponibles:

#### Campos de cuenta

* [!UICONTROL **Nombre de cuenta**]: nombre de la cuenta de FTP.

* [!UICONTROL **Descripción de cuenta**]: una descripción de la cuenta de FTP.

* [!UICONTROL **Hostname**]: introduzca la dirección URL de destino SFTP que desee. Por ejemplo, `sftp.company.com`.

  >[!NOTE]
  >
  >  No incluir `sftp://` al principio de la dirección URL.

* [!UICONTROL **Nombre de usuario**]: introduzca el nombre de usuario para iniciar sesión en el sitio SFTP.

* [!UICONTROL **Usar extensiones de archivo temporales durante la carga**]: cuando está activada, la variable `.part` La extensión de archivo se utiliza durante el proceso de carga. Mantenga esta opción habilitada a menos que el servidor SFTP restrinja que los nombres de archivo se cambien una vez completada la carga.

* [!UICONTROL **Claves públicas**]: descargue la clave pública adecuada al crear el destino del almacén de datos.

#### Campos de ubicación

* [!UICONTROL **Nombre de ubicación**]: nombre de la ubicación de la cuenta SFTP a la que desea enviar los archivos.

* [!UICONTROL **Descripción de ubicación**]: una descripción de la ubicación en la cuenta SFTP.

* [!UICONTROL **Ruta de directorio**]: Ruta a la ubicación en la cuenta SFTP.

Para obtener más información sobre la configuración de SFTP, consulte [Envío de solicitudes de Data Warehouse a los servidores SFTP](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-dw.md).

### S3

Puede enviar datos de almacén directamente a los bloques de Amazon S3. Este tipo de destino requiere un nombre de contenedor, un ID de clave de acceso y una clave secreta. Consulte los [requisitos de nomenclatura de contenedor de Amazon S3](https://docs.aws.amazon.com/es_es/awscloudtrail/latest/userguide/cloudtrail-s3-bucket-naming-requirements.html) en los documentos de Amazon S3 para obtener más información.

El usuario que proporcione para cargar los datos del Data Warehouse debe tener lo siguiente [permissions](https://docs.aws.amazon.com/es_es/AmazonS3/latest/API/API_Operations_Amazon_Simple_Storage_Service.html):

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

El Data Warehouse admite destinos de Azure Blob. Se necesita un contenedor, una cuenta y una clave. Amazon cifra automáticamente los datos en reposo. Cuando se descarguen los datos, estos se descifrarán automáticamente. Consulte [Creación de una cuenta de almacenamiento](https://docs.microsoft.com/es-es/azure/storage/common/storage-quickstart-create-account?tabs=azure-portal#view-and-copy-storage-access-keys) en los documentos de Microsoft Azure para obtener más información.

>[!NOTE]
>
>Debe implementar su propio proceso para administrar el espacio en disco en el destino de Data Warehouse. Adobe no elimina ningún dato del servidor.

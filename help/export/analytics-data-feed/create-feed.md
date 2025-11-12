---
title: Crear una fuente de datos
description: Obtenga información sobre cómo crear una fuente de datos y sobre la información de archivo que se va a proporcionar a Adobe.
feature: Data Feeds
exl-id: 36c8a40e-6137-4836-9d4b-bebf17b932bc
source-git-commit: d78a2d683073d90b0b92db50253b3755ff909d9e
workflow-type: tm+mt
source-wordcount: '4227'
ht-degree: 52%

---

# Creación de una fuente de datos

Al crear una fuente de datos, debe proporcionar a Adobe lo siguiente:

* La información sobre el destino al que desea enviar los archivos de datos sin procesar
* Los datos que desea incluir en cada archivo

Antes de crear una fuente de datos, es importante tener una comprensión básica de las fuentes de datos y asegurarse de que cumple todos los requisitos previos. Para obtener más información, consulte [Resumen de fuentes de datos](data-feed-overview.md).

## Creación y configuración de una fuente de datos {#create-and-configure-data-feed}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa_datafeed_os_strings"
>title="Reemplazar cadenas del sistema operativo"
>abstract="Esta opción limpia el resultado de los datos detectando las siguientes secuencias de cadenas incrustadas en los datos del cliente y reemplazándolas por un espacio: <br/>Windows: CRLF, CR o TAB<br/>Mac y Linux: \n, \r o \t"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa_datafeed_export_file"
>title="Manifiesto"
>abstract="Elija si desea incluir un archivo de manifiesto con cada entrega de fuente de datos. Los archivos de manifiesto contienen información para cada archivo incluido en la fuente de datos. Al enviar datos de fuentes de datos en un solo paquete, también puede optar por incluir un archivo de finalización, pero se recomiendan los archivos de manifiesto. "

<!-- markdownlint-enable MD034 -->

1. Inicie sesión en [experiencecloud.adobe.com](https://experiencecloud.adobe.com) con sus credenciales de Adobe ID.
1. Seleccione el icono de 9 cuadrados en la esquina superior derecha, luego seleccione [!UICONTROL **Analytics**].
1. En la barra de navegación superior, ve a [!UICONTROL **Administración**] > [!UICONTROL **Fuentes de datos**].
1. Seleccione [!UICONTROL **Añadir**].

   ![Agregar fuente de datos](assets/datafeed-add.png)

   Se muestra una página con tres categorías principales: [!UICONTROL **Información de fuente**], [!UICONTROL **Destino**] y [!UICONTROL **Definiciones de columnas de datos**].
1. En la sección [!UICONTROL **Información de fuente**], rellene los campos siguientes:

   | Campo | Función |
   |---------|----------|
   | [!UICONTROL **Nombre**] | Nombre de la fuente de datos. Debe ser único dentro del grupo de informes seleccionado y puede tener hasta 255 caracteres de longitud. [Más información](/help/export/analytics-data-feed/df-faq.md#must-feed-names-be-unique) |
   | [!UICONTROL **Grupo de informes**] | Grupo de informes en el que se basa la fuente de datos. Si se crean varias fuentes de datos para el mismo grupo de informes, deben tener definiciones de columnas diferentes. Solo los grupos de informes de origen admiten fuentes de datos, no se admiten los grupos de informes virtuales. |
   | [!UICONTROL **Enviar correo electrónico al finalizar**] | La dirección de correo electrónico que se notificará cuando una fuente termine de procesarse. La dirección de correo electrónico debe tener el formato correcto. |
   | [!UICONTROL **Intervalo de fuente**] | Seleccione **Diario** para datos históricos o de relleno. Las fuentes diarias contienen datos de un día completo, de medianoche a medianoche en el huso horario del grupo de informes. Seleccione **Cada hora** para continuar los datos (Diariamente también está disponible para continuar las fuentes, si lo prefiere). Las fuentes por hora contienen datos de una sola hora. |
   | [!UICONTROL **Retrasar procesamiento**] | Espere un tiempo determinado antes de procesar un archivo de fuente de datos. Un retraso puede resultar útil para ofrecer a las implementaciones móviles la oportunidad de que los dispositivos sin conexión se conecten y envíen datos. También se puede utilizar para dar cabida a los procesos del lado del servidor de su organización en la administración de archivos procesados anteriormente. En la mayoría de los casos, no es necesario un retraso. Una fuente se puede retrasar hasta 120 minutos. |
   | [!UICONTROL **Fechas de inicio y finalización**] | La fecha de inicio indica la fecha en la que desea que comience la fuente de datos. Para comenzar a procesar inmediatamente fuentes de datos para datos históricos, establezca esta fecha en cualquier fecha en el pasado en que se estén recopilando datos. Las fechas de inicio y finalización se basan en el huso horario del grupo de informes. |
   | [!UICONTROL **Fuente continua**] | Esta casilla elimina la fecha de finalización, lo que permite que una fuente se ejecute indefinidamente. Cuando una fuente termina de procesar datos históricos, la fuente espera a que los datos terminen de recopilar durante una hora o un día determinados. Una vez finalizada la hora o el día actuales, el procesamiento comienza después del retraso especificado. |

1. En la sección [!UICONTROL **Destino**], en el menú desplegable [!UICONTROL **Tipo**], seleccione el destino al que desea enviar los datos.

   >[!NOTE]
   >
   >Al configurar un destino de informe, tenga en cuenta lo siguiente:
   >
   >* Se recomienda utilizar una cuenta de nube para el destino del informe. Hay [cuentas heredadas de FTP y SFTP](#legacy-destinations) disponibles, pero no se recomiendan.
   >* Todas las cuentas de nube que haya configurado anteriormente están disponibles para su uso en las fuentes de datos. Puede configurar cuentas en la nube de cualquiera de estas formas:
   >
   >   * Al configurar cuentas en la nube para [Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md)
   >   
   >   * Al [importar datos de clasificación de Adobe Analytics](/help/components/locations/locations-manager.md) (no se pueden usar ninguna ubicación configurada para importar datos de clasificación).
   >   
   >   * Desde el administrador Ubicaciones, en [Componentes > Ubicaciones](/help/components/locations/configure-import-accounts.md)
   >
   >* Las cuentas en la nube están asociadas a su cuenta de usuario de Adobe Analytics. Otros usuarios no pueden usar ni ver las cuentas en la nube que configure.
   >
   >* Puede editar cualquier ubicación que cree desde el Administrador de ubicaciones en [Componentes > Ubicaciones](/help/components/locations/configure-import-accounts.md)

   ![Menú desplegable de destino de fuente de datos](assets/datafeed-destinations-dropdown.png)

   Utilice cualquiera de los siguientes tipos de destino al crear una fuente de datos. Para obtener instrucciones de configuración, expanda el tipo de destino. (También están disponibles otros [destinos heredados](#legacy-destinations), pero no se recomiendan).

   +++Amazon S3

   Puede enviar fuentes directamente a los bloques de Amazon S3. Este tipo de destino solo requiere su cuenta de Amazon S3 y la ubicación (bloque).

   Adobe Analytics utiliza la autenticación entre cuentas para cargar archivos desde Adobe Analytics a la ubicación especificada en la instancia de Amazon S3.

   Al utilizar Amazon S3 con fuentes de datos, solo se admite el cifrado SSE-S3.

   Para configurar un contenedor de Amazon S3 como destino de una fuente de datos:

   1. Comience a crear una fuente de datos como se describe en [Crear y configurar una fuente de datos](#create-and-configure-a-data-feed).

   1. En la sección [!UICONTROL **Destino**], en el menú desplegable [!UICONTROL **Tipo**], seleccione [!UICONTROL **Amazon S3**].

      ![Destino de Amazon S3](assets/datafeed-destination-amazons3.png)

   1. Seleccione [!UICONTROL **Seleccionar ubicación**].

      Se muestra la página Ubicaciones de exportación de Amazon S3.

   1. (Condicional) Si ya se ha configurado una cuenta de Amazon S3 (y una ubicación en esa cuenta) en Adobe Analytics, puede utilizarla como destino de la fuente de datos:

      >[!NOTE]
      >
      >Las cuentas solo están disponibles si las configuró o si se compartieron con una organización de la que forma parte.

      1. Seleccione la cuenta del menú desplegable [!UICONTROL **Seleccionar cuenta**].

         Cualquier cuenta de nube que se haya configurado en cualquiera de las siguientes áreas de Adobe Analytics está disponible para usar:

         * Al importar datos de clasificación de Adobe Analytics, tal como se describe en [Esquema](/help/components/classifications/sets/manage/schema.md).

           Sin embargo, no se puede utilizar ninguna ubicación configurada para importar datos de clasificación. En su lugar, añada un nuevo destino tal como se describe a continuación.

         * Al configurar cuentas y ubicaciones en el área Ubicaciones, tal como se describe en [Configuración de cuentas de importación y exportación en la nube](/help/components/locations/configure-import-accounts.md) y [Configuración de ubicaciones de importación y exportación en la nube](/help/components/locations/configure-import-locations.md).

      1. Seleccione la ubicación en el menú desplegable [!UICONTROL **Seleccionar ubicación**].

      1. Seleccione [!UICONTROL **Guardar**] > [!UICONTROL **Guardar**].

      El destino ahora está configurado para enviar datos a la ubicación de Amazon S3 especificada.

   1. (Condicional) Si no ha agregado anteriormente una cuenta de Amazon S3:

      1. Seleccione [!UICONTROL **Añadir cuenta**] y, a continuación, especifique la siguiente información:

         | Campo | Función |
         |---------|----------|
         | [!UICONTROL **Nombre de la cuenta**] | Un nombre para la cuenta. Puede ser cualquier nombre que elija. |
         | [!UICONTROL **Descripción de la cuenta**] | Una descripción de la cuenta. |
         | [!UICONTROL **ARN de función**] | Debe proporcionar un ARN de función (nombre de recurso de Amazon) que Adobe pueda utilizar para obtener acceso a la cuenta de Amazon S3. Para ello, se crea una directiva de permisos de IAM para la cuenta de origen, se adjunta la directiva a un usuario y, a continuación, se crea una función para la cuenta de destino. Para obtener información específica, consulte [esta documentación de AWS](https://aws.amazon.com/premiumsupport/knowledge-center/cross-account-access-iam/). |
         | [!UICONTROL **ARN de usuario**] | El ARN (nombre del recurso de Amazon) del usuario lo proporciona Adobe. Debe adjuntar este usuario a la directiva que ha creado. |

         {style="table-layout:auto"}

      1. Seleccione [!UICONTROL **Añadir ubicación**] y, a continuación, especifique la siguiente información:

         | Campo | Función |
         |---------|----------|
         | [!UICONTROL **Nombre**] | Un nombre para la cuenta. |
         | [!UICONTROL **Descripción**] | Una descripción de la cuenta. |
         | [!UICONTROL **Cubo**] | El bloque de su cuenta de Amazon S3 al que quiere enviar los datos de Adobe Analytics. <p>Asegúrese de que el ARN del usuario proporcionado por Adobe tiene el permiso `S3:PutObject` para cargar archivos en este bloque. Este permiso permite al ARN del usuario cargar archivos iniciales y sobrescribir archivos para cargas posteriores.</p><p>Los nombres de bloques deben cumplir reglas de nomenclatura específicas. Los nombres bloques deben tener entre 3 y 63 caracteres de longitud, solo pueden constar de letras minúsculas, números, puntos (.) y guiones (-), y deben empezar y terminar con una letra o un número. [En la documentación de AWS encontrará una lista completa de las reglas de nomenclatura](https://docs.aws.amazon.com/AmazonS3/latest/userguide/bucketnamingrules.html). </p> |
         | [!UICONTROL **Prefijo**] | La carpeta dentro del bloque en el que quiere colocar los datos. Especifique un nombre de carpeta y, a continuación, añada una barra invertida después del nombre para crear la carpeta. Por ejemplo, `folder_name/` |

         {style="table-layout:auto"}

      1. Seleccione [!UICONTROL **Crear**] > [!UICONTROL **Guardar**].

         El destino ahora está configurado para enviar datos a la ubicación de Amazon S3 especificada.

      1. (Condicional) Si necesita administrar el destino (cuenta y ubicación) que acaba de crear, está disponible en el [administrador de ubicaciones](/help/components/locations/locations-manager.md).

   +++

   +++Azure RBAC

   Puede enviar fuentes directamente a un contenedor de Azure mediante la autenticación RBAC. Este tipo de destino requiere un ID de aplicación, un ID de inquilino y un secreto.

   Para configurar una cuenta RBAC de Azure como destino de una fuente de datos:

   1. Si aún no lo ha hecho, cree una aplicación de Azure que Adobe Analytics pueda utilizar para la autenticación y, a continuación, conceda permisos de acceso en el control de acceso (IAM).

      Para obtener más información, consulte la [documentación de Microsoft Azure sobre cómo crear una aplicación de Azure Active Directory](https://learn.microsoft.com/en-us/azure/active-directory/develop/howto-create-service-principal-portal).

   1. En Admin Console de Adobe Analytics, en la sección [!UICONTROL **Destino**], en el menú desplegable [!UICONTROL **Tipo**], seleccione [!UICONTROL **Azure RBAC**].

      ![Destino RBAC de Azure](assets/datafeed-destination-azurerbac.png)

   1. Seleccione [!UICONTROL **Seleccionar ubicación**].

      Se muestra la página Ubicaciones de exportación de Azure RBAC.

   1. (Condicional) Si ya se ha configurado una cuenta de Azure RBAC (y una ubicación en esa cuenta) en Adobe Analytics, puede utilizarla como destino de la fuente de datos:

      >[!NOTE]
      >
      >Las cuentas solo están disponibles si las configuró o si se compartieron con una organización de la que forma parte.

      1. Seleccione la cuenta del menú desplegable [!UICONTROL **Seleccionar cuenta**].

      Puede utilizar cualquier cuenta en la nube que haya configurado en cualquiera de las siguientes áreas de Adobe Analytics:

      * Al importar datos de clasificación de Adobe Analytics, tal como se describe en [Esquema](/help/components/classifications/sets/manage/schema.md).

        Sin embargo, no se puede utilizar ninguna ubicación configurada para importar datos de clasificación. En su lugar, añada un nuevo destino tal como se describe a continuación.

      * Al configurar cuentas y ubicaciones en el área Ubicaciones, tal como se describe en [Configuración de cuentas de importación y exportación en la nube](/help/components/locations/configure-import-accounts.md) y [Configuración de ubicaciones de importación y exportación en la nube](/help/components/locations/configure-import-locations.md).

      1. Seleccione la ubicación en el menú desplegable [!UICONTROL **Seleccionar ubicación**].

      1. Seleccione [!UICONTROL **Guardar**] > [!UICONTROL **Guardar**].

         El destino ahora está configurado para enviar datos a la ubicación RBAC de Azure que especificó.

   1. (Condicional) Si no ha agregado anteriormente una cuenta de Azure RBAC:

      1. Seleccione [!UICONTROL **Añadir cuenta**] y, a continuación, especifique la siguiente información:

         | Campo | Función |
         |---------|----------|
         | [!UICONTROL **Nombre de la cuenta**] | Un nombre para la cuenta de Azure RBAC. Este nombre se muestra en el campo desplegable [!UICONTROL **Seleccionar cuenta**] y puede ser cualquier nombre que elija. |
         | [!UICONTROL **Descripción de la cuenta**] | Descripción de la cuenta de Azure RBAC. Esta descripción se muestra en el campo desplegable [!UICONTROL **Seleccionar cuenta**] y puede ser cualquier nombre que elija. |
         | [!UICONTROL **ID de aplicación**] | Copie este ID de la aplicación de Azure que ha creado. En Microsoft Azure, esta información se encuentra en la pestaña **Información general** dentro de la aplicación. Para obtener más información, consulte la [documentación de Microsoft Azure sobre cómo registrar una aplicación con la plataforma de identidad de Microsoft](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
         | [!UICONTROL **ID de inquilino**] | Copie este ID de la aplicación de Azure que ha creado. En Microsoft Azure, esta información se encuentra en la pestaña **Información general** dentro de la aplicación. Para obtener más información, consulte la [Documentación de Microsoft Azure sobre cómo registrar una aplicación con la plataforma de identidad de Microsoft](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
         | [!UICONTROL **Secreto**] | Copie el secreto de la aplicación de Azure que ha creado. En Microsoft Azure, esta información se encuentra en la pestaña **Certificados y secretos** dentro de la aplicación. Para obtener más información, consulte la [Documentación de Microsoft Azure sobre cómo registrar una aplicación con la plataforma de identidad de Microsoft](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |

         {style="table-layout:auto"}

      1. Seleccione [!UICONTROL **Añadir ubicación**] y, a continuación, especifique la siguiente información:

         | Campo | Función |
         |---------|----------|
         | [!UICONTROL **Nombre**] | Un nombre para la ubicación. Este nombre se muestra en el campo desplegable [!UICONTROL **Seleccionar ubicación**] y puede ser cualquier nombre que elija. |
         | [!UICONTROL **Descripción**] | Una descripción de la ubicación. Esta descripción se muestra en el campo desplegable [!UICONTROL **Seleccionar ubicación**] y puede ser cualquier nombre que elija. |
         | [!UICONTROL **Cuenta**] | La cuenta de almacenamiento de Azure. |
         | [!UICONTROL **Contenedor**] | El contenedor de la cuenta que especificó dónde desea que se envíen los datos de Adobe Analytics. Asegúrese de conceder permisos para cargar archivos en la aplicación de Azure que creó anteriormente. |
         | [!UICONTROL **Prefijo**] | La carpeta dentro del contenedor en la que desea colocar los datos. Especifique un nombre de carpeta y, a continuación, añada una barra invertida después del nombre para crear la carpeta. Por ejemplo, `folder_name/`<p>Asegúrese de que el ID de aplicación que especificó al configurar la cuenta de Azure RBAC tenga concedida la función `Storage Blob Data Contributor` para acceder al contenedor (carpeta).</p> <p>Para obtener más información, consulte [Funciones integradas de Azure](https://learn.microsoft.com/en-us/azure/role-based-access-control/built-in-roles).</p> |

         {style="table-layout:auto"}

      1. Seleccione [!UICONTROL **Crear**] > [!UICONTROL **Guardar**].

         El destino ahora está configurado para enviar datos a la ubicación RBAC de Azure que especificó.

      1. (Condicional) Si necesita administrar el destino (cuenta y ubicación) que acaba de crear, está disponible en el [administrador de ubicaciones](/help/components/locations/locations-manager.md).

   +++

   +++Azure SAS

   Puede enviar fuentes directamente a un contenedor de Azure mediante la autenticación SAS. Este tipo de destino requiere un ID de aplicación, un ID de inquilino, un URI de almacén de claves, un nombre secreto de almacén de claves y un secreto.

   Para configurar Azure SAS como destino de una fuente de datos:

   1. Si aún no lo ha hecho, cree una aplicación de Azure que Adobe Analytics pueda utilizar para la autenticación.

      Para obtener más información, consulte la [documentación de Microsoft Azure sobre cómo crear una aplicación de Azure Active Directory](https://learn.microsoft.com/en-us/azure/active-directory/develop/howto-create-service-principal-portal).

   1. En Admin Console de Adobe Analytics, en la sección [!UICONTROL **Destino**], seleccione [!UICONTROL **Azure SAS**].

      ![Destino SAS de Azure](assets/datafeed-destination-azuresas.png)

   1. Seleccione [!UICONTROL **Seleccionar ubicación**].

      Se muestra la página Ubicaciones de exportación de Azure SAS.

   1. (Condicional) Si ya se ha configurado una cuenta SAS de Azure (y una ubicación en esa cuenta) en Adobe Analytics, puede utilizarla como destino de la fuente de datos:

      >[!NOTE]
      >
      >Las cuentas solo están disponibles si las configuró o si se compartieron con una organización de la que forma parte.

      1. Seleccione la cuenta del menú desplegable [!UICONTROL **Seleccionar cuenta**].

         Puede utilizar cualquier cuenta en la nube que haya configurado en cualquiera de las siguientes áreas de Adobe Analytics:

         * Al importar datos de clasificación de Adobe Analytics, tal como se describe en [Esquema](/help/components/classifications/sets/manage/schema.md).

           Sin embargo, no se puede utilizar ninguna ubicación configurada para importar datos de clasificación. En su lugar, añada un nuevo destino tal como se describe a continuación.

         * Al configurar cuentas y ubicaciones en el área Ubicaciones, tal como se describe en [Configuración de cuentas de importación y exportación en la nube](/help/components/locations/configure-import-accounts.md) y [Configuración de ubicaciones de importación y exportación en la nube](/help/components/locations/configure-import-locations.md).

      1. Seleccione la ubicación en el menú desplegable [!UICONTROL **Seleccionar ubicación**].

      1. Seleccione [!UICONTROL **Guardar**] > [!UICONTROL **Guardar**].

         El destino ahora está configurado para enviar datos a la ubicación SAS de Azure especificada.

   1. (Condicional) Si no ha agregado previamente una cuenta SAS de Azure:

      1. Seleccione [!UICONTROL **Añadir cuenta**] y, a continuación, especifique la siguiente información:

         | Campo | Función |
         |---------|----------|
         | [!UICONTROL **Nombre de la cuenta**] | Un nombre para la cuenta SAS de Azure. Este nombre se muestra en el campo desplegable [!UICONTROL **Seleccionar cuenta**] y puede ser cualquier nombre que elija. |
         | [!UICONTROL **Descripción de la cuenta**] | Descripción de la cuenta SAS de Azure. Esta descripción se muestra en el campo desplegable [!UICONTROL **Seleccionar cuenta**] y puede ser cualquier nombre que elija. |
         | [!UICONTROL **ID de aplicación**] | Copie este ID de la aplicación de Azure que ha creado. En Microsoft Azure, esta información se encuentra en la pestaña **Información general** dentro de la aplicación. Para obtener más información, consulte la [documentación de Microsoft Azure sobre cómo registrar una aplicación con la plataforma de identidad de Microsoft](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
         | [!UICONTROL **ID de inquilino**] | Copie este ID de la aplicación de Azure que ha creado. En Microsoft Azure, esta información se encuentra en la pestaña **Información general** dentro de la aplicación. Para obtener más información, consulte la [documentación de Microsoft Azure sobre cómo registrar una aplicación con la plataforma de identidad de Microsoft](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
         | [!UICONTROL **URI de almacén de claves**] | <p>Ruta al URI de SAS en Azure Key Vault. Para configurar Azure SAS, debe almacenar un URI de SAS como un secreto mediante Azure Key Vault. Para obtener más información, consulte la [documentación de Microsoft Azure sobre cómo establecer y recuperar un secreto de Azure Key Vault](https://learn.microsoft.com/en-us/azure/key-vault/secrets/quick-create-portal?source=recommendations).</p><p>Una vez creado el URI del almacén de claves:<ul><li>Añada una directiva de acceso en el almacén de claves para poder conceder permiso a la aplicación de Azure que ha creado.<p>Para obtener más información, consulte [Documentación de Microsoft Azure sobre cómo asignar una directiva de acceso de almacén de claves](https://learn.microsoft.com/en-us/azure/key-vault/general/assign-access-policy?tabs=azure-portal).</p><p>O bien</p><p>Si desea conceder un rol de acceso directamente sin crear una directiva de acceso, consulte la [documentación de Microsoft Azure sobre cómo asignar roles de Azure mediante Azure Portal](https://learn.microsoft.com/en-us/azure/role-based-access-control/role-assignments-portal). Esto agrega la asignación de funciones para que el ID de aplicación acceda al URI del almacén de claves. </p></li><li>Asegúrese de que al ID de aplicación se le haya concedido la `Key Vault Certificate User` función integrada para acceder al URI de almacén de claves.</br><p>Para obtener más información, consulte [Funciones integradas de Azure](https://learn.microsoft.com/en-us/azure/role-based-access-control/built-in-roles).</p></li></ul> |
         | [!UICONTROL **Nombre secreto del almacén de claves**] | El nombre secreto que creó al añadir el secreto a Azure Key Vault. En Microsoft Azure, esta información se encuentra en el almacén de claves que ha creado, en las páginas de configuración del **Almacén de claves**. Para obtener más información, consulte [Documentación de Microsoft Azure sobre cómo establecer y recuperar un secreto de Azure Key Vault](https://learn.microsoft.com/en-us/azure/key-vault/secrets/quick-create-portal?source=recommendations). |
         | [!UICONTROL **Secreto**] | Copie el secreto de la aplicación de Azure que ha creado. En Microsoft Azure, esta información se encuentra en la pestaña **Certificados y secretos** dentro de la aplicación. Para obtener más información, consulte la [Documentación de Microsoft Azure sobre cómo registrar una aplicación con la plataforma de identidad de Microsoft](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |

         {style="table-layout:auto"}

      1. Seleccione [!UICONTROL **Añadir ubicación**] y, a continuación, especifique la siguiente información:

         | Campo | Función |
         |---------|----------|
         | [!UICONTROL **Nombre**] | Un nombre para la ubicación. Este nombre se muestra en el campo desplegable [!UICONTROL **Seleccionar ubicación**] y puede ser cualquier nombre que elija. |
         | [!UICONTROL **Descripción**] | Una descripción de la ubicación. Esta descripción se muestra en el campo desplegable [!UICONTROL **Seleccionar ubicación**] y puede ser cualquier nombre que elija. |
         | [!UICONTROL **Contenedor**] | El contenedor de la cuenta que especificó dónde desea que se envíen los datos de Adobe Analytics. |
         | [!UICONTROL **Prefijo**] | La carpeta dentro del contenedor en la que desea colocar los datos. Especifique un nombre de carpeta y, a continuación, añada una barra invertida después del nombre para crear la carpeta. Por ejemplo, `folder_name/`<p>Asegúrese de que el almacén de URI de SAS que especificó en el campo de nombre secreto del almacén de claves al configurar la cuenta SAS de Azure tenga el permiso `Write`. Esto permite que el URI de SAS cree archivos en el contenedor de Azure. <p>Si desea que el URI de SAS sobrescriba también los archivos, asegúrese de que el almacén de URI de SAS tenga el permiso `Delete`.</p><p>Para obtener más información, consulte [Recursos de almacenamiento de blob](https://learn.microsoft.com/en-us/azure/storage/blobs/storage-blobs-introduction#blob-storage-resources) en la documentación de almacenamiento de Azure Blob.</p> |

         {style="table-layout:auto"}

      1. Seleccione [!UICONTROL **Crear**] > [!UICONTROL **Guardar**].

         El destino ahora está configurado para enviar datos a la ubicación SAS de Azure especificada.

      1. (Condicional) Si necesita administrar el destino (cuenta y ubicación) que acaba de crear, está disponible en el [administrador de ubicaciones](/help/components/locations/locations-manager.md).

   +++

   +++Google Cloud Platform

   Puede enviar fuentes directamente a los bloques de Google Cloud Platform (GCP). Este tipo de destino solo requiere su nombre de cuenta de GCP y el nombre de la ubicación (bloque).

   Adobe Analytics utiliza la autenticación entre cuentas para cargar archivos desde Adobe Analytics a la ubicación especificada en la instancia de GCP.

   Para configurar un bloque de GCP como destino para una fuente de datos:

   1. En Admin Console de Adobe Analytics, en la sección [!UICONTROL **Destino**], seleccione [!UICONTROL **Google Cloud Platform**].

      ![Destino de Google Cloud Platform](assets/datafeed-destination-gcp.png)

   1. Seleccione [!UICONTROL **Seleccionar ubicación**].

      Se muestra la página Ubicaciones de exportación de GCP.

   1. (Condicional) Si ya se ha configurado una cuenta de Google Cloud Platform (y una ubicación en esa cuenta) en Adobe Analytics, puede utilizarla como destino de la fuente de datos:

      >[!NOTE]
      >
      >Las cuentas solo están disponibles si las configuró o si se compartieron con una organización de la que forma parte.

      1. Seleccione la cuenta del menú desplegable [!UICONTROL **Seleccionar cuenta**].

         Puede utilizar cualquier cuenta en la nube que haya configurado en cualquiera de las siguientes áreas de Adobe Analytics:

         * Al importar datos de clasificación de Adobe Analytics, tal como se describe en [Esquema](/help/components/classifications/sets/manage/schema.md).

           Sin embargo, no se puede utilizar ninguna ubicación configurada para importar datos de clasificación. En su lugar, añada un nuevo destino tal como se describe a continuación.

         * Al configurar cuentas y ubicaciones en el área Ubicaciones, tal como se describe en [Configuración de cuentas de importación y exportación en la nube](/help/components/locations/configure-import-accounts.md) y [Configuración de ubicaciones de importación y exportación en la nube](/help/components/locations/configure-import-locations.md).

      1. Seleccione la ubicación en el menú desplegable [!UICONTROL **Seleccionar ubicación**].

      1. Seleccione [!UICONTROL **Guardar**] > [!UICONTROL **Guardar**].

         El destino ahora está configurado para enviar datos a la ubicación de Google Cloud Platform que haya especificado.

   1. (Condicional) Si no ha agregado anteriormente una cuenta de GCP:

      1. Seleccione [!UICONTROL **Añadir cuenta**] y, a continuación, especifique la siguiente información:

         | Campo | Función |
         |---------|----------|
         | [!UICONTROL **Nombre de la cuenta**] | Un nombre para la cuenta. Puede ser cualquier nombre que elija. |
         | [!UICONTROL **Descripción de la cuenta**] | Una descripción de la cuenta. |
         | [!UICONTROL **ID del proyecto**] | Su ID del proyecto de Google Cloud. Consulte la [documentación de Google Cloud sobre cómo obtener un ID de proyecto](https://cloud.google.com/resource-manager/docs/creating-managing-projects#identifying_projects). |

         {style="table-layout:auto"}

      1. Seleccione [!UICONTROL **Añadir ubicación**] y, a continuación, especifique la siguiente información:

         | Campo | Función |
         |---------|----------|
         | [!UICONTROL **Principal**] | Adobe proporciona la entidad de seguridad. Debe conceder permiso para recibir fuentes a esta entidad de seguridad. |
         | [!UICONTROL **Nombre**] | Un nombre para la cuenta. |
         | [!UICONTROL **Descripción**] | Una descripción de la cuenta. |
         | [!UICONTROL **Cubo**] | El bloque de su cuenta de GCP al que desea enviar los datos de Adobe Analytics. <p>Asegúrese de que ha concedido alguno de los siguientes permisos al principal proporcionado por Adobe: (Para obtener información sobre la concesión de permisos, consulte [Adición de un principal a una política de nivel de bloque](https://cloud.google.com/storage/docs/access-control/using-iam-permissions#bucket-add) en la documentación de Google Cloud).<ul><li>`roles/storage.objectCreator`: utilice este permiso si desea limitar el principal para que solo cree archivos en la cuenta de GCP. </br>**Importante:** si utiliza este permiso con informes programados, debe utilizar un nombre de archivo único para cada nueva exportación programada. De lo contrario, la generación del informe no se realizará porque el principal no tiene acceso para sobrescribir los archivos existentes.</li><li>(Recomendado) `roles/storage.objectUser`: Use este permiso si desea que la entidad de seguridad tenga acceso para ver, enumerar, actualizar y eliminar archivos en su cuenta de GCP.</br>Este permiso permite al principal sobrescribir los archivos existentes para cargas posteriores, sin necesidad de generar automáticamente nombres de archivo únicos para cada nueva exportación programada.</li></ul><p>Si su organización utiliza [Restricciones de política de organización](https://cloud.google.com/storage/docs/org-policy-constraints) para permitir únicamente la cuenta de Google Cloud Platform en su lista de permitidos, necesita el siguiente ID de organización de Google Cloud Platform propiedad de Adobe: <ul><li>`DISPLAY_NAME`: `adobe.com`</li><li>`ID`: `178012854243`</li><li>`DIRECTORY_CUSTOMER_ID`: `C02jo8puj`</li></ul> </p> |
         | [!UICONTROL **Prefijo**] | La carpeta dentro del bloque en el que quiere colocar los datos. Especifique un nombre de carpeta y, a continuación, añada una barra invertida después del nombre para crear la carpeta. Por ejemplo, `folder_name/` |

         {style="table-layout:auto"}

      1. Seleccione [!UICONTROL **Crear**] > [!UICONTROL **Guardar**].

         El destino ahora está configurado para enviar datos a la ubicación de GCP especificada.

      1. (Condicional) Si necesita administrar el destino (cuenta y ubicación) que acaba de crear, está disponible en el [administrador de ubicaciones](/help/components/locations/locations-manager.md).

   +++

1. En la sección [!UICONTROL **Definiciones de columnas de datos**], seleccione la última plantilla de [!UICONTROL **Todas las columnas de Adobe**] en el menú desplegable y, a continuación, complete los campos siguientes:

   | Campo | Función |
   |---------|----------|
   | [!UICONTROL **Quitar caracteres de escape**] | Al recopilar datos, algunos caracteres (como las líneas nuevas) pueden causar problemas. Marque esta casilla si desea eliminar estos caracteres de los archivos de fuente. |
   | [!UICONTROL **Formato de compresión**] | Tipo de compresión utilizado. **Gzip** genera archivos en formato `.tar.gz`. **Zip** genera archivos en formato `.zip`. |
   | [!UICONTROL **Tipo de paquete**] | Seleccione [!UICONTROL **Varios archivos**] para la mayoría de las fuentes de datos. Esta opción pagina los datos en fragmentos de 2 GB sin comprimir. (Si se selecciona la opción [!UICONTROL **Varios archivos**] y los datos sin comprimir de la ventana de informes ocupan menos de 2 GB, se envía un solo archivo). Seleccionar **Un solo archivo** genera el archivo `hit_data.tsv` en un único archivo potencialmente masivo. |
   | [!UICONTROL **Manifiesto**] | Determina si Adobe debe entregar un [archivo de manifiesto](c-df-contents/datafeeds-contents.md#feed-manifest) al destino cuando no se recopilen datos para un intervalo de fuente. Si selecciona **Archivo de manifiesto**, recibirá un archivo de manifiesto similar al siguiente cuando no se recopilen datos:<p>`text`</p><p>`Datafeed-Manifest-Version: 1.0`</p><p>`Lookup-Files: 0`</p><p>`Data-Files: 0`</p><p> `Total-Records: 0`</p> |
   | [!UICONTROL **Plantillas de columna**] | Al crear muchas fuentes de datos, Adobe recomienda crear una plantilla de columna. La selección de una plantilla de columna incluye automáticamente las columnas especificadas en la plantilla. Adobe también proporciona varias plantillas de forma predeterminada. |
   | [!UICONTROL **Columnas disponibles**] | Todas las columnas de datos disponibles en Adobe Analytics. Haga clic en [!UICONTROL Agregar todo] para incluir todas las columnas en una fuente de datos. |
   | [!UICONTROL **Columnas incluidas**] | Columnas que se incluyen en una fuente de datos. Haga clic en [!UICONTROL Eliminar todo] para eliminar todas las columnas de una fuente de datos. |
   | [!UICONTROL **Descargar CSV**] | Descarga un archivo CSV que contiene todas las columnas incluidas. |

1. Seleccione [!UICONTROL **Guardar**] en la parte superior derecha.

   El procesamiento de datos históricos comienza inmediatamente. Cuando los datos terminan de procesarse durante un día, el archivo se envía al destino configurado.

   Para obtener información sobre cómo tener acceso a la fuente de datos y comprender mejor su contenido, vea [Contenido de la fuente de datos: información general](/help/export/analytics-data-feed/c-df-contents/datafeeds-contents.md).

## Destinos heredados

>[!IMPORTANT]
>
>Los destinos descritos en esta sección son heredados y no se recomiendan. En su lugar, utilice uno de los siguientes destinos al crear una fuente de datos: Amazon S3, Google Cloud Platform, Azure RBAC o Azure SAS. Consulte [Crear y configurar una fuente de datos](#create-and-configure-a-data-feed) para obtener información detallada sobre cada uno de estos destinos recomendados.


La siguiente información proporciona información de configuración para cada uno de los destinos heredados:

### FTP

Los datos de las fuentes de datos se pueden entregar en una ubicación de Adobe o de FTP alojado por el cliente. Se necesita un host FTP, un nombre de usuario y una contraseña. Utilice el campo de ruta para colocar los archivos de fuente en una carpeta. Las carpetas ya deben existir, las fuentes generan un error si la ruta de acceso especificada no existe.

Utilice la siguiente información al completar los campos disponibles:

* [!UICONTROL **Host**]: escriba la dirección URL de destino de FTP que desee. Por ejemplo, `ftp://ftp.omniture.com`.
* [!UICONTROL **Ruta**]: se puede dejar en blanco
* [!UICONTROL **Nombre de usuario**]: introduzca el nombre de usuario para iniciar sesión en el sitio FTP.
* [!UICONTROL **Contraseña y confirmar contraseña**]: introduzca la contraseña para iniciar sesión en el sitio FTP.

### SFTP

La compatibilidad con SFTP para fuentes de datos está disponible. Se necesita un host SFTP, un nombre de usuario y el sitio de destino para contener una clave pública RSA o DSA válida. Puede descargar la clave pública adecuada al crear la fuente.

### S3

Puede enviar fuentes directamente a los bloques de Amazon S3. Este tipo de destino requiere un nombre de contenedor, un ID de clave de acceso y una clave secreta. Consulte los [requisitos de nomenclatura de contenedor de Amazon S3](https://docs.aws.amazon.com/es_es/awscloudtrail/latest/userguide/cloudtrail-s3-bucket-naming-requirements.html) en los documentos de Amazon S3 para obtener más información.

El usuario que proporcione para cargar fuentes de datos debe tener los siguientes [permisos](https://docs.aws.amazon.com/es_es/AmazonS3/latest/API/API_Operations_Amazon_Simple_Storage_Service.html):

* s3:GetObject
* s3:PutObject
* s3:PutObjectAcl

  >[!NOTE]
  >
  >Para cada carga en un contenedor de Amazon S3, [!DNL Analytics] agrega el propietario del contenedor a la ACL BucketOwnerFullControl, independientemente de si el contenedor tiene una directiva que la requiera. Para obtener más información, consulte &quot;[¿Cuál es la configuración de BucketOwnerFullControl para las fuentes de datos de Amazon S3?](df-faq.md#BucketOwnerFullControl)&quot;

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

Las fuentes de datos admiten destinos de Azure Blob. Se necesita un contenedor, una cuenta y una clave. Amazon cifra automáticamente los datos en reposo. Cuando se descarguen los datos, estos se descifrarán automáticamente. Consulte [Creación de una cuenta de almacenamiento](https://docs.microsoft.com/es-es/azure/storage/common/storage-quickstart-create-account?tabs=azure-portal#view-and-copy-storage-access-keys) en los documentos de Microsoft Azure para obtener más información.

>[!NOTE]
>
>Debe implementar su propio proceso para administrar el espacio en disco en el destino de la fuente. Adobe no elimina ningún dato del servidor.

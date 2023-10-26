---
description: Configure la cuenta de importación y la ubicación de la nube en la que se pueden cargar los datos de clasificación
keywords: Analysis Workspace
title: Configurar cuentas de importación en la nube
feature: Classifications
exl-id: 40d3d3f1-1047-4c37-8caf-6b0aabaa590a
source-git-commit: c43d7bbdad0ad0265e038ee273c74bec136f1c72
workflow-type: tm+mt
source-wordcount: '901'
ht-degree: 5%

---

# Configurar cuentas de importación en la nube

<!-- This page is almost duplicated with the "Configure cloud export locations" article in CJA. Differences are that Snowflake isn't supported here and there is a Suffix field for each account type. -->

Para poder importar datos de clasificación de Adobe Analytics desde un destino de nube, debe agregar y configurar la cuenta y la ubicación dentro de esa cuenta donde desea que se recopilen los datos de clasificación.

Este proceso consiste en agregar y configurar la cuenta (como el ARN de la función de Amazon S3, Google Cloud Platform, etc.) tal como se describe en este artículo y, a continuación, agregar y configurar la ubicación dentro de esa cuenta (como una carpeta dentro de la cuenta) tal como se describe en [Configurar ubicaciones de importación en la nube](/help/components/locations/configure-import-locations.md).

Debe configurar Adobe Analytics con la información necesaria para acceder a su cuenta de destino en la nube.

Para configurar una cuenta de importación de nube:

1. En Adobe Analytics, seleccione [!UICONTROL **Componentes**] > [!UICONTROL **Ubicaciones**].
1. En el [!UICONTROL Ubicaciones] , seleccione la [!UICONTROL **Credenciales de ubicación**] pestaña.
1. Seleccionar [!UICONTROL **Añadir cuenta**]. <!-- add screenshot? -->

   Se muestra el cuadro de diálogo Agregar cuenta.
1. Especifique la siguiente información: |Campo Función | | |---------|----------| | [!UICONTROL **Nombre de cuenta de ubicación**] | El nombre de la cuenta de ubicación. Este nombre aparece al crear una ubicación | | [!UICONTROL **Descripción de cuenta de ubicación**] | Proporcione una breve descripción de la cuenta para diferenciarla de otras cuentas del mismo tipo de cuenta. | | [!UICONTROL **Tipo de cuenta**] | Seleccione el tipo de cuenta en la nube. Recomendamos tener una sola cuenta para cada tipo de cuenta, con varias ubicaciones según sea necesario dentro de esa cuenta. |
1. En el [!UICONTROL **Propiedades de cuenta**] , especifique la información específica del tipo de cuenta que ha seleccionado.

   Para obtener instrucciones de configuración, expanda la sección siguiente que corresponde a la variable [!UICONTROL **Tipo de cuenta**] que ha seleccionado.

   +++Amazon S3 Role ARN

   Especifique la siguiente información para configurar una cuenta ARN de la función Amazon S3:

   | Campo | Función |
   |---------|----------|
   | [!UICONTROL **ARN de función**] | Debe proporcionar un ARN de la función (nombre de recurso de Amazon) que el Adobe pueda utilizar para obtener acceso a la cuenta de Amazon S3. Para ello, se crea una directiva de permisos de IAM para la cuenta de origen, se adjunta la directiva a un usuario y, a continuación, se crea un rol para la cuenta de destino. Para obtener información específica, consulte [esta documentación de AWS](https://aws.amazon.com/premiumsupport/knowledge-center/cross-account-access-iam/). |

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
   | [!UICONTROL **ID de la aplicación**] | Copie este ID de la aplicación de Azure que ha creado. En Microsoft Azure, esta información se encuentra en **Información general** dentro de la aplicación. Para obtener más información, consulte la [Documentación de Microsoft Azure sobre cómo registrar una aplicación con Microsoft identity platform](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
   | [!UICONTROL **ID de inquilino**] | Copie este ID de la aplicación de Azure que ha creado. En Microsoft Azure, esta información se encuentra en **Información general** dentro de la aplicación. Para obtener más información, consulte la [Documentación de Microsoft Azure sobre cómo registrar una aplicación con Microsoft identity platform](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
   | [!UICONTROL **URI de almacén de claves**] | <p>Ruta al token SAS en Azure Key Vault.  Para configurar Azure SAS, debe almacenar un token SAS como secreto mediante Azure Key Vault. Para obtener más información, consulte [Documentación de Microsoft Azure sobre cómo establecer y recuperar un secreto de Azure Key Vault](https://learn.microsoft.com/en-us/azure/key-vault/secrets/quick-create-portal?source=recommendations).</p><p>Una vez creado el URI del almacén de claves, agregue una directiva de acceso en el almacén de claves para conceder permiso a la aplicación de Azure que ha creado. Para obtener más información, consulte [Documentación de Microsoft Azure sobre cómo asignar una directiva de acceso de Key Vault](https://learn.microsoft.com/en-us/azure/key-vault/general/assign-access-policy?tabs=azure-portal).</p> |
   | [!UICONTROL **Nombre secreto del almacén de claves**] | El nombre secreto que creó al agregar el secreto a Azure Key Vault. En Microsoft Azure, esta información se encuentra en Key Vault que ha creado, en **Key Vault** páginas de configuración. Para obtener más información, consulte [Documentación de Microsoft Azure sobre cómo establecer y recuperar un secreto de Azure Key Vault](https://learn.microsoft.com/en-us/azure/key-vault/secrets/quick-create-portal?source=recommendations). |
   | [!UICONTROL **Secreto de cuenta de ubicación**] | Copie el secreto de la aplicación de Azure que ha creado. En Microsoft Azure, esta información se encuentra en **Certificados y secretos** dentro de la aplicación. Para obtener más información, consulte la [Documentación de Microsoft Azure sobre cómo registrar una aplicación con Microsoft identity platform](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |

   {style="table-layout:auto"}

+++

   +++Azure RBAC

   Especifique la siguiente información para configurar una cuenta RBAC de Azure:

   | Campo | Función |
   |---------|----------|
   | [!UICONTROL **ID de la aplicación**] | Copie este ID de la aplicación de Azure que ha creado. En Microsoft Azure, esta información se encuentra en **Información general** dentro de la aplicación. Para obtener más información, consulte la [Documentación de Microsoft Azure sobre cómo registrar una aplicación con Microsoft identity platform](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
   | [!UICONTROL **ID de inquilino**] | Copie este ID de la aplicación de Azure que ha creado. En Microsoft Azure, esta información se encuentra en **Información general** dentro de la aplicación. Para obtener más información, consulte la [Documentación de Microsoft Azure sobre cómo registrar una aplicación con Microsoft identity platform](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
   | [!UICONTROL **Secreto de cuenta de ubicación**] | Copie el secreto de la aplicación de Azure que ha creado. En Microsoft Azure, esta información se encuentra en **Certificados y secretos** dentro de la aplicación. Para obtener más información, consulte la [Documentación de Microsoft Azure sobre cómo registrar una aplicación con Microsoft identity platform](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |

   {style="table-layout:auto"}

+++

1. Seleccione [!UICONTROL **Guardar**].

1. Continuar con [Configurar ubicaciones de importación en la nube](/help/components/locations/configure-import-locations.md).

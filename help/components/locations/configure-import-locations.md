---
description: Configure la cuenta de importación y la ubicación de la nube en la que se pueden cargar los datos de clasificación
keywords: Analysis Workspace
title: Configurar ubicaciones de importación en la nube
feature: Classifications
exl-id: 55179868-6228-44ff-835c-f4a7b38e929b
source-git-commit: f71b80dce9d447c431130901d86947d23e28d378
workflow-type: tm+mt
source-wordcount: '584'
ht-degree: 7%

---

# Configurar ubicaciones de importación en la nube

<!-- This page is almost duplicated with the "Configure cloud export locations" article in CJA. Differences are that Snowflake isn't supported here and there is a Suffix field for each account type. -->

Para poder importar datos de clasificación de Adobe Analytics desde un destino de nube, debe agregar y configurar la cuenta y la ubicación dentro de esa cuenta donde desea que se recopilen los datos de clasificación.

Este proceso consiste en añadir y configurar la cuenta (como el ARN de la función de Amazon S3, Google Cloud Platform, etc.) y la ubicación dentro de la cuenta (como una carpeta dentro de la cuenta).

Para configurar una ubicación de importación en la nube:

1. Debe agregar una cuenta antes de agregar una ubicación. Si aún no lo ha hecho, agregue una cuenta como se describe en [Configurar cuentas de importación en la nube](/help/components/locations/configure-import-accounts.md).
1. En Adobe Analytics, seleccione [!UICONTROL **Componentes**] > [!UICONTROL **Ubicaciones**].
1. En el [!UICONTROL Ubicaciones] , seleccione la [!UICONTROL **Ubicaciones**] pestaña.
1. Seleccionar [!UICONTROL **Añadir ubicación**]. <!-- add screenshot? -->

   Se muestra el cuadro de diálogo Ubicación.
1. Especifique la siguiente información: |Campo Función | | |---------|----------| | [!UICONTROL **Nombre**] | El nombre de la ubicación.  | | [!UICONTROL **Descripción**] | Proporcione una breve descripción de la cuenta para diferenciarla de otras cuentas del mismo tipo de cuenta. | | [!UICONTROL **Cuenta de ubicación**] | Seleccione la cuenta de ubicación que creó en [Agregar una cuenta](#add-an-account). |

1. En el [!UICONTROL **Propiedades de ubicación**] , especifique información específica para el tipo de cuenta de su cuenta de ubicación.

   Para obtener instrucciones de configuración, expanda la sección siguiente que corresponde al tipo de cuenta seleccionado en la [!UICONTROL **Cuentas de ubicación**] field.

   +++Amazon S3 Role ARN

   Especifique la siguiente información para configurar una ubicación ARN de la función Amazon S3:

   | Campo | Función |
   |---------|----------|
   | [!UICONTROL **Nombre del segmento**] | El bloque de su cuenta de Amazon S3 al que desea enviar los datos de Adobe Analytics. |
   | [!UICONTROL **Prefijo clave**] | La carpeta dentro del bloque en el que desea colocar los datos. Especifique un nombre de carpeta y, a continuación, agregue una barra invertida después del nombre para crear la carpeta. Por ejemplo, folder_name/ |

   {style="table-layout:auto"}

+++

   +++Google Cloud Platform

   Especifique la siguiente información para configurar una ubicación de Google Cloud Platform:

   | Campo | Función |
   |---------|----------|
   | [!UICONTROL **Nombre del segmento**] | El bloque de su cuenta de GCP al que desea enviar los datos de Adobe Analytics. Asegúrese de haber concedido permiso al principal proporcionado por el Adobe para cargar archivos en este bloque. |
   | [!UICONTROL **Prefijo clave**] | La carpeta dentro del bloque en el que desea colocar los datos. Especifique un nombre de carpeta y, a continuación, agregue una barra invertida después del nombre para crear la carpeta. Por ejemplo, folder_name/ |

   {style="table-layout:auto"}

+++

   +++Azure SAS

   Especifique la siguiente información para configurar una ubicación SAS de Azure:

   | Campo | Función |
   |---------|----------|
   | [!UICONTROL **Nombre de contenedor**] | El contenedor de la cuenta que especificó a donde desea enviar los datos de Adobe Analytics. |
   | [!UICONTROL **Prefijo clave**] | Carpeta dentro del contenedor en la que desea colocar los datos. Especifique un nombre de carpeta y, a continuación, agregue una barra invertida después del nombre para crear la carpeta. Por ejemplo, `folder_name/` |

   {style="table-layout:auto"}

+++

   +++Azure RBAC

   Especifique la siguiente información para configurar una ubicación RBAC de Azure:

   | Campo | Función |
   |---------|----------|
   | [!UICONTROL **Nombre de contenedor**] | El contenedor de la cuenta que especificó a donde desea enviar los datos de Adobe Analytics. Asegúrese de conceder permisos para cargar archivos en la aplicación de Azure que creó anteriormente. |
   | [!UICONTROL **Prefijo clave**] | Carpeta dentro del contenedor en la que desea colocar los datos. Especifique un nombre de carpeta y, a continuación, agregue una barra invertida después del nombre para crear la carpeta. Por ejemplo, `folder_name/` |
   | [!UICONTROL **Nombre de la cuenta**] | La cuenta de almacenamiento de Azure. |

   {style="table-layout:auto"}

+++

1. Seleccione [!UICONTROL **Guardar**].

   Ahora puede importar datos desde la cuenta y la ubicación configuradas.

   Los datos no se eliminan del destino de nube una vez importados.

   >[!NOTE]
   >
   >   Si ha utilizado anteriormente [FTP para importar clasificaciones](/help/components/classifications/importer/c-uploading-saint-data-files-via-ftp.md) a Adobe Analytics, tenía que cargar un archivo FIN. Este archivo FIN no es necesario al importar desde cuentas en la nube.


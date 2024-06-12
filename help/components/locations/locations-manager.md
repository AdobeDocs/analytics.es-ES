---
description: Configure la cuenta de importación y la ubicación de la nube en la que se pueden cargar los datos de clasificación
keywords: Analysis Workspace
title: Administrador de ubicaciones
feature: Classifications
exl-id: ace70568-220a-44e8-8e5f-f73002b9e2a2
source-git-commit: c42ad8d3e0c21cc1fb13f9a8993aca4825286d4f
workflow-type: tm+mt
source-wordcount: '1476'
ht-degree: 1%

---

# Administrador de ubicaciones

El Administrador de ubicaciones le permite ver, crear, editar o eliminar cuentas y ubicaciones. Pueden utilizarse para cualquiera de los siguientes fines:

* Exportación de archivos mediante [Fuentes de datos](/help/export/analytics-data-feed/create-feed.md)
* Exportación de informes mediante [Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md)
* Importación de esquemas mediante [Conjuntos de clasificaciones](/help/components/classifications/sets/overview.md)

## Ver, filtrar y buscar ubicaciones

El administrador de ubicaciones le permite ver cualquier ubicación que haya creado o cualquier ubicación que se comparta con la organización. Los administradores del sistema pueden ver las ubicaciones creadas por todos los usuarios, independientemente de si están compartidas o no.

1. Para acceder al Administrador de ubicaciones en Adobe Analytics, seleccione **[!UICONTROL Componentes]** > **[!UICONTROL Ubicaciones]**.

1. (Condicional) Si es administrador del sistema, puede habilitar la variable [!UICONTROL **Ver ubicaciones para todos los usuarios**] para ver las ubicaciones creadas por todos los usuarios de su organización. <!-- Maybe add a screenshot? This is new functionality -->

1. Filtre o busque la lista de ubicaciones:

   * **Filtro:** Seleccione el icono Filtro para filtrar la lista de ubicaciones.

     Puede filtrar las ubicaciones por **[!UICONTROL Tipo de ubicación]**, **[!UICONTROL Cuenta]**, o **[!UICONTROL Creado por]**.

     ![Filtros de ubicaciones](assets/locations-filters.png)

   * **Buscar:** En el campo de búsqueda, empiece a escribir el nombre de la ubicación que desea ver. Los resultados se filtran a medida que escribe. Se buscan las siguientes columnas: **Nombre de ubicación**, **Tipo de ubicación**, **Cuenta**, y **Creado por**.

1. (Opcional) Si tiene más de 1000 ubicaciones, solo se muestran las 1000 primeras. Seleccionar [!UICONTROL **Cargar más**] para cargar 1.000 ubicaciones más.

## Configurar columnas en el Administrador de ubicaciones

Las siguientes columnas están disponibles en el administrador Ubicaciones. Para personalizar las columnas que se muestran en la tabla, seleccione la **Personalizar tabla** icono ![Icono Personalizar tabla](assets/customize-table-icon.png).

* **[!UICONTROL Nombre de ubicación]**: nombre de la ubicación. Seleccione el menú de 3 puntos junto al nombre de una ubicación para [editar la ubicación](/help/components/locations/configure-import-locations.md) o elimínelo.
* **[!UICONTROL Tipo de ubicación]**: el tipo de cuenta asociada con la ubicación.
* **[!UICONTROL Cuenta]**: La cuenta específica asociada con la ubicación.
* **Aplicación**: el tipo de aplicación con la que se puede utilizar la ubicación (como fuentes de datos, Data Warehouse o conjuntos de clasificaciones).
* **[!UICONTROL Último uso]**: La fecha en la que se utilizó la ubicación por última vez.
* **[!UICONTROL Creado por]**: el usuario que creó la ubicación.
* **[!UICONTROL Fecha de creación]**: La fecha en la que se creó la ubicación.

## Creación y administración de ubicaciones

Puede crear, editar y eliminar ubicaciones.

### Crear una ubicación

Para obtener información sobre cómo crear una ubicación, consulte [Configurar ubicaciones de importación y exportación de la nube](/help/components/locations/configure-import-locations.md).

<!-- Do I need to add some steps here about how to create a location and then assign that location to be used with DF, DW, or Classifications sets? Need to hear back from Ron and team whether we are including this functionality -->

### Editar una ubicación

Una ubicación solo la puede editar el usuario que la creó o un administrador del sistema.

Para obtener información sobre cómo editar una ubicación, consulte [Configurar ubicaciones de importación y exportación de la nube](/help/components/locations/configure-import-locations.md).

### Eliminar una ubicación

>[!IMPORTANT]
>
>Si se elimina una ubicación, cualquier archivo de fuente de datos, informe de Data Warehouse o esquema de conjunto de clasificaciones asociado a la ubicación eliminada generará un error la próxima vez que se utilicen.
>
>Si elimina una ubicación, debería [editar las fuentes de datos](/help/export/analytics-data-feed/create-feed.md), [informes de Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md), y [Esquemas de conjuntos de clasificaciones](/help/components/classifications/sets/manage/schema.md) para utilizar una ubicación en funcionamiento.

Una ubicación solo la puede eliminar el usuario que la creó o un administrador del sistema.

Para eliminar una ubicación en el Administrador de ubicaciones en Adobe Analytics:

1. Seleccionar **[!UICONTROL Componentes]** > **[!UICONTROL Ubicaciones]**, luego seleccione la [!UICONTROL **Ubicaciones**] pestaña.

1. Seleccione el menú de 3 puntos en la [!UICONTROL **Nombre de ubicación**] para la ubicación que desea eliminar.

1. Seleccione [!UICONTROL **Eliminar**].

## Creación y administración de cuentas

Puede crear, editar y eliminar cuentas.

### Crear una cuenta

Para obtener información sobre cómo crear una cuenta, consulte [Configuración de cuentas de importación y exportación de nube](/help/components/locations/configure-import-accounts.md).

### Editar una cuenta

Solamente el usuario que la creó o un administrador del sistema pueden editar una cuenta.

Para obtener información sobre cómo editar una cuenta, consulte [Configuración de cuentas de importación y exportación de nube](/help/components/locations/configure-import-accounts.md).

### Ver claves de cuenta

Después de crear una cuenta, puede ver todas las claves de cuenta asociadas a ella. Es posible que deba ver esta información si no terminó de configurar la cuenta con su proveedor de la nube al [configuró originalmente la cuenta](/help/components/locations/configure-import-accounts.md).

Para ver las claves asociadas a una cuenta de exportación:

1. En Adobe Analytics, seleccione **[!UICONTROL Componentes]** > **[!UICONTROL Ubicaciones]**, luego seleccione la [!UICONTROL **Cuentas de ubicación**] pestaña.

1. (Condicional) Si es administrador del sistema, puede habilitar la variable [!UICONTROL **Ver ubicaciones para todos los usuarios**] para ver las ubicaciones creadas por todos los usuarios de su organización. <!-- Maybe add a screenshot? This is new functionality -->

1. Seleccione el icono de 3 puntos en la cuenta que desee editar y, a continuación, seleccione [!UICONTROL **Claves de cuenta**].

### Eliminación de una cuenta

>[!IMPORTANT]
>
>Las cuentas solo se pueden eliminar si no hay ninguna ubicación que las utilice. Antes de eliminar una cuenta, primero debe eliminar las ubicaciones de la cuenta, tal como se describe en [Eliminar una ubicación](#delete-a-location).

Solamente el usuario que la creó o un administrador del sistema pueden eliminar una cuenta.

Para eliminar una cuenta:

1. En Adobe Analytics, seleccione **[!UICONTROL Componentes]** > **[!UICONTROL Ubicaciones]**, luego seleccione la [!UICONTROL **Cuentas de ubicación**] pestaña.

1. (Condicional) Si es administrador del sistema, puede habilitar la variable [!UICONTROL **Ver cuentas de todos los usuarios**] para ver las ubicaciones creadas por todos los usuarios de su organización.

1. Seleccione el icono de 3 puntos en la cuenta que desee editar y, a continuación, seleccione [!UICONTROL **Eliminar cuenta**]

## Configuración en toda la empresa (solo administradores)

{{release-limited-testing-section}}

Los administradores del sistema pueden restringir la creación de cuentas y ubicaciones por parte de los usuarios, o bien pueden limitar los tipos de cuentas que los usuarios pueden crear y utilizar.

![Pestaña Configuración de administración](assets/locations-admin-settings.png)

### Configurar si los usuarios pueden crear y editar cuentas

De forma predeterminada, todos los usuarios de la organización pueden crear cuentas y editar las que creen en su entorno de Adobe Analytics, tal como se describe en [configuración de cuentas de importación y exportación de cloud](/help/components/locations/configure-import-accounts.md).

Puede restringir la creación de cuentas de los usuarios. Cuando lo haga, los usuarios podrán seguir utilizando las cuentas que hayan creado, pero ya no podrán editarlas. Puede eliminar las cuentas que hayan creado los usuarios, tal como se describe en [Eliminación de una cuenta](#delete-an-account).

Para restringir la creación y edición de cuentas a todos los usuarios:

1. En Adobe Analytics, seleccione **[!UICONTROL Componentes]** > **[!UICONTROL Ubicaciones]**, luego seleccione la [!UICONTROL **Configuración de administración**] pestaña.

1. En el [!UICONTROL **Cuentas de ubicaciones**] , anule la selección de la opción, [!UICONTROL **Permitir a los usuarios crear y administrar cuentas de ubicación**].

1. Seleccione [!UICONTROL **Guardar**].

1. (Opcional) Elimine las cuentas que hayan creado los usuarios y que ya no desee que utilicen, tal como se describe en [Eliminación de una cuenta](#delete-an-account).

### Configurar si los usuarios pueden crear y editar ubicaciones

De forma predeterminada, todos los usuarios de la organización pueden crear ubicaciones y editar las que creen en su entorno de Adobe Analytics, tal como se describe en [configuración de ubicaciones de importación y exportación de cloud](/help/components/locations/configure-import-locations.md).

Puede restringir la creación de ubicaciones por parte de los usuarios. Cuando lo haga, los usuarios podrán seguir utilizando cualquier ubicación que ya hayan creado, pero ya no podrán editarlas. Puede eliminar las ubicaciones que hayan creado los usuarios, tal como se describe en [Eliminar ubicaciones](#delete-a-location).

Para restringir la creación y edición de ubicaciones a todos los usuarios:

1. En Adobe Analytics, seleccione **[!UICONTROL Componentes]** > **[!UICONTROL Ubicaciones]**, luego seleccione la [!UICONTROL **Configuración de administración**] pestaña.

1. En el [!UICONTROL **Ubicaciones**] , anule la selección de la opción, [!UICONTROL **Permitir a los usuarios crear y administrar ubicaciones**].

1. Seleccione [!UICONTROL **Guardar**].

1. (Opcional) Elimine las ubicaciones que hayan creado los usuarios y que ya no desee que utilicen, tal como se describe en [Eliminar una ubicación](#delete-a-location).

### Limitar los tipos de cuentas que los usuarios pueden crear y utilizar

Puede limitar los tipos de cuenta que ven los usuarios en las siguientes circunstancias:

* Cuándo [creación de nuevas cuentas](/help/components/locations/configure-import-accounts.md).

* Al elegir qué cuentas utilizar al exportar archivos mediante [Fuentes de datos](/help/export/analytics-data-feed/create-feed.md), exportación de informes mediante [Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md)o importar esquemas utilizando [Conjuntos de clasificaciones](/help/components/classifications/sets/overview.md).

Al limitar los tipos de cuenta como se describe en esta sección, los usuarios ya no podrán ver las cuentas del tipo que limite. Esto significa que no se pueden crear nuevas cuentas de ese tipo y que no se pueden usar las cuentas existentes de ese tipo al crear fuentes de datos, Data Warehouse o conjuntos de clasificaciones.

Sin embargo, las cuentas existentes configuradas para exportaciones programadas deben eliminarse si desea restringir su uso.

#### Asegúrese de que las cuentas no se utilicen para las exportaciones programadas

Al limitar los tipos de cuenta, las cuentas existentes se ocultan, no se eliminan.

Si las programaciones ya están configuradas para enviar datos a una cuenta del tipo que usted limite, las programaciones seguirán ejecutándose incluso después de limitar el tipo de cuenta y los datos se seguirán enviando a la cuenta.  Por ejemplo, si una fuente de datos está programada para enviar datos a un tipo de cuenta que usted limite, la programación seguirá ejecutándose.

Si necesita asegurarse de que las cuentas de un tipo determinado no se utilizan en las exportaciones programadas, puede eliminarlas antes que usted [limitar los tipos de cuenta](#limit-the-account-types-that-are-available-to-users).

Para eliminar cuentas:

1. Busque las cuentas del tipo de cuenta que planea limitar y que se están utilizando para exportaciones programadas.

1. Elimine las cuentas tal como se describe en [Eliminación de una cuenta](#delete-an-account).

1. Continúe con la siguiente sección, [Limitar los tipos de cuenta disponibles para los usuarios](#limit-the-account-types-that-are-available-to-users).

#### Limitar los tipos de cuenta disponibles para los usuarios

Para limitar los tipos de cuentas disponibles para los usuarios al crear y utilizar cuentas:

1. En Adobe Analytics, seleccione **[!UICONTROL Componentes]** > **[!UICONTROL Ubicaciones]**, luego seleccione la [!UICONTROL **Configuración de administración**] pestaña.

1. Busque el [!UICONTROL **Tipos de cuenta permitidos**] sección.

   Los siguientes tipos de cuenta están disponibles para los usuarios de forma predeterminada. Anule la selección de cualquiera de estos tipos de cuenta para impedir que los usuarios los utilicen.

   * [!UICONTROL **ARN de la función de Amazon S3**]

   * [!UICONTROL **Google Cloud Platform**]

   * [!UICONTROL **Azure SAS**]

   * [!UICONTROL **Azure RBAC**]

   * [!UICONTROL **Correo electrónico**]

   * Tipos de cuentas heredadas, incluidos [!UICONTROL **Amazon S3**], [!UICONTROL **Azure**], [!UICONTROL **FTP**], y [!UICONTROL **SFTP**]

1. Seleccione [!UICONTROL **Guardar**].



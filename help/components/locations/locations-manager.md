---
description: Configure la cuenta de importación y la ubicación de la nube en la que se pueden cargar los datos de clasificación
keywords: Analysis Workspace
title: Administrador de ubicaciones
feature: Classifications
exl-id: ace70568-220a-44e8-8e5f-f73002b9e2a2
source-git-commit: 273fea86cde8880d9c9e03ac9c6a99b75f70f6cd
workflow-type: tm+mt
source-wordcount: '648'
ht-degree: 1%

---

# Administrador de ubicaciones

El Administrador de ubicaciones le permite ver, crear, editar o eliminar cuentas y ubicaciones. Pueden utilizarse para cualquiera de los siguientes fines:

* Exportación de archivos mediante [Fuentes de datos](/help/export/analytics-data-feed/create-feed.md)
* Exportación de informes mediante [Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md)
* Importación de esquemas mediante [Conjuntos de clasificaciones](/help/components/classifications/sets/overview.md)

## Ver, filtrar y buscar ubicaciones

El Administrador de ubicaciones le permite ver cualquier ubicación que haya creado. Los administradores del sistema pueden ver las ubicaciones creadas por todos los usuarios.

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

Para obtener información sobre cómo editar una ubicación, consulte [Configurar ubicaciones de importación y exportación de la nube](/help/components/locations/configure-import-locations.md).

### Eliminar una ubicación

>[!IMPORTANT]
>
>Si se elimina una ubicación, cualquier archivo de fuente de datos, informe de Data Warehouse o esquema de conjunto de clasificaciones asociado a la ubicación eliminada generará un error la próxima vez que se utilicen.
>
>Si elimina una ubicación, debería [editar las fuentes de datos](/help/export/analytics-data-feed/create-feed.md), [informes de Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md), y [Esquemas de conjuntos de clasificaciones](/help/components/classifications/sets/manage/schema.md) para utilizar una ubicación en funcionamiento.

Para eliminar una ubicación en el Administrador de ubicaciones en Adobe Analytics:

1. Seleccionar **[!UICONTROL Componentes]** > **[!UICONTROL Ubicaciones]**, luego seleccione la [!UICONTROL **Ubicaciones**] pestaña.

1. Seleccione el menú de 3 puntos en la [!UICONTROL **Nombre de ubicación**] para la ubicación que desea eliminar.

1. Seleccione [!UICONTROL **Eliminar**].

## Editar una cuenta

1. Para editar cuentas en el Administrador de ubicaciones en Adobe Analytics, seleccione **[!UICONTROL Componentes]** > **[!UICONTROL Ubicaciones]**, luego seleccione la [!UICONTROL **Cuentas de ubicación**] pestaña.

1. (Condicional) Si es administrador del sistema, puede habilitar la variable [!UICONTROL **Ver cuentas de todos los usuarios**] para ver las ubicaciones creadas por todos los usuarios de su organización. <!-- Maybe add a screenshot? This is new functionality -->


1. Seleccionar [!UICONTROL **Ver detalles**] en la cuenta que desee editar.

1. Realice los cambios que desee y seleccione [!UICONTROL **Guardar**].

## Ver claves de cuenta

Después de crear una cuenta, puede ver todas las claves de cuenta asociadas a ella. Es posible que deba ver esta información si no terminó de configurar la cuenta con su proveedor de la nube al [configuró originalmente la cuenta](/help/components/locations/configure-import-accounts.md).

Para ver las claves asociadas a una cuenta de exportación:

1. En Adobe Analytics, seleccione **[!UICONTROL Componentes]** > **[!UICONTROL Ubicaciones]**, luego seleccione la [!UICONTROL **Cuentas de ubicación**] pestaña.

1. Seleccione el icono de 3 puntos en la cuenta que desee editar y, a continuación, seleccione [!UICONTROL **Claves de cuenta**].

## Eliminación de una cuenta

1. En Adobe Analytics, seleccione **[!UICONTROL Componentes]** > **[!UICONTROL Ubicaciones]**, luego seleccione la [!UICONTROL **Cuentas de ubicación**] pestaña.

1. Seleccione el icono de 3 puntos en la cuenta que desee editar y, a continuación, seleccione [!UICONTROL **Eliminar cuenta**]

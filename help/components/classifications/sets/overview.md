---
title: Información general sobre los conjuntos de clasificación
description: Utilice los conjuntos de clasificaciones para administrar los datos de clasificación.
exl-id: a139b298-1188-42ce-b52f-c71e0ff7c4e3
feature: Classifications
source-git-commit: 66be48d0f41061d259cc53fb835ebd155294a710
workflow-type: tm+mt
source-wordcount: '333'
ht-degree: 84%

---

# Información general sobre los conjuntos de clasificación

Los conjuntos de clasificaciones proporcionan una interfaz única para administrar las clasificaciones y las reglas. Este flujo de trabajo combina el concepto de crear clasificaciones en la configuración del grupo de informes con el concepto de Importador de clasificaciones para proporcionar una interfaz más intuitiva para crear y administrar los datos de clasificación.

**[!UICONTROL Componentes]** > **[!UICONTROL Conjuntos de clasificaciones]**

Debe ser administrador de productos o pertenecer a un perfil de productos que contenga el elemento de permiso [!UICONTROL Herramientas de grupos de informes] > [!UICONTROL Clasificaciones] para ver este elemento de menú. Tenga en cuenta que mientras que las interfaces de administración de clasificaciones anteriores están en el menú [!UICONTROL Administrador], los conjuntos de clasificaciones están en el menú [!UICONTROL Componentes].

## Mejoras

La arquitectura back-end publicada con conjuntos de clasificación contiene varias mejoras notables:

* Reducción del tiempo de procesamiento (72 horas → 24 horas)
* Una IU rediseñada para administrar clasificaciones
* La opción de usar datos de clasificación en Adobe Experience Platform en el futuro mediante el [Conector de origen de Adobe Analytics para datos de clasificación](https://experienceleague.adobe.com/es/docs/experience-platform/sources/connectors/adobe-applications/classifications)

La arquitectura back-end publicada con conjuntos de clasificación también contiene varios cambios importantes:

* Al usar el explorador o la importación automatizada, “[!UICONTROL Sobrescribir en caso de conflicto]” siempre está habilitado.
* Al usar el explorador o la importación automatizada, ya no se admite la opción de exportar inmediatamente después de la importación. Las exportaciones deben iniciarse por separado.
* El punto final `GetDimensions` de la API de Analytics 2.0 ahora devuelve identificadores de cadena para clasificaciones en lugar de identificadores numéricos. Se pueden seguir utilizando identificadores numéricos, pero Adobe recomienda utilizar los nuevos identificadores de cadena siempre que sea posible. Los identificadores numéricos se pueden recuperar utilizando el parámetro de cadena de consulta `?expansion=hidden`.

>[!IMPORTANT]
>
>El rendimiento de los conjuntos de clasificaciones depende principalmente del número de valores de clave única que contienen datos. Adobe recomienda tener cuidado al tratar con variables que contienen grandes cantidades de valores únicos. Esta precaución se aplica especialmente cuando se combinan variables de varios grupos de informes y dimensiones en un único conjunto de clasificaciones.

Los conjuntos de clasificaciones constan de tres áreas principales:

* [**[!UICONTROL Administrador de conjuntos de clasificaciones]**](manage/set-manager.md): cree, edite y elimine conjuntos de clasificaciones.
* [**[!UICONTROL Administrador de trabajos de conjuntos de clasificaciones]**](job-manager.md): vea el estado de los trabajos de conjuntos de clasificaciones y descargue los archivos de exportación.
* [**[!UICONTROL Consolidaciones de conjuntos de clasificaciones]**](consolidations/manage.md): combine varios conjuntos de clasificaciones en uno solo.

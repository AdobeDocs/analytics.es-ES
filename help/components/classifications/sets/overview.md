---
title: Información general sobre conjuntos de clasificaciones
description: Utilice conjuntos de clasificaciones para administrar los datos de clasificación.
exl-id: a139b298-1188-42ce-b52f-c71e0ff7c4e3
source-git-commit: 05243d37d252274d88650566de049327ff2bd439
workflow-type: tm+mt
source-wordcount: '294'
ht-degree: 26%

---

# Información general sobre conjuntos de clasificaciones

Los conjuntos de clasificaciones proporcionan una interfaz única para administrar las clasificaciones y las reglas. Este flujo de trabajo combina el concepto de crear clasificaciones en la configuración del grupo de informes con el concepto de importador de clasificaciones para proporcionar una interfaz más intuitiva para crear y administrar los datos de clasificación.

**[!UICONTROL Componentes]** > **[!UICONTROL Conjuntos de clasificaciones]**

La arquitectura back-end lanzada con los conjuntos de clasificaciones contiene varias mejoras importantes:

* Menor tiempo de procesamiento (72 horas → 24 horas)
* La capacidad para utilizar la IU de conjuntos de clasificaciones
* La opción de usar datos de clasificación en Adobe Experience Platform en el futuro mediante el [Conector de origen de Adobe Analytics para datos de clasificación](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/classifications.html?lang=es)

La arquitectura back-end lanzada con los conjuntos de clasificaciones también contiene varios cambios importantes:

* Al utilizar el explorador o la importación automatizada, &#39;[!UICONTROL Sobrescribir en caso de conflicto]&#39; siempre está habilitado.
* Al utilizar el explorador o la importación automatizada, ya no se admite la opción de exportar inmediatamente después de la importación. Las exportaciones deben iniciarse por separado.
* El punto final `GetDimensions` de la API de Analytics 2.0 ahora devuelve identificadores de cadena para clasificaciones en lugar de identificadores numéricos. Se pueden seguir utilizando identificadores numéricos, pero Adobe recomienda utilizar los nuevos identificadores de cadena siempre que sea posible. Los identificadores numéricos se pueden recuperar utilizando el parámetro de cadena de consulta `?expansion=hidden`.

>[!IMPORTANT]
>
>El rendimiento de los conjuntos de clasificaciones depende principalmente del número de valores de clave única que contienen datos. Adobe recomienda tener cuidado al tratar con variables que contienen grandes cantidades de valores únicos. Esta precaución se aplica especialmente cuando se combinan variables de varios grupos de informes y dimensiones en un único conjunto de clasificaciones.

Los conjuntos de clasificaciones constan de tres áreas principales:

* [**[!UICONTROL Administrador de conjuntos de clasificaciones]**](manage/set-manager.md): cree, edite y elimine conjuntos de clasificaciones.
* [**[!UICONTROL Administrador de trabajos de conjuntos de clasificaciones]**](job-manager.md): vea el estado de los trabajos del conjunto de clasificaciones y descargue los archivos de exportación.
* [**[!UICONTROL Consolidación de conjuntos de clasificaciones]**](consolidations/manage.md): Combine varios conjuntos de clasificaciones en uno solo.

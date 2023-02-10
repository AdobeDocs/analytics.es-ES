---
title: Información general sobre los conjuntos de clasificaciones
description: Utilice los conjuntos de clasificaciones para administrar los datos de clasificación.
exl-id: a139b298-1188-42ce-b52f-c71e0ff7c4e3
source-git-commit: 2ba6ffc7f632975ca16fa02ee79d467d4d53f076
workflow-type: tm+mt
source-wordcount: '264'
ht-degree: 45%

---

# Información general sobre los conjuntos de clasificaciones

Los conjuntos de clasificaciones proporcionan una interfaz única para administrar las clasificaciones y las reglas. Este flujo de trabajo combina el concepto de crear clasificaciones en la configuración del grupo de informes con el concepto de Importador de clasificaciones para proporcionar una interfaz más intuitiva para crear y administrar los datos de clasificación.

**[!UICONTROL Componentes]** > **[!UICONTROL Conjuntos de clasificaciones]**

>[!NOTE]
>
>Los conjuntos de clasificaciones estarán disponibles para todos los clientes a los que se haya migrado su grupo de informes a la nueva arquitectura de clasificaciones. Para obtener más información, póngase en contacto con el Servicio de atención al cliente de Adobe o con su Administrador de cuentas.

La arquitectura back-end lanzada con Conjuntos de clasificaciones contiene varias mejoras notables:

* Reducción significativa del tiempo de procesamiento (72 horas → 24 horas)
* La capacidad de usar la IU de conjuntos de clasificaciones
* La opción de usar datos de clasificación en Adobe Experience Platform en el futuro mediante el [Conector de origen de Adobe Analytics para datos de clasificación](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/classifications.html)

La arquitectura back-end lanzada con Conjuntos de clasificaciones también contiene varios cambios importantes:

* Al usar el explorador o la importación mediante FTP, &#39;[!UICONTROL Sobrescribir en conflicto]&#39; siempre está habilitado.
* Al utilizar el explorador o la importación mediante FTP, ya no se admite la opción de exportar inmediatamente después de la importación. Las exportaciones deben iniciarse por separado.
* La API de Analytics 2.0 `GetDimensions` ahora devuelve identificadores de cadena para clasificaciones en lugar de identificadores numéricos. Se pueden seguir utilizando identificadores numéricos, pero Adobe recomienda utilizar los nuevos identificadores de cadena siempre que sea posible. Los identificadores numéricos se pueden recuperar utilizando la variable `?expansion=hidden` parámetro de cadena de consulta.


Los conjuntos de clasificaciones constan de dos áreas principales:

* [**[!UICONTROL Administrador de conjuntos de clasificaciones]**](set-manager.md): crear, editar y eliminar conjuntos de clasificaciones.
* [**[!UICONTROL Administrador de trabajos de conjuntos de clasificaciones]**](job-manager.md): vea el estado de los trabajos de conjuntos de clasificaciones y descargue los archivos de exportación.

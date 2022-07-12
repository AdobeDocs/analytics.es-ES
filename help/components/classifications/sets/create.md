---
title: Crear un conjunto de clasificaciones
description: Campos y descripciones disponibles al crear un conjunto de clasificaciones.
exl-id: 6d692d90-8cc7-4306-a780-58d03db45be8
source-git-commit: 3b0e2bbe531692f26ed118b1d2adc0b5ed28a9bf
workflow-type: tm+mt
source-wordcount: '191'
ht-degree: 100%

---

# Crear un conjunto de clasificaciones

Puede usar el Administrador de conjuntos de clasificaciones para crear un conjunto de clasificaciones.

>[!NOTE]
>
>Actualmente, esta funcionalidad está en versión limitada. Si desea acceder a esta funcionalidad, póngase en contacto con el servicio de atención al cliente de Adobe o con el administrador de cuentas, que podrán reenviar la solicitud al equipo de clasificaciones para que la solicite.

**[!UICONTROL Componentes]** > **[!UICONTROL Conjuntos de clasificaciones]** > **[!UICONTROL Conjuntos]** > **[!UICONTROL Agregar]**

Al crear un conjunto de clasificaciones, están disponibles los campos siguientes.

* **[!UICONTROL Nombre]**: Campo de texto utilizado para identificar el conjunto de clasificaciones. Este campo no se puede editar tras la creación, pero se puede cambiar el nombre más adelante.
* **[!UICONTROL Nombre de columna]**: Nombre de la dimensión de clasificación que desea crear. Este campo es el nombre de dimensión que se utiliza en Analysis Workspace y el nombre de columna al exportar datos de clasificación.
* **[!UICONTROL Tipo]**: Botones de radio que indican el tipo de clasificación. Las clasificaciones principales suelen usarse; Representación de clasificaciones de búsqueda [Subclasificaciones](../c-sub-classifications.md).
* **[!UICONTROL Suscripciones]** Grupo de informes y dimensión a los que se aplica este conjunto de clasificaciones. Se ha planificado la compatibilidad con varios grupos de informes.

![Crear un conjunto de clasificaciones](../assets/classification-set-create.png)

Si existe un conjunto de clasificaciones para un grupo de informes + variable, en su lugar se agrega la clasificación al esquema.

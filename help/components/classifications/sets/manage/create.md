---
title: Crear un conjunto de clasificación
description: Campos y descripciones disponibles al crear un conjunto de clasificaciones.
exl-id: 6d692d90-8cc7-4306-a780-58d03db45be8
feature: Classifications
source-git-commit: 811e321ce96aaefaeff691ed5969981a048d2c31
workflow-type: tm+mt
source-wordcount: '188'
ht-degree: 22%

---

# Crear un conjunto de clasificación

Puede usar el Administrador de conjuntos de clasificaciones para crear un conjunto de clasificaciones.

**[!UICONTROL Componentes]** > **[!UICONTROL Conjuntos de clasificaciones]** > **[!UICONTROL Conjuntos]** > **[!UICONTROL Agregar]**

Al crear un conjunto de clasificaciones, están disponibles los campos siguientes.

* **[!UICONTROL Nombre]**: Campo de texto utilizado para identificar el conjunto de clasificaciones. Este campo no se puede editar tras la creación, pero se puede cambiar el nombre más adelante.
* **[!UICONTROL Nombre de columna]**: El nombre de la primera dimensión de clasificación que desea crear. Este campo es el nombre de dimensión que se utiliza en Analysis Workspace y el nombre de columna al exportar datos de clasificación. Puede agregar más nombres de columna después de crear el conjunto de clasificaciones.
* **[!UICONTROL Tipo]**: Botones de radio que indican el tipo de clasificación. Las clasificaciones principales suelen usarse; Representación de clasificaciones de búsqueda [Subclasificaciones](../../c-sub-classifications.md).
* **[!UICONTROL Suscripciones]** Los grupos de informes y las dimensiones a los que se aplica este conjunto de clasificación. Puede agregar varias combinaciones de grupos de informes y dimensiones a un conjunto de clasificaciones.

![Crear un conjunto de clasificaciones](../../assets/classification-set-create.png)

Si existe un conjunto de clasificaciones para un grupo de informes + variable, en su lugar se agrega la clasificación al esquema. Una combinación de grupo de informes + variable determinada no puede pertenecer a varios conjuntos de clasificaciones.

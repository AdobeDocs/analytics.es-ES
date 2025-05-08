---
title: Crear un conjunto de clasificación
description: Campos y descripciones disponibles al crear un conjunto de clasificaciones.
exl-id: 6d692d90-8cc7-4306-a780-58d03db45be8
feature: Classifications
source-git-commit: a40f30bbe8fdbf98862c4c9a05341fb63962cdd1
workflow-type: tm+mt
source-wordcount: '287'
ht-degree: 8%

---

# Crear un conjunto de clasificación

Puede usar el Administrador de conjuntos de clasificaciones para crear un conjunto de clasificaciones.

**[!UICONTROL Componentes]** > **[!UICONTROL Conjuntos de clasificaciones]** > **[!UICONTROL Conjuntos]** > **[!UICONTROL Agregar]**

Al crear un conjunto de clasificaciones, están disponibles los campos siguientes.

* **[!UICONTROL Nombre]**: Campo de texto utilizado para identificar el conjunto de clasificaciones. Este campo no se puede editar tras la creación, pero se puede cambiar el nombre más adelante.
* **[!UICONTROL Nombre de columna]**: El nombre de la primera dimensión de clasificación que desea crear. Este campo es el nombre de dimensión que se utiliza en Analysis Workspace y el nombre de columna al exportar datos de clasificación. Puede agregar más nombres de columna después de crear el conjunto de clasificaciones.
* **[!UICONTROL Tipo]**: Botones de opción que indican el tipo de clasificación.
   * **[!UICONTROL Principal]**: Aplicar a dimensiones recopiladas en Analytics. Son una forma de agrupar (clasificar) los valores de dimensión granulares en niveles de datos más significativos. Por ejemplo, es posible que desee agrupar palabras clave de búsqueda interna en categorías de búsqueda interna para comprender mejor los temas en los datos de búsqueda.
   * **[!UICONTROL Búsqueda]**: normalmente denominada como secundaria o subclasificaciones, una tabla de búsqueda es una clasificación de una clasificación principal. Se trata de metadatos sobre un valor de clasificación, no de la dimensión original. Por ejemplo, la variable Product podría tener la clasificación principal &quot;Código de color&quot;. Luego se podría adjuntar una tabla de búsqueda de &quot;Nombre de color&quot; al &quot;Código de color&quot; para explicar más detalladamente qué significa cada código.
* **[!UICONTROL Suscripciones]** Los grupos de informes y las dimensiones a los que se aplica este conjunto de clasificación. Puede agregar varias combinaciones de grupos de informes y dimensiones a un conjunto de clasificaciones.

![Crear un conjunto de clasificaciones](../../assets/classification-set-create.png)

Si existe un conjunto de clasificaciones para un grupo de informes + variable, en su lugar se agrega la clasificación al esquema. Una combinación de grupo de informes + variable determinada no puede pertenecer a varios conjuntos de clasificaciones.

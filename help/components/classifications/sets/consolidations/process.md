---
title: Proceso de consolidación del conjunto de clasificaciones
description: Proceso completo de consolidación de conjuntos de clasificaciones.
exl-id: f36bcbcb-0ed0-44a7-a6a9-b28fd244fb27
feature: Classifications
source-git-commit: 9f70dbeb9dfe54897915213480f05cbdfaf920ef
workflow-type: tm+mt
source-wordcount: '410'
ht-degree: 0%

---

# Proceso de consolidación del conjunto de clasificaciones

Utilice esta interfaz para crear una consolidación de juego de clasificaciones de principio a fin.

## Creación

**[!UICONTROL Componentes]** > **[!UICONTROL Conjuntos de clasificaciones]** > **[!UICONTROL Consolidaciones]** > **[!UICONTROL Agregar]**

Los campos siguientes están disponibles al crear una consolidación:

* **[!UICONTROL Nombre]**: El nombre de la consolidación.
* **[!UICONTROL Notificar problemas]**: Lista de direcciones de correo electrónico delimitada por comas a las que se notifican los problemas con esta consolidación.
* **[!UICONTROL Conjunto de datos que debe coincidir]**: Una lista desplegable de todos los conjuntos de clasificaciones.

Una vez seleccionado un conjunto de clasificaciones, aparece una tabla con dos columnas:

* La columna derecha contiene todos los conjuntos de clasificaciones que desea consolidar. Comienza con el conjunto de clasificaciones seleccionado mediante la lista desplegable anterior.
* La columna izquierda contiene todos los conjuntos de clasificaciones que pueden combinarse con el conjunto de datos seleccionado originalmente. **Los esquemas deben coincidir exactamente para poder optar a la consolidación**. Si los esquemas no coinciden con el conjunto de clasificaciones seleccionado, no aparecen en esta columna izquierda.

Arrastre los conjuntos de clasificaciones deseados desde la columna disponible a la izquierda hasta la columna de consolidación a la derecha. Una vez que se asigne un nombre a la consolidación y dos o más conjuntos de clasificaciones estén en la columna derecha, haga clic en **[!UICONTROL Guardar y continuar]**.

## Validación

Una vez creada una consolidación, a la derecha aparece una lista de conjuntos de datos de origen. El botón **[!UICONTROL Validar]** se asegura de que cada conjunto de clasificaciones individual sea válido para esta consolidación. Puede reordenar los pasos de clasificación aquí para determinar la prioridad en casos de valores de clasificación no coincidentes. **El conjunto de clasificaciones más alto de la lista sobrescribe los valores no coincidentes de otros conjuntos de clasificaciones.**

## Ejecutar

Una vez validada una consolidación, puede ejecutarla. La ejecución de una consolidación proporciona un informe de similitud con las siguientes columnas de la tabla:

* **[!UICONTROL Nombre del conjunto de datos]**: El nombre del conjunto de clasificación.
* **[!UICONTROL Discordancia]**: Porcentaje de filas donde los valores de clave no coinciden con el conjunto de clasificación de origen. Si el porcentaje de discrepancia es alto, es posible que los datos de clasificación sean demasiado diferentes. Compruebe y asegúrese de que los conjuntos de clasificaciones seleccionados tienen datos de clasificación similares.
* **[!UICONTROL Ausente]**: Porcentaje de filas donde los valores clave estaban en ese conjunto de clasificaciones pero no en el conjunto de clasificaciones de origen. Todas las filas ausentes se añaden al conjunto de clasificaciones consolidadas.

## Aprobar

Actúa como una última llamada antes de eliminar los conjuntos de clasificaciones individuales y crear uno consolidado. Asegúrese de que todo es correcto y haga clic en **[!UICONTROL Aprobar]**.

Una vez aprobado, se crea el conjunto de clasificaciones consolidado. El estado se establece en [!UICONTROL Completo] y no se requiere ninguna otra acción para la consolidación.

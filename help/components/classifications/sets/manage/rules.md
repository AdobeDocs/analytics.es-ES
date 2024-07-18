---
title: Reglas del conjunto de clasificación
description: Ver y editar las reglas de un conjunto de clasificaciones individual.
exl-id: 1ccb6a20-1993-4fd3-90eb-9154d12d0ec7
feature: Classifications
source-git-commit: 9f70dbeb9dfe54897915213480f05cbdfaf920ef
workflow-type: tm+mt
source-wordcount: '485'
ht-degree: 1%

---

# Reglas del conjunto de clasificación

Las reglas de conjuntos de clasificaciones permiten clasificar automáticamente los valores según el valor en el que esté configurada la variable. Estas reglas se aplican a todos los valores de variables entrantes de todas las suscripciones del conjunto de clasificaciones.

**[!UICONTROL Componentes]** > **[!UICONTROL Conjuntos de clasificación]** > **[!UICONTROL Conjuntos]** > Haga clic en el nombre del conjunto de clasificación deseado > **[!UICONTROL Reglas]**

## Configuración de reglas

Configuración que se aplica a todo el conjunto de reglas.

* **[!UICONTROL Sobrescritura de reglas]**: Determina el comportamiento de todas las reglas en los casos en que existe un valor de clasificación.
   * **[!UICONTROL Aplicar a todos los valores]**: Si una regla coincide, sobrescriba siempre el valor de clasificación.
   * **[!UICONTROL Aplicar solo a valores no establecidos]**: Si una regla coincide, escriba únicamente el valor de clasificación si está en blanco. Si existe un valor de clasificación, no haga nada.
* **[!UICONTROL Ventana retrospectiva]**: Cuando se activa esta regla, todas las reglas se ejecutan con todos los valores únicos vistos dentro de la ventana retrospectiva establecida aquí.

## Reglas

Una lista de reglas que se ejecutan para cada valor único.

* **[!UICONTROL Buscar]**: Cuadro de búsqueda que le permite filtrar reglas por criterios de coincidencia.
* **[!UICONTROL Agregar regla]**: Agrega una fila en blanco a la tabla de reglas.
* **[!UICONTROL Conjunto de reglas de prueba]**: Muestra una interfaz de usuario de prueba que le permite validar las reglas. A la izquierda, puede escribir manualmente los valores clave, o bien puede arrastrar y soltar un archivo de clasificación para importar muchos valores con los que probar. A la derecha se muestra una tabla que muestra los resultados preliminares del aspecto que tendrían los valores clasificados si se activara el conjunto de reglas. Dado que esta interfaz solo es para validación, no se clasifica ningún valor.

Seleccione una o varias reglas haciendo clic en la casilla de verificación situada junto a la regla que desee. Al seleccionar una regla, se muestran las siguientes opciones:

* **[!UICONTROL Eliminar]**: elimina la fila de la tabla de reglas.
* **[!UICONTROL Duplicate]**: copia las filas seleccionadas en las filas nuevas de la tabla de reglas.

## Tabla de reglas

La tabla de reglas se separa verticalmente en dos partes principales: condición coincidente y acción de clasificación. Cada fila (una regla individual) contiene una condición coincidente y una acción de clasificación.

* **Número de regla**: Las reglas se ejecutan en el mismo orden en que se configura la tabla de reglas. Si [!UICONTROL Las reglas se sobrescriben] se establece en [!UICONTROL Aplicar a todos los valores], la última regla que coincida sobrescribirá cualquier regla anterior para la misma dimensión de clasificación. Si [!UICONTROL Las reglas se sobrescriben] se establece en [!UICONTROL Aplicar solo a los valores no establecidos], se aplica la primera regla que establece un valor de clasificación.
* **[!UICONTROL Seleccionar tipo de regla]**: Los criterios de regla. Las opciones incluyen [!UICONTROL Contiene], [!UICONTROL Termina con], [!UICONTROL Expresión regular], [!UICONTROL Expresión regular] y [!UICONTROL Comienza con].
* **[!UICONTROL Escriba los criterios de coincidencia]**: La cadena de texto que debe coincidir. Si selecciona [!UICONTROL Expresión regular] como tipo de regla, aparecerá una superposición que le permitirá introducir el valor, probar la expresión regular y proporcionar sintaxis de ejemplo.
* **[!UICONTROL Establecer clasificación]**: Una lista desplegable que establece la dimensión de clasificación a la que desea asignar un valor. Las opciones válidas incluyen elementos en su [esquema](schema.md).
* **[!UICONTROL Para]**: La cadena de texto en la que se debe establecer el valor clasificado. Si el tipo de regla es [!UICONTROL Expresión regular], puede incluir una combinación de texto y grupos de coincidencias.

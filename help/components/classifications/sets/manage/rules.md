---
title: Reglas del conjunto de clasificaciones
description: Ver y editar las reglas de un conjunto de clasificaciones individual.
exl-id: b3518aaa-382f-47ad-860f-b6af6ddb3cbc
feature: Classifications
source-git-commit: 811e321ce96aaefaeff691ed5969981a048d2c31
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Reglas del conjunto de clasificaciones

Las reglas de conjuntos de clasificaciones permiten clasificar automáticamente los valores según el valor en el que esté configurada la variable. Estas reglas se aplican a todos los valores de variables entrantes de todas las suscripciones del conjunto de clasificaciones.

**[!UICONTROL Componentes]** > **[!UICONTROL Conjuntos de clasificaciones]** > **[!UICONTROL Conjuntos]** > Haga clic en el nombre del conjunto de clasificaciones deseado > **[!UICONTROL Reglas]**

## Configuración de reglas

Configuración que se aplica a todo el conjunto de reglas.

* **[!UICONTROL Sobrescritura de reglas]**: Determina el comportamiento de todas las reglas en casos en los que existe un valor de clasificación.
   * **[!UICONTROL Aplicar a todos los valores]**: Si una regla coincide, sobrescriba siempre el valor de clasificación.
   * **[!UICONTROL Aplicar solo a valores no establecidos]**: Si una regla coincide, escriba el valor de clasificación solo si está en blanco. Si existe un valor de clasificación, no haga nada.
* **[!UICONTROL Ventana retroactiva]**: cuando se activa esta regla, todas las reglas se ejecutan con todos los valores únicos vistos dentro de la ventana retrospectiva establecida aquí.

## Reglas

Una lista de reglas que se ejecutan para cada valor único.

* **[!UICONTROL Buscar]**: Un cuadro de búsqueda que le permite filtrar reglas por criterios de coincidencia.
* **[!UICONTROL Añadir regla]**: agrega una fila en blanco a la tabla de reglas.
* **[!UICONTROL Conjunto de reglas de prueba]**: Muestra una interfaz de usuario de prueba que le permite validar las reglas. A la izquierda, puede escribir manualmente los valores clave, o bien puede arrastrar y soltar un archivo de clasificación para importar muchos valores con los que probar. A la derecha se muestra una tabla que muestra los resultados preliminares del aspecto que tendrían los valores clasificados si se activara el conjunto de reglas. Dado que esta interfaz solo es para validación, no se clasifica ningún valor.

Seleccione una o varias reglas haciendo clic en la casilla de verificación situada junto a la regla que desee. Al seleccionar una regla, se muestran las siguientes opciones:

* **[!UICONTROL Eliminar]**: elimina la fila de la tabla de reglas.
* **[!UICONTROL Duplicar]**: copia las filas seleccionadas en las nuevas filas de la tabla de reglas.

## Tabla de reglas

La tabla de reglas se separa verticalmente en dos partes principales: condición coincidente y acción de clasificación. Cada fila (una regla individual) contiene una condición coincidente y una acción de clasificación.

* **Número de regla**: Las reglas se ejecutan en el mismo orden en que se configura la tabla de reglas. If [!UICONTROL Sobrescritura de reglas] se establece en [!UICONTROL Aplicar a todos los valores]Sin embargo, la última regla coincidente sobrescribe las reglas anteriores para la misma dimensión de clasificación. If [!UICONTROL Sobrescritura de reglas] se establece en [!UICONTROL Aplicar solo a valores no configurados], se aplica la primera regla que establece un valor de clasificación.
* **[!UICONTROL Seleccionar tipo de regla]**: los criterios de la regla. Las opciones incluyen [!UICONTROL Contains], [!UICONTROL Finaliza con], [!UICONTROL Expresión regular], [!UICONTROL Expresión regular], y [!UICONTROL Comienza por].
* **[!UICONTROL Introducir criterios de coincidencia]**: La cadena de texto que debe coincidir. Si selecciona [!UICONTROL Expresión regular] como tipo de regla, aparece una superposición que permite introducir el valor, probar la expresión regular y proporcionar sintaxis de ejemplo.
* **[!UICONTROL Establecer clasificación]**: Lista desplegable que establece la dimensión de clasificación a la que desea asignar un valor. Las opciones válidas incluyen elementos en su [esquema](schema.md).
* **[!UICONTROL Hasta]**: Cadena de texto en la que se establece el valor clasificado. Si el tipo de regla es [!UICONTROL Expresión regular], puede incluir una combinación de texto y grupos de coincidencias.

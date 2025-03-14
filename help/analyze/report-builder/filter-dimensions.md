---
title: Cómo filtrar dimensiones en Report Builder
description: Describe cómo filtrar dimensiones en Report Builder
role: User
feature: Report Builder
type: Documentation
solution: Analytics
exl-id: 43f48abf-951d-4fd1-afd4-58304ee5247b
source-git-commit: 06d762614969f3557c8ccf310af266742cde9738
workflow-type: tm+mt
source-wordcount: '1021'
ht-degree: 75%

---

# Filtrar dimensiones

De forma predeterminada, cada elemento de dimensión de la tabla devuelve los 10 elementos principales para esa dimensión.

Para cambiar los elementos de dimensión devueltos para cada dimensión

1. Haga clic en **[!UICONTROL Administrar]** y seleccione un bloque de datos de la lista.

   ![Administrar > Editar bloque de datos](./assets/manage-edit.png)

1. Haga clic en **[!UICONTROL Editar bloque de datos]** en el panel COMANDOS.

1. Haga clic en **[!UICONTROL Siguiente]** para mostrar la ficha Dimension.

1. Haga clic en el icono **...** junto al nombre de un componente en la tabla.

   ![Opciones del icono de los tres puntos.](./assets/image27.png)

1. Seleccione **[!UICONTROL Filtrar dimensión]** en el menú emergente para mostrar el panel **[!UICONTROL Filtrar dimensión]**.

1. Seleccione **[!UICONTROL Más popular]** o **[!UICONTROL Específico]**.

   ![La opción específica seleccionada en el panel Dimensión de filtro.](./assets/image28.png)

1. Seleccione las opciones adecuadas en función del tipo de filtro elegido.

1. Haga clic en **[!UICONTROL Aplicar]** para agregar el filtro.

   Report Builder muestra una notificación para confirmar el filtro añadido.

Para mostrar los filtros aplicados, pase el ratón sobre una dimensión. Las dimensiones con filtros aplicados muestran un icono de filtro a la derecha del nombre de la dimensión.

## Tipo de filtro

Existen dos formas de filtrar los elementos de dimensión: el más popular y específico.

## Más popular

La opción [!UICONTROL Más popular] le permite filtrar dinámicamente elementos de dimensión en función de los valores de las métricas. El filtrado [!UICONTROL Más popular] devuelve los elementos de dimensión de mayor clasificación en función de los valores de las métricas. De forma predeterminada, se muestran los 10 primeros elementos de dimensión, ordenados por la primera métrica añadida al bloque de datos.

![La opción más popular.](./assets/image29.png)


### Opciones de página y filas

Utilice los campos **Página** y **Filas** para dividir los datos en grupos secuenciales o páginas. Esto le permite extraer en el informe valores de fila clasificados que no sean los valores más altos. Esta función es especialmente útil para extraer datos que superen el límite de 50 000 filas.

#### Valores predeterminados de página y filas

- Página = 1
- Filas = 10

La configuración predeterminada Página y Filas identifica que cada página tiene 10 filas de datos. La página 1 devuelve los 10 elementos principales, la página 2 devuelve los 10 elementos siguientes, etc.

En la tabla siguiente se muestran ejemplos de valores de página, fila y el resultado.

| Página | Fila | Output |
|------|--------|----------------------|
| 1 | 10 | Primeros 10 elementos |
| 2 | 10 | Elementos 11 a 20 |
| 1 | 100 | Primeros 100 elementos |
| 2 | 100 | Elementos 101 a 200 |
| 2 | 50 000 | Elementos 50 001 a 100 000 |

#### Valores mínimos y máximos

- Página de inicio: mín. = 1, máx.: 50 millones
- Número de filas: mín. = 1, máx.: 50 000

### Incluir “Sin valor”

En Adobe Analytics, algunas dimensiones recopilan una entrada sin valor. Este filtro le permite excluir estos valores de los informes. Por ejemplo, puede crear una clasificación como la de Nombre del producto basada en la clave SKU del producto. Si no se ha configurado un SKU de producto específico con su clasificación de nombre de producto específica, su valor de nombre de producto se establece en “sin valor”.

Incluir “**Sin valor**” está seleccionado de forma predeterminada. Anule la selección de esta opción para excluir las entradas sin valor.

### Filtrado por criterios

Puede filtrar los elementos de dimensión en función de si se cumplen todos los criterios o alguno.

Definición de criterios de filtrado

1. Seleccione un operador en la lista desplegable.

   ![La lista de operadores.](./assets/image31.png)

1. Escriba un valor en el campo de búsqueda.

1. Haga clic en **[!UICONTROL Agregar fila]** para confirmar la selección y agregar otro elemento de criterio.

1. Haga clic en el icono Eliminar para quitar un elemento de criterio.

   Puede incluir hasta 10 elementos de criterio.

### Cambio del filtro y el orden

Aparece una flecha junto a la métrica utilizada para filtrar y ordenar el bloque de datos. La dirección de la flecha indica si la métrica se ordena de mayor a menor o menor a mayor.

Para cambiar la dirección del orden, haga clic en la flecha situada junto a la métrica.

Para cambiar la métrica utilizada para filtrar y ordenar el bloque de datos,

1. Pase el ratón sobre el componente de métrica deseado en el Generador de tablas para ver las opciones adicionales.

2. Haga clic en la flecha de la métrica preferida.

   ![Generador de tablas y métricas.](./assets/image30.png)


## Filtro específico

La opción Específico permite crear una lista fija de elementos de dimensión para cada dimensión. Utilice el tipo de filtro **[!UICONTROL Específico]** para especificar los elementos de dimensión exactos que se incluirán en el filtro. Puede seleccionar elementos de una lista o de un rango de celdas.

![Opciones específicas y elementos seleccionados.](./assets/image32.png)

### De la lista

1. Seleccione la opción **[!UICONTROL De la lista]** para buscar y seleccionar elementos de dimensión.

   Al seleccionar la variable **[!UICONTROL De la lista]**, la lista se rellena con elementos de dimensión con la mayoría de eventos primero.

   ![La opción De la lista y los elementos disponibles.](./assets/image33.png)

   La lista **[!UICONTROL Elementos disponibles]** se ordena de elementos de dimensión con la mayor cantidad de eventos a aquellos con la menor cantidad.

1. Escriba un término de búsqueda en el campo **[!UICONTROL Añadir elemento]** para buscar en la lista.

1. Para buscar un elemento no incluido en los últimos 90 días de datos, haga clic en **[!UICONTROL Mostrar elementos de los últimos 6 meses]** para ampliar la búsqueda.

   ![La lista Mostrar elementos de los últimos 6 meses.](./assets/image34.png)

   Después de cargar los datos de los últimos 6 meses, el Report Builder actualiza el vínculo a **[!UICONTROL Mostrar elementos de los últimos 18 meses]**.

1. Seleccionar un elemento de dimensión.

   Los elementos de dimensión seleccionados se añaden automáticamente a la lista **[!UICONTROL Elementos seleccionados]**.

   ![](./assets/image35.png)

   Para quitar un elemento de la lista, haga clic en el icono eliminar.

   Para mover un elemento en la lista, arrastre y suelte el elemento o haga clic en ... para mostrar el menú de mover.

   ![La lista de elementos de dimensión.](./assets/image36.png)

1. Haga clic en **[!UICONTROL Aplicar]**

   Report Builder actualiza la lista para mostrar el filtro específico que ha aplicado.

### Desde el rango de celdas

Seleccione la opción **[!UICONTROL Desde el rango de celdas]** para elegir un rango de celdas que contenga la lista de elementos de dimensiones que desea que coincidan.

![La opción Desde el rango de celdas y el campo para seleccionar un rango de celdas.](./assets/image37.png)

Cuando seleccione un rango de celdas, tenga en cuenta las restricciones siguientes:

- El rango debe tener al menos una celda.
- El rango no puede tener más de 50 000 celdas.
- El rango debe estar en una sola fila o columna sin interrupciones.

La selección puede contener celdas vacías o con valores que no coinciden con un elemento de dimensión específico.

### Desde la pestaña Dimensiones del Generador de tablas

En la pestaña **[!UICONTROL Dimensiones]**, haga clic en el icono de cheurón situado junto al nombre de una dimensión para ver la lista de elementos que contiene.

![La ficha Dimension y la lista de dimensiones.](./assets/dimensions_chevron.png)

Puede arrastrar y soltar elementos en la **[!UICONTROL Tabla]** o hacer doble clic en un nombre de elemento para añadirlo al Generador de **[!UICONTROL tablas]**.

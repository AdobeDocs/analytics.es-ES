---
description: Documentación que describe cómo filtrar y ordenar tablas en Analysis Workspace.
title: Filtrado y ordenación de tablas
feature: Freeform Tables
role: User, Admin
exl-id: 15fea9e2-f8d8-4489-9a44-e74a351b8f36
source-git-commit: 7f5fca4f7c3641d47e5d1d929a196d5e380c1e6b
workflow-type: tm+mt
source-wordcount: '811'
ht-degree: 77%

---

# Filtrado y ordenación de tablas

Las tablas de forma libre en Analysis Workspace son la base del análisis interactivo de datos. Como tal, pueden contener miles de filas de información. Filtrar y ordenar los datos puede ser una parte fundamental para que la información más importante aparezca de forma eficaz.

## Filtrado de tablas

Los filtros de Analysis Workspace le ayudan a mostrar la información más importante.

>[!NOTE]
>
> Solo se pueden filtrar los elementos de dimensión dinámicos como se describe en esta sección. Los elementos de dimensión estáticos no se pueden filtrar. Para obtener más información, consulte [Elementos de dimensión dinámicos o estáticos en tablas improvisadas](/help/analyze/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md).

### Excluir rápidamente filas específicas de una tabla

Puede excluir rápidamente filas específicas de la tabla sin tener que abrir el cuadro de diálogo Filtro .

>[!NOTE]
>
>Cuando excluye filas como se describe en esta sección, una [!UICONTROL **No es igual a**] se aplica automáticamente en la variable [**[!UICONTROL Filtro avanzado]**](#apply-a-simple-or-advanced-filter) diálogo.

Para excluir rápidamente filas específicas de una tabla improvisada:

1. Pase el ratón sobre la fila que quiera excluir y, a continuación, seleccione el icono x .

   Mantenga pulsada la tecla Mayús para seleccionar un rango de filas o mantenga pulsada la tecla Comando (en Mac) o la tecla Ctrl (en Windows) para seleccionar varias filas.

### Aplicar un filtro simple o avanzado a una tabla

Para filtrar datos en tablas de forma libre:

1. Pase el ratón sobre la columna que contiene los datos que desea filtrar. <!--only some types of columns show the filter... Which? Just Dimensions?-->

1. Seleccione el icono de **Filtro** cuando aparezca.

   ![Icono de filtro en una tabla](assets/table-filter-icon.png)

   Las opciones disponibles son las siguientes:

   | Opción | Función |
   |---------|----------|
   | [!UICONTROL **Palabra o frase de búsqueda**] | Especifique una palabra o frase por la que desee filtrar. Solo se muestran las filas que contienen la palabra o la frase exacta especificada. |
   | [!UICONTROL **Incluir no especificado (ninguno)**] | Seleccione esta opción para mostrar los datos de la tabla que no estén dentro de ninguna de sus dimensiones. <!--what is this?--> |

1. (Opcional) Para filtrar por diferentes criterios o por varios criterios, seleccione [!UICONTROL **Filtro avanzado**].

   Las siguientes opciones de filtro avanzado están disponibles:

   | Opción | Función |
   |---------|----------|
   | [!UICONTROL **Incluir no especificado (ninguno)**] | Seleccione esta opción para mostrar los datos de la tabla que no estén dentro de ninguna de sus dimensiones. <!--what is this?--> |
   | [!UICONTROL **Coincidencias**] | <p>Seleccione [!UICONTROL **Si se cumplen todos los criterios**] para mostrar solo los datos que cumplan todos los criterios especificados. Esta opción suele dar como resultado datos más precisos.</p> <p>Seleccione [!UICONTROL **Si se cumplen algunos criterios**] para mostrar los datos que cumplan cualquiera de los criterios de filtro especificados. Esta opción suele dar como resultado datos menos precisos.</p> |
   | [!UICONTROL **Criterios**] | <p>Seleccione entre las siguientes opciones de filtro:</p><p>(Seleccione [!UICONTROL **Agregar fila**] para añadir varios criterios de filtro. La opción que seleccione en la sección [!UICONTROL **Coincidencia**] determina si se deben cumplir todos o cualquiera de los criterios agregados).</p><ul><li><p>[!UICONTROL **Contiene la frase**]: en los resultados filtrados solo se incluyen los datos que contienen la frase exacta especificada. Las palabras deben estar en el orden especificado en el [!UICONTROL **campo Buscar palabra o frase**].<p>Esta es la configuración predeterminada al realizar una búsqueda simple.</p></p></li><li><p>[!UICONTROL **Contiene cualquier término**]: en los resultados filtrados solo se incluyen los datos que contienen una o más palabras de la frase especificada. </p></li><li><p>[!UICONTROL **Contiene todos los términos**]: en los resultados filtrados solo se incluyen los datos que contienen todas las palabras de la frase especificada. Las palabras no tienen que estar en el orden especificado en el [!UICONTROL **campo Buscar palabra o frase**].</p></li><li><p>[!UICONTROL **No contiene ningún término**]: en los resultados filtrados solo se incluyen los datos que no contienen ninguna de las palabras de la frase especificada. </p></li><li><p>[!UICONTROL **No contiene la frase**]: en los resultados filtrados solo se incluyen los datos que no contienen la frase exacta especificada. Las palabras deben estar en el orden especificado en el [!UICONTROL **campo Buscar palabra o frase**].</p></li><li><p>[!UICONTROL **Es igual a**]: en los resultados filtrados solo se incluyen los datos que coinciden exactamente con la frase especificada. </p></li><li><p>[!UICONTROL **No es igual a**]: en los resultados filtrados solo se incluyen los datos que no coinciden exactamente con la frase especificada. </p></li><li><p>[!UICONTROL **Comienza con**]: en los resultados filtrados solo se incluyen los datos que comienzan con la palabra o frase exacta que especifique. </p></li><li><p>[!UICONTROL **Finaliza con**]: en los resultados filtrados solo se incluyen los datos que terminan con la palabra o frase exacta que especifique. </p></li></ul> |
   | [!UICONTROL **Excluir artículos siempre**] | Especifique el nombre de cualquier elemento que desee excluir de los datos filtrados. |

1. Seleccione [!UICONTROL **Aplicar**] para filtrar los datos.

   El icono de **filtro** de la ![Tabla filtrada](assets/table-filter-blue-icon.png) se vuelve azul cuando se aplica un filtro a la tabla.

## Orden de tablas

Puede ordenar los datos de una tabla de forma libre según cualquier columna de Analysis Workspace que sea una métrica.

El icono de flecha hacia abajo en la ![columna de tabla ordenada](assets/table-sort-arrow-icon.png) es visible en el encabezado de la columna por la que se ordenan actualmente los datos.

Para ordenar los datos de una tabla de forma libre por una columna concreta:

1. Pase el ratón sobre el título de la columna por la que desea ordenar los datos.

1. Seleccione el icono de flecha hacia abajo cuando aparezca.

   ![Icono de flecha hacia abajo en la columna de tabla ordenada](assets/table-sort.png)

   Los datos de la tabla se ordenan por la columna seleccionada.

---
description: Documentación que describe cómo filtrar y ordenar tablas en Analysis Workspace.
title: Filtrado y ordenación de tablas de forma libre
feature: Freeform Tables
role: User, Admin
exl-id: 15fea9e2-f8d8-4489-9a44-e74a351b8f36
source-git-commit: 398d4ae264ce108c16a03cef086ae2614b442a2b
workflow-type: tm+mt
source-wordcount: '874'
ht-degree: 72%

---

# Filtrado y ordenación de tablas de forma libre

Las tablas de forma libre en Analysis Workspace son la base del análisis interactivo de datos. Como tal, pueden contener miles de filas de información. Filtrar y ordenar los datos puede ser una parte fundamental para que la información más importante aparezca de forma eficaz.

## Filtrado de tablas

Los filtros de Analysis Workspace le ayudan a mostrar la información más importante.

>[!NOTE]
>
> Solo se pueden filtrar los elementos de dimensión dinámicos como se describe en esta sección. Los elementos de dimensión estáticos no se pueden filtrar. Para obtener más información, consulte [Elementos de dimensión dinámicos o estáticos en tablas de forma libre](/help/analyze/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md).

## Filtrar filas de tabla de forma libre

Puede utilizar varios métodos para filtrar filas de una tabla de forma libre. 

- Haga clic en la &quot;X&quot; de la fila.
- Filtros de tabla
- Segmentación

Asegúrese de leer el impacto de cada método [Totales de tabla de forma libre](/help/analyze/analysis-workspace/visualizations/freeform-table/workspace-totals.md).

### Excluir rápidamente filas específicas de una tabla

Puede excluir rápidamente filas específicas de la tabla sin necesidad de abrir el cuadro de diálogo Filtro.

>[!NOTE]
>
>Cuando excluya filas como se describe en esta sección, [!UICONTROL **Excluir elementos siempre**] La regla de se aplica automáticamente en el cuadro de diálogo filtro avanzado. (Puede ver la regla aplicada seleccionando el icono Filtrar y, a continuación, [**[!UICONTROL Mostrar avanzadas]**](#apply-a-simple-or-advanced-filter-to-a-table).)

Para excluir rápidamente filas específicas de una tabla de forma libre:

1. Pase el ratón sobre la fila que quiera excluir y luego seleccione el icono x.

   Mantenga pulsada la tecla Mayús para seleccionar un rango de filas o la tecla Comando (en Mac) o Ctrl (en Windows) para seleccionar varias filas.

<!--### Right-click > Delete selected rows

Note: this option does not seem to work. AN-338422

1. Select 1 or more rows. 
1. Right-click and select **[!UICONTROL Delete Selected Rows]**. 

   This action will remove the rows from the table and apply a table filter.-->

### Aplicar un filtro simple o avanzado a una tabla

Para filtrar datos en tablas de forma libre:

1. Pase el ratón sobre la columna que contiene los datos que desea filtrar. <!--only some types of columns show the filter... Which? Just Dimensions?-->

1. Seleccione el icono de **Filtro** cuando aparezca.

   ![Icono de filtro en una tabla](assets/table-filter-icon.png)

   Las opciones disponibles son las siguientes:

   | Opción | Función |
   |---------|----------|
   | [!UICONTROL **Buscar palabra o frase**] | Especifique una palabra o frase por la que desee filtrar. Solo se muestran las filas que contienen la palabra o la frase exacta especificada. |
   | [!UICONTROL **Incluir no especificado (ninguno)**] | Seleccione esta opción para mostrar los datos de la tabla que no estén dentro de ninguna de sus dimensiones. <!--what is this?--> |

1. (Opcional) Para filtrar por diferentes criterios o por varios criterios, seleccione [!UICONTROL **Mostrar avanzadas**].

   Estas son las opciones de filtro avanzadas disponibles:

   | Opción | Función |
   |---------|----------|
   | [!UICONTROL **Incluir no especificado (ninguno)**] | Seleccione esta opción para mostrar los datos de la tabla que no estén dentro de ninguna de sus dimensiones. <!--what is this?--> |
   | [!UICONTROL **Coincidencias**] | <p>Seleccione [!UICONTROL **Si se cumplen todos los criterios**] para mostrar solo los datos que cumplan todos los criterios especificados. Esta opción suele dar como resultado datos más precisos.</p> <p>Seleccione [!UICONTROL **Si se cumplen algunos criterios**] para mostrar los datos que cumplan cualquiera de los criterios de filtro especificados. Esta opción suele dar como resultado datos menos precisos.</p> |
   | [!UICONTROL **Criterios**] | <p>Seleccione entre las siguientes opciones de filtro:</p><p>(Seleccione [!UICONTROL **Agregar fila**] para añadir varios criterios de filtro. La opción que seleccione en la sección [!UICONTROL **Coincidencia**] determina si se deben cumplir todos o cualquiera de los criterios agregados).</p><ul><li><p>[!UICONTROL **Contiene la frase**]: en los resultados filtrados solo se incluyen los datos que contienen la frase exacta especificada. Las palabras deben estar en el orden especificado en el [!UICONTROL **campo Buscar palabra o frase**].<p>Esta es la configuración predeterminada al realizar una búsqueda simple.</p></p></li><li><p>[!UICONTROL **Contiene cualquier término**]: en los resultados filtrados solo se incluyen los datos que contienen una o más palabras de la frase especificada. </p></li><li><p>[!UICONTROL **Contiene todos los términos**]: en los resultados filtrados solo se incluyen los datos que contienen todas las palabras de la frase especificada. Las palabras no tienen que estar en el orden especificado en el [!UICONTROL **campo Buscar palabra o frase**].</p></li><li><p>[!UICONTROL **No contiene ningún término**]: en los resultados filtrados solo se incluyen los datos que no contienen ninguna de las palabras de la frase especificada. </p></li><li><p>[!UICONTROL **No contiene la frase**]: en los resultados filtrados solo se incluyen los datos que no contienen la frase exacta especificada. Las palabras deben estar en el orden especificado en el [!UICONTROL **campo Buscar palabra o frase**].</p></li><li><p>[!UICONTROL **Es igual a**]: en los resultados filtrados solo se incluyen los datos que coinciden exactamente con la frase especificada. </p></li><li><p>[!UICONTROL **No es igual a**]: en los resultados filtrados solo se incluyen los datos que no coinciden exactamente con la frase especificada. </p></li><li><p>[!UICONTROL **Comienza con**]: en los resultados filtrados solo se incluyen los datos que comienzan con la palabra o frase exacta que especifique. </p></li><li><p>[!UICONTROL **Finaliza con**]: en los resultados filtrados solo se incluyen los datos que terminan con la palabra o frase exacta que especifique. </p></li></ul> |
   | [!UICONTROL **Excluir artículos siempre**] | Especifique el nombre de cualquier elemento que desee excluir de los datos filtrados. |

1. Seleccione [!UICONTROL **Aplicar**] para filtrar los datos.

   El icono de **filtro** de la ![Tabla filtrada](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg) se vuelve azul cuando se aplica un filtro a la tabla.

### Segmentación

Consulte nuestra [Documentación de segmentación](/help/components/segmentation/seg-home.md) para obtener más información.

## Orden de tablas

Puede ordenar los datos de una tabla de forma libre por cualquier columna de Analysis Workspace que sea una métrica.

El icono de flecha hacia abajo en la ![columna de tabla ordenada](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) es visible en el encabezado de la columna por la que se ordenan actualmente los datos.

Para ordenar los datos de una tabla de forma libre por una columna concreta:

1. Pase el ratón sobre el título de la columna por la que desea ordenar los datos.

2. Seleccione el icono de flecha hacia abajo cuando aparezca.

   ![Icono de flecha hacia abajo en la columna de tabla ordenada](assets/table-sort.png)

   Los datos de la tabla se ordenan por la columna seleccionada.

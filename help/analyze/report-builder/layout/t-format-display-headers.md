---
description: Se puede asignar un nombre al informe y configurar cómo mostrar los encabezados de fila y columna. El vínculo Opciones de formato está disponible para los tipos de diseño personalizado y de tabla dinámica.
seo-description: Se puede asignar un nombre al informe y configurar cómo mostrar los encabezados de fila y columna. El vínculo Opciones de formato está disponible para los tipos de diseño personalizado y de tabla dinámica.
seo-title: Formato de encabezados de visualización
solution: Analytics
title: Formato de encabezados de visualización
topic: Creador de informes
uuid: cd 0 e 167 b -9463-43 fd -87 b 2-724 d 1 c 79 de 68
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Formato de encabezados de visualización

Se puede asignar un nombre al informe y configurar cómo mostrar los encabezados de fila y columna. El vínculo Opciones de formato está disponible para los tipos de diseño personalizado y de tabla dinámica.

1. Cree una solicitud en el [!UICONTROL Asistente para solicitudes: Paso 1].
1. Click **[!UICONTROL Next]**.
1. En el formulario [!UICONTROL Asistente para solicitudes: Paso 2], añada los datos de dimensiones y métricas a la solicitud.
1. Click **[!UICONTROL Format Options]**.
1. Configure las opciones de [!UICONTROL visualización:]

   | Elemento | Descripción |
   |--- |--- |
   | Nombre del informe | Displays either the name of the report type you selected from the tree in the  Request Wizard: Step 1 (for example, [!DNL Traffic Report]), or the name you type in the [!DNL Name this Request] field. |
   | Parámetros de filtros | Muestra los filtros de dimensión como, por ejemplo, un filtro de búsqueda. |
   | Segmento | Muestra el parámetro de segmento. |
   | Creación de los datos | Muestra los parámetros de la actualización de datos. For example:    Data Recency: Page Views (1.5 hr ago), Exits (30 mins ago)  See [Options](../../../analyze/report-builder/options.md) for information about current data processing. |

   Respecto al orden de visualización, si la cuadrícula [!UICONTROL Rótulo de fila] (en el Paso 2) contiene un elemento, éste se muestra en primer lugar en la solicitud. De lo contrario, el sistema utiliza el primer elemento presente en la cuadrícula [!UICONTROL Rótulo de columna]. Si no existen filas ni columnas, se muestra el primer elemento de la cuadrícula [!UICONTROL Métrica].

   **Mostrar encabezados de columna y fila:** Añade una fila y una columna para mostrar estos elementos.

   En la versión 3.11, es posible mostrar un encabezado para cada elemento. La versión 4 muestra todos estos elementos o ninguno de ellos. Si ha creado una solicitud en la versión 3.11 y la abre en la versión 4.x, el Creador de informes le indicará en el paso 2 que actualice el intervalo en una celda para los elementos que no tengan encabezado.

   **Cambiar encabezados a filtros automáticos de Excel:** solo está disponible si se muestran los encabezados de fila y columna. Esta opción crea un filtro automático de Excel y lo añade a los datos que devuelve el Creador de informes para esta solicitud.

   >[!NOTE]
   >
   >Excel solo admite un filtro automático por hoja de cálculo. Si se crea un nuevo filtro automático en una hoja de cálculo donde ya existe otro, Excel no muestra una advertencia indicando que el filtro automático existente se va a reemplazar.

   **Realizar contorno automático:** transforma los datos devueltos por el Creador de informes de una vista de lista a una vista de árbol.

   **Asignar nombre a esta solicitud:** Permite escribir un nombre definido por el usuario para la solicitud, o usar el nombre predeterminado seleccionado en el Paso 1. Este nombre aparece como nombre de [!UICONTROL Informe] en el [!UICONTROL Administrador de solicitudes]. Consulte [Especificar el nombre de una solicitud](../../../analyze/report-builder/layout/name-a-request.md#concept_37277AFB63EA4541B6FD93A5B713D82D).

1. Haga clic en **[!UICONTROL Aceptar]**.

---
description: Se puede asignar un nombre al informe y configurar cómo mostrar los encabezados de fila y columna. El vínculo Opciones de formato está disponible para los tipos de diseño personalizado y de tabla dinámica.
title: Dar formato a los encabezados
topic: Report builder
uuid: cd0e167b-9463-43fd-87b2-724d1c79de68
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Dar formato a los encabezados

Se puede asignar un nombre al informe y configurar cómo mostrar los encabezados de fila y columna. El vínculo Opciones de formato está disponible para los tipos de diseño personalizado y de tabla dinámica.

1. Cree una solicitud en el [!UICONTROL Request Wizard: Step 1].
1. Haga clic en **[!UICONTROL Next]**.
1. On the [!UICONTROL Request Wizard: Step 2] form, add dimensions and metrics data to the request, as desired.
1. Haga clic en **[!UICONTROL Format Options]**.
1. Configure the [!UICONTROL Display] options:

   | Elemento | Descripción |
   |--- |--- |
   | Nombre del informe | Muestra el nombre del tipo de informe seleccionado en el árbol en el Asistente para solicitudes: Paso 1 (por ejemplo, [!DNL Traffic Report]), o bien el nombre que escriba en el campo [!DNL Name this Request]. |
   | Parámetros de filtros | Muestra los filtros de dimensión como, por ejemplo, un filtro de búsqueda. |
   | Segmento | Muestra el parámetro de segmento. |
   | Actualización de los datos | Muestra los parámetros de la actualización de datos. Por ejemplo:    Actualización de los datos: Vistas de página (hace 1,5 horas), Salidas (hace 30 minutos)  Consulte [Opciones](/help/analyze/report-builder/options.md) para obtener información sobre el procesamiento de datos actual. |

   Regarding display order, if the [!UICONTROL Row Label] grid (on Step 2) contains an item, it is displayed first in the request. If not, the system uses the first item present in the [!UICONTROL Column Label] grid. If no row or column items exist, the first item in the [!UICONTROL Metrics] grid is displayed.

   **Mostrar encabezados de columna y fila:** Añade una fila y una columna para mostrar estos elementos.

   En la versión 3.11, es posible mostrar un encabezado para cada elemento. La versión 4 muestra todos estos elementos o ninguno de ellos. Si ha creado una solicitud en la versión 3.11 y la abre en la versión 4.x, Report Builder le indicará en el paso 2 que actualice el intervalo en una celda para los elementos que no tengan encabezado.

   **Cambiar encabezados a filtros automáticos de Excel:** solo está disponible si se muestran los encabezados de fila y columna. Esta opción crea un filtro automático de Excel y lo añade a los datos que devuelve Report Builder para esta solicitud.

   >[!NOTE]
   >
   >Excel solo admite un filtro automático por hoja de cálculo. Si se crea un nuevo filtro automático en una hoja de cálculo donde ya existe otro, Excel no muestra una advertencia indicando que el filtro automático existente se va a reemplazar.

   **Realizar contorno automático:** transforma los datos devueltos por Report Builder de una vista de lista a una vista de árbol.

   **Asignar nombre a esta solicitud:** Permite escribir un nombre definido por el usuario para la solicitud, o usar el nombre predeterminado seleccionado en el Paso 1. Este nombre aparece como el [!UICONTROL Report] nombre en la [!UICONTROL Request Manager]. See [Name a Request](/help/analyze/report-builder/layout/name-a-request.md).

1. Haga clic en **[!UICONTROL OK]**.

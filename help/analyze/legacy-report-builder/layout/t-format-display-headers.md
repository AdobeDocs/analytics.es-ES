---
description: Obtenga información sobre cómo asignar un nombre al informe y configurar cómo mostrar los encabezados de fila y columna.
title: Cómo dar formato a los encabezados de visualización
uuid: cd0e167b-9463-43fd-87b2-724d1c79de68
feature: Report Builder
role: User, Admin
exl-id: 168daa6b-965c-4f8b-97b7-651a7ad55d6c
source-git-commit: fcecc8a493852f5682fd7fbd5b9bb484a850922c
workflow-type: tm+mt
source-wordcount: '409'
ht-degree: 76%

---

# Dar formato a los encabezados

{{legacy-arb}}

Se puede asignar un nombre al informe y configurar cómo mostrar los encabezados de fila y columna. El vínculo Opciones de formato está disponible para los tipos de diseño personalizado y de tabla dinámica.

1. Cree una solicitud en el [!UICONTROL Asistente para solicitudes: Paso 1].
1. Haga clic en **[!UICONTROL Siguiente]**.
1. En el formulario [!UICONTROL Asistente para solicitudes: Paso 2], añada los datos de dimensiones y métricas a la solicitud.
1. Haga clic en **[!UICONTROL Opciones de formato]**.
1. Configure las opciones de [!UICONTROL visualización:]

   | Elemento | Descripción |
   |--- |--- |
   | Nombre del informe | Muestra el nombre del tipo de informe seleccionado en el árbol en el Asistente para solicitudes: Paso 1 (por ejemplo, [!DNL Traffic Report]), o bien el nombre que escriba en el campo [!DNL Name this Request]. |
   | Parámetros de filtros | Muestra los filtros de dimensión como, por ejemplo, un filtro de búsqueda. |
   | Segmento | Muestra el parámetro de segmento. |
   | Actualización de los datos | Muestra los parámetros de la actualización de datos. Por ejemplo:    Actualización de los datos: Vistas de página (hace 1,5 horas), Salidas (hace 30 minutos)  Consulte [Opciones](/help/analyze/legacy-report-builder/options.md) para obtener información sobre el procesamiento de datos actual. |

   Respecto al orden de visualización, si la cuadrícula [!UICONTROL Rótulo de fila] (en el Paso 2) contiene un elemento, éste se muestra en primer lugar en la solicitud. De lo contrario, el sistema utiliza el primer elemento presente en la cuadrícula [!UICONTROL Rótulo de columna]. Si no existen filas ni columnas, se muestra el primer elemento de la cuadrícula [!UICONTROL Métrica].

   **Mostrar encabezados de columna y fila:** Añade una fila y una columna para mostrar estos elementos.

   En la versión 3.11, es posible mostrar un encabezado para cada elemento. La versión 4 muestra todos estos elementos o ninguno de ellos. Si ha creado una solicitud en la versión 3.11 y la abre en la versión 4.x, Report Builder le indicará en el paso 2 que actualice el rango en una celda para los elementos que no tengan encabezado.

   **Cambiar encabezados a filtros automáticos de Excel:** solo está disponible si se muestran los encabezados de fila y columna. Esta configuración crea un filtro automático de Excel y lo anexa a los datos que devuelve Report Builder para esta solicitud.

   >[!NOTE]
   >
   >Excel solo admite un filtro automático por hoja de cálculo. Si se crea un nuevo filtro automático en una hoja de cálculo donde ya existe otro, Excel no muestra una advertencia indicando que el filtro automático existente se va a reemplazar.

   **Realizar contorno automático:** transforma la fecha devuelta por Report Builder de una vista de lista a una vista de árbol.

   **Asignar nombre a esta solicitud:** Permite escribir un nombre definido por el usuario para la solicitud, o usar el nombre predeterminado seleccionado en el Paso 1. Este nombre aparece como nombre de [!UICONTROL Informe] en el [!UICONTROL Administrador de solicitudes]. Consulte [Nombrar una solicitud](/help/analyze/legacy-report-builder/layout/name-a-request.md).

1. Haga clic en **[!UICONTROL Aceptar]**.

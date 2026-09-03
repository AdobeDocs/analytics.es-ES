---
description: Obtenga información sobre cómo asignar un nombre al informe y configurar cómo mostrar los encabezados de fila y columna.
title: Cómo dar formato a los encabezados de visualización
uuid: cd0e167b-9463-43fd-87b2-724d1c79de68
feature: Report Builder
role: User, Admin
exl-id: 168daa6b-965c-4f8b-97b7-651a7ad55d6c
TQID: https://experienceleague.adobe.com/n9LlAH6wZ87xQTOO7SLYSpKudcHxuqqielFv6hJXAYw
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7id: f73667dc-d296-4875-8975-ac3fdc3adc42
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 415
ht-degree: 49%

---

# Dar formato a los encabezados

{{legacy-arb}}

Puede asignar un nombre al informe y configurar cómo se muestran los encabezados de fila y columna. El vínculo Opciones de formato está disponible para los tipos Tabla dinámica y Diseño personalizado.

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

   En cuanto al orden de visualización, si la cuadrícula [!UICONTROL Etiqueta de fila] (en el paso 2) contiene un elemento, este se muestra primero en la solicitud. Si no, el sistema utiliza el primer elemento presente en la cuadrícula [!UICONTROL Etiqueta de columna]. Si no existen elementos de fila o columna, se mostrará el primer elemento de la cuadrícula [!UICONTROL Métricas].

   **Mostrar encabezados de columna y fila:** Añade una fila y una columna para mostrar estos elementos.

   En la versión 3.11, se podía mostrar un encabezado para cada elemento. La versión 4 muestra todos estos elementos o ninguno de ellos. Si ha creado una solicitud en la versión 3.11 y la abre en la versión 4.x, Report Builder le indicará en el paso 2 que actualice el rango en una celda para los elementos que no tengan encabezado.

   **Cambiar encabezados a filtros automáticos de Excel:** solo está disponible si se muestran los encabezados de fila y columna. Esta configuración crea un filtro automático de Excel y lo anexa a los datos que devuelve Report Builder para esta solicitud.

   >[!NOTE]
   >
   >Excel solo admite un filtro automático por hoja de cálculo. Si se crea un nuevo filtro automático en una hoja de cálculo donde ya existe otro, Excel no muestra una advertencia indicando que el filtro automático existente se va a reemplazar.

   **Realizar contorno automático:** transforma la fecha devuelta por Report Builder de una vista de lista a una vista de árbol.

   **Asignar nombre a esta solicitud:** Permite escribir un nombre definido por el usuario para la solicitud, o usar el nombre predeterminado seleccionado en el Paso 1. Este nombre aparece como el nombre de [!UICONTROL Informe] en el [!UICONTROL Administrador de solicitudes]. Consulte [Nombrar una solicitud](/help/analyze/legacy-report-builder/layout/name-a-request.md).

1. Haga clic en **[!UICONTROL Aceptar]**.

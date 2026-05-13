---
description: Permite que los usuarios de nivel de administración vean y gestionen informes programados en toda la organización.
title: Cola de informes programados
feature: Admin Tools
uuid: 3fcf92d3-a472-465f-ad7a-c48cd9a8238b
exl-id: 7287e6c7-e354-48a0-9343-35dccfc46e63
role: Admin
TQID: https://experienceleague.adobe.com/HL78cbB5NqKCjv4NvZ5OiqjfbwBjI0KAC8hEr8Afd2U
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
subfeature_v2:
  - id: c80b99d6-98b9-4aeb-b5c4-933ef2ef705c
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 319
ht-degree: 53%

---

# Cola de informes programados

Permite que los usuarios de nivel de administración vean y gestionen informes programados en toda la organización.

**[!UICONTROL Analytics]** > **[!UICONTROL Componentes]** > **[!UICONTROL Todos los componentes]** > **[!UICONTROL Informes programados]**

Algunas funciones de nivel de administración en el Administrador de informes programados son:

* La opción [Mostrar todos los informes programados](/help/components/scheduled-reports-admin.md#section_3F167CAAEEC24140B476CF95B7402690) de su organización.
* [Funciones de filtrado avanzado](/help/components/scheduled-reports-admin.md#section_206A52A85DE84947AAB3AD082FBF6275) en toda la organización.
* La nueva ficha [Cola de informes](/help/components/scheduled-reports-admin.md#section_03C866115D354BB182E90BF4D52F1E0B) que enumera todos los informes que están en cola para su ejecución en servidores de informes.
* Exponiendo el [ID de programa](/help/components/scheduled-reports-admin.md#section_568B70F4228C4229977CB85D2DCD53A1) en la interfaz de la cola de informes.

## Mostrar todos los informes programados {#section_3F167CAAEEC24140B476CF95B7402690}

En la pestaña **[!UICONTROL Lista de informes]**, puede **[!UICONTROL Mostrar todos los informes programados]** en su organización, además de los que programó personalmente.

>[!NOTE]
>
>La columna **[!UICONTROL Nombre del informe]** muestra el nombre del informe que se está programando. La columna **[!UICONTROL Nombre del archivo]** muestra todo nombre de archivo personalizado que haya establecido en las Opciones de envío avanzadas. Como resultado, si se programan varios informes del mismo tipo y se especifican nombres personalizados para cada uno, el Administrador de informes programados mostrará varias entradas con el mismo nombre de informe pero con nombres de archivo diferentes. Esto se debe a que el informe back-end que se programa es el mismo, por lo que la columna Nombre del informe tendría los mismos nombres de informe para todos los archivos excepto para los personalizados (según se hayan configurado).

![](assets/show_all_scheduled_reports.png)

## Funciones de filtro avanzado {#section_206A52A85DE84947AAB3AD082FBF6275}

Por ejemplo, si desea filtrar todos los informes que están programados cada hora, especifique **[!UICONTROL Frecuencia igual a cada hora]** en el filtro **[!UICONTROL Avanzado]** y haga clic en **[!UICONTROL Aplicar]**:

![](assets/advanced_filtering_schedl_reports.png)

## Cola de informes {#section_03C866115D354BB182E90BF4D52F1E0B}

Esta cola le permite administrar y eliminar potencialmente cualquier informe programado que esté &quot;obstruyendo&quot; la cola. (Normalmente, los informes agotan el tiempo de espera después de 4 horas).

![](assets/scheduled_reports_2.png)

La cola de informes también permite omitir un informe programado una vez. Haga clic en el icono azul en la columna **[!UICONTROL Administrar]**.

## ID de programación {#section_568B70F4228C4229977CB85D2DCD53A1}

Si el **[!UICONTROL ID de programación]** está expuesto en la interfaz de la cola de informes es útil cuando necesita ponerse en contacto con el servicio de atención al cliente de Adobe para resolver un problema de los informes programados.

![](assets/schedule_id.png)

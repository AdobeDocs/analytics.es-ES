---
description: Permite que los usuarios de nivel de administración vean y gestionen informes programados en toda la organización.
title: Cola de informes programados
topic: Reports
uuid: 3fcf92d3-a472-465f-ad7a-c48cd9a8238b
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Cola de informes programados

Permite que los usuarios de nivel de administración vean y gestionen informes programados en toda la organización.

**[!UICONTROL Analytics]** > **[!UICONTROL Components]** > **[!UICONTROL Scheduled Reports]**

Algunas funciones de nivel de administración en el Administrador de informes programados son:

* La opción para [mostrar todos los informes](/help/admin/admin/scheduled-reports-admin.md#section_3F167CAAEEC24140B476CF95B7402690) programados de su organización.
* [Funciones](/help/admin/admin/scheduled-reports-admin.md#section_206A52A85DE84947AAB3AD082FBF6275) de filtrado avanzadas en toda la organización.
* La nueva ficha Cola [de](/help/admin/admin/scheduled-reports-admin.md#section_03C866115D354BB182E90BF4D52F1E0B) informes que lista todos los informes que están en cola para su ejecución en servidores sistema de informes.
* Exposición del ID [de](/help/admin/admin/scheduled-reports-admin.md#section_568B70F4228C4229977CB85D2DCD53A1) programación en la interfaz Cola de informes.

## Mostrar todos los informes programados {#section_3F167CAAEEC24140B476CF95B7402690}

En la **[!UICONTROL Report List]** ficha, puede **[!UICONTROL Show All Scheduled Reports]** en su organización, además de las que programó personalmente.

>[!NOTE] La **[!UICONTROL Report Name]** columna muestra el nombre del informe que se está programando y la **[!UICONTROL File Name]** columna muestra cualquier nombre de archivo personalizado configurado por usted en Opciones de Envío avanzadas. Como resultado, si programa varios informes del mismo tipo de informe y especifica nombres personalizados para cada uno, el Administrador de informes programados mostrará varias entradas con el mismo Nombre de informe pero con diferentes nombres de archivo. Esto se debe a que el informe back-end que se está programando es el mismo, de modo que la columna Nombre del informe tendría los mismos nombres de informe para todos los nombres de archivo excepto los personalizados (según se configuró).

![](assets/show_all_scheduled_reports.png)

## Funciones de filtro avanzado {#section_206A52A85DE84947AAB3AD082FBF6275}

For example, if you wanted to filter on all reports that are scheduled hourly, you would specify **[!UICONTROL Frequency equals Hourly]** in the **[!UICONTROL Advanced]** filter and click **[!UICONTROL Apply]**:

![](assets/advanced_filtering_schedl_reports.png)

## Cola de informes {#section_03C866115D354BB182E90BF4D52F1E0B}

Esta cola le permite administrar y potencialmente eliminar cualquier informe programado que esté &quot;obstruyendo&quot; la cola. (Generalmente, los informes agotan el tiempo de espera después de 4 horas).

![](assets/scheduled_reports_2.png)

La cola de informes también le permite &quot;Omitir un informe programado una vez&quot;. Just click the blue icon in the **[!UICONTROL Manage]** column.

## ID de programa {#section_568B70F4228C4229977CB85D2DCD53A1}

Having the **[!UICONTROL Schedule ID]** exposed in the Report Queue interface helps when you need to contact Adobe Client Care for resolution of a scheduled reports issue.

![](assets/schedule_id.png)

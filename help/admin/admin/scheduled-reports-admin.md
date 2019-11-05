---
description: Permite que los usuarios de nivel de administración vean y gestionen informes programados en toda la organización.
seo-description: Permite que los usuarios de nivel de administración vean y gestionen informes programados en toda la organización.
seo-title: Cola de informes programados
solution: Analytics
title: Cola de informes programados
topic: Informes
uuid: 3fcf92d3-a472-465f-ad7a-c48cd9a8238b
translation-type: tm+mt
source-git-commit: 57fe1f6d613b9f54a5191ac8684d36bccfebf4e5

---


# Cola de informes programados

Permite que los usuarios de nivel de administración vean y gestionen informes programados en toda la organización.

**[!UICONTROL Analytics]** &gt; **[!UICONTROL Componentes]** &gt; Informes **[!UICONTROL programados]**

Algunas funciones de nivel de administración en el Administrador de informes programados son:

* La opción [Mostrar todos los informes programados](/help/admin/admin/scheduled-reports-admin.md#section_3F167CAAEEC24140B476CF95B7402690) de su organización.
* [Funciones de filtro avanzado](/help/admin/admin/scheduled-reports-admin.md#section_206A52A85DE84947AAB3AD082FBF6275) de su organización.
* La nueva ficha [Cola de informes](/help/admin/admin/scheduled-reports-admin.md#section_03C866115D354BB182E90BF4D52F1E0B) que enumera todos los informes que están en cola para la ejecución en los servidores de informes.
* Visualización del [ID de programa](/help/admin/admin/scheduled-reports-admin.md#section_568B70F4228C4229977CB85D2DCD53A1) en la interfaz de cola de informe.

## Mostrar todos los informes programados {#section_3F167CAAEEC24140B476CF95B7402690}

En la ficha **[!UICONTROL Lista de informes]**, puede **mostrar todos los informes programados]en su organización, además de los que programó personalmente.[!UICONTROL **

> [!NOTE] La columna Nombre **[!UICONTROL del]** informe muestra el nombre del informe que se está programando y la columna Nombre **[!UICONTROL del]** archivo muestra cualquier nombre de archivo personalizado que haya definido en Opciones de envío avanzadas. En consecuencia, si programa varios informes del mismo tipo de informe y especifica nombres personalizados para cada uno, el Administrador de informes programados mostraría varias entradas con el mismo Nombre de informe pero con diferentes nombres de archivos. Esto se debe que el informe de servidor que se programa es el mismo, por lo que la columna Nombre del informe tendría los mismos nombres de informes para todos excepto los nombres de archivos personalizados (tal como se estableció).

![](assets/show_all_scheduled_reports.png)

## Funciones de filtro avanzado {#section_206A52A85DE84947AAB3AD082FBF6275}

For example, if you wanted to filter on all reports that are scheduled hourly, you would specify **[!UICONTROL Frequency equals Hourly]** in the **[!UICONTROL Advanced]** filter and click **[!UICONTROL Apply]**:

![](assets/advanced_filtering_schedl_reports.png)

## Cola de informes {#section_03C866115D354BB182E90BF4D52F1E0B}

Esta cola le permite gestionar y eliminar potencialmente cualquier informe programado que esté "obstaculizando" la cola. (Generalmente, los informes agotan el tiempo de espera a las 4 horas).

![](assets/scheduled_reports_2.png)

La cola de informes también le proporciona la habilidad de "Omitir el informe programado una vez". Haga clic en el icono azul en la columna **[!UICONTROL Administrar].**

## ID de programa {#section_568B70F4228C4229977CB85D2DCD53A1}

Si el **[!UICONTROL ID de programa]está expuesto en la interfaz de la cola de informe es útil cuando necesita ponerse el contacto con Adobe Client Care para resolver un problema de los informes programados.**

![](assets/schedule_id.png)

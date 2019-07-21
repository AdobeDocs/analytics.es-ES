---
description: Permite que los usuarios de nivel de administración vean y gestionen informes programados en toda la organización.
seo-description: Permite que los usuarios de nivel de administración vean y gestionen informes programados en toda la organización.
seo-title: Cola de informes programados
solution: Analytics
title: Cola de informes programados
topic: 'Informes '
uuid: 3 fcf 92 d 3-a 472-465 f-ad 7 a-c 48 cd 9 a 8238 b
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Cola de informes programados

Permite que los usuarios de nivel de administración vean y gestionen informes programados en toda la organización.

**[!UICONTROL Analytics]** &gt; **[!UICONTROL Componentes]** &gt; **[!UICONTROL Informes programados]**

Algunas funciones de nivel de administración en el Administrador de informes programados son:

* La opción [Mostrar todos los informes programados](../../admin/admin/scheduled-reports-admin.md#section_3F167CAAEEC24140B476CF95B7402690) de su organización.
* [Funciones de filtro avanzado](../../admin/admin/scheduled-reports-admin.md#section_206A52A85DE84947AAB3AD082FBF6275) de su organización.
* La nueva ficha [Cola de informes](../../admin/admin/scheduled-reports-admin.md#section_03C866115D354BB182E90BF4D52F1E0B) que enumera todos los informes que están en cola para la ejecución en los servidores de informes.
* Visualización del [ID de programa](../../admin/admin/scheduled-reports-admin.md#section_568B70F4228C4229977CB85D2DCD53A1) en la interfaz de cola de informe.

## Mostrar todos los informes programados {#section_3F167CAAEEC24140B476CF95B7402690}

En la ficha **[!UICONTROL Lista de informes]**, puede **mostrar todos los informes programados]en su organización, además de los que programó personalmente.[!UICONTROL **

>[!NOTE]
>
>The **[!UICONTROL Report Name]** column displays the name of the report which is being scheduled and the **[!UICONTROL File Name]** column displays any custom file name set by you in Advanced Delivery Options. En consecuencia, si programa varios informes del mismo tipo de informe y especifica nombres personalizados para cada uno, el Administrador de informes programados mostraría varias entradas con el mismo Nombre de informe pero con diferentes nombres de archivos. Esto se debe que el informe de servidor que se programa es el mismo, por lo que la columna Nombre del informe tendría los mismos nombres de informes para todos excepto los nombres de archivos personalizados (tal como se estableció).

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

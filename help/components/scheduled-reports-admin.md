---
description: Permite que los usuarios de nivel de administración vean y gestionen informes programados en toda la organización.
title: Cola de informes programados
feature: Admin Tools
uuid: 3fcf92d3-a472-465f-ad7a-c48cd9a8238b
exl-id: 7287e6c7-e354-48a0-9343-35dccfc46e63
role: Admin
source-git-commit: be5a73347d417c8dc6667d4059e7d46ef5f0f5cd
workflow-type: tm+mt
source-wordcount: '316'
ht-degree: 100%

---

# Cola de informes programados

Permite que los usuarios de nivel de administración vean y gestionen informes programados en toda la organización.

**[!UICONTROL Analytics]** > **[!UICONTROL Componentes]** > **[!UICONTROL Todos los componentes]** > **[!UICONTROL Informes programados]**

Algunas funciones de nivel de administración en el Administrador de informes programados son:

* La opción [Mostrar todos los informes programados](/help/components/scheduled-reports-admin.md#section_3F167CAAEEC24140B476CF95B7402690) de su organización.
* [Funciones de filtro avanzado](/help/components/scheduled-reports-admin.md#section_206A52A85DE84947AAB3AD082FBF6275) de su organización.
* La nueva ficha [Cola de informes](/help/components/scheduled-reports-admin.md#section_03C866115D354BB182E90BF4D52F1E0B) que enumera todos los informes que están en cola para la ejecución en los servidores de informes.
* Visualización del [ID de programa](/help/components/scheduled-reports-admin.md#section_568B70F4228C4229977CB85D2DCD53A1) en la interfaz de cola de informe.

## Mostrar todos los informes programados {#section_3F167CAAEEC24140B476CF95B7402690}

En la pestaña **[!UICONTROL Lista de informes]**, puede **[!UICONTROL Mostrar todos los informes programados]** en su organización, además de los que programó personalmente.

>[!NOTE]
>
>La columna **[!UICONTROL Nombre del informe]** muestra el nombre del informe que se está programando. La columna **[!UICONTROL Nombre del archivo]** muestra todo nombre de archivo personalizado que haya establecido en las Opciones de envío avanzadas. En consecuencia, si programa varios informes del mismo tipo de informe y especifica nombres personalizados para cada uno, el Administrador de informes programados mostraría varias entradas con el mismo Nombre de informe pero con diferentes nombres de archivos. Esto se debe que el informe de servidor que se programa es el mismo, por lo que la columna Nombre del informe tendría los mismos nombres de informes para todos excepto los nombres de archivos personalizados (tal como se estableció).

![](assets/show_all_scheduled_reports.png)

## Funciones de filtro avanzado {#section_206A52A85DE84947AAB3AD082FBF6275}

Por ejemplo, si desea filtrar todos los informes que están programados cada hora, especifique **[!UICONTROL Frecuencia igual a cada hora]** en el filtro **[!UICONTROL Avanzado]** y haga clic en **[!UICONTROL Aplicar]**:

![](assets/advanced_filtering_schedl_reports.png)

## Cola de informes {#section_03C866115D354BB182E90BF4D52F1E0B}

Esta cola le permite gestionar y eliminar potencialmente cualquier informe programado que esté &quot;obstaculizando&quot; la cola. (Generalmente, los informes agotan el tiempo de espera a las 4 horas).

![](assets/scheduled_reports_2.png)

La cola de informes también le proporciona la habilidad de &quot;Omitir el informe programado una vez&quot;. Haga clic en el icono azul en la columna **[!UICONTROL Administrar]**.

## ID de programación {#section_568B70F4228C4229977CB85D2DCD53A1}

Si el **[!UICONTROL ID de programación]** está expuesto en la interfaz de la cola de informes es útil cuando necesita ponerse en contacto con el servicio de atención al cliente de Adobe para resolver un problema de los informes programados.

![](assets/schedule_id.png)

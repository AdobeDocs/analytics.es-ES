---
description: Instrucciones sobre cómo crear una solicitud de Data Warehouse.
title: Configuración general de solicitudes de Data Warehouse
feature: Data Warehouse
exl-id: f564d5a9-78a2-431e-987a-78c4b0b9d31e
source-git-commit: b5095574c31d77b77d310acca8ca6000aa7c5891
workflow-type: tm+mt
source-wordcount: '271'
ht-degree: 27%

---

# Configuración general de solicitudes de Data Warehouse

Hay varias opciones de configuración disponibles al crear una solicitud de Data Warehouse. La siguiente información describe cómo configurar las opciones generales de la solicitud.

Para obtener información sobre cómo empezar a crear una solicitud, así como vínculos a otras opciones de configuración importantes, consulte [Creación de una solicitud de Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md).

Para definir la configuración general de una solicitud de Data Warehouse:

1. Comience a crear una solicitud de Data Warehouse en Adobe Analytics seleccionando **[!UICONTROL Herramientas]** > **[!UICONTROL Data Warehouse]** > [!UICONTROL **Añadir**].

   Para obtener más información, consulte [Creación de una solicitud de Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md).

1. En la página Nueva solicitud de Data Warehouse, seleccione [!UICONTROL **Configuración general**] pestaña.

   ![Pestaña Destino del informe](assets/dw-general-settings.png)

1. Complete los campos siguientes:

   | Opción | Función |
   |---------|----------|
   | Nombre de la solicitud | Este nombre aparece en la página de Data Warehouse principal al administrar solicitudes. |
   | Intervalos de fechas | Seleccione el intervalo de fechas que se incluirá en el informe. <p>Puede elegir fechas personalizadas o un intervalo de fechas preestablecido. Los intervalos preestablecidos son relativos a la fecha en la que se envía el informe.</p><p>Estas son las opciones preestablecidas disponibles:</p><ul><li>Hoy</li><li>Ayer</li><li>Últimos 7 días</li><li>Últimos 30 días</li><li>Esta semana</li><li>Última semana</li><li>Últimas 2 semanas</li><li>Últimas 3 semanas</li><li>Últimas 4 semanas</li><li>Este mes</li><li>Mes pasado</li><li>Última hora</li></ul> |
   | Granularidad | <!--what does this setting do? It's not the schedule/frequency... --> La granularidad de tiempo. Los valores válidos son Ninguno, Hora, Día, Semana, Mes, Trimestre y Año.<p>Registrar la granularidad requiere tiempos de procesamiento más prolongados. Si se desea registrar la granularidad mensual de todo un año, los informes se procesarán mucho más rápido si se envía una solicitud de informe cada mes.</p> <!-- Make this into a new row: Make available to users in your organization - All data warehouse requests are visible only to you and any system administrators. Enable this option if you want to make the request visible to everyone in your organization. <p>Enabling this option is useful if you want other users in your organization to help create or update the request.</p>--> |

   {style="table-layout:auto"}

1. Siga configurando la solicitud de Data Warehouse en [!UICONTROL **Genere su informe**] pestaña. Para obtener más información, consulte [Creación de un informe para una solicitud de Data Warehouse](/help/export/data-warehouse/create-request/dw-request-build-report.md).

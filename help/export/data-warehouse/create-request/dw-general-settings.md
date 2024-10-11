---
description: Instrucciones sobre cómo crear una solicitud de Data Warehouse.
title: Configuración general de solicitudes de Data Warehouse
feature: Data Warehouse
exl-id: f564d5a9-78a2-431e-987a-78c4b0b9d31e
source-git-commit: 1e1a26b8595ca026fb049322125a6f91d9d5513c
workflow-type: tm+mt
source-wordcount: '399'
ht-degree: 32%

---

# Configuración general de solicitudes de Data Warehouse

Hay varias opciones de configuración disponibles al crear una solicitud de Data Warehouse. La siguiente información describe cómo configurar las opciones generales de la solicitud.

Para obtener información sobre cómo empezar a crear una solicitud, así como vínculos a otras opciones de configuración importantes, consulte [Crear una solicitud de Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md).

Para definir la configuración general de una solicitud de Data Warehouse:

1. Comience a crear una solicitud de Data Warehouse en Adobe Analytics seleccionando **[!UICONTROL Herramientas]** > **[!UICONTROL Data Warehouse]** > [!UICONTROL **Agregar**].

   Para obtener más información, consulte [Crear una solicitud de Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md).

1. En la página Nueva solicitud de Data Warehouse, seleccione la ficha [!UICONTROL **Configuración general**].

   ![Pestaña Destino del informe](assets/dw-general-settings.png)

1. Complete los campos siguientes:

   | Opción | Función |
   |---------|----------|
   | Nombre de la solicitud | Este nombre aparece en la página de Data Warehouse principal al administrar solicitudes. |
   | Intervalos de fechas | Seleccione el intervalo de fechas que se incluirá en el informe. <p>Puede elegir fechas personalizadas o un intervalo de fechas preestablecido. Los intervalos preestablecidos son relativos a la fecha en la que se envía el informe.</p><p>Estas son las opciones preestablecidas disponibles:</p><ul><li>Hoy</li><li>Ayer</li><li>Últimos 7 días</li><li>Últimos 30 días</li><li>Esta semana</li><li>Última semana</li><li>Últimas 2 semanas</li><li>Últimas 3 semanas</li><li>Últimas 4 semanas</li><li>Este mes</li><li>Mes pasado</li><li>Última hora</li></ul> |
   | Granularidad | La granularidad de tiempo. Los valores válidos son Ninguno, Hora, Día, Semana, Mes, Trimestre y Año.<p>Registrar la granularidad requiere tiempos de procesamiento más prolongados. Si se desea registrar la granularidad mensual de todo un año, los informes se procesarán mucho más rápido si se envía una solicitud de informe cada mes.</p><p>**Nota:** Al aplicar la granularidad en una solicitud de Data Warehouse, se agrega la columna &#39;Fecha&#39; al informe. Según la granularidad seleccionada, el formato de fecha cambia de la siguiente manera:</p><ul><li>**Granularidad horaria**:<ul> <li>**Formato**: `mmmm d, yyyy` Hora `H`</li><li>**Ejemplo**: 1 de enero de 20XX, hora 0 </li></ul><li>**Granularidad diaria**:<ul> <li>**Formato**: `mmmm d, yyyy`</li><li>**Ejemplo**: 1 de enero de 20XX</li></ul><li>**Granularidad semanal**:<ul> <li>**Formato**: Semana `w, yyyy`</li><li>**Ejemplo**: Semana 1, 20XX </li></ul><li>**Granularidad mensual**:<ul> <li>**Formato**: `mmmm yyyy`</li><li>**Ejemplo**: 20 de enero </li></ul><li>**Granularidad trimestral**:<ul> <li>**Formato**: `q` Trimestre `yyyy`</li><li>**Ejemplo**: Primer trimestre de 20XX </li></ul><li>**Granularidad anual**:<ul> <li>**Formato**: `yyyy`</li><li>**Ejemplo**: 20XX</li></ul> |
   | Poner a disposición de los usuarios de su organización | Todas las solicitudes del Data Warehouse solo son visibles para usted y para los administradores del sistema. Active esta opción si desea que la solicitud sea visible para todos los miembros de su organización. <p>Habilitar esta opción resulta útil si desea que otros usuarios de su organización ayuden a crear o actualizar la solicitud.</p> |

   {style="table-layout:auto"}

1. Siga configurando la solicitud de Data Warehouse en la ficha [!UICONTROL **Generar el informe**]. Para obtener más información, consulte [Crear un informe para una solicitud de Data Warehouse](/help/export/data-warehouse/create-request/dw-request-build-report.md).

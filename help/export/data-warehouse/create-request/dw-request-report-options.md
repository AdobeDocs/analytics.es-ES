---
description: Instrucciones sobre cómo crear una solicitud de Data Warehouse.
title: Configuración de las opciones de informes de una solicitud de Data Warehouse
feature: Data Warehouse
source-git-commit: 0abf0c76f38b481c0b72d113fe49e0da03ddd8cd
workflow-type: tm+mt
source-wordcount: '492'
ht-degree: 18%

---

# Configuración de las opciones de informes de una solicitud de Data Warehouse

>[!AVAILABILITY]
>
>Algunas de las funciones de Data Warehouse descritas en este artículo (y otros artículos de Data Warehouse en esta sección) están disponibles solamente en la fase de Prueba limitada de la versión y es posible que aún no estén disponibles en su entorno.
>
>Para obtener información sobre las funciones que aún no están disponibles para todos los clientes, así como sobre la cronología de lanzamiento de estas funciones, consulte la [notas de la versión](/help/release-notes/latest.md).
>
>Esta nota se eliminará cuando la funcionalidad esté disponible de forma general. Para obtener información sobre el proceso de lanzamiento de Analytics, consulte [Lanzamientos de funciones de Adobe Analytics](/help/release-notes/releases.md).

Hay varias opciones de configuración disponibles al crear una solicitud de Data Warehouse. La siguiente información describe cómo configurar las opciones del informe para la solicitud.

Para obtener información sobre cómo empezar a crear una solicitud, así como vínculos a otras opciones de configuración importantes, consulte [Creación de una solicitud de Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md).

Para configurar las opciones de informe de una solicitud de Data Warehouse:

1. Comience a crear una solicitud en Adobe Analytics seleccionando **[!UICONTROL Herramientas]** > **[!UICONTROL Data Warehouse]** > [!UICONTROL **Añadir**].

   Para obtener más información, consulte [Creación de una solicitud de Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md).

1. En la página Nueva solicitud de Data Warehouse, seleccione [!UICONTROL **Opciones de informe**] pestaña.

   ![Pestaña Destino del informe](assets/dw-report-options.png) <!-- update screenshot to include Sort by metrics -->

1. Complete los campos siguientes:

   | Opción | Función |
   |---------|----------|
   | Nombre del archivo | Identifica el informe. |
   | Anexar intervalo de fechas del informe al nombre del archivo | Agrega el intervalo de fechas al nombre del archivo de informe. <p>Por ejemplo, si solicita datos del 1 al 7 de mayo de 2024, el nombre de archivo incluye el intervalo de fechas 20240501 - 20240507.</p> |
   | CSV | Ofrece informes en formato de archivo CSV para ver los datos en una hoja de cálculo. |
   | Tableau (TDE) | Presenta informes en formato de archivo Tableau Data Extract (TDE), que se puede utilizar para visualizar datos y capas en datos adicionales dentro de Tableau. |
   | Enviar informe como archivo comprimido (ZIP) | Presenta informes en un formato de archivo comprimido (ZIP). Se recomienda habilitar esta opción al utilizar el correo electrónico como [destino del informe](/help/export/data-warehouse/create-request/dw-request-report-destinations.md). |
   | Número de filas de la tabla | El número de filas que se pueden incluir en el informe. Utilice 0 para incluir todas las filas (esta es la selección predeterminada). <!-- when would you want to limit the rows? To improve performance? Do we have recommendations? --> |
   | Comentarios | Agregue los comentarios que desee incluir en el informe. Los comentarios aparecen al principio del informe. |
   | Ordenar por métricas | Proporciona informes de desgloses clasificados en Data Warehouse, ordenados por el valor de métrica descendente. La ordenación por métrica permite interpretar más fácilmente los informes de Data Warehouse, así como compararlos más fácilmente con otras vistas de informes de desgloses de Analytics.<p>Para obtener más información, consulte [Ordenar por métrica](/help/export/data-warehouse/sorting-by-metric.md).</p> |
   | Enviar archivo de manifiesto | Incluye metadatos sobre los archivos incluidos en el informe.<!-- What kind of metadata is included in the manifest file? --> |
   | Enviar archivo de firma digital | Permite a los destinatarios del informe comprobar que el archivo proviene del Adobe y que no se ha alterado. |
   | Enviar un archivo vacío cuando no haya datos en el informe | Envía un informe incluso cuando el informe no contiene datos. |

   {style="table-layout:auto"}

1. Siga configurando la solicitud de Data Warehouse en [!UICONTROL **Opciones de programación**] pestaña. Para obtener más información, consulte [Configuración de las opciones de programación para una solicitud de Data Warehouse](/help/export/data-warehouse/create-request/dw-request-scheduling.md).
---
description: Instrucciones sobre cómo crear una solicitud de Data Warehouse.
title: Configuración de las opciones de informes de una solicitud de Data Warehouse
feature: Data Warehouse
source-git-commit: 6e6a406c7f3ab6ad83dcf60dbd78a5f6953f1fbb
workflow-type: tm+mt
source-wordcount: '532'
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
   | [!UICONTROL **Nombre del archivo**] | Identifica el informe. <p>Si se utiliza cualquiera de los siguientes caracteres especiales en el nombre del archivo, la solicitud no se puede guardar: <code>! &quot; # $ &amp; &#39; ( ) * + , / : ; > = &lt; ? @ [ ] \ ^ ` {  } \| ~</code> </p><p>El carácter % solo se puede usar si va seguido de &quot;R&quot;, &quot;rsid&quot; o &quot;id&quot;, como se indica a continuación: <code>%R</code>, <code>%rsid</code>, y <code>%id</code>.</p> |
   | [!UICONTROL **Anexar intervalo de fechas del informe al nombre del archivo**] | Agrega el intervalo de fechas al nombre del archivo de informe. <p>Por ejemplo, si solicita datos del 1 al 7 de mayo de 2024, el nombre de archivo incluye el intervalo de fechas 20240501 - 20240507.</p> |
   | [!UICONTROL **CSV**] | Ofrece informes en formato de archivo CSV para ver los datos en una hoja de cálculo. |
   | [!UICONTROL **Tableau (TDE)**] | Presenta informes en formato de archivo Tableau Data Extract (TDE), que se puede utilizar para visualizar datos y capas en datos adicionales dentro de Tableau. |
   | [!UICONTROL **Enviar informe como archivo comprimido (ZIP)**] | Presenta informes en un formato de archivo comprimido (ZIP). Se recomienda habilitar esta opción al utilizar el correo electrónico como [destino del informe](/help/export/data-warehouse/create-request/dw-request-report-destinations.md). |
   | [!UICONTROL **Devolver todas las filas**] | Cuando se habilita, todas las filas se incluyen en el informe. Desactive esta opción para especificar el número de filas que desea incluir. |
   | [!UICONTROL **Comentarios al principio del informe**] | Agregue los comentarios que desee incluir en el informe. Los comentarios aparecen al principio del informe. |
   | [!UICONTROL **Ordenar por métricas**] | Proporciona informes de desgloses clasificados en Data Warehouse, ordenados por el valor de métrica descendente. La ordenación por métrica permite interpretar más fácilmente los informes de Data Warehouse, así como compararlos más fácilmente con otras vistas de informes de desgloses de Analytics.<p>Para obtener más información, consulte [Ordenar por métrica](/help/export/data-warehouse/sorting-by-metric.md).</p> |
   | [!UICONTROL **Enviar un archivo de manifiesto**] | Incluye metadatos sobre los archivos incluidos en el informe.<!-- What kind of metadata is included in the manifest file? --> |
   | [!UICONTROL **Enviar un archivo de firma digital**] | Permite a los destinatarios del informe comprobar que el archivo proviene del Adobe y que no se ha alterado. |
   | [!UICONTROL **Enviar un archivo vacío cuando no haya datos en el informe**] | Envía un informe incluso cuando el informe no contiene datos. |

   {style="table-layout:auto"}

1. Siga configurando la solicitud de Data Warehouse en [!UICONTROL **Opciones de programación**] pestaña. Para obtener más información, consulte [Configuración de las opciones de programación para una solicitud de Data Warehouse](/help/export/data-warehouse/create-request/dw-request-scheduling.md).

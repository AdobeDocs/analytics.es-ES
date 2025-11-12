---
description: Instrucciones sobre cómo crear una solicitud de Data Warehouse.
title: Configuración de opciones de informes para una solicitud de Data Warehouse
feature: Data Warehouse
exl-id: b273bddb-431c-44d9-82a5-cb088829b3a3
source-git-commit: ca84a5f807545d7196e2e0e90d3209c32d3fd789
workflow-type: tm+mt
source-wordcount: '453'
ht-degree: 22%

---

# Configuración de opciones de informes para una solicitud de Data Warehouse

Hay varias opciones de configuración disponibles al crear una solicitud de Data Warehouse. La siguiente información describe cómo configurar las opciones del informe para la solicitud.

Para obtener información sobre cómo empezar a crear una solicitud, así como vínculos a otras opciones de configuración importantes, consulte [Crear una solicitud de Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md).

Para configurar las opciones de informes de una petición Data Warehouse:

1. Si aún no lo ha hecho, empiece a crear una solicitud en Adobe Analytics seleccionando **[!UICONTROL Herramientas]** > **[!UICONTROL Data Warehouse]** > [!UICONTROL **Añadir**].

   Para obtener más información, consulte [Crear una solicitud de Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md).

1. En la página Nueva solicitud de Data Warehouse, seleccione la pestaña [!UICONTROL **Opciones de informe**].

   ![Ficha de destino del informe](assets/dw-report-options.png) <!-- update screenshot to include Sort by metrics -->

1. Complete los campos siguientes:

   | Opción | Función |
   |---------|----------|
   | [!UICONTROL **Nombre de archivo**] | Identifica el informe. <p>Si se usa alguno de los siguientes caracteres especiales en el nombre de archivo, la solicitud no se puede guardar: <code>. &quot; # $ &amp; &#39; ( ) * + , / : ; > = &lt; ? @ [ ] \ ^ &grave; { } \| ~</code> </p><p>El carácter % solo se puede usar si va seguido de &quot;R&quot;, &quot;rsid&quot; o &quot;id&quot;, como se indica a continuación: <code>%R</code>, <code>%rsid</code>y <code>%id</code>.</p> |
   | [!UICONTROL **Anexar intervalo de fechas del informe al nombre de archivo**] | Agrega el intervalo de fechas al nombre del archivo de informe. <p>Por ejemplo, si solicita datos del 1 al 7 de mayo de 2024, el nombre de archivo incluye el intervalo de fechas 20240501 - 20240507.</p> |
   | [!UICONTROL **CSV**] | Ofrece informes en formato de archivo CSV para ver los datos en una hoja de cálculo. |
   | [!UICONTROL **Tableau (TDE)**] | Presenta informes en formato de archivo Tableau Data Extract (TDE), que se puede utilizar para visualizar datos y capas en datos adicionales dentro de Tableau. |
   | [!UICONTROL **Enviar informe como archivo comprimido (ZIP)**] | Presenta informes en un formato de archivo comprimido (ZIP). Se recomienda habilitar esta opción cuando se use el correo electrónico como [destino del informe](/help/export/data-warehouse/create-request/dw-request-report-destinations.md). |
   | [!UICONTROL **Devolver todas las filas**] | Cuando se habilita, todas las filas se incluyen en el informe. Desactive esta opción para especificar el número de filas que desea incluir. |
   | [!UICONTROL **Principio de los comentarios del informe**] | Agregue los comentarios que desee incluir en el informe. Los comentarios aparecen al principio del informe. |
   | [!UICONTROL **Ordenar por métricas**] | Proporciona informes de desgloses clasificados en Data Warehouse, ordenados por un valor de métrica descendente. La ordenación por métrica permite interpretar más fácilmente los informes de Data Warehouse, así como compararlos más fácilmente con otras vistas de informes de desgloses de Analytics.<p>Para obtener más información, vea [Ordenar por métrica](/help/export/data-warehouse/sorting-by-metric.md).</p> |
   | [!UICONTROL **Enviar un archivo de manifiesto**] | Incluye metadatos sobre los archivos incluidos en el informe.<!-- What kind of metadata is included in the manifest file? --> |
   | [!UICONTROL **Enviar un archivo de firma digital**] | Permite a los destinatarios del informe comprobar que el archivo proviene de Adobe y que no se ha alterado. |
   | [!UICONTROL **Enviar un archivo vacío cuando no haya datos en el informe**] | Envía un informe incluso cuando el informe no contiene datos. |

   {style="table-layout:auto"}

1. Siga configurando la solicitud de Data Warehouse en la ficha [!UICONTROL **Opciones de programación**]. Para obtener más información, consulte [Configurar opciones de programación para una solicitud de Data Warehouse](/help/export/data-warehouse/create-request/dw-request-scheduling.md).

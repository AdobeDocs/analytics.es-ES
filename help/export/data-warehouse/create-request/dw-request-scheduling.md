---
description: Instrucciones sobre cómo crear una solicitud de Data Warehouse.
title: Configuración del destino de un informe para una solicitud de Data Warehouse
feature: Data Warehouse
source-git-commit: 3b116cb8d0d3f3eb86b512d712f37b29876f2b22
workflow-type: tm+mt
source-wordcount: '375'
ht-degree: 15%

---

# Configuración de las opciones de programación para una solicitud de Data Warehouse

>[!AVAILABILITY]
>
>Algunas de las funciones de Data Warehouse descritas en este artículo (y otros artículos de Data Warehouse en esta sección) están disponibles solamente en la fase de Prueba limitada de la versión y es posible que aún no estén disponibles en su entorno.
>
>Para obtener información sobre las funciones que aún no están disponibles para todos los clientes, así como sobre la cronología de lanzamiento de estas funciones, consulte la [notas de la versión](/help/release-notes/latest.md).
>
>Esta nota se eliminará cuando la funcionalidad esté disponible de forma general. Para obtener información sobre el proceso de lanzamiento de Analytics, consulte [Lanzamientos de funciones de Adobe Analytics](/help/release-notes/releases.md).

Hay varias opciones de configuración disponibles al crear una solicitud de Data Warehouse. En la siguiente información se describe cómo configurar las opciones de programación de la solicitud.

Para obtener información sobre cómo empezar a crear una solicitud, así como vínculos a otras opciones de configuración importantes, consulte [Creación de una solicitud de Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md).

Para configurar las opciones de programación de una solicitud de Data Warehouse:

1. Comience a crear una solicitud en Adobe Analytics seleccionando **[!UICONTROL Herramientas]** > **[!UICONTROL Data Warehouse]** > [!UICONTROL **Añadir**].

   Para obtener más información, consulte [Creación de una solicitud de Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md).

1. En la página Nueva solicitud de Data Warehouse, seleccione [!UICONTROL **Opciones de programación**] pestaña.

   ![Pestaña Destino del informe](assets/dw-scheduling-options.png) <!-- update screenshot -->

1. Complete los campos siguientes:

   | Opción | Función |
   |---------|----------|
   | [!UICONTROL **Enviar informe ahora**] | Envía el informe como un informe de un solo uso. Cuando se selecciona esta opción, se ocultan todas las opciones de programación. |
   | [!UICONTROL **Programar para más tarde**] | Proporciona opciones para programar la entrega de informes. A continuación se describen todas las opciones. |
   | [!UICONTROL **Frecuencia del informe**] | Frecuencia con la que se entregan los informes. <p>Las opciones disponibles son las siguientes:</p><ul><li>Por hora</li><p>[!UICONTROL **Por hora**] solo está disponible cuando la variable [!UICONTROL **Intervalos de fechas**] opción en la [!UICONTROL **Configuración general**] La pestaña está configurada en [!UICONTROL **Última hora**].</p><li>Diario</li><li>Semanal</li><li>Mensual</li><li>Anual</li></ul><p>Se mostrarán opciones adicionales en función de la frecuencia seleccionada.</p> |
   | [!UICONTROL **Comienza el**] | La fecha en la que debería comenzar la nueva programación. |
   | [!UICONTROL **Hora del día**] | Hora del día a la que se debe enviar el informe. |
   | [!UICONTROL **Opciones de finalización de envío**] | Elija cuándo finalizar los envíos programados. Puede elegir entre no finalizar nunca, finalizar después de un número determinado de incidencias o finalizar en una fecha determinada. |

   {style="table-layout:auto"}

1. Siga configurando la solicitud de Data Warehouse en [!UICONTROL **Correo electrónico de notificación**] pestaña. Para obtener más información, consulte [Configuración de un correo electrónico de notificación para una solicitud de Data Warehouse](/help/export/data-warehouse/create-request/dw-request-email.md).


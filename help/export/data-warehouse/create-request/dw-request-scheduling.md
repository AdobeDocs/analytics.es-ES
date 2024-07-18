---
description: Instrucciones sobre cómo crear una solicitud de Data Warehouse.
title: Configuración del destino de un informe para una solicitud de Data Warehouse
feature: Data Warehouse
exl-id: e5f8acaa-156f-41fb-a0fc-bc5475f1f3b7
source-git-commit: 4e4b5e1c362778223be01f78b173a698c53f9b32
workflow-type: tm+mt
source-wordcount: '291'
ht-degree: 33%

---

# Configuración de las opciones de programación para una solicitud de Data Warehouse

Hay varias opciones de configuración disponibles al crear una solicitud de Data Warehouse. En la siguiente información se describe cómo configurar las opciones de programación de la solicitud.

Para obtener información sobre cómo empezar a crear una solicitud, así como vínculos a otras opciones de configuración importantes, consulte [Crear una solicitud de Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md).

Para configurar las opciones de programación de una solicitud de Data Warehouse:

1. Si aún no lo ha hecho, empiece a crear una solicitud en Adobe Analytics seleccionando **[!UICONTROL Herramientas]** > **[!UICONTROL Data Warehouse]** > [!UICONTROL **Añadir**].

   Para obtener más información, consulte [Crear una solicitud de Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md).

1. En la página Nueva solicitud de Data Warehouse, seleccione la ficha [!UICONTROL **Opciones de programación**].

   ![Ficha de destino del informe](assets/dw-scheduling-options.png) <!-- update screenshot -->

1. Complete los campos siguientes:

   | Opción | Función |
   |---------|----------|
   | [!UICONTROL **Enviar informe ahora**] | Envía el informe como un informe de un solo uso. Cuando se selecciona esta opción, se ocultan todas las opciones de programación. |
   | [!UICONTROL **Programar para más tarde**] | Proporciona opciones para programar la entrega de informes. A continuación se describen todas las opciones. |
   | [!UICONTROL **Frecuencia del informe**] | Frecuencia con la que se entregan los informes. <p>Las opciones disponibles son las siguientes:</p><ul><li>Por hora</li><p>[!UICONTROL **Cada hora**] solo está disponible cuando la opción [!UICONTROL **Intervalos de fechas**] de la ficha [!UICONTROL **Configuración general**] está establecida en [!UICONTROL **Última hora**].</p><li>Diario</li><li>Semanal</li><li>Mensual</li><li>Anual</li></ul><p>Se mostrarán opciones adicionales en función de la frecuencia seleccionada.</p> |
   | [!UICONTROL **A partir de**] | La fecha en la que debería comenzar la nueva programación. |
   | [!UICONTROL **Hora del día**] | Hora del día a la que se debe enviar el informe. |
   | [!UICONTROL **Opciones de finalización de envío**] | Elija cuándo finalizar los envíos programados. Puede elegir entre no finalizar nunca, finalizar después de un número determinado de incidencias o finalizar en una fecha determinada. |

   {style="table-layout:auto"}

1. Siga configurando la solicitud de Data Warehouse en la ficha [!UICONTROL **Correo electrónico de notificación**]. Para obtener más información, consulte [Configuración de un correo electrónico de notificación para una solicitud de Data Warehouse](/help/export/data-warehouse/create-request/dw-request-email.md).

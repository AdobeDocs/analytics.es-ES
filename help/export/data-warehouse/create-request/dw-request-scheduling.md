---
description: Instrucciones sobre cómo crear una solicitud de Data Warehouse.
title: Configuración del destino de un informe para una solicitud de Data Warehouse
feature: Data Warehouse
source-git-commit: 393355cd971f264da3e3e1b8736f5752fc4bdc62
workflow-type: tm+mt
source-wordcount: '442'
ht-degree: 13%

---

# Configuración de las opciones de programación para una solicitud de Data Warehouse

{{release-limited-testing}}

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
   | Enviar informe ahora | Envía el informe como un informe de un solo uso. Cuando se selecciona esta opción, se ocultan todas las opciones de programación. |
   | Programar para más tarde | Proporciona opciones para programar la entrega de informes. A continuación se describen todas las opciones. |
   | Frecuencia del informe | Frecuencia con la que se entregan los informes. <p>Las opciones disponibles son las siguientes:</p><ul><li>Por hora</li><p>[!UICONTROL **Por hora**] solo está disponible cuando la variable [!UICONTROL **Intervalos de fechas**] opción en la [!UICONTROL **Configuración general**] La pestaña está configurada en [!UICONTROL **Última hora**].</p><li>Diario</li><li>Semanal</li><li>Mensual</li><li>Anual</li></ul>  <!-- Is this valid? Was in the old docs: "To schedule Data Warehouse requests for Daily, Weekly, Monthly, or Yearly, make sure *Preset* is correctly selected" --> |
   | Periodicidad mensual | Intervalo entre meses entre el momento en que se envía el informe. |
   | Día del mes | La fecha cada mes en que se envía el informe.<p>Cuando esta opción está disponible, la variable [!UICONTROL **Semana del mes**] y [!UICONTROL **Día de la semana**] Las opciones de no son. Seleccione el [!UICONTROL **Formato alternativo**] botón para alternar hacia atrás y adelante. </p> |
   | Semana del mes | La semana de cada mes en que se debe enviar el informe. <p>Las opciones disponibles son las siguientes:</p><ul><li>Primero</li><li>Segundo</li><li>Tercero</li><li>Cuarto</li><p>Envíe el informe la cuarta semana, incluso en los meses con 5 semanas. Elegir [!UICONTROL **Último**] si desea que el informe se envíe la última semana de cada mes.</p><li>Última posición</li></ul><p>Cuando esta opción está disponible, la variable [!UICONTROL **Día del mes**] La opción no está disponible. Seleccione el [!UICONTROL **Formato alternativo**] botón para alternar hacia atrás y adelante. </p> |
   | Día de la semana | El día de la semana en que se debe enviar el informe. <p>Cuando esta opción está disponible, la variable [!UICONTROL **Día del mes**] La opción no está disponible. Seleccione el [!UICONTROL **Formato alternativo**] botón para alternar hacia atrás y adelante. </p> |
   | Comienza el | La fecha en la que debería comenzar la nueva programación. |
   | Hora del día | Hora del día a la que se debe enviar el informe. |
   | Opciones de finalización de envío | Elija cuándo finalizar los envíos programados. Puede elegir entre no finalizar nunca, finalizar después de un número determinado de incidencias o finalizar en una fecha determinada. |

   {style="table-layout:auto"}

1. Siga configurando la solicitud de Data Warehouse en [!UICONTROL **Correo electrónico de notificación**] pestaña. Para obtener más información, consulte [Configuración de un correo electrónico de notificación para una solicitud de Data Warehouse](/help/export/data-warehouse/create-request/dw-request-email.md).


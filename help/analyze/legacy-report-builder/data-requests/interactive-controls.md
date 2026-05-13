---
description: Los controles interactivos permiten editar segmentos e intervalos de fechas para una o más solicitudes directamente desde la hoja de cálculo. Esto le proporciona una mayor flexibilidad al actualizar solicitudes de Report Builder.
title: Controles interactivos
feature: Report Builder
role: User, Admin
exl-id: 2340ff31-1478-4a54-a4c3-c51e73c39109
TQID: https://experienceleague.adobe.com/I1Lw6gp33QByF6J9SZRgTdn30CpdhJH3yWZ5XwOkBqc
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: c153fd90-23e1-4614-81d3-3cc7571227f7id: f73667dc-d296-4875-8975-ac3fdc3adc42
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 603
ht-degree: 29%

---

# Controles interactivos

{{legacy-arb}}

Los controles interactivos permiten editar segmentos e intervalos de fechas para una o más solicitudes directamente desde la hoja de cálculo. Esto le proporciona una mayor flexibilidad al actualizar solicitudes de Report Builder.

Los controles interactivos se crearon en respuesta a un flujo de trabajo común en el que los analistas crean libros de trabajo y los comparten con la organización de marketing. Los controles interactivos proporcionan a los especialistas en marketing la capacidad de modificar y actualizar las solicitudes sin tener que tener conocimientos en profundidad de cómo funciona Report Builder. (Tenga en cuenta que para actualizar una solicitud, el destinatario del libro debe ser un usuario de Report Builder). Estos controles funcionan en libros programados. Actualmente hay disponibles dos tipos de controles interactivos:

* Intervalo de fecha móvil
* Segmentos

>[!IMPORTANT]
>
>Debe tener Report Builder 5.0 instalado para que funcionen los controles interactivos. >
>* Si ejecuta Microsoft Excel en Windows pero ejecuta una versión anterior de Report Builder o si no tiene Report Builder instalado: puede cambiar el valor en el control interactivo, pero no actualizará la solicitud asociada, ni actualizará los parámetros asociados a la solicitud.
>* Si ejecuta Excel en Mac y cambia el valor en el control provocará que se muestre el siguiente mensaje: “No se encuentra la macro &#39;Adobe.ReportBuilder.Bridge.FormControlClick.Event’”.
>

>[!WARNING]
>
>No manipule el nombre del control. (Para ver el nombre, establezca el foco en el control y aparecerá el nombre de control directamente sobre la cuadrícula de Excel, en la esquina superior izquierda).

## Implementación del control de intervalo de fecha interactivo {#section_39B228F2D2C44985863D31424C953280}

1. En el paso 1 del Asistente para solicitudes, seleccione, por ejemplo, el informe **[!UICONTROL Página]**.
1. Junto al menú desplegable de **[!UICONTROL Fechas más utilizadas]**, haga clic en el icono **[!UICONTROL Configuración de controles]**:

   ![Captura de pantalla del Paso 1 del Asistente para solicitudes que resalta el icono Configuración de control. ](assets/date_range_control.png)

1. En el cuadro de diálogo Configuración de control, seleccione todos los elementos de intervalo de fechas que desee que se muestren en el control interactivo. Además, especifique la ubicación de la celda superior izquierda del control.

   ![Captura de pantalla que muestra los elementos de intervalo de fechas seleccionados y la ubicación de la celda superior izquierda.](assets/control_settings.png)

1. Tenga en cuenta la opción para “Actualizar automáticamente las solicitudes vinculadas al seleccionar el elemento”.

   * Si esta opción está activada, se actualizan todas las solicitudes que utilizan este control.
   * Si no se selecciona, los parámetros de solicitud asociados se actualizan, pero la solicitud no se actualiza.

1. Haga clic en **[!UICONTROL Aceptar]**. El control aparece en la ubicación de celda especificada:

1. Ahora puede cambiar el intervalo de fechas y la solicitud se actualizará con ese intervalo.

   ![Captura de pantalla que muestra el intervalo de fechas seleccionado.](assets/date_range_control_interactive.png)

1. También puede copiar la solicitud y hacer clic con el botón derecho para utilizar una de las dos opciones de Pegar solicitud:

   * **[!UICONTROL Pegar solicitud]** > **[!UICONTROL Usar celda de entrada absoluta]**. Esto significa que la solicitud copiada señalará al mismo control de intervalo de fechas interactivo que la solicitud original.

   * **[!UICONTROL Pegar solicitud]** > **[!UICONTROL Utilizar celda de entrada relativa]**. Esto significa que la solicitud copiada señalará a su propio control.

     >[!NOTE]
     >
     >Puede utilizar la función de control nativa de Microsoft Excel de cortar/copiar/pegar. Report Builder reconoce automáticamente los controles recientemente añadidos.

## Implementación del control de segmento interactivo {#section_5003D3F724644280BF1BCD6E1B0CB784}

Implementar el control de segmento interactivo es similar a implementar el control de intervalo de fechas.

1. En el paso 1 del Asistente para solicitudes, junto a la lista desplegable **[!UICONTROL Segmento]**, seleccione el icono Configuración del control de segmentos:

   ![Captura de pantalla del icono Configuración de control de segmentos.](assets/segment_interactive_1.png)

1. En el cuadro de diálogo Configuración del control de segmentos, seleccione los segmentos que desea incluir en la lista desplegable. Además, especifique la ubicación de la celda superior izquierda del control.

   ![Captura de pantalla que muestra la configuración de control de segmentos con los segmentos seleccionados y la ubicación de la celda.](assets/segment_drop_down_properties.png)

1. El nuevo control interactivo aparecerá ahora en el libro:

   ![Captura de pantalla que muestra el nuevo control interactivo seleccionado.](assets/segment_interactive_3.png)

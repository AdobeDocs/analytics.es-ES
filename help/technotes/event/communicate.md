---
title: Comunicar el impacto a los usuarios
description: Aprenda formas eficaces de comunicar el impacto de un evento en su organización.
exl-id: 9ba83f3f-2eea-44c2-80b2-a0a9111d51cf
feature: Event
source-git-commit: 811e321ce96aaefaeff691ed5969981a048d2c31
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Comunicar el impacto del evento a los usuarios

Si tiene datos [afectado por un evento](overview.md)Además, es importante comunicar ese evento a los usuarios de su organización.

* Desarrolle una exención de responsabilidad común que pueda utilizar en las comunicaciones para mantener la coherencia
* Proporcionar una comunicación continua a los usuarios de Analytics y a las partes interesadas clave durante y después del evento
* Coloque un recordatorio de calendario para los hitos siguientes, como el mes o año siguiente. Esta comunicación futura le ayudará a recordar a los usuarios que visualicen informes el impacto de los mismos en informes mes tras mes o año tras año.

En Adobe Analytics, las secciones siguientes muestran diferentes formas de comunicarse con los usuarios de su organización. También puede utilizar otros métodos fuera de Adobe Analytics, como el correo electrónico, para comunicarse con los usuarios.

## Comunicarse mediante descripciones de paneles o visualizaciones

Si tiene un proyecto de Workspace compartido entre los usuarios de su organización, puede comunicar el impacto de un evento a través de descripciones de paneles o visualizaciones. Haga clic con el botón derecho en un panel o encabezado de visualización y seleccione **[!UICONTROL Editar descripción]**.

![Descripción del panel](assets/panel_description.png)

## Comunicarse mediante visualizaciones de texto

También puede comunicar el impacto de un evento a través de visualizaciones de texto dedicadas. Consulte [Visualizaciones de texto](/help/analyze/analysis-workspace/visualizations/text.md) en la guía de usuario sobre análisis.

![Visualización del texto](assets/text_visualization.png)

## Añadir eventos de calendario personalizados a las tendencias de Workspace

Para cualquier visualización de tendencias en Workspace, puede añadir una serie que represente el intervalo de fechas afectado.

1. Cree una métrica calculada con el segmento &quot;Días afectados&quot; siguiendo [Excluir fechas específicas en el análisis](segments.md).
1. Añada la métrica deseada al lienzo de la métrica calculada.

   ![Métrica](assets/calcmetric_event.png)

1. Añada un título y una descripción que informen a los usuarios del impacto. También puede etiquetar esta métrica como una anotación de calendario si lo desea.

   ![Título y descripción](assets/calcmetric_title_description.png)

1. En una tabla de forma libre, agregue la dimensión &quot;Día&quot;. Añada &quot;Visitas&quot; y la métrica calculada como columnas en paralelo.

   ![Tabla de forma libre](assets/calcmetric_freeform.png)

1. Haga clic en el icono de engranaje de la configuración de columna de la métrica calculada y active **[!UICONTROL La interpretación de cero no tiene valor]**.

   ![Configuración de métricas calculadas](assets/calcmetric_zero_no_value.png)

1. Añada una visualización de Línea. Los días afectados se representan con un color diferente. Los usuarios también pueden hacer clic en el icono &quot;Información&quot; en la métrica calculada para obtener más información.

   ![Icono de información](assets/calcmetric_infoicon.png)

## Uso de un evento de calendario en Reports &amp; Analytics

Si usa Reports &amp; Analytics, puede usar un [evento de calendario](/help/components/t-calendar-event.md) para resaltar los días afectados en cualquier informe de tendencias. Este método no se aplica a Analysis Workspace.

1. Vaya a **[!UICONTROL Componentes]** > **[!UICONTROL Todos los componentes]** > **[!UICONTROL Eventos de calendario]**.
2. Introduzca el título, el intervalo de fechas y el texto de la nota que desee.
3. Haga clic en **[!UICONTROL Guardar]**.

![Evento de calendario](assets/exclude_calendar_event.png)

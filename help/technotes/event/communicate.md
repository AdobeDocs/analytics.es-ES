---
title: Comunicación del impacto a los usuarios
description: Aprenda formas eficaces de comunicar el impacto de un evento en su organización.
exl-id: 9ba83f3f-2eea-44c2-80b2-a0a9111d51cf
feature: Curate and Share
source-git-commit: 29ab0cc535bd8f74b50428c11756bf8b446a23ab
workflow-type: tm+mt
source-wordcount: '346'
ht-degree: 1%

---

# Comunicar el impacto del evento a los usuarios

Si los datos [se han visto afectados por un evento](overview.md), es importante que comunique ese evento a los usuarios de su organización.

* Desarrolle una exención de responsabilidad común que pueda utilizar en las comunicaciones para mantener la coherencia
* Proporcionar una comunicación continua a los usuarios de Analytics y a las partes interesadas clave durante y después del evento
* Coloque un recordatorio de calendario para los hitos siguientes, como el mes o año siguiente. Esta comunicación futura le ayudará a recordar a los usuarios que visualicen informes el impacto de los mismos en informes mes tras mes o año tras año.

En Adobe Analytics, las secciones siguientes muestran diferentes formas de comunicarse con los usuarios de su organización. También puede utilizar otros métodos fuera de Adobe Analytics, como el correo electrónico, para comunicarse con los usuarios.

## Comunicarse mediante descripciones de paneles o visualizaciones

Si tiene un proyecto de Workspace compartido entre los usuarios de su organización, puede comunicar el impacto de un evento a través de descripciones de paneles o visualizaciones. Haga clic con el botón derecho en un panel o encabezado de visualización y seleccione **[!UICONTROL Editar descripción]**.

![Descripción del panel](assets/panel_description.png)

## Comunicarse mediante visualizaciones de texto

También puede comunicar el impacto de un evento a través de visualizaciones de texto dedicadas. Consulte [Visualizaciones de texto](/help/analyze/analysis-workspace/visualizations/text.md) en la guía de usuario sobre análisis.

![Visualización de texto](assets/text_visualization.png)

## Añadir eventos de calendario personalizados a las tendencias en Workspace

Para cualquier visualización de tendencias en Workspace, puede agregar una serie que represente el intervalo de fechas afectado.

1. Cree una métrica calculada con el segmento &quot;Días afectados&quot; siguiendo [Excluir fechas específicas en el análisis](segments.md).
1. Añada la métrica deseada al lienzo de la métrica calculada.

   ![Métrica](assets/calcmetric_event.png)

1. Añada un título y una descripción que informen a los usuarios del impacto. También puede etiquetar esta métrica como una anotación de calendario si lo desea.

   ![Título y descripción](assets/calcmetric_title_description.png)

1. En una tabla de forma libre, agregue la dimensión &quot;Día&quot;. Añada &quot;Visitas&quot; y la métrica calculada como columnas en paralelo.

   ![Tabla de forma libre](assets/calcmetric_freeform.png)

1. Haga clic en el icono de engranaje de configuración de columna de la métrica calculada y habilite **[!UICONTROL Interpretar cero como sin valor]**.

   ![Configuración de métricas calculadas](assets/calcmetric_zero_no_value.png)

1. Añada una visualización de Línea. Los días afectados se representan con un color diferente. Los usuarios también pueden hacer clic en el icono &quot;Información&quot; en la métrica calculada para obtener más información.

   ![Icono de información](assets/calcmetric_infoicon.png)


---
title: Introducción a los Canales de mercadotecnia
description: Obtenga información sobre el flujo de trabajo de Canales de marketing, la configuración automática y cómo aplicar la configuración del grupo de informes de plantilla a varios grupos de informes.
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Introducción a los Canales de mercadotecnia

Los Canales de mercadotecnia se utilizan comúnmente para proporcionar una perspectiva sobre cómo llegan los visitantes al sitio. Puede personalizar las reglas de procesamiento de Marketing Canal en función de los canales que desee rastrear y de cómo desea rastrearlos.

Los canales de mercadotecnia giran en torno a las métricas de primer y último toque, las cuales son componentes de las métricas de conversión estándar.

## Flujo de trabajo de Canales de marketing

![](assets/step1_icon.png) Definir los canales en función de las necesidades empresariales.

La definición de los canales que se utilizan es uno de los componentes más importantes de los Canales de marketing. La definición de los canales puede requerir la colaboración entre varias personas de la organización. Estas son algunas de las preguntas que hay que tener en cuenta:

* ¿Está utilizando una búsqueda paga?
* ¿Está usando campañas de correo electrónico? ¿Está utilizando varias campañas de correo electrónico que desea rastrear por separado?
* ¿Tiene afiliados que dirijan el tráfico a su sitio? ¿Hay afiliados que desee rastrear individualmente?
* ¿Existen campañas externas que resultarían ventajosas para rastrear por separado?
* ¿Desea acumulado todos los sitios de redes sociales o hay alguno que desee rastrear individualmente?
* ¿Hay otros canales que puedan afectar a la conversión que desee rastrear?

Hay una lista de canales recomendados en  [Preguntas frecuentes y ejemplos](/help/components/c-marketing-channels/c-faq.md). Cree una lista con los canales que desee usar. De este modo, será más fácil activar y definir los canales a la hora de crearlos.

![](assets/step2_icon.png) Añada canales de mercadotecnia en la [!UICONTROL Marketing Channel Manager] página.

After defining what channels to track, you enable them in **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**.

Consulte [Acerca de los canales y las reglas](/help/components/c-marketing-channels/c-channels.md) para obtener información importante sobre requisitos previos y conceptos.

Consulte [Agregar canales](/help/components/c-marketing-channels/c-channels.md) de marketing para ver el procedimiento.

>[!NOTE]
>
>Si los canales de marketing no se han configurado anteriormente, se muestra la [configuración automática](/help/components/c-marketing-channels/c-getting-started-mchannel.md). Esta configuración proporciona varios canales preconfigurados que puede personalizar. Adobe recomienda utilizar estas reglas como plantilla. Sin embargo, si ya tiene definiciones de canal sólidas, puede omitir la configuración automática.

![](assets/step3_icon.png) Configure o perfeccione las reglas de cada canal en la [!UICONTROL Marketing Channel Processing Rules] página.

Después de crear canales en la [!UICONTROL Marketing Channel Manager] página, puede configurar las reglas para que los canales puedan recuperar datos e informar sobre ellos.

See [Marketing Channel Processing Rules](/help/components/c-marketing-channels/c-rules.md).

Si se crearon canales en la configuración automática, se definen las reglas de esos canales. Puede modificarlas para adaptarlas a sus necesidades.

## Configuración automática para Canales de mercadotecnia {#run-auto-setup}

El informe Canal de marketing incluye una página de configuración de una sola vez para ayudarle a empezar. Proporciona varios canales de mercadotecnia que puede utilizar para realizar seguimientos. Puede omitir esta configuración si ya sabe cómo crear canales y reglas. Sin embargo, Adobe recomienda dejar que sea el asistente el que cree los canales. La configuración automática permite ver cómo se construyen las reglas, o editarlas para los fines que desee. Puede deshabilitar o eliminar los canales predefinidos en cualquier momento.

Cómo se ejecuta la configuración automática para los canales de mercadotecnia.

1. Haga clic **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**.
1. En el [!UICONTROL Report Suite Manager], seleccione un grupo de informes.
1. Haga clic **[!UICONTROL Edit Settings]** > **[!UICONTROL Marketing Channels]** > **[!UICONTROL Marketing Channel Manager]**.

   ![Resultado](assets/wizard.png)

   >[!NOTE]
   >
   >The [!UICONTROL Marketing Channels: Auto Setup] page displays automatically when you access channel configuration applications in Admin Tools. (Consulte el [administrador de Canales de marketing](/help/components/c-marketing-channels/c-channels.md).) Esta página no se muestra si el grupo de informes contiene uno o más canales de mercadotecnia. No puede volver a acceder a esta página a menos que seleccione otro grupo de informes que no contenga canales de marketing.

1. Asegúrese de que los canales que desee crear estén seleccionados.

   Cuando se selecciona, **[!UICONTROL Email]**, **[!UICONTROL Display]** y **[!UICONTROL Affiliate]** son campos obligatorios.

1. Haga clic en **[!UICONTROL Save]**.

## Aplicación de la configuración de un grupo de informes de plantilla a varios grupos de informes

Cómo utilizar un grupo de informes maestro como plantilla para probar la configuración de su canal de mercadotecnia. Para ahorrar tiempo, puede aplicar esta plantilla a uno o varios grupos de informes de producción en una actualización masiva. Esta tarea se realiza por separado para canales y conjuntos de reglas.

>[!NOTE] Aplique los canales a partir de una plantilla antes de aplicar los conjuntos de reglas. Los canales deben ser los mismos en todos los grupos de informes al realizar este procedimiento.

1. Asegúrese de que el informe de canal de mercadotecnia esté habilitado en los grupos de informes seleccionados. El administrador de su cuenta será el encargado de llevar a cabo este paso.
1. Haga clic **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**.
1. On the **[!UICONTROL Report Suite Manager]** page, select the template report suite, as well as one or more target report suites.
1. Haga clic **[!UICONTROL Edit Settings]** > **[!UICONTROL Marketing Channels]** > **[!UICONTROL Marketing Channel Manager]**.
1. En la **[!UICONTROL Select Master Report Suites]** página, seleccione un grupo de informes de plantilla.
1. Haga clic en **[!UICONTROL Save All]**.
1. Aplique las reglas a partir de una plantilla a varios grupos de informes:
   1. Vuelva a la [!UICONTROL Report Suite Manager] página.
   1. Seleccione el grupo de informes de plantilla y uno o más grupos de informes de destino.
   1. Haga clic **[!UICONTROL Edit Settings]** > **[!UICONTROL Marketing Channels]** > **[!UICONTROL Marketing Channel Processing Rules]**.
   1. Haga clic en **[!UICONTROL Save]**. Si el botón Guardar está deshabilitado en este paso, expanda una de las reglas para habilitarlo.


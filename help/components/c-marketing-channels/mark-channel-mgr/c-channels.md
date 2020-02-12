---
description: Agregue o habilite canales de marketing en el Administrador de canales de marketing. En los grupos de informes que no tengan canales de mercadotecnia, puede crear varios canales, junto con sus reglas, gracias a una configuración automática. Puede editar los canales predefinidos según sus necesidades o crear otros (hasta un total de 25).
subtopic: Marketing channels
title: Administrar Canales de marketing
topic: Reports and analytics
uuid: 9d367bb6-a17b-49b8-9cd5-24fac35ae982
translation-type: tm+mt
source-git-commit: dd58453a0459bc200a00badf34d06c259ce9fb59

---


# Administrar Canales de marketing

Agregue o habilite canales de marketing en el Administrador de canales de marketing. En los grupos de informes que no tengan canales de mercadotecnia, puede crear varios canales, junto con sus reglas, gracias a una configuración automática. Puede editar los canales predefinidos según sus necesidades o crear otros (hasta un total de 25).

Aquí tiene algunas indicaciones para la creación de canales:

* Planifíquelos con tiempo y haga una lista de todos los canales, de modo que todas las visitas se clasifiquen en el canal correcto.
* Incluya siempre canales para las categorías de visitas [Internas](/help/components/c-marketing-channels/mc-faq/c-faq.md) y [Directas](/help/components/c-marketing-channels/mc-faq/c-faq.md).

Adding channels to the [!UICONTROL Marketing Channels] page is done independently of creating rules on the [Marketing Channel Processing Rules](/help/components/c-marketing-channels/mc-proc-rules/t-rules.md) page. Al crear las reglas, se asocian a los canales.

## Agregar canales de marketing {#add-mktg-channels}

Agregue canales de marketing en el Administrador de canales de marketing.

> [!NOTE] Los canales no se pueden eliminar. Si no desea utilizar un canal, puede deshabilitarlo o cambiarle el nombre y guardarlo para utilizarlo después.

1. Haga clic **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**.
1. En la [!UICONTROL Report Suite Manager] página, seleccione un grupo de informes.

   Si selecciona varios grupos de informes, debe seleccionar una plantilla que copie la configuración de la plantilla a los grupos de informes seleccionados.

   Consulte [Aplicación de la configuración de un grupo de informes de plantilla a varios grupos de informes](/help/components/c-marketing-channels/getting-started/t-template.md).

1. Haga clic **[!UICONTROL Edit Settings]** > **[!UICONTROL Marketing Channels]** > **[!UICONTROL Marketing Channel Manager]**.

   Si no se han definido canales en el grupo de informes, se abre la página [Configuración automática](/help/components/c-marketing-channels/getting-started/c-channel-autosetup.md).

1. En la [!UICONTROL Marketing Channel Manager] página, haga clic en **[!UICONTROL Add Channel]**.

   Esta opción no está disponible cuando ya se han definido 25 canales.

1. Haga clic en **[!UICONTROL Save.]**
1. Para configurar las reglas del canal, haga clic en **[!UICONTROL Marketing Channel Processing Rules]**.

   Consulte [Creación de reglas de procesamiento para los canales de marketing](/help/components/c-marketing-channels/mc-proc-rules/t-rules.md).

## Administrador del canal de marketing: definiciones de la interfaz {#mktg-channel-mgr}

Definiciones de los campos de la [!UICONTROL Marketing Channel Manager] página.

| Campo | Definición |
|--- |--- |
| Habilitado | Habilita o deshabilita el canal de mercadotecnia. |
| Nombre del canal | Nombre descriptivo del canal de mercadotecnia. |
| Anular canal de último toque | Permite sobrescribir un canal de último toque persistente actual con el canal seleccionado. Si selecciona esta casilla, cualquier canal (incluidos el directo y el interno) sobrescribirán el canal que se haya tocado por última vez. Por lo tanto, se atribuirá la conversión a un canal al que, posiblemente, no corresponda el crédito. Por ejemplo, esta opción podría garantizar que el canal directo no reciba el crédito por la conversión si el usuario ha sido adquirido anteriormente mediante el canal Búsqueda natural. |
| Desglose de canal | Permite desglosar un canal según el valor especificado. You can add possible channel breakdowns (subchannels) when creating [marketing channel classifications](/help/components/c-marketing-channels/mc-classifications/classifictions-mchannel.md). |
| Tipo | Especifica cómo llegó el usuario a su sitio web. Puede seleccionar En línea o Sin conexión. Utilice los canales en línea para los visitantes que llegaron mediante un motor de búsqueda o una campaña de correo electrónico. Los canales sin conexión se aplican a los visitantes que hayan encontrado el sitio mediante cupones de periódicos o anuncios en revistas. Por lo general, los canales sin conexión incluyen datos importados a través de las fuentes de datos de informes. Consulte [Fuentes de datos](https://docs.adobe.com/content/help/en/analytics/import/data-sources/datasrc-home.html). Consulte [ Añadir datos sin conexión](/help/components/c-marketing-channels/getting-started/c-channel-autosetup.md). |
| Color | El color asociado al canal de mercadotecnia. El color representa el canal en el informe Canal de mercadotecnia. |
---
description: Agregue o habilite canales de marketing en el Administrador de canales de marketing. Para los grupos de informes que no tienen canales de marketing, una configuración automática permite crear varios canales, junto con sus reglas. Puede editar canales predefinidos para adaptarlos a sus necesidades o crear los suyos propios (hasta un total de 25).
subtopic: Marketing channels
title: Administrar Canales de marketing
topic: Reports and analytics
uuid: 9d367bb6-a17b-49b8-9cd5-24fac35ae982
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Administrar Canales de marketing

Agregue o habilite canales de marketing en el Administrador de canales de marketing. Para los grupos de informes que no tienen canales de marketing, una configuración automática permite crear varios canales, junto con sus reglas. Puede editar canales predefinidos para adaptarlos a sus necesidades o crear los suyos propios (hasta un total de 25).

Estas son las directrices para la creación de canales:

* Planee con anticipación realizando una lista de todos sus canales, de modo que todas las visitas de visitante se clasifiquen en el canal correcto.
* Incluya siempre canales para las categorías de visitas [internas](/help/components/c-marketing-channels/c-faq.md) y visitas [directas](/help/components/c-marketing-channels/c-faq.md) .

Adding channels to the [!UICONTROL Marketing Channels] page is done independently of creating rules on the [Marketing Channel Processing Rules](/help/components/c-marketing-channels/c-rules.md) page. Las reglas se asocian con canales al crear la regla.

## Agregar canales de marketing {#add-mktg-channels}

Agregue canales de marketing en el Administrador de canales de marketing.

>[!NOTE] Los canales no se pueden eliminar. Si no desea utilizar un canal, puede deshabilitarlo o cambiarle el nombre y guardarlo para utilizarlo después.

1. Haga clic **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**.
1. En la [!UICONTROL Report Suite Manager] página, seleccione un grupo de informes.

   Si selecciona varios grupos de informes, seleccione una plantilla que copie la configuración de la plantilla a los grupos de informes seleccionados.

   See [Apply template report suite settings to multiple report suites](/help/components/c-marketing-channels/c-getting-started-mchannel.md).

1. Haga clic **[!UICONTROL Edit Settings]** > **[!UICONTROL Marketing Channels]** > **[!UICONTROL Marketing Channel Manager]**.

   Si no se han definido canales en el grupo de informes, se abre la página [Configuración automática](/help/components/c-marketing-channels/c-getting-started-mchannel.md).

1. En la [!UICONTROL Marketing Channel Manager] página, haga clic en **[!UICONTROL Add Channel]**.

   Esta opción no está disponible cuando ya se han definido 25 canales.

1. Haga clic en **[!UICONTROL Save.]**
1. Para configurar las reglas del canal, haga clic en **[!UICONTROL Marketing Channel Processing Rules]**.

   Consulte [Creación de reglas de procesamiento para los canales de marketing](/help/components/c-marketing-channels/c-rules.md).

## Administrador del canal de marketing: definiciones de la interfaz {#mktg-channel-mgr}

Definiciones de los campos de la [!UICONTROL Marketing Channel Manager] página.

| Campo | Definición |
|--- |--- |
| Habilitado | Habilita o deshabilita este canal de mercadotecnia. |
| Nombre del canal | Nombre descriptivo del canal de marketing. |
| Anular canal de último toque | Le permite elegir si desea anular un canal de último toque persistente existente con el canal seleccionado. Si selecciona esta casilla, cualquier canal (incluidos el directo y el interno) sobrescribirán el canal que se haya tocado por última vez. Por lo tanto, se atribuirá la conversión a un canal al que, posiblemente, no corresponda el crédito. Por ejemplo, esta opción puede garantizar que el canal directo no reciba crédito por la conversión si el usuario se había adquirido previamente mediante el canal de búsqueda natural. |
| Desglose de canal | Permite desglosar un canal por este valor. Puede agregar posibles desgloses de canal (subcanales) al crear clasificaciones [de canal de](/help/components/c-marketing-channels/classifictions-mchannel.md)mercadotecnia. |
| Tipo | Especifica cómo llegó el usuario a su sitio web. Puede seleccionar En línea o Sin conexión. Use canales en línea para visitantes que llegan a través de un motor de búsqueda o una campaña de correo electrónico. Los canales sin conexión se aplican a los visitantes que han encontrado el sitio mediante cupones de periódicos o anuncios de revistas. Los canales sin conexión suelen incluir datos importados mediante fuentes de datos de sistema de informes. Consulte [Fuentes de datos](https://docs.adobe.com/content/help/es-ES/analytics/import/data-sources/datasrc-home.html). Consulte [ Añadir datos sin conexión](/help/components/c-marketing-channels/c-getting-started-mchannel.md). |
| Color | El color asociado con este canal de marketing. El color representa el canal en el informe Canal de mercadotecnia. |

## Definir canales

Antes de que los datos de canales y canales se puedan mostrar en el informe, cree los canales y las reglas subyacentes que procesan los datos. También puede crear importes de costo y presupuesto para canales asociados, y especificar cuánto tiempo desea que dure el período de compromiso de visitante. Las tareas de configuración de informes se realizan en las Herramientas de administración.

Piense en un canal como un contenedor para las visitas. Las reglas asignan las visitas al contenedor adecuado.

![](assets/buckets_2.png)

Adobe ofrece varios canales predefinidos durante la  [configuración automática](/help/components/c-marketing-channels/c-getting-started-mchannel.md), que puede editar para adaptarlos a sus necesidades.

>[!NOTE]
>
>Adobe recomienda que configure el informe en un grupo de informes, que puede utilizar como plantilla para realizar pruebas. Puede utilizar la plantilla para aplicar conjuntos de canales y reglas de forma global a uno o varios grupos de informes de producción.
>
>See [Apply Template Report Suite Settings to Multiple Report Suites](/help/components/c-marketing-channels/c-getting-started-mchannel.md).

### Requisitos previos {#prereqs}

En caso necesario, póngase en contacto con el departamento de atención al cliente para obtener ayuda con los requisitos previos:

* In the Administration Console (General Account Settings), enable the **[!UICONTROL Conversion Level]** (e-commerce) option for the report suite.

   Consulte [Configuración general de cuenta](https://docs.adobe.com/content/help/es-ES/analytics/admin/admin-tools/general-acct-settings-admin.html) en la sección de ayuda de Analytics para obtener más información.

* Configure el acceso a las dimensiones de Marketing Canal.

   See [Marketing Channels permissions](/help/components/c-marketing-channels/c-channel-report-access.md).

* Ensure that your account manager has enabled **[!UICONTROL Channel Reports]** for your report suite.

### Notas de procesamiento importantes {#important-proc-rules}

* El sistema procesa las reglas en el orden especificado y, cuando se cumple una regla, deja de procesar las reglas restantes.
* Las reglas pueden acceder a las variables que VISTA ha establecido, pero no pueden acceder a los datos que VISTA ha eliminado.
* Los Canales solo almacenan métricas de conversión. Las métricas de tráfico no están disponibles.
* Dos canales de mercadotecnia nunca reciben crédito por el mismo evento (como compras o clics). De este modo, los canales de mercadotecnia difieren de las eVars (donde dos eVars pueden recibir crédito por el mismo evento).
* El informe puede procesar hasta 25 canales a la vez.


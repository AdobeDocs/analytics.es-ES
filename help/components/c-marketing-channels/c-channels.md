---
description: Agregue o habilite canales de marketing en el Administrador de canales de marketing. En los grupos de informes que no tengan canales de mercadotecnia, puede crear varios canales, junto con sus reglas, gracias a una configuración automática. Puede editar los canales predefinidos según sus necesidades o crear otros (hasta un total de 25).
subtopic: Marketing channels
title: Administrar Canales de marketing
topic: Reports and analytics
uuid: 9d367bb6-a17b-49b8-9cd5-24fac35ae982
translation-type: tm+mt
source-git-commit: c10a12781a8fe52b7b897cd337dc686aa0bbb240

---


# Administrar Canales de marketing

Agregue o habilite canales de marketing en el Administrador de canales de marketing. En los grupos de informes que no tengan canales de mercadotecnia, puede crear varios canales, junto con sus reglas, gracias a una configuración automática. Puede editar los canales predefinidos según sus necesidades o crear otros (hasta un total de 25).

Aquí tiene algunas indicaciones para la creación de canales:

* Planifíquelos con tiempo y haga una lista de todos los canales, de modo que todas las visitas se clasifiquen en el canal correcto.
* Incluya siempre canales para las categorías de visitas [Internas](/help/components/c-marketing-channels/c-faq.md) y [Directas](/help/components/c-marketing-channels/c-faq.md).

Adding channels to the [!UICONTROL Marketing Channels] page is done independently of creating rules on the [Marketing Channel Processing Rules](/help/components/c-marketing-channels/c-rules.md) page. Al crear las reglas, se asocian a los canales.

## Agregar canales de marketing {#add-mktg-channels}

Agregue canales de marketing en el Administrador de canales de marketing.

> [!NOTE] Los canales no se pueden eliminar. Si no desea utilizar un canal, puede deshabilitarlo o cambiarle el nombre y guardarlo para utilizarlo después.

1. Haga clic **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**.
1. En la [!UICONTROL Report Suite Manager] página, seleccione un grupo de informes.

   Si selecciona varios grupos de informes, debe seleccionar una plantilla que copie la configuración de la plantilla a los grupos de informes seleccionados.

   Consulte [Aplicación de la configuración de un grupo de informes de plantilla a varios grupos de informes](/help/components/c-marketing-channels/c-getting-started-mchannel.md).

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
| Habilitado | Habilita o deshabilita el canal de mercadotecnia. |
| Nombre del canal | Nombre descriptivo del canal de mercadotecnia. |
| Anular canal de último toque | Permite sobrescribir un canal de último toque persistente actual con el canal seleccionado. Si selecciona esta casilla, cualquier canal (incluidos el directo y el interno) sobrescribirán el canal que se haya tocado por última vez. Por lo tanto, se atribuirá la conversión a un canal al que, posiblemente, no corresponda el crédito. Por ejemplo, esta opción podría garantizar que el canal directo no reciba el crédito por la conversión si el usuario ha sido adquirido anteriormente mediante el canal Búsqueda natural. |
| Desglose de canal | Permite desglosar un canal según el valor especificado. You can add possible channel breakdowns (subchannels) when creating [marketing channel classifications](/help/components/c-marketing-channels/classifictions-mchannel.md). |
| Tipo | Especifica cómo llegó el usuario a su sitio web. Puede seleccionar En línea o Sin conexión. Utilice los canales en línea para los visitantes que llegaron mediante un motor de búsqueda o una campaña de correo electrónico. Los canales sin conexión se aplican a los visitantes que hayan encontrado el sitio mediante cupones de periódicos o anuncios en revistas. Por lo general, los canales sin conexión incluyen datos importados a través de las fuentes de datos de informes. Consulte [Fuentes de datos](https://docs.adobe.com/content/help/en/analytics/import/data-sources/datasrc-home.html). Consulte [ Añadir datos sin conexión](/help/components/c-marketing-channels/c-getting-started-mchannel.md). |
| Color | El color asociado al canal de mercadotecnia. El color representa el canal en el informe Canal de mercadotecnia. |

## Definición de canales

Para que los canales y sus datos puedan aparecer en el informe, debe crear los canales y las reglas subyacentes que procesan los datos. También puede crear importes de costos y presupuestos para los canales relacionados, y especificar cuánto tiempo desea que dure el período de compromiso del visitante. Las tareas de configuración de informes se realizan en las Herramientas de administración.

Imagine que el canal es un contenedor de visitas y que las reglas asignan las visitas al contenedor correspondiente.

![](assets/buckets_2.png)

Adobe ofrece varios canales predefinidos durante la [configuración automática](/help/components/c-marketing-channels/c-getting-started-mchannel.md), que puede editar para adaptarlos a sus necesidades.

>[!NOTE]
>
>Adobe recomienda que configure el informe en un grupo de informes, que puede utilizar como plantilla para realizar pruebas. Puede usar la plantilla para aplicar conjuntos de canales y reglas de forma global a uno o más grupos de informes de producción.
>
>Consulte [Aplicación de la configuración de un grupo de informes de plantilla a varios grupos de informes](/help/components/c-marketing-channels/c-getting-started-mchannel.md).

### Requisitos previos {#prereqs}

En caso necesario, póngase en contacto con el departamento de atención al cliente para obtener ayuda con los requisitos previos:

* In the Administration Console (General Account Settings), enable the **[!UICONTROL Conversion Level]** (e-commerce) option for the report suite.

   Consulte [Configuración general de cuenta](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/general-acct-settings-admin.html) en la sección de ayuda de Analytics para obtener más información.

* Configure el acceso a las dimensiones del canal de mercadotecnia.

   See [Marketing Channels permissions](/help/components/c-marketing-channels/c-channel-report-access.md).

* Ensure that your account manager has enabled **[!UICONTROL Channel Reports]** for your report suite.

### Notas de procesamiento importantes {#important-proc-rules}

* El sistema procesa las reglas en el orden en el que las especifique y, cuando se cumple una regla, se detiene el procesamiento de las demás reglas.
* Las reglas pueden acceder a las variables que ha establecido VISTA, pero no pueden acceder a los datos que VISTA ha eliminado.
* Los canales almacenan solamente las métricas de conversión. Las métricas de tráfico no están disponibles.
* Dos canales de mercadotecnia nunca reciben crédito por el mismo evento (por ejemplo, compras o clics). En este sentido, los canales de mercadotecnia difieren de las eVars (ya que dos eVars pueden recibir crédito por el mismo evento).
* El informe puede procesar hasta 25 canales al mismo tiempo.


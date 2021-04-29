---
description: Agregue o habilite canales de marketing en el Administrador de canales de marketing. En los grupos de informes que no tengan canales de marketing, puede crear varios canales, junto con sus reglas, gracias a una configuración automática. Puede editar los canales predefinidos según sus necesidades o crear otros (hasta un total de 25).
subtopic: Marketing channels
title: Administrar Canales de marketing
feature: Conceptos básicos de Reports & Analytics
exl-id: a768a4c2-f922-4d96-a9fb-78a1dfac04d8
translation-type: tm+mt
source-git-commit: 7202a49dda7c3ef4f4b535476d3cf637b9e9f7f6
workflow-type: tm+mt
source-wordcount: '752'
ht-degree: 96%

---

# Administrar Canales de marketing

>[!NOTE]
>
>Para maximizar la eficacia de los canales de marketing para Attribution IQ y Customer Journey Analytics, hemos publicado algunas [prácticas recomendadas revisadas](/help/components/c-marketing-channels/mchannel-best-practices.md).

Agregue o habilite canales de marketing en el Administrador de canales de marketing. En los grupos de informes que no tengan canales de marketing, puede crear varios canales, junto con sus reglas, gracias a una configuración automática. Puede editar los canales predefinidos según sus necesidades o crear otros (hasta un total de 25).

La adición de canales a la página [!UICONTROL Canales de marketing] se realiza independientemente de la creación de reglas en la página [Reglas de procesamiento de canal de marketing](/help/components/c-marketing-channels/c-rules.md). Al crear las reglas, se asocian a los canales.

Aquí tiene algunas indicaciones para la creación de canales:

* Planifíquelos con tiempo y haga una lista de todos los canales, de modo que todas las visitas se clasifiquen en el canal correcto.
* Incluya canales para las categorías de visitas [Internas](/help/components/c-marketing-channels/c-rules.md) y [Directas](/help/components/c-marketing-channels/c-rules.md).
* Incluya un canal “Otras Campañas”, que se colocará después de los canales pagados y antes de los canales orgánicos.


## Requisitos previos {#prereqs}

* Configure el acceso a las dimensiones del canal de marketing.

   Consulte los [permisos de los canales de marketing](/help/components/c-marketing-channels/c-channel-report-access.md).

## Agregar canales de marketing {#add-mktg-channels}

Agregue canales de marketing en el Administrador de canales de marketing.

>[!NOTE]
>
> Los canales no se pueden eliminar. Si no desea utilizar un canal, puede deshabilitarlo o cambiarle el nombre y guardarlo para utilizarlo después.

1. Haga clic en **[!UICONTROL Analytics]** > **[!UICONTROL Administración]** > **[!UICONTROL Grupos de informes]**.
1. En la página [!UICONTROL Administrador del grupo de informes], seleccione un grupo de informes.

   Si selecciona varios grupos de informes, debe seleccionar una plantilla que copie la configuración de la plantilla a los grupos de informes seleccionados.

   Consulte [Aplicación de la configuración de un grupo de informes de plantilla a varios grupos de informes](/help/components/c-marketing-channels/c-getting-started-mchannel.md).

1. Haga clic en **[!UICONTROL Editar configuración]** > **[!UICONTROL Canales de marketing]** > **[!UICONTROL Administrador de canales de marketing]**.

   Si no se han definido canales en el grupo de informes, se abre la página [Configuración automática](/help/components/c-marketing-channels/c-getting-started-mchannel.md).

1. En la página [!UICONTROL Administrador de canales de marketing], haga clic en **[!UICONTROL Agregar canal]**.

   Esta opción no está disponible cuando ya se han definido 25 canales.

1. Haga clic en **[!UICONTROL Guardar]**.
1. Para configurar las reglas del canal, haga clic en **[!UICONTROL Reglas de procesamiento de canal de marketing]**.

   Consulte [Creación de reglas de procesamiento para los canales de marketing](/help/components/c-marketing-channels/c-rules.md).

## Aplicar configuración de canal {#mktg-channel-mgr}

Hay varias opciones de configuración que se pueden aplicar a cada canal en la página [!UICONTROL Administrador de canales de marketing].

| Campo | Definición |
|--- |--- |
| Habilitado | Habilita o deshabilita el canal de marketing. |
| Nombre del canal | Nombre descriptivo del canal de marketing. |
| Anular canal de último contacto | Permite sobrescribir un canal de último contacto persistente actual con el canal seleccionado. Si selecciona esta casilla, cualquier canal (incluidos el directo y el interno) sobrescribirán el canal que se haya tocado por última vez. Por lo tanto, se atribuirá la conversión a un canal al que, posiblemente, no corresponda el crédito. Por ejemplo, esta opción podría garantizar que el canal directo no reciba el crédito por la conversión si el usuario ha sido adquirido anteriormente mediante el canal Búsqueda natural. |
| Desglose de canal | Permite desglosar un canal según el valor especificado. Puede agregar posibles desgloses de canal (subcanales) al crear [clasificaciones de canal de marketing](/help/components/c-marketing-channels/classifictions-mchannel.md). |
| Tipo | Especifica cómo llegó el usuario a su sitio web. Puede seleccionar En línea o Sin conexión. Utilice los canales en línea para los visitantes que llegaron mediante un motor de búsqueda o una campaña de correo electrónico. Los canales sin conexión se aplican a los visitantes que hayan encontrado el sitio mediante cupones de periódicos o anuncios en revistas. Por lo general, los canales sin conexión incluyen datos importados a través de las fuentes de datos de informes. Consulte [Fuentes de datos](https://docs.adobe.com/content/help/es-ES/analytics/import/data-sources/datasrc-home.html). Consulte [Añadir datos sin conexión](/help/components/c-marketing-channels/c-getting-started-mchannel.md). |
| Color | Solo informes y análisis: El color asociado con este canal de marketing. El color representa el canal en el informe Canal de marketing. |

### Prácticas recomendadas sobre anulaciones

Se recomienda desactivar la opción de anulación del último contacto para los canales directos e internos, de modo que no puedan tomar crédito de otros canales de último contacto persistentes (o entre sí).

![](assets/int-channel2.png)

## Definir reglas de canal

Para que los canales y sus datos puedan aparecer en el informe, debe crear los canales y las reglas subyacentes que procesan los datos. También puede especificar cuánto tiempo desea que dure el [periodo de compromiso del visitante](/help/components/c-marketing-channels/visitor-engagement.md).

Adobe proporciona varios canales predefinidos durante una [configuración automática](/help/components/c-marketing-channels/c-getting-started-mchannel.md) que puede editar para adaptarlos a sus necesidades. Además, puede modificar esta configuración y definir reglas personalizadas dentro de las [reglas de procesamiento del canal de marketing](/help/components/c-marketing-channels/c-rules.md).

>[!NOTE]
>
>Adobe recomienda que configure el informe en un grupo de informes, que puede utilizar como plantilla para realizar pruebas. Puede usar la plantilla para aplicar conjuntos de canales y reglas de forma global a uno o más grupos de informes de producción.
>
>Consulte [Aplicación de la configuración de un grupo de informes de plantilla a varios grupos de informes](/help/components/c-marketing-channels/c-getting-started-mchannel.md).

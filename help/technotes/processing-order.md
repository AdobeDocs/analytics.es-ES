---
title: Orden de procesamiento de los datos en Adobe Analytics
description: Conozca el orden de los componentes y servicios que procesan los datos en Adobe Analytics.
exl-id: a8dc9c12-07d3-4dc8-b2df-136f7a7a1e77
feature: Data Configuration and Collection
source-git-commit: 6c947812d4fd8bc2ee951a5933c6e3b6d8ca1a6b
workflow-type: tm+mt
source-wordcount: '1040'
ht-degree: 35%

---

# Orden de procesamiento de los datos en Adobe Analytics

Adobe ofrece muchas maneras de modificar o manipular los datos antes de que aparezcan en la creación de informes. Esta página muestra el orden en que varias funciones de Adobe Analytics procesan los datos. Puede utilizar esta lista para solucionar problemas de inconsistencias de datos o determinar la mejor funcionalidad que debe utilizarse cuando sea necesario realizar ajustes de datos.

![Imagen de orden de procesamiento](assets/processing-order.png)

## Datos antes de enviarse a Adobe

Antes de enviar los datos a Adobe, suelen compilarse en el lado del cliente mediante uno de los métodos siguientes:

* **AppMeasurement**: un archivo JavaScript alojado en el sitio al que se hace referencia en cada página. Los datos se envían directamente a Adobe Analytics.
* **SDK web de Adobe Experience Platform**: un archivo JavaScript alojado en el sitio al que se hace referencia en cada página. Los datos se envían al Edge Network de Adobe Experience Platform.
* **Etiquetas en la recopilación de datos de Adobe Experience Platform**: un archivo JavaScript al que se hace referencia en cada página y que contiene reglas creadas dentro de la IU de recopilación de datos. La extensión de Adobe Analytics ofrece una forma más sencilla de implementar AppMeasurement. La extensión del SDK web ofrece una forma más sencilla de implementar el SDK web.
* **API**: tanto AppMeasurement como Edge Network ofrecen métodos programáticos para enviar datos a Adobe. AppMeasurement ofrece la [API de inserción de datos](https://developer.adobe.com/analytics-apis/docs/1.4/guides/data-insertion/) y la [API de inserción de datos en lotes](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/bulk-data-insertion/); Edge Network ofrece la [API de recopilación de datos](https://developer.adobe.com/data-collection-apis/docs/).

Si envía datos a Edge Network, puede configurarlos para que reenvíen datos a Adobe Analytics (así como a muchas otras soluciones de Adobe Experience Cloud). Independientemente del método de implementación, los datos de visitas recopilados llegan finalmente a los servidores de procesamiento de Adobe Analytics en un formato que puede analizar.

## Preprocesamiento en la colección de Adobe Analytics

Cuando los datos llegan a Adobe Analytics, entran en una fase de preprocesamiento:

1. [**Variables dinámicas**](/help/implement/vars/page-vars/dynamic-variables.md): si se ve una variable dinámica en cualquier parte de una solicitud de imagen, el valor se copia y se trata como un valor independiente en adelante.
1. [**Ofuscación de IP (último octeto)**](/help/admin/tools/manage-rs/edit-settings/general/general-acct-settings-admin.md): si el grupo de informes está configurado para ofuscar solo el último octeto, esa ofuscación se aplica aquí. Tenga en cuenta que la ocultación de la IP (eliminación de la IP) se produce más adelante en la canalización de procesamiento.
1. **Tablas de búsqueda**: Las dimensiones que dependen de tablas de búsqueda internas de Adobe (por ejemplo, la dimensión [Explorador](/help/components/dimensions/browser.md)) coinciden con su valor correspondiente.
1. [**Exclusión de IP**](/help/admin/tools/exclude-ip.md): Las direcciones IP que excluya explícitamente del informe se marcarán durante este paso.
1. [**Reglas de bots**](/help/admin/tools/manage-rs/edit-settings/general/bot-removal/bot-rules.md): aplique un filtro de bots estándar o personalizado para excluir esos datos de la creación de informes.
1. **Datos de geolocalización**: se rellenan dimensiones que dependen de la búsqueda de direcciones IP (por ejemplo, [Países](/help/components/dimensions/countries.md)).
1. [**Reglas de procesamiento**](/help/admin/tools/manage-rs/edit-settings/general/processing-rules/pr-overview.md): reglas personalizadas aplicadas a los datos por su organización. Incluye la asignación de [Variables de datos de contexto](/help/implement/vars/page-vars/contextdata.md) a sus respectivas variables de Analytics.
1. [**Reglas VISTA**](vista.md): reglas flexibles personalizadas aplicadas a los datos por un consultor de Adobe. Las reglas VISTA pueden ejecutarse antes o después de las reglas de procesamiento, según las necesidades de su organización. La mayoría de las reglas VISTA suelen ejecutarse después de las de procesamiento, pero cada organización está configurada de forma diferente. Póngase en contacto con su equipo de cuenta de Adobe para obtener más información sobre las reglas VISTA existentes.
1. **Conversión de moneda**: Si la visita contiene un [`currencyCode`](/help/implement/vars/config-vars/currencycode.md) diferente a la moneda del grupo de informes, todas las variables de moneda aplicables se convierten utilizando el tipo de cambio del día actual.
1. [**Código postal**](/help/components/dimensions/zip-code.md): La dimensión &quot;Código postal&quot; se rellena según la configuración del grupo de informes.

## Fase &quot;Valor medio&quot; de la canalización de recopilación de datos

Cuando termina el preprocesamiento, varias funciones utilizan esta forma de datos procesada parcialmente, conocida como &quot;valores medios&quot;. Antes de que esos datos se envíen a cualquier lugar, se aplica algún procesamiento específico de valor medio:

1. [**Reglas de procesamiento de canal de marketing de nivel de éxito**](/help/admin/tools/manage-rs/edit-settings/marketing-channels/mc-proc-rules.md): estas reglas de procesamiento se ejecutan específicamente para el Conector de Source de Analytics. Dado que todavía no hay contexto en el nivel de visita o visitante, estas reglas de procesamiento suponen que una visita no es la primera visita individual de una visita. Los resultados de ejecutar las reglas de procesamiento para una visita están disponibles en `channel.typeAtSource` y `channel._id`.
1. [**Confusión de IP (eliminar IP)**](/help/admin/tools/manage-rs/edit-settings/general/general-acct-settings-admin.md): si el grupo de informes está configurado para proteger completamente una dirección IP, esa confusión se aplica aquí (solo para valores medios).

En este punto, los datos de valor medio se envían a su función correspondiente:

* [**API de Livestream**](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/livestream/): conecte una aplicación al servicio livestream de Adobe para obtener un flujo de datos a medida que se va recopilando.
* [**Conector de Source de Analytics**](https://experienceleague.adobe.com/es/docs/experience-platform/sources/connectors/adobe-applications/analytics): ingrese datos del grupo de informes de Adobe Analytics en un conjunto de datos de Adobe Experience Platform.
* [**Informes en tiempo real**](/help/components/c-real-time-reporting/realtime.md): Proporciona hasta tres informes configurables en tiempo real en Analysis Workspace.

## Procesamiento a nivel de visita y visitante

Hasta este punto, una visita determinada no tiene conocimiento ni contexto de las visitas recopiladas antes o después de ella. Esta fase de procesamiento rellena los campos de nivel de visita y de visitante.

1. [**Visita + definición de visitante**](/help/implement/id/overview.md): La visita se identifica en función de las variables de visitante contenidas en ella.
1. [**Número de visita**](/help/components/dimensions/visit-number.md): En función de otras visitas del visitante identificado, se calcula el número de visitas.
1. **Anulación de duplicación de eventos**: Si la visita contiene un duplicado de [`purchaseID`](/help/implement/vars/page-vars/purchaseid.md) o [serialización de eventos](/help/implement/vars/page-vars/events/event-serialization.md), esos identificadores se comprueban y se marcan respectivamente.
1. [**Reglas de procesamiento de canales de marketing de nivel de visita**](/help/admin/tools/manage-rs/edit-settings/marketing-channels/mc-proc-rules.md): Cada visita se ejecuta a través de reglas de procesamiento de canales de marketing, y su canal + detalles de canal se determinan si la visita coincide con alguna regla. Estas reglas rellenan las dimensiones [canal de mercadotecnia](/help/components/dimensions/marketing-channel.md) y [detalle del canal de mercadotecnia](/help/components/dimensions/marketing-detail.md) disponibles en Analysis Workspace.
1. **Persistencia variable**: Para las dimensiones que tienen persistencia (como [eVars](/help/components/dimensions/evar.md)), ese valor se determina en este paso. En términos generales, la mayoría de los valores de `post` se establecen aquí.
1. **ID de transacción**: si la visita contiene un nuevo valor de [`transactionID`](/help/implement/vars/page-vars/transactionid.md), se almacenará una &quot;captura de pantalla&quot; de todos los valores admitidos. Cuando una carga de fuente de datos contiene un ID de transacción coincidente, todos los valores admitidos de esta instantánea se incluyen en la fila de la fuente de datos.
1. [**Ofuscación de IP (eliminar IP)**](/help/admin/tools/manage-rs/edit-settings/general/general-acct-settings-admin.md): si el grupo de informes está configurado para ofuscar por completo una dirección IP, esa ofuscación se aplica aquí después de que finalice el resto del procesamiento.

En este punto, la visita individual se registra en las tablas de datos del grupo de informes. Después del intervalo estándar de [latencia](latency.md), está disponible en la creación de informes.

## Cambio de datos después de procesarlos

Los datos de Adobe Analytics son en su mayoría permanentes; sin embargo, hay algunas características que pueden permitir el ajuste o la eliminación selectivos de los datos:

* [**API de reparación de datos**](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/data-repair/): edite determinadas columnas o elimine las filas de datos deseadas.
* [**Gobernanza de datos**](/help/technotes/privacy/privacy-overview.md): acepte solicitudes de privacidad para eliminar datos de forma permanente.
* [**Clasificaciones**](/help/components/classifications/classifications-overview.md): cree dimensiones basadas en reglas o datos cargados que le permitan organizar los datos de forma diferente. Los datos del grupo de informes subyacente no se modifican, por lo que puede editar o sobrescribir libremente los datos de clasificación.
* [**Grupos de informes virtuales**](/help/components/vrs/vrs-about.md): cree una vista de grupo de informes alternativa que pueda cambiar el tiempo de espera de visita.

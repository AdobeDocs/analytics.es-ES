---
title: Orden de procesamiento de los datos en Adobe Analytics
description: Conozca el orden de los componentes y servicios que procesan los datos en Adobe Analytics.
exl-id: a8dc9c12-07d3-4dc8-b2df-136f7a7a1e77
feature: Data Configuration and Collection
source-git-commit: a40f30bbe8fdbf98862c4c9a05341fb63962cdd1
workflow-type: tm+mt
source-wordcount: '585'
ht-degree: 91%

---

# Orden de procesamiento de los datos en Adobe Analytics

Adobe ofrece muchas maneras de modificar o manipular los datos antes de que aparezcan en la creación de informes. Esta página muestra el orden en que varias funciones de Adobe Analytics procesan los datos. Puede utilizar esta lista para solucionar problemas de inconsistencias de datos o determinar la mejor funcionalidad que debe utilizarse cuando sea necesario realizar ajustes de datos.

![Orden de procesamiento](assets/processing-order.png)

## Datos antes de enviarse a Adobe

Antes de enviar los datos a Adobe, suelen compilarse en el lado del cliente mediante uno de los métodos siguientes:

* **AppMeasurement**: un archivo JavaScript alojado en el sitio al que se hace referencia en cada página. Los datos se envían directamente a Adobe Analytics.
* **SDK web de Adobe Experience Platform**: un archivo JavaScript alojado en el sitio al que se hace referencia en cada página. Los datos se envían al Edge Network de Adobe Experience Platform.
* **Etiquetas en la recopilación de datos de Adobe Experience Cloud**: un archivo JavaScript al que se hace referencia en cada página y que contiene reglas creadas dentro de la IU de recopilación de datos. La extensión de Adobe Analytics ofrece una forma más sencilla de implementar AppMeasurement. La extensión del SDK web ofrece una forma más sencilla de implementar el SDK web.

Si envía datos a Edge Network, puede configurarlos para que reenvíen datos a Adobe Analytics (así como a muchas otras soluciones de Adobe Experience Cloud). Independientemente del método de implementación, en última instancia se envía una solicitud de imagen con las variables deseadas a los servidores de recopilación de datos de Adobe.

## Datos a medida que llegan a los servidores de recopilación de datos de Adobe Analytics

Una vez que los datos llegan a Adobe Analytics, las siguientes funciones ajustan los datos según sea necesario:

1. **Tablas de búsqueda**: dimensiones que dependen de tablas de búsqueda internas de Adobe (por ejemplo, [Explorador](/help/components/dimensions/browser.md)) emparejadas con su valor correspondiente.
2. [**Variables dinámicas**](/help/implement/vars/page-vars/dynamic-variables.md): si se ve una variable dinámica en cualquier parte de una solicitud de imagen, el valor se copia y se trata como un valor independiente en adelante.
3. [**Reglas de bots**](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-rules.md): aplique un filtro de bots estándar o personalizado para excluir esos datos de la creación de informes.
4. [**Reglas de procesamiento**](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules.md): reglas personalizadas aplicadas a los datos por su organización. Incluye la asignación de [Variables de datos de contexto](/help/implement/vars/page-vars/contextdata.md) a su variable respectiva.
5. **Reglas VISTA**: reglas flexibles personalizadas aplicadas a los datos por un consultor de Adobe. Las reglas VISTA pueden ejecutarse antes o después de las reglas de procesamiento, según las necesidades de su organización. La mayoría de las reglas VISTA suelen ejecutarse después de las de procesamiento, pero cada organización está configurada de forma diferente. Póngase en contacto con su equipo de cuenta de Adobe para obtener más información sobre las reglas VISTA existentes.
6. [**Reglas de procesamiento de canal de marketing**](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/marketing-channels/c-rules.md): puede usar [Reglas de procesamiento](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules.md) para preparar los datos y usarlos en las reglas de procesamiento del canal de marketing.
7. **Datos de geolocalización**: se rellenan dimensiones que dependen de la búsqueda de direcciones IP (por ejemplo, [Países](/help/components/dimensions/countries.md)).
8. [**Confusión de IP**](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/general-acct-settings-admin.md): si su organización ha optado por proteger las direcciones IP de los datos sin procesar, se realiza después de que se hayan completado todas las demás funciones de procesamiento.

En este punto, la visita individual se registra en las tablas de datos del grupo de informes. Después del intervalo estándar de [latencia](latency.md), está disponible en la creación de informes.

## Cambio de datos después de procesarlos

Los datos de Adobe Analytics son en su mayoría permanentes; sin embargo, hay algunas características que pueden permitir el ajuste o la eliminación selectivos de los datos:

* [**API de reparación de datos**](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/data-repair/): edite determinadas columnas o elimine las filas de datos deseadas.
* [**Gobernanza de datos**](/help/admin/admin/c-data-governance/an-gdpr-workflow.md): acepte solicitudes de privacidad para eliminar datos de forma permanente.
* [**Clasificaciones**](/help/components/classifications/classifications-overview.md): cree dimensiones basadas en reglas o datos cargados que le permitan organizar los datos de forma diferente. Los datos del grupo de informes subyacente no se modifican, por lo que puede editar o sobrescribir libremente los datos de clasificación.
* [**Grupos de informes virtuales**](/help/components/vrs/vrs-about.md): cree una vista de grupo de informes alternativa que pueda cambiar el tiempo de espera de visita o permitir el [Análisis entre dispositivos](/help/components/cda/overview.md).

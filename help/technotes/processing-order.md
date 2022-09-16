---
title: Orden de procesamiento de los datos en Adobe Analytics
description: Conozca el orden de los componentes y servicios que procesan los datos en Adobe Analytics.
source-git-commit: 65ee7ae6d838f34149eb60547d976856e4da3b17
workflow-type: tm+mt
source-wordcount: '584'
ht-degree: 0%

---

# Orden de procesamiento de los datos en Adobe Analytics

Adobe ofrece muchas maneras de modificar o manipular los datos antes de que aparezcan en los informes. Esta página muestra el orden en que varias funciones de Adobe Analytics procesan los datos. Puede utilizar esta lista para solucionar problemas de inconsistencias de datos o determinar la mejor función que debe utilizarse cuando sea necesario realizar ajustes de datos.

## Datos antes de enviarlos a Adobe

Antes de enviar los datos al Adobe, este suele compilarse en el lado del cliente mediante uno de los métodos siguientes:

* **AppMeasurement**: Archivo JavaScript alojado en el sitio al que se hace referencia en cada página. Los datos se envían directamente a Adobe Analytics.
* **SDK web de Adobe Experience Platform**: Archivo JavaScript alojado en el sitio al que se hace referencia en cada página. Los datos se envían a Adobe Experience Edge.
* **Etiquetas en la recopilación de datos de Adobe Experience Cloud**: Referencia de JavaScript en cada página, que contiene reglas creadas dentro de la interfaz de usuario de la recopilación de datos. La extensión de Adobe Analytics ofrece una forma más sencilla de implementar AppMeasurement. La extensión del SDK web ofrece una forma más sencilla de implementar el SDK web.

Si envía datos a Adobe Experience Edge, puede configurarlos para que reenvíen datos a Adobe Analytics (así como a muchas otras soluciones de Adobe Experience Cloud). Independientemente del método de implementación, en última instancia se envía una solicitud de imagen con las variables deseadas a los servidores de recopilación de datos de Adobe.

## Datos a medida que llegan a los servidores de recopilación de datos de Adobe Analytics

Una vez que los datos llegan a Adobe Analytics, las siguientes funciones ajustan los datos según sea necesario:

1. **Tablas de búsqueda**: Dimension que dependen de tablas de búsqueda internas de Adobe (por ejemplo, la variable [Navegador](/help/components/dimensions/browser.md) dimensión) coincide con su valor correspondiente.
2. [**Variables dinámicas**](/help/implement/vars/page-vars/dynamic-variables.md): Si se ve una variable dinámica en cualquier parte de una solicitud de imagen, el valor se copia y se trata como un valor independiente que avanza.
3. [**Reglas de bots**](/help/admin/admin/bot-removal/bot-rules.md): Aplique un filtro de bots estándar o personalizado para excluir esos datos de los informes.
4. [**Reglas de procesamiento**](/help/admin/admin/c-processing-rules/processing-rules.md): Reglas personalizadas aplicadas a los datos por su organización. Incluye la asignación de [Variables de datos de contexto](/help/implement/vars/page-vars/contextdata.md) a su variable respectiva.
5. **Reglas de VISTA**: Reglas flexibles personalizadas aplicadas a los datos por un consultor de Adobe. Las reglas de VISTA pueden ejecutarse antes o después de las reglas de procesamiento, según las necesidades de su organización. La mayoría de las reglas de VISTA generalmente se ejecutan después de las reglas de procesamiento, pero cada organización está configurada de forma diferente. Póngase en contacto con el administrador de cuentas de Adobe para obtener más información acerca de las reglas de VISTA existentes.
6. [**Reglas de procesamiento de canal de marketing**](/help/components/c-marketing-channels/c-rules.md): Puede usar [Reglas de procesamiento](/help/admin/admin/c-processing-rules/processing-rules.md) para preparar los datos para usarlos en las reglas de procesamiento del canal de marketing.
7. **Datos de geolocalización**: Dimension que dependen de la búsqueda de direcciones IP (por ejemplo, la variable [Países](/help/components/dimensions/countries.md) dimensión) se rellenan.
8. [**Confusión de IP**](/help/admin/admin/general-acct-settings-admin.md): Si su organización ha optado por proteger las direcciones IP de los datos sin procesar, se realiza después de que se hayan completado todas las demás funciones de procesamiento.

En este punto, la visita individual se registra en las tablas de datos del grupo de informes. Después del estándar [latencia](latency.md) , está disponible en los informes.

## Cambio de datos después de procesarlos

Los datos de Adobe Analytics son en su mayoría permanentes; sin embargo, hay algunas características que pueden permitir el ajuste o la eliminación selectivos de los datos:

* [**API de reparación de datos**](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/data-repair/): Edite determinadas columnas o elimine las filas de datos deseadas.
* [**Administración de datos**](/help/admin/c-data-governance/an-gdpr-workflow.md): Acepte solicitudes de privacidad para eliminar datos de forma permanente.
* [**Clasificaciones**](/help/components/classifications/c-classifications.md): Cree dimensiones basadas en reglas o datos cargados que le permitan organizar los datos de forma diferente. Los datos del grupo de informes subyacente no se modifican, por lo que puede editar o sobrescribir libremente los datos de clasificación.
* [**Grupos de informes virtuales**](/help/components/vrs/vrs-about.md): Cree una vista de grupo de informes alternativa que pueda cambiar el tiempo de espera de visita o permitir [Análisis entre dispositivos](/help/components/cda/overview.md).

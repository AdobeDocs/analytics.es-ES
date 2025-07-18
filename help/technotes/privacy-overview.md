---
description: Información general sobre los datos que recopila Adobe Analytics y otras consideraciones de privacidad.
keywords: privacidad
title: Resumen de privacidad
feature: Data Governance
exl-id: 71c83106-a047-47d7-9a70-4a24595e3d0a
source-git-commit: 1281bdc569c9ebc5d8daa151b19dc21710633eab
workflow-type: tm+mt
source-wordcount: '978'
ht-degree: 98%

---

# Resumen de privacidad

Adobe desea habilitar su organización para que pueda cumplir con las leyes y regulaciones aplicables. Consulte [Privacidad de Adobe Experience Cloud](https://www.adobe.com/es/privacy/experience-cloud.html){target=_blank} para obtener más información. Entre Adobe Analytics y su organización, Adobe actúa como “procesador de datos” y usted es el “controlador de datos” (o equivalente según las leyes de privacidad y protección de datos aplicables). Revelar el uso de los productos y servicios de Adobe es decisión de su organización, ya que es esta quien controla exclusivamente cómo implementar las soluciones de Adobe. Al utilizar Adobe Analytics, su organización es responsable de cumplir con su propia política de privacidad, el acuerdo de servicio con Adobe y todas las leyes aplicables.

Adobe recomienda encarecidamente adherirse a los siguientes conceptos generales:

* **Si recopila datos personales, asegúrese de cumplir con las leyes y regulaciones de privacidad.** Las variables personalizadas le permiten recopilar prácticamente cualquier cosa a la que pueda acceder; sin embargo, también debe tener en cuenta la política de privacidad de su organización y las leyes aplicables.
* **Proporcione a sus clientes información de privacidad de su organización fácil de encontrar y comprender.** La información útil incluye vínculos de exclusión, cómo se utilizan los datos de navegación y cómo utiliza o planea utilizar los servicios de Adobe.
* **Tenga en cuenta las leyes locales y las leyes internacionales que se le aplican.** Si su organización opera a escala global, pueden aplicarse algunas leyes internacionales.

## Desglose de los datos recopilados

Adobe ofrece varias bibliotecas de recopilación de datos para ayudarle a enviar datos a Adobe. Algunos ejemplos son:

* **AppMeasurement**: una biblioteca diseñada para enviar datos directamente a Adobe Analytics.
* **SDK web**: una biblioteca diseñada para enviar datos a Edge Network de Adobe Experience Platform, que luego reenvía esos datos a Adobe Analytics.
* **Etiquetas**: IU basada en la web que le permite configurar la implementación sin necesidad de acceder a un sitio web o al código fuente de una aplicación más allá de la implementación inicial de la etiqueta. Las extensiones están disponibles tanto para AppMeasurement como para el SDK web.

Adobe Analytics puede recopilar los siguientes tipos de datos:

| Tipo de datos | Detalles | Variables de ejemplo que contienen estos datos |
| --- | --- | --- |
| Nombres de páginas o direcciones URL de páginas web del sitio | Estos datos son necesarios para que Adobe Analytics funcione. Se requiere una dirección URL o un nombre de página para cada visita. | [Página](../components/dimensions/page.md), [URL de página](../components/dimensions/page-url.md) |
| Datos cronológicos | Estos datos son necesarios para que Adobe Analytics funcione. Se requiere una marca de tiempo para la recopilación de datos y los datos cronológicos se derivan de la marca de tiempo. | [Tiempo empleado en la página](../components/dimensions/time-spent-on-page.md), [Hora del día](../components/dimensions/hour-of-day.md), [AM/PM](../components/dimensions/am-pm.md), [Día laborable/fin de semana](../components/dimensions/weekday-weekend.md), [Día de la semana](../components/dimensions/day-of-week.md), [Mes del año](../components/dimensions/month-of-year.md) |
| Datos del referente | Las bibliotecas de recopilación de datos recopilan la dirección URL de referencia de forma predeterminada cuando un visitante llega al sitio web. Puede personalizar la implementación para recopilar datos dentro de la cadena de consulta de un referente. Esta práctica es común para las campañas y el seguimiento del rendimiento de los anuncios. | [Referente](../components/dimensions/referrer.md), [Dominio de referencia](../components/dimensions/referring-domain.md) |
| ID de visitante anonimizado | Las bibliotecas de recopilación de datos generan y hacen referencia a un ID de visitante para cada explorador que visite el sitio. Este ID se almacena en una cookie. Si una biblioteca de recopilación de datos no puede establecer un identificador de cookie, la biblioteca utiliza un método de reserva de identificación de visitante anónimo. Este método implica vincular visitas relacionadas con la misma visita utilizando la dirección IP del visitante y la cadena del agente de usuario. Si su organización tiene habilitada la confusión de IP, se respeta esta configuración. Consulte [Cookies de Adobe Analytics y del explorador](cookies/cookies.md) para obtener más información. | [Visitantes únicos](../components/metrics/unique-visitors.md) |
| ID de visitante identificable | Adobe no recopila automáticamente los ID de visitante personalizados. Sin embargo, puede personalizar la implementación para recopilar estos datos. | [`visitorID`](../implement/vars/config-vars/visitorid.md) |
| Términos de búsqueda externa | Los datos de búsqueda externa incluyen palabras clave procedentes de los motores de búsqueda. Las bibliotecas de recopilación de datos buscan estos datos en función de la dirección URL de referencia. Sin embargo, muchos motores de búsqueda modernos ya no incluyen esta información. | [Palabra clave de búsqueda](../components/dimensions/search-keyword.md) |
| Términos de búsqueda interna | Los datos de búsqueda interna incluyen palabras clave que se originan dentro de las capacidades de búsqueda del sitio web o la aplicación. Adobe no recopila automáticamente datos de búsqueda interna. Sin embargo, puede personalizar la implementación para recopilar estos datos. Esta práctica es común en las organizaciones que utilizan Adobe Analytics. | [eVar](../components/dimensions/evar.md) |
| Especificaciones del ordenador y del explorador | Las bibliotecas de recopilación de datos recopilan automáticamente sugerencias de explorador de baja entropía, como el tipo de explorador, el tipo de sistema operativo y si el dispositivo es de escritorio o móvil. Se requiere una configuración personalizada para recopilar sugerencias de alta entropía, como la versión/compilación específica del explorador, el modelo del dispositivo o la versión del sistema operativo. Consulte [Información general sobre sugerencias de cliente](client-hints.md) para obtener más información. | [Explorador](../components/dimensions/browser.md), [Sistema operativo](../components/dimensions/operating-systems.md), [Dimensiones móviles](../components/dimensions/mobile-dimensions.md), [Resolución del monitor](../components/dimensions/monitor-resolution.md) |
| Información de geolocalización | Adobe ofrece la capacidad de evitar la ubicación geográfica detallada estableciendo el último octeto de una dirección IP en 0. Esto hace que la información geográfica sea menos precisa y se pueda establecer en [configuración del grupo de informes](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/manage-report-suites/edit-report-suite/report-suite-general/general-acct-settings-admin.html?lang=es). | [Ciudades](../components/dimensions/cities.md), [Regiones](../components/dimensions/regions.md), [Países](../components/dimensions/countries.md) |
| Dirección IP | Adobe permite ocultar (hash) o quitar por completo la dirección IP del visitante al almacenar estos datos. Los clientes de EMEA suelen tener la configuración de la dirección IP ocultada de forma predeterminada. Independientemente de la configuración de ofuscación, la dirección IP no está disponible como dimensión en Analysis Workspace; solo se incluye en [Fuentes de datos](../export/analytics-data-feed/data-feed-overview.md). Consulte [Configuración general de la cuenta](../admin/admin/c-manage-report-suites/c-edit-report-suites/general/general-acct-settings-admin.md) en la Guía de administración para obtener más información sobre la configuración de ofuscación disponible. | Ninguno |
| Información del formulario proporcionada en el sitio | Todos los tipos de implementación requieren configuración para recopilar estos datos. Puede incluir estos datos en variables personalizadas. | [eVar](../components/dimensions/evar.md) |
| Anuncios o vínculos en los que se ha hecho clic en el sitio | Recopilado si [`trackExternalLinks`](../implement/vars/config-vars/trackexternallinks.md) o [`trackDownloadLinks`](../implement/vars/config-vars/trackdownloadlinks.md) está habilitado. Información adicional, como la ubicación de los clics, está disponible cuando habilita Activity Map. | [Activity Map](../analyze/activity-map/overview.md), [Vínculo de salida](../components/dimensions/exit-link.md), [Vínculo de descarga](../components/dimensions/download-link.md) |
| Productos comprados en su sitio | Todos los tipos de implementación requieren configuración para recopilar estos datos. Adobe ofrece varias variables predeterminadas para recopilar esta información. | [Producto](../components/dimensions/product.md), [Pedidos](../components/metrics/orders.md), [Ingresos](../components/metrics/revenue.md) |

{style="table-layout:auto"}

Consulte el menú de navegación debajo de [Información general sobre dimensiones](../components/dimensions/overview.md) y [Resumen de métricas](../components/metrics/overview.md) para más variables en las que el Adobe pueda recopilar datos.

## Ubicaciones de procesamiento de datos

Adobe mantiene tres ubicaciones de procesamiento de datos para Adobe Analytics. Estos sitios reciben datos sin procesar y los procesan en un grupo de informes, que está optimizado para el almacenamiento de datos y la recuperación de informes. Estas ubicaciones de procesamiento de datos residen actualmente en Estados Unidos (Oregón), Reino Unido (Londres) y Singapur. Consulte [Información general sobre la seguridad de Adobe Analytics](https://www.adobe.com/content/dam/cc/es/trust-center/ungated/whitepapers/experience-cloud/adb-analytics-security-wp.pdf){target=_blank} para obtener más información.

---
description: Información general sobre los datos que recopila Adobe Analytics y otras consideraciones de privacidad.
keywords: privacidad
title: Resumen de privacidad
feature: Privacy
exl-id: 71c83106-a047-47d7-9a70-4a24595e3d0a
source-git-commit: ee0bf5beeac3c9780eb0c8420845114f7e840aec
workflow-type: tm+mt
source-wordcount: '694'
ht-degree: 12%

---

# Resumen de privacidad

En el [Centro de privacidad de Adobe](https://www.adobe.com/es/privacy.html), los visitantes pueden obtener más información sobre cómo suele usar Adobe la información que recopila. Revelar el uso de los productos y servicios de Adobe es decisión de su organización, ya que es esta quien controla exclusivamente cómo implementar los servicios de Adobe. Su organización es responsable de cumplir con su propia política de privacidad, su contrato de servicio con el Adobe y todas las leyes aplicables.

El Adobe recomienda encarecidamente adherirse a los siguientes conceptos generales:

* **Evite recopilar información de identificación personal en Adobe Analytics.** Las variables personalizadas le permiten recopilar prácticamente cualquier cosa a la que pueda acceder; sin embargo, también debe tener en cuenta la política de privacidad de su organización y las leyes aplicables.
* **Proporcionar a los visitantes información fácil de encontrar y comprender sobre la información de exclusión.** Permita que se excluyan de cualquier cosa que no sea estrictamente necesaria. La mayoría de los países de la Unión Europea no consideran estrictamente necesarias las cookies de Analytics.

## Desglose de la recopilación de datos

Adobe Analytics recopila automáticamente o puede recopilar los siguientes tipos de datos:

| Tipo de datos | Detalles | Variables de ejemplo que contienen estos datos |
| --- | --- | --- |
| Nombres de páginas o direcciones URL de páginas web del sitio | Siempre recopilado. Se requiere una URL o un nombre de página para cada visita. | [Página](../components/dimensions/page.md), [URL de página](../components/dimensions/page-url.md) |
| Datos basados en el tiempo | Siempre recopilado. La marca de tiempo es necesaria para la recopilación de datos y los datos basados en tiempo se derivan de la marca de tiempo. | [Tiempo empleado en la página](../components/dimensions/time-spent-on-page.md), [Hora del día](../components/dimensions/hour-of-day.md), [AM/PM](../components/dimensions/am-pm.md), [Día laborable/fin de semana](../components/dimensions/weekday-weekend.md), [Día de la semana](../components/dimensions/day-of-week.md), [Mes del año](../components/dimensions/month-of-year.md) |
| Datos de páginas web de otros sitios | El Adobe no puede recopilar datos en sitios no afiliados donde no se puede modificar el código fuente del sitio web. AppMeasurement recopila automáticamente la dirección URL de referencia cuando un visitante llega al sitio web. Puede personalizar la implementación para recopilar datos dentro de las cadenas de consulta una vez que lleguen al sitio. | [Referente](../components/dimensions/referrer.md), [Dominio de referencia](../components/dimensions/referring-domain.md) |
| ID de visitante anonimizado | El AppMeasurement genera y hace referencia automáticamente a un ID de visitante para cada explorador que visite el sitio. Este ID se almacena en una cookie de. Si las cookies no están disponibles para una implementación determinada, Adobe Analytics utiliza un método de reserva de identificación de visitantes mediante la dirección IP y la cadena del agente de usuario. Consulte [Cookies de Adobe Analytics y del explorador](cookies/cookies.md) para obtener más información. | [Visitantes únicos](../components/metrics/unique-visitors.md) |
| ID de visitante identificable | El Adobe de no recopila automáticamente los ID de visitante personalizados. Sin embargo, puede personalizar la implementación para recopilar estos datos. | [`visitorID`](../implement/vars/config-vars/visitorid.md) |
| Términos de búsqueda externa | AppMeasurement intenta recopilar automáticamente estos datos en función de la dirección URL de referencia. Sin embargo, muchos motores de búsqueda modernos ya no incluyen esta información. | [Palabra clave de búsqueda](../components/dimensions/search-keyword.md) |
| Términos de búsqueda interna | El Adobe no recopila automáticamente datos de búsqueda interna. Sin embargo, puede personalizar la implementación para recopilar estos datos y es una práctica habitual en las organizaciones que utilizan Adobe Analytics. | [eVar](../components/dimensions/evar.md) |
| Especificaciones del ordenador y del navegador | El AppMeasurement recopila automáticamente sugerencias de explorador de baja entropía, como el tipo de explorador, el tipo de sistema operativo y si el dispositivo es de escritorio o móvil. La configuración es necesaria para recopilar sugerencias de alta entropía, como la versión/compilación específica del explorador, el modelo del dispositivo o la versión del sistema operativo. Consulte [Información general sobre Client hints](client-hints.md) para obtener más información. | [Explorador](../components/dimensions/browser.md), [Sistema operativo](../components/dimensions/operating-systems.md), [Dimensiones móviles](../components/dimensions/mobile-dimensions.md), [Resolución del monitor](../components/dimensions/monitor-resolution.md) |
| Información de geolocalización | El Adobe permite habilitar o deshabilitar la recopilación de datos de geolocalización para cada sitio web o aplicación (a nivel de grupo de informes). Muchos tipos de implementación, incluido el AppMeasurement, recopilan automáticamente estos datos. | [Ciudades](../components/dimensions/cities.md), [Regiones](../components/dimensions/regions.md), [Países](../components/dimensions/countries.md) |
| Dirección IP | El Adobe permite oscurecer el último octeto o oscurecer por completo la dirección IP del visitante al almacenar estos datos. Los clientes de EMEA suelen tener la dirección IP completamente oscurecida de forma predeterminada. La dirección IP no está disponible como dimensión en Adobe Analytics; solo se incluye en los datos sin procesar ([Fuentes de datos](../export/analytics-data-feed/data-feed-overview.md)). | Ninguno |
| Información del formulario proporcionada en el sitio | Todos los tipos de implementación requieren configuración para recopilar estos datos. Puede incluir estos datos en variables personalizadas. | [eVar](../components/dimensions/evar.md) |
| Anuncios o vínculos en los que se hace clic en el sitio | Se recopila automáticamente si se utiliza el AppMeasurement. La información adicional, como la ubicación de los clics, está disponible con el Activity Map habilitado. | [Activity Map](../analyze/activity-map/activity-map.md), [Vínculo de salida](../components/dimensions/exit-link.md), [Vínculo de descarga](../components/dimensions/download-link.md) |
| Productos comprados en su sitio | Todos los tipos de implementación requieren configuración para recopilar estos datos. El Adobe ofrece varias variables predeterminadas para almacenar esta información. | [Product](../components/dimensions/product.md), [Pedidos](../components/metrics/orders.md), [Ingresos](../components/metrics/revenue.md) |

{style="table-layout:auto"}

Consulte el menú de navegación debajo de [Resumen para Dimension](../components/dimensions/overview.md) y [Resumen de métricas](../components/metrics/overview.md) para más variables en las que el Adobe pueda recopilar datos.

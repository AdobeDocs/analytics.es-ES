---
title: Notas de la versión de Adobe Analytics actual
description: Ver las notas de la versión actuales de Adobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 88d60f38d5a87bacb755a49dc884700ac66039ce
workflow-type: tm+mt
source-wordcount: '725'
ht-degree: 77%

---

# Notas de la versión actuales de Adobe Analytics (agosto de 2024)

**Última actualización**: jueves, 14 de agosto de 2024

Estas notas de la versión abarcan el periodo de lanzamiento del 14 de agosto de 2024 a septiembre de 2024. Las versiones de Adobe Analytics funcionan con un [modelo de entrega continua](releases.md) que permite un enfoque más escalable y gradual de la implementación de funcionalidades. Por lo tanto, estas notas de la versión se actualizan varias veces al mes. Compruébelas regularmente.

## Nuevas funciones o mejoras {#features}

| Función | Descripción | [Inicio del despliegue](releases.md) | [Disponibilidad general](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Mejoras en el SDK web para el seguimiento de vínculos** | Hay varias mejoras importantes disponibles en la última versión del SDK web en torno al seguimiento de vínculos, lo que beneficia directamente a Activity Map. Estas nuevas funciones están disponibles tanto en la biblioteca de JavaScript del SDK web como en su extensión de etiquetas.<ul><li>Agrupación de eventos: cuando un visitante hace clic en un vínculo interno, puede optar por agrupar los datos de evento en la página siguiente en lugar de activar una llamada de evento independiente para el seguimiento de vínculos. Esta mejora reduce el número de eventos que utiliza el SDK web en relación con el límite contractual.</li><li>Filtrado de propiedades de clic: una nueva llamada de retorno que reemplaza a `OnBeforeLinkClickSend`. Puede utilizar esta llamada de retorno para filtrar u ocultar datos relacionados con vínculos antes de enviarlos a Adobe.</li></ul><p>Consulte [clickCollection](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/clickcollection) en la guía del usuario del SDK web para obtener más información.</p> | La versión beta comenzó el 10 de julio de 2024 | viernes, 18 de julio de 2024 |

{style="table-layout:auto"}

## Correcciones en Adobe Analytics

* Se ha corregido un problema por el cual se mostraban varios valores desconocidos en Workspace (AN-353632)
* Se ha corregido un problema por el cual el correo electrónico de notificación no se enviaba después de agregar nuevos clientes o perfiles de producto de Analytics en Admin Console (AN-350930)

### Otras correcciones de Analytics

AN-354361; AN-354248; AN-354211; AN-354324; AN-351532; AN-349808; AN-347831; AN-353777; AN-354092 AN-354064 AN-AN-354006 AN-AN; AN-AN-AN; AN-AN; AN-AN; AN-AN;-AN; Y-AN-AN; Y-AN-354097; AN-AN; Y-AN-AN; Y-AN-AN; Y-AN-AN-AN; Y-AN-AN-AN; Y-AN-AN; Y-354202; AN-; AN-352548; AN-353819; AN-353818; AN-353628; AN-353747; AN-353527; AN-353490; AN-352647; AN-352656; AN-351274; AN-352135; AN-351519; AN-344906; AN-353697; AN-354499; AN-354402; AN-354062; AN-353905; AN-353932; AN-354142; AN-354194; AN-354182; AN-353758; AN-353039; AN-353612; AN-350799; AN-354414; AN-354636 354249 353637 350949 349402 355103 354174 353823 354819 354215 354219 354040 354763 354597 354478 354528 354335;

## Avisos importantes para los administradores de Adobe Analytics {#admin}

| Aviso | Fecha de incorporación o actualización | Descripción |
| ----------- | ---------- | ---------- |
| **13 meses de caducidad de`cust_visids`** guardado | 22 de mayo de 2024 | Una próxima versión del motor de procesamiento de las visitas de Analytics, **prevista para julio de 2024**, empezará a aplicar una caducidad de 13 meses de las `cust_visids` guardadas. Si el conjunto de informes tiene activada la opción &quot;Habilitar identificación de visitantes entre dispositivos&quot;, este ajuste se utiliza para encontrar `cust_visid` para un `visid_high/visid_low value` sin ningún `cust_visid` en la visita. Actualmente, no hay caducidad de la asignación de un `cust_visid` para un `visid_high/visid_low`. Con esta versión, si han pasado 13 meses o más desde que `visid_high/visid_low` tuvo un `cust_visid` en una visita, la asignación caduca. |

{style="table-layout:auto"}

## Avisos de final de la vida útil {#eol}

| Final de la vida útil de producto o función | Fecha de incorporación o actualización | Descripción |
| --- | --- | --- |
| **Final de la vida útil de la API de Adobe Analytics (versión 1.4)** | 17 de julio de 2024 | El **12 de agosto de 2026**, los siguientes servicios de la API heredada de Analytics llegarán al final de su vida útil y se cerrarán, y las integraciones actuales creadas con estos servicios dejarán de funcionar:<ul><li>API de Adobe Analytics (versión 1.4)</li><li>Autenticación WSSE de Adobe Analytics</li></ul><p>Las integraciones que usan la API de Adobe Analytics (versión 1.4) deben migrarse a la [API de Adobe Analytics 2.0](https://developer.adobe.com/analytics-apis/docs/2.0/), mientras que las integraciones de WSSE deben migrarse a un protocolo de autenticación basado en OAuth en [Adobe Developer Console](https://developer.adobe.com/console).</p><p>Consulte las [preguntas frecuentes sobre el final de la vida útil de la API de Adobe Analytics 1.4](/help/admin/c-admin-api/c-admin-14-api-eol.md) para obtener respuestas a dudas comunes y más indicaciones.</p> |
| **Migración a las credenciales de servidor a servidor de Adobe I/O OAuth** | 11 de mayo de 2023 | Los clientes de la API de Adobe Analytics y Livestream que utilizan las credenciales de JWT de Adobe I/O deben migrar a las credenciales de servidor a servidor de Adobe I/O OAuth de forma predeterminada el **1 de enero de 2025**. Adobe I/O no permitirá que se creen nuevas credenciales de JWT a partir del 1 de mayo de 2024. Los clientes que utilizan JWT deben crear una nueva credencial de servidor a servidor OAuth o migrar su credencial JWT existente a una credencial de servidor a servidor OAuth. Los clientes también deben actualizar sus aplicaciones cliente para utilizar las nuevas credenciales de servidor a servidor de OAuth. <ul><li>[Migración de credenciales de cuenta de servicio (JWT)](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[Guía de implementación para aplicaciones nuevas y antiguas con OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[Uso de las nuevas credenciales de servidor a servidor de OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[Preguntas frecuentes](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |

{style="table-layout:auto"}

## AppMeasurement

Para obtener las últimas actualizaciones de las versiones de AppMeasurement (2.26.0), consulte las [notas de la versión de AppMeasurement para JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=es).


## Recursos relacionados

* [Notas de la versión anteriores de 2024](/help/release-notes/2024.md)
* [Notas de la versión de Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=es)
* [Notas de la versión del complemento de colección Streaming Media](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=es)
* Las últimas actualizaciones de la versión para los [productos de Adobe Experience Cloud](https://business.adobe.com/products/adobe-experience-cloud-products.html?lang=es)

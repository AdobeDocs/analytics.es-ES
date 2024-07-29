---
title: Notas de la versión de Adobe Analytics actual
description: Ver las notas de la versión actuales de Adobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: cb0eab15dac6d679e9f912010045e6be2e47df4a
workflow-type: ht
source-wordcount: '732'
ht-degree: 100%

---

# Notas de la versión actuales de Adobe Analytics (julio de 2024)

**Última actualización**: 17 de julio de 2024

Estas notas de la versión cubren el periodo comprendido entre el 17 de julio de 2024 y agosto de 2024. Las versiones de Adobe Analytics funcionan con un [modelo de entrega continua](releases.md) que permite un enfoque más escalable y gradual de la implementación de funcionalidades. Por lo tanto, estas notas de la versión se actualizan varias veces al mes. Compruébelas regularmente.

## Nuevas funciones o mejoras {#features}

| Función | Descripción | [Inicio del despliegue](releases.md) | [Disponibilidad general](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Mejoras en el SDK web para el seguimiento de vínculos** | Hay varias mejoras importantes disponibles en la última versión del SDK web en torno al seguimiento de vínculos, lo que beneficia directamente a Activity Map. Estas nuevas funciones están disponibles tanto en la biblioteca de JavaScript del SDK web como en su extensión de etiquetas.<ul><li>Agrupación de eventos: cuando un visitante hace clic en un vínculo interno, puede optar por agrupar los datos de evento en la página siguiente en lugar de activar una llamada de evento independiente para el seguimiento de vínculos. Esta mejora reduce el número de eventos que utiliza el SDK web en relación con el límite contractual.</li><li>Filtrado de propiedades de clic: una nueva llamada de retorno que reemplaza a `OnBeforeLinkClickSend`. Puede utilizar esta llamada de retorno para filtrar u ocultar datos relacionados con vínculos antes de enviarlos a Adobe.</li></ul><p>Consulte [clickCollection](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/clickcollection) en la guía del usuario del SDK web para obtener más información.</p> | La versión beta comenzó el 10 de julio de 2024 | Por determinar |

{style="table-layout:auto"}

## Correcciones en Adobe Analytics

* Se ha corregido un problema que impedía que los usuarios iniciaran sesión en la interfaz de usuario de Analytics (AN-352953)
* Se ha corregido un problema que impedía que los usuarios iniciaran sesión en la aplicación móvil de Analytics (AN-352463)
* Se ha corregido un problema que impedía descargar el proyecto como PDF (AN-352680)
* Se ha corregido un problema por el que no se importaban las clasificaciones (AN-352178)

### Otras correcciones de Analytics

AN-352905; AN-352902; AN-352693; AN-352659; AN-352619;
AN-352577; AN-352575; AN-352572; AN-352571; AN-352549; AN-352501; AN-352499; AN-352478; AN-352466; AN-352437; AN-352378; AN-352355; AN-352341; AN-352318; AN-352297; AN-352272; AN-352267; AN-352263; AN-352088; AN-352019; AN-352018; AN-351978; AN-351908; AN-351809; AN-351750; AN-351689; AN-351624; AN-351564; AN-351524; AN-351507; AN-351416; AN-351414; AN-351405; AN-351299; AN-351283; AN-351231; AN-350710; AN-349912; AN-349786; AN-348300; AN-348061; AN-347865; AN-347676; AN-347478; AN-343611; AN-343114; AN-334124

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

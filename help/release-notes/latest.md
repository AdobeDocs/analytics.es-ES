---
title: Notas de la versión de Adobe Analytics actual
description: Ver las notas de la versión actuales de Adobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 258ef488f5bcf2ea2057ad3da605679f9e3438b6
workflow-type: tm+mt
source-wordcount: '1145'
ht-degree: 99%

---

# Notas de la versión actuales de Adobe Analytics (mayo de 2024)

**Última actualización**: martes, 03 de junio de 2024

Estas notas de la versión abarcan el periodo de lanzamiento desde el 15 de mayo a junio de 2024. Las versiones de Adobe Analytics funcionan con un [modelo de entrega continua](releases.md) que permite un enfoque más escalable y gradual de la implementación de funcionalidades. Por lo tanto, estas notas de la versión se actualizan varias veces al mes. Compruébelas regularmente.

## Nuevas funciones o mejoras {#features}

| Función | Descripción | [Inicio del despliegue](releases.md) | [Disponibilidad general](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Nueva documentación para actualizar de Adobe Analytics a Customer Journey Analytics** | Para las organizaciones que actualizan de Adobe Analytics a Customer Journey Analytics, existen varias opciones de actualización y muchas consideraciones que se deben tener en cuenta según la implementación de Adobe Analytics actual y los objetivos a largo plazo de una organización. Ya hay disponibles nuevos recursos de documentación para ayudarle a comprender mejor:<ul><li>Las distintas rutas de actualización existentes</li><li>Qué rutas de actualización están disponibles según la implementación de Adobe Analytics actual de una organización</li><li>Las ventajas y desventajas de cada ruta de actualización</li><li>Guía paso a paso para cada ruta de actualización</li><li>Consideraciones para administrar datos históricos</li></ul>[Introducción a la actualización a Customer Journey Analytics](https://experienceleague.adobe.com/es/docs/analytics-platform/using/compare-aa-cja/upgrade-to-cja/cja-upgrade-getstarted) | | Ya disponible |
| **Establecer `contextData` campos mediante XDM** | Los clientes que envían datos a Adobe Analytics a través de Experience Edge Network pueden [establecer valores de datos de contexto](https://experienceleague.adobe.com/es/docs/analytics/implementation/vars/page-vars/contextdata) directamente en XDM o en las partes de “datos” de la carga útil. |  | Ya disponible |
| **API de creación de informes en tiempo real de Analytics 2.0** | La nueva API de creación de informes en tiempo real 2.0 de Adobe Analytics mejora la integración de los clientes y proporciona resultados rápidos de la creación de informes. Estos resultados se pueden utilizar mediante programación para que trabajen con informes básicos, de tendencias y de desglose. [Más información](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/reports/real-time/) | | 30 de mayo de 2024 |
| **Medios de streaming: envíe datos web a Edge Network de Adobe Experience Platform con SDK web** | Ahora puede utilizar SDK web de Adobe Experience Platform para enviar datos web de medios de streaming a Adobe Experience Platform Edge Network. Esta mejora le permite crear campañas más personalizadas y proporcionar contenido más personalizado, lo que da como resultado más datos de seguimiento sobre los que informar.<p>Este cambio proporciona un método de colección unificado para implementaciones web en todas las soluciones de Platform, como Customer Journey Analytics, Adobe Real-time CDP, Adobe Journey Optimizer y reenvío de eventos. Anteriormente, la única manera de enviar datos web de medios de streaming a Edge Network era mediante la API de Media Edge.  <p>[Más información](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/edge-web-sdk)</p> | | jueves, 29 de mayo de 2024 |
| **Aumento de los umbrales de bajo tráfico predeterminados** | A **mediados de abril de 2024**, Adobe empezará a aumentar los umbrales de bajo tráfico predeterminados del grupo de informes de la siguiente manera: ![umbrales de bajo tráfico](assets/thresholds.png) Esto afectará únicamente a las variables que actualmente están configuradas por debajo de los nuevos umbrales. Estos cambios se introducirán gradualmente y esperamos que el trabajo esté terminado a **finales de mayo**. A medida que se vayan aplicando estos incrementos, es posible que note cambios en las variables de alta cardinalidad:<ul><li>Puede haber más valores de dimensión disponibles para la creación de informes.</li><li>Los segmentos y las métricas calculadas pueden incluir más datos.</li><li>Los conjuntos de informes virtuales basados en segmentos pueden incluir más datos.</li><li>Las exportaciones de clasificación pueden incluir más datos.</li></ul> | Mediados de abril de 2024 | 31 de mayo de 2024 |
| **Configuración del administrador para controlar las cuentas y ubicaciones que se utilizan para exportación e importación** | La nueva pestaña “Configuración de administración” del Administrador de ubicaciones permite a los administradores controlar si los usuarios pueden crear y editar cuentas y ubicaciones. Esta configuración se aplica cuando los usuarios configuran cuentas de importación y exportación en la nube y configuran ubicaciones de importación y exportación en la nube. <p>Los administradores también pueden limitar los tipos de cuentas (Google Cloud Platform, Azure RBAC, Amazon S3, etc.) que pueden crear y utilizar los usuarios.</p><p>Anteriormente, cualquier usuario podía crear, editar y utilizar cuentas y ubicaciones para cualquier tipo de cuenta.</p><p>(Vínculo a documentación actualizada a seguir)</p> | jueves, 12 de junio de 2024 | lunes, 30 de junio de 2024 |
| **Compartir cuentas y ubicaciones que se utilizan para exportar e importar** | Ahora, los usuarios pueden poner las cuentas y ubicaciones que creen a disposición de todos los usuarios de su organización. Los propietarios de cuentas y ubicaciones y los administradores del sistema son los únicos que pueden editar y eliminar cuentas y ubicaciones.<p>Antes, las cuentas y ubicaciones solo las podía utilizar el usuario que las había creado.</p><p>Esta configuración está disponible cuando los usuarios configuran cuentas de importación y exportación en la nube y configuran ubicaciones de importación y exportación en la nube. </p> <p>(Vínculo a documentación actualizada a seguir)</p> | jueves, 12 de junio de 2024 | lunes, 30 de junio de 2024 |
| **Activity Map utiliza menos llamadas al servidor para SDK web** | Actualmente, los eventos de vínculo de Activity Map se cuentan como eventos propios e incurren en un coste adicional. Esta mejora toma algunos eventos de vínculo y los empaqueta en la siguiente visita, de forma similar a como se gestionan los eventos en AppMeasurement. <p>(Vínculo a documentación actualizada a seguir)</p> | La versión beta abierta comienza el 19 de junio de 2024 | Por determinar |

{style="table-layout:auto"}

## Correcciones en Adobe Analytics

* Se han corregido los siguientes problemas de clasificaciones: AN-343186; AN-344711; AN-344856; AN-345094; AN-345179; AN-346265; AN-345288; AN-346339; AN-346560; AN-347572; AN-347681; AN-347768; AN-348024
* Se han corregido los siguientes problemas del almacén de datos: AN-346789; AN-347031; AN-347568;
* Se han corregido los siguientes problemas de fuentes de datos: AN-343616; AN-345831; AN-345988; AN-346124; AN-346232; AN-346972; AN-347680; AN-347755; AN-347954
* Se ha corregido el siguiente problema de fuentes de datos: AN-347890;
* Se han corregido los siguientes problemas de Analysis Workspace: AN-321503; AN-343103; AN-343471; AN-345171; AN-345223; AN-345912; AN-346026; AN-346330; AN-346839; AN-347679
* Se ha corregido el siguiente problema de A4T: AN-345118;

### Otras correcciones de Analytics

AN-327749; AN-332949; AN-342881; AN-343171; AN-343708; AN-344034; AN-345559; AN-346023; AN-346230; AN-346330; AN-346469; AN-346606; AN-346750; AN-346973; AN-347026; AN-347110; AN-347439;

## Avisos importantes para los administradores de Adobe Analytics {#admin}

| Aviso | Fecha de incorporación o actualización | Descripción |
| ----------- | ---------- | ---------- |
| **13 meses de caducidad de`cust_visids`** guardado | 22 de mayo de 2024 | Una próxima versión del motor de procesamiento de las visitas de Analytics, **prevista para julio de 2024**, empezará a aplicar una caducidad de 13 meses de las `cust_visids` guardadas. Si el conjunto de informes tiene activada la opción &quot;Habilitar identificación de visitantes entre dispositivos&quot;, este ajuste se utiliza para encontrar `cust_visid` para un `visid_high/visid_low value` sin ningún `cust_visid` en la visita. Actualmente, no hay caducidad de la asignación de un `cust_visid` para un `visid_high/visid_low`. Con esta versión, si han pasado 13 meses o más desde que `visid_high/visid_low` tuvo un `cust_visid` en una visita, la asignación caduca. |
| **Actualizaciones de región ISO** | 10 de mayo de 2024 | Adobe realizará actualizaciones de la zona ISO 2024 el 7 de junio de 2024. Es de esperar que se produzcan pequeñas actualizaciones de la información geográfica (región) tras esta versión. |

{style="table-layout:auto"}

## Avisos de final de la vida útil {#eol}

| Final de la vida útil de producto o función | Fecha de incorporación o actualización | Descripción |
| --- | --- | --- |
| **Migración a las credenciales de servidor a servidor de Adobe I/O OAuth** | 11 de mayo de 2023 | Los clientes de la API de Adobe Analytics y Livestream que utilizan las credenciales de JWT de Adobe I/O deben migrar a las credenciales de servidor a servidor de Adobe I/O OAuth de forma predeterminada el **1 de enero de 2025**. Adobe I/O no permitirá que se creen nuevas credenciales de JWT a partir del 1 de mayo de 2024. Los clientes que utilizan JWT deben crear una nueva credencial de servidor a servidor OAuth o migrar su credencial JWT existente a una credencial de servidor a servidor OAuth. Los clientes también deben actualizar sus aplicaciones cliente para utilizar las nuevas credenciales de servidor a servidor de OAuth. <ul><li>[Migración de credenciales de cuenta de servicio (JWT)](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[Guía de implementación para aplicaciones nuevas y antiguas con OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[Uso de las nuevas credenciales de servidor a servidor de OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[Preguntas frecuentes](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |

{style="table-layout:auto"}

## AppMeasurement

Para obtener las últimas actualizaciones de las versiones de AppMeasurement (2.26.0), consulte las [notas de la versión de AppMeasurement para JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=es).


## Recursos relacionados

* [Notas de la versión anteriores de 2023](/help/release-notes/2023.md)
* [Notas de la versión de Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=es)
* [Notas de la versión de Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=es)
* Las últimas actualizaciones de la versión para los [productos de Adobe Experience Cloud](https://business.adobe.com/es/products/adobe-experience-cloud-products.html)

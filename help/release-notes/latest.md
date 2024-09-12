---
title: Notas de la versión de Adobe Analytics actual
description: Ver las notas de la versión actuales de Adobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 7dd42948073b56a33c1d00f9b4292d1cc3416470
workflow-type: tm+mt
source-wordcount: '750'
ht-degree: 66%

---

# Notas de la versión actuales de Adobe Analytics (septiembre de 2024)


**Última actualización**: jueves, 11 de septiembre de 2024

Estas notas de la versión abarcan el periodo de lanzamiento del 11 de septiembre de 2024 a principios de octubre. Las versiones de Adobe Analytics funcionan con un [modelo de entrega continua](releases.md) que permite un enfoque más escalable y gradual de la implementación de funcionalidades. Por lo tanto, estas notas de la versión se actualizan varias veces al mes. Compruébelas regularmente.

## Nuevas funciones o mejoras {#features}

| Función | Descripción | [Inicio del despliegue](releases.md) | [Disponibilidad general](releases.md) |
|--- | --- | --- | --- |
| **Información adicional en la columna “Utilizado en” del Administrador de métricas calculadas y del Administrador de segmentos** | La columna “Utilizado en” del Administrador de métricas calculadas y del Administrador de segmentos contiene las siguientes áreas nuevas de creación de informes:<ul><li>**Report Builder**: muestra el número de métricas calculadas o segmentos que se están usando en el Report Builder.</li><li>**Componentes ad hoc**: Muestra el número de métricas calculadas ad hoc o segmentos ad hoc que se están usando en los proyectos. Estas métricas calculadas ad hoc y segmentos ad hoc (también conocidos como “métricas calculadas rápidas” y “segmentos rápidos”) solo se pueden usar en el proyecto en el que se crearon, por lo que se notifican por separado desde el área de creación de informes del “Proyecto” en la columna “Utilizado en”.</li></ul>Para obtener más información, consulte [Administrador de métricas calculadas](https://experienceleague.adobe.com/en/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-manager) y [Administrador de segmentos](https://experienceleague.adobe.com/en/docs/analytics/components/segmentation/segmentation-workflow/seg-manage). |  | 11 de septiembre de 2024 |
| **extensión de Activity Map v3** | Ya está disponible la extensión de Activity Map v3. Si tiene instalada la extensión v2, desinstálela antes de instalar la extensión v3. Vaya a **[!UICONTROL Herramientas]** > **[!UICONTROL Activity Map]** para obtener la versión más reciente de la extensión. |  | 3 de septiembre de 2024 |


## Correcciones en Adobe Analytics

A4T: AN-355736
Activity Map: AN-353779
Analysis Workspace: AN-348485; AN-349693; AN-357247
Aplicación móvil de Analytics: AN-352645
Clasificaciones: AN-355636; AN-355651; AN-355753; AN-356005; AN-356439; AN-356540; AN-356577; AN-356622
Análisis entre dispositivos: AN-355138
Fuentes de datos: AN-356258; AN-357133
Data Warehouse: AN-339292; AN-353807
Ubicaciones de exportación: AN-356912
API de privacidad: AN-352420
Report Builder: AN-352555; AN-354316
Proyectos programados: AN-355971
Segmentación: AN-352095;
Informes de Target: AN-355748

Otras correcciones: AN-349698; AN-349880; AN-354860; AN-355355; AN-356289;

## Avisos importantes para los administradores de Adobe Analytics {#admin}

| Aviso | Fecha de incorporación o actualización | Descripción |
| ----------- | ---------- | ---------- |
| **13 meses de caducidad de`cust_visids`** guardado | 20 de agosto de 2024 | La versión del **20 de agosto de 2024** del motor de procesamiento de la visita de análisis aplica una caducidad de 13 meses de `cust_visids` guardado. Si el conjunto de informes tiene activada la opción &quot;Habilitar identificación de visitantes entre dispositivos&quot;, este ajuste se utiliza para encontrar `cust_visid` para un `visid_high/visid_low value` sin ningún `cust_visid` en la visita. Actualmente, no hay caducidad de la asignación de un `cust_visid` para un `visid_high/visid_low`. Con esta versión, si han pasado 13 meses o más desde que `visid_high/visid_low` tuvo un `cust_visid` en una visita, la asignación caduca. |
| **Campos XDM de detalle de implementación adicionales asignados automáticamente** | 11 de septiembre de 2024 | Al utilizar el Edge Network de Adobe Experience Platform para enviar datos a Adobe Analytics, los campos XDM `xdm.implementationdetails.name` y `xdm.implementationdetails.environment` ahora siempre se asignan a las variables de datos de contexto `c.a.x.implementationdetails.name` y `c.a.x.implementationdetails.environment`. Anteriormente, algunos escenarios evitaban que estos valores se rellenaran. Ajuste las reglas de procesamiento relevantes para ajustarse a la disponibilidad de estos valores. |

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

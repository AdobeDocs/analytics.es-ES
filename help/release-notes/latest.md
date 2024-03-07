---
title: Notas de la versión de Adobe Analytics actual
description: Ver las notas de la versión actuales de Adobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 3c6e11dd9d0044dbf79fa0ba97e55a547966d120
workflow-type: tm+mt
source-wordcount: '903'
ht-degree: 50%

---

# Notas de la versión actuales de Adobe Analytics (febrero de 2024)

**Última actualización**: jueves, 21 de febrero de 2024

Estas notas de la versión abarcan el periodo de lanzamiento del 14 de febrero de 2024 al 11 de marzo de 2024. Las versiones de Adobe Analytics funcionan con un [modelo de entrega continua](releases.md) que permite un enfoque más escalable y gradual de la implementación de funcionalidades. Por lo tanto, estas notas de la versión se actualizan varias veces al mes. Compruébelas regularmente.

## Nuevas funciones o mejoras {#features}

| Función | Descripción | [Inicio del despliegue](releases.md) | [Disponibilidad general](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **actualización de AppMeasurement** | [Versión de AppMeasurement v2.26.0](/help/implement/appmeasurement-updates.md) está disponible. | | martes, 04 de marzo de 2024 |
| **Actualizaciones de Data Warehouse** | Ya están disponibles las siguientes mejoras de Data Warehouse:<ul><li>Al crear una solicitud de Data Warehouse, los usuarios ahora pueden poner las solicitudes a disposición de todos los usuarios de la organización habilitando la nueva opción denominada [!UICONTROL **Poner a disposición de los usuarios de su organización**].<p>Para obtener más información, consulte [Configuración general de solicitudes de Data Warehouse](/help/export/data-warehouse/create-request/dw-general-settings.md).</p></li><li>Al crear o administrar destinos de informes de Data Warehouse, los administradores del sistema ahora pueden mostrar cuentas y ubicaciones creadas por usuarios de la organización habilitando la opción llamada [!UICONTROL **Mostrar todos los destinos**].<p>Para obtener más información, consulte [Configuración del destino de un informe para una solicitud de Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md).</p></li> | N/A | 10 de enero de 2024 |
| **Actualizaciones de la visualización Resumen de métricas clave** | Al utilizar la visualización Resumen de métricas clave, el intervalo de fechas de comparación ahora se puede actualizar automáticamente, en función de si la opción Intervalo de fechas de comparación que elija es relativa al intervalo de fechas principal o fija. [Más información](/help/analyze/analysis-workspace/visualizations/key-metric.md). | N/A | 17 de enero de 2024 |
| **Documentación de API de Data Warehouse** | Consulte la [API DE Data Warehouse DE Adobe Analytics 2.0](https://adobedocs.github.io/analytics-2.0-apis/?urls.primaryName=Data%20Warehouse%20APIs#/Data%20Warehouse%20Scheduled%20Requests%20API) para obtener más información. Ir a [!UICONTROL Seleccionar una definición] y seleccione [!UICONTROL API de Data Warehouse]. | | martes, 19 de febrero de 2024 |
| **Activity Map para SDK web sin coste adicional** | Actualmente, los eventos de vínculo de Activity Map se cuentan como eventos propios y conllevan un coste adicional. Esta mejora toma algunos eventos de vínculo y los empaqueta en la siguiente visita, de forma similar a como el AppMeasurement gestiona los eventos. |  | jueves, 03 de abril de 2024 |
| **Aumento de los umbrales de poco tráfico predeterminados** | Entrada **mediados de abril de 2024**, el Adobe empezará a aumentar los umbrales de poco tráfico predeterminados del grupo de informes de la siguiente manera: ![umbrales de poco tráfico](assets/thresholds.png) Esto solo afecta a las variables que actualmente están configuradas por debajo de los nuevos umbrales. Estos cambios se realizarán gradualmente y esperamos que el trabajo se complete antes de que finalice el **finales de mayo**. A medida que se desplieguen estos aumentos, es posible que observe cambios en las variables de alta cardinalidad:<ul><li>Pueden estar disponibles más valores de dimensión para la creación de informes.</li><li>Los segmentos y las métricas calculadas pueden incluir más datos.</li><li>Los grupos de informes virtuales basados en segmentos pueden incluir más datos.</li><li>Las exportaciones de clasificación pueden incluir más datos.</li></ul> | Mediados de abril de 2024 | Final de mayo de 2024 |

{style="table-layout:auto"}

## Correcciones en Adobe Analytics

* Se han corregido los siguientes problemas de clasificaciones: AN-319515; AN-337559; AN-338149; AN-338702; AN-338769; AN-338891; AN-339327; AN-339649; AN-339668; AN-339669; AN-339776; AN-339822; AN-340017; AN-340202; AN-340476;
* Se han corregido los siguientes problemas del Generador de reglas de clasificación: AN-338385; AN-338399; AN-338592; AN-338810; AN-338893; AN-339431; AN-339894; AN-339933; AN-340201; AN-340309;
* Se han corregido los siguientes problemas de A4T: AN-334830; AN-336194; AN-338309; AN-338650;
* Se ha corregido el siguiente problema de recopilación de datos: AN-339323
* Se han corregido los siguientes problemas de Data Warehouse: AN-335542; AN-331425; AN-337215; AN-338445; AN-338643; AN-338651; AN-339461; AN-340066; AN-340207; AN-340460
* Se han corregido los siguientes problemas de fuentes de datos: AN-335952; AN-338653; AN-339508; AN-339681; AN-340418
* Se han corregido los siguientes problemas de fuentes de datos: AN-338648
* Se han corregido los siguientes problemas de Analysis Workspace: AN-326509; AN-336186; AN-336190; AN-336309; AN-337922; AN-338094; AN-338323; AN-338556; AN-339600; AN-340445

### Otras correcciones de Analytics

AN-328239; AN-332908; AN-335449; AN-335517; AN-336075; AN-336100; AN-336128; AN-338088; AN-338270; AN-338393; AN-338494; AN-339326; AN-339742; AN-339883; AN-340419;

## Avisos importantes para los administradores de Adobe Analytics {#admin}

| Aviso | Fecha de incorporación o actualización | Descripción |
| ----------- | ---------- | ---------- |
| Adiciones de miembros de objeto de API de Adobe | 17 de enero de 2024 | El Adobe puede agregar miembros de solicitud y respuesta opcionales (pares de nombre/valor) a objetos de API existentes en cualquier momento y sin previo aviso ni cambios en el control de versiones. El Adobe recomienda que consulte la documentación de la API de cualquier herramienta de terceros que integre con nuestras API para que dichas adiciones se ignoren en el procesamiento, si no se comprenden. Si se implementan correctamente, estas adiciones son cambios interactivos para la implementación. Adobe no quitará los parámetros ni añadirá los parámetros necesarios sin antes proporcionar una notificación estándar mediante las notas de la versión. |
| `getPageLoadTime` complemento obsoleto | 10 de enero de 2024 | Este complemento ya no es compatible.  Su código utiliza el método performance.timing, que (según MDN) ha quedado [obsoleto](https://developer.mozilla.org/en-US/docs/Web/API/PerformanceTiming).  Se ha iniciado el trabajo en un complemento actualizado. |

{style="table-layout:auto"}

## Avisos de final de la vida útil {#eol}

| Final de la vida útil de producto o función | Fecha de incorporación o actualización | Descripción |
| --- | --- | --- |
| **Migración a las credenciales de servidor a servidor de Adobe I/O OAuth** | 11 de mayo de 2023 | Los clientes de la API de Adobe Analytics y Livestream que utilizan las credenciales de JWT de Adobe I/O deben migrar a las credenciales de servidor a servidor de Adobe I/O OAuth de forma predeterminada el **1 de enero de 2025**. Adobe I/O no permitirá que se creen nuevas credenciales de JWT a partir del 1 de mayo de 2024. Los clientes que utilizan JWT deben crear una nueva credencial de servidor a servidor OAuth o migrar su credencial JWT existente a una credencial de servidor a servidor OAuth. Los clientes también deben actualizar sus aplicaciones cliente para utilizar las nuevas credenciales de servidor a servidor de OAuth. <ul><li>[Migración de credenciales de cuenta de servicio (JWT)](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[Guía de implementación para aplicaciones nuevas y antiguas con OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[Uso de las nuevas credenciales de servidor a servidor de OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[Preguntas frecuentes](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |

{style="table-layout:auto"}

## AppMeasurement

Para obtener las últimas actualizaciones de las versiones de AppMeasurement (2.25.0), consulte las [notas de la versión de AppMeasurement para JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=es).


## Recursos relacionados

* [Notas de la versión anteriores de 2023](/help/release-notes/2023.md)
* [Notas de la versión de Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=es)
* [Notas de la versión de Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=es)
* Las últimas actualizaciones de la versión para los [productos de Adobe Experience Cloud](https://business.adobe.com/es/products/adobe-experience-cloud-products.html)

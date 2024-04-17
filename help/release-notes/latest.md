---
title: Notas de la versión de Adobe Analytics actual
description: Ver las notas de la versión actuales de Adobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: d2b2ebdbc6a3c0f20b8684ba5c1b4b89cefb8e5a
workflow-type: tm+mt
source-wordcount: '1240'
ht-degree: 51%

---

# Notas de la versión actuales de Adobe Analytics (abril de 2024)

**Última actualización**: jueves, 17 de abril de 2024

Estas notas de la versión abarcan el periodo de lanzamiento del 17 de abril de 2024 a mayo. Las versiones de Adobe Analytics funcionan con un [modelo de entrega continua](releases.md) que permite un enfoque más escalable y gradual de la implementación de funcionalidades. Por lo tanto, estas notas de la versión se actualizan varias veces al mes. Compruébelas regularmente.

## Nuevas funciones o mejoras {#features}

| Función | Descripción | [Inicio del despliegue](releases.md) | [Disponibilidad general](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Streaming Media: Envío de datos de Roku al Edge Network de Adobe Experience Platform** | Ahora, cuando [instalación de Media Analytics con Experience Platform Edge](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge)Además, puede utilizar el SDK de Roku de Adobe Experience Platform para enviar datos de medios de streaming a Adobe Experience Platform. |  | 12 de abril de 2024 |
| **Flujo de trabajo mejorado para la migración del SDK web** | La recopilación de datos de Adobe Experience Platform ahora asigna automáticamente muchos campos del objeto de datos directamente a Adobe Analytics. Este flujo de trabajo mejorado ofrece las siguientes ventajas:<ul><li>Permite a su organización migrar al SDK web sin tener que preocuparse por crear o adherirse a un [!UICONTROL Esquema XDM]. Consulte [Asignación de variables de objeto de datos](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/data-var-mapping) para obtener más información. (Más vínculos de documentación a continuación)</li><li>Después de migrar al SDK web, su organización está en mejor posición para migrar de Adobe Analytics a Customer Journey Analytics. Esto se debe a que el SDK web permite una migración más fluida a Customer Journey Analytics.</li></ul> (Próximamente, se proporcionará más información sobre esta y otras opciones de migración). |  | Abril de 2024 |
| **Mejora de permisos solo para proyectos [!UICONTROL Workspace] componentes** | Anteriormente, si un usuario (usuario A) compartía un proyecto con otro usuario (usuario B) y daba al usuario B acceso de edición al proyecto, el usuario B podía editar el proyecto. Sin embargo, el usuario B no podría editar [!UICONTROL Segmentos rápidos] incrustado en el proyecto. Esa limitación se ha eliminado: el usuario B puede editar [!UICONTROL Segmentos rápidos] y otros componentes solo de proyecto incrustados en el proyecto compartido. |  | 17 de abril de 2024 |
| **Utilice las mismas cuentas de nube para [!UICONTROL Fuentes de datos], [!UICONTROL Data Warehouse], y [!UICONTROL Conjuntos de clasificaciones]** | Las cuentas y ubicaciones de nube que cree ahora se pueden utilizar para exportar datos (con [!UICONTROL Fuentes de datos] y [!UICONTROL Data Warehouse]) e importación de datos (con [!UICONTROL Conjuntos de clasificaciones]).<p> **Cambios al configurar cuentas:** Los usuarios pueden [Configuración de cuentas de importación y exportación de nube](https://experienceleague.adobe.com/en/docs/analytics/components/locations/configure-import-accounts) y [Configurar ubicaciones de importación y exportación de la nube](https://experienceleague.adobe.com/en/docs/analytics/components/locations/configure-import-locations) que se puede utilizar para cualquiera de los siguientes fines:<ul><li>Importación de datos [!UICONTROL Conjuntos de clasificaciones]</li><li>Exportar datos con [!UICONTROL Fuentes de datos]</li><li>Exportar datos con [!UICONTROL Data Warehouse].</li></ul><p>**Cambios al administrar cuentas**: los usuarios pueden utilizar el [Ubicaciones](https://experienceleague.adobe.com/en/docs/analytics/components/locations/locations-manager) página (debajo de [!UICONTROL Componentes] > Locacciones) para ver y administrar todas las cuentas y ubicaciones que crean, independientemente de dónde se crearon. <p>Anteriormente, la variable [!UICONTROL Ubicaciones] página se aplica solo a las cuentas creadas para importar datos con [!UICONTROL Conjuntos de clasificaciones].</p> | | 17 de abril de 2024 |
| **Los administradores pueden administrar todas las ubicaciones y cuentas de su organización** | Una nueva opción de la pestaña Ubicaciones (en la página Componentes > Ubicaciones) permite a los administradores ver y administrar todas las ubicaciones de la organización.<p>Una nueva opción de [Ubicación](https://experienceleague.adobe.com/en/docs/analytics/components/locations/locations-manager) La pestaña Cuentas (en la página Componentes > Ubicaciones) permite a los administradores ver y administrar todas las cuentas de la organización.</p> <p>Anteriormente, los administradores solo podían ver y administrar las ubicaciones y cuentas que habían creado.</p> |  | 17 de abril de 2024 |
| **Aumento de los umbrales de bajo tráfico predeterminados** | A **mediados de abril de 2024**, Adobe empezará a aumentar los umbrales de bajo tráfico predeterminados del grupo de informes de la siguiente manera: ![umbrales de bajo tráfico](assets/thresholds.png) Esto afectará únicamente a las variables que actualmente están configuradas por debajo de los nuevos umbrales. Estos cambios se introducirán gradualmente y esperamos que el trabajo esté terminado a **finales de mayo**. A medida que se vayan aplicando estos incrementos, es posible que note cambios en las variables de alta cardinalidad:<ul><li>Puede haber más valores de dimensión disponibles para la creación de informes.</li><li>Los segmentos y las métricas calculadas pueden incluir más datos.</li><li>Los conjuntos de informes virtuales basados en segmentos pueden incluir más datos.</li><li>Las exportaciones de clasificación pueden incluir más datos.</li></ul> | Mediados de abril de 2024 | sábado, 31 de mayo de 2024 |
| **Activity Map utiliza menos llamadas al servidor para el SDK web** | Actualmente, los eventos de vínculo de Activity Map se cuentan como eventos propios e incurren en un coste adicional. <p>Esta mejora toma algunos eventos de vínculo y los empaqueta en la siguiente visita, de forma similar a como se gestionan los eventos en AppMeasurement.</p> |  | sábado, 31 de mayo de 2024 |

{style="table-layout:auto"}

## Correcciones en Adobe Analytics

* Se han corregido los siguientes problemas de clasificaciones: AN-343439; AN-343503; AN-343504; AN-343986; AN-344262; AN-344564; AN-345204; AN-345234
* Se han corregido los siguientes problemas del Generador de reglas de clasificación: AN-341488; AN-342501; AN-345751
* Se ha corregido el siguiente problema de Alertas inteligentes: AN-343466;
* Se ha corregido el siguiente problema de segmentación: AN-342313
* Se ha corregido el siguiente problema de Data Warehouse: AN-344292
* Se han corregido los siguientes problemas de fuentes de datos: AN-339545; AN-340092; AN-342124; AN-342862; AN-343737; AN-344035; AN-344329; AN-344703; AN-344721; AN-344940; AN-345180; AN-345196; AN-345225; AN-345236; AN-345326; AN-345631; AN-345659
* Se ha corregido el siguiente problema de fuente de datos: AN-343541
* Se han corregido los siguientes problemas de Analysis Workspace: AN-336303; AN-336472; AN-338422; AN-338556; AN-339718; AN-340147; AN-340301; AN-340421; AN-340951; AN-341172; AN-342905; AN-342909; AN-343448; AN-343570; AN-344050; AN-344182; AN-344763; AN-344768;
* Se han corregido los siguientes problemas de administración de Analytics: AN-342519; AN-342523; AN-343623; AN-343882; AN-344237; AN-344829; AN-345235;
* Se han corregido los siguientes problemas de A4T: AN-341619; AN-344402
* Se ha corregido el siguiente problema de la aplicación móvil: AN-342010

### Otras correcciones de Analytics

AN-336099; AN-337474; AN-337993; AN-339718; AN-339901; AN-340014; AN-341356; AN-343021; AN-343102; AN-343353; AN-343416; AN-340014; AN-344037; AN-344525; AN-345737

## Avisos importantes para los administradores de Adobe Analytics {#admin}

| Aviso | Fecha de incorporación o actualización | Descripción |
| ----------- | ---------- | ---------- |
| **13 meses de caducidad de`cust_visids`** guardado | 20 de marzo de 2024 | Una próxima versión del motor de procesamiento de la visita de análisis, prevista para abril o mayo, empezará a aplicar una caducidad de 13 meses de `cust_visids` guardado. Si el conjunto de informes tiene activada la opción &quot;Habilitar identificación de visitantes entre dispositivos&quot;, este ajuste se utiliza para encontrar `cust_visid` para un `visid_high/visid_low value` sin ningún `cust_visid` en la visita. Actualmente, no hay caducidad de la asignación de un `cust_visid` para un `visid_high/visid_low`. Con esta versión, si han pasado 13 meses o más desde que `visid_high/visid_low` tuvo un `cust_visid` en una visita, la asignación caducará. |
| **Adiciones de miembros de objeto de API de Adobe** | 17 de enero de 2024 | Adobe puede añadir miembros de solicitud y respuesta opcionales (pares de nombre/valor) a objetos de API existentes sin previo aviso ni cambios en las versiones. Adobe le recomienda que consulte la documentación de la API de cualquier herramienta de terceros que integre con nuestras API para que dichas adiciones se ignoren en el procesamiento, si no se comprenden. Si se implementan correctamente, estas adiciones son cambios no rupturistas para su implementación. Adobe no quitará los parámetros ni añadirá los parámetros necesarios sin antes proporcionar una notificación estándar mediante las notas de la versión. |

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

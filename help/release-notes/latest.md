---
title: Notas de la versión de Adobe Analytics actual
description: Ver las notas de la versión actuales de Adobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 6349edc65b953ce7f41d5a5990c8afd6efa20d8d
workflow-type: tm+mt
source-wordcount: '987'
ht-degree: 55%

---

# Notas de la versión actuales de Adobe Analytics (junio de 2024)

**Última actualización**: jueves, 12 de junio de 2024

Estas notas de la versión abarcan el periodo de lanzamiento del 12 de junio de 2024 a julio. Las versiones de Adobe Analytics funcionan con un [modelo de entrega continua](releases.md) que permite un enfoque más escalable y gradual de la implementación de funcionalidades. Por lo tanto, estas notas de la versión se actualizan varias veces al mes. Compruébelas regularmente.

## Nuevas funciones o mejoras {#features}

| Función | Descripción | [Inicio del despliegue](releases.md) | [Disponibilidad general](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Seleccione varios filtros cuando estén disponibles en el menú desplegable de una tabla de forma libre** | Cuando se han agregado varios filtros a una tabla de forma libre como menú desplegable, los usuarios de la tabla de forma libre ahora pueden seleccionar más de un filtro a la vez. La tabla de forma libre se filtra para incluir cualquiera de los filtros seleccionados. Anteriormente, los usuarios solo podían seleccionar un filtro a la vez en un menú desplegable de filtros.<p>(A continuación encontrará un vínculo a la documentación). |  | jueves, 19 de junio de 2024 |
| **Tabla de contenido de los proyectos de Workspace** | Ya está disponible una nueva tabla de contenido para los proyectos. La tabla de contenido proporciona vínculos que permiten a los usuarios saltar rápidamente a paneles y visualizaciones dentro del proyecto. La tabla de contenido se puede habilitar para proyectos individuales o para todos los proyectos de un usuario determinado.<p>(A continuación encontrará un vínculo a la documentación). |  | jueves, 19 de junio de 2024 |
| **Creación de hipervínculos para elementos de dimensión en una tabla de forma libre** | Puede crear hipervínculos para uno o varios elementos de dimensión a fin de que se pueda hacer clic en ellos dentro de una tabla de forma libre en Analysis Workspace. <p>Puede crear hipervínculos para elementos de dimensión que tengan valores de URL o puede crear direcciones URL personalizadas para elementos de dimensión que no tengan valores de URL.</p><p>Puede crear direcciones URL personalizadas dinámicas para varios elementos de dimensión mediante variables. Las variables pueden hacer referencia al valor de un elemento de dimensión o pueden hacer referencia a la dimensión de desglose.</p><p>(A continuación encontrará un vínculo a la documentación).<!--For more information, see "Add hyperlinks to dimensions in a freeform table."--></p> |  | jueves, 19 de junio de 2024 |
| **Configuración del administrador para controlar las cuentas y ubicaciones que se utilizan para exportación e importación** | Un nuevo [Pestaña &quot;Configuración de administración&quot; en el Administrador de ubicaciones](/help/components/locations/locations-manager.md#configure-company-wide-settings-administrators-only) proporciona a los administradores control sobre si los usuarios pueden crear y editar cuentas y ubicaciones. Esta configuración se aplica cuando los usuarios [configuración de cuentas de importación y exportación de cloud](/help/components/locations/configure-import-accounts.md) y [configuración de ubicaciones de importación y exportación de cloud](/help/components/locations/configure-import-locations.md). <p>Los administradores también pueden limitar los tipos de cuentas (Google Cloud Platform, Azure RBAC, Amazon S3, etc.) que pueden crear y utilizar los usuarios.</p><p>Anteriormente, cualquier usuario podía crear, editar y utilizar cuentas y ubicaciones para cualquier tipo de cuenta.</p> | 12 de junio de 2024 | 30 de junio de 2024 |
| **Compartir cuentas y ubicaciones que se utilizan para exportar e importar** | Ahora, los usuarios pueden poner las cuentas y ubicaciones que creen a disposición de todos los usuarios de su organización. Los propietarios de cuentas y ubicaciones y los administradores del sistema son los únicos que pueden editar y eliminar cuentas y ubicaciones.<p>Anteriormente, las cuentas y ubicaciones solo las podía usar el usuario que las creaba.</p><p>Esta configuración está disponible cuando los usuarios [configuración de cuentas de importación y exportación de cloud](https://experienceleague.adobe.com/es/docs/analytics/components/locations/configure-import-accounts) y [configuración de ubicaciones de importación y exportación de cloud](https://experienceleague.adobe.com/es/docs/analytics/components/locations/configure-import-locations). </p> | 12 de junio de 2024 | 30 de junio de 2024 |
| **Activity Map utiliza menos llamadas al servidor para SDK web** | Actualmente, los eventos de vínculo de Activity Map se cuentan como eventos propios e incurren en un coste adicional. Esta mejora toma algunos eventos de vínculo y los empaqueta en la siguiente visita, de forma similar a como se gestionan los eventos en AppMeasurement. <p>(Vínculo a documentación actualizada a seguir)</p> | La versión beta abierta comienza el 19 de junio de 2024 | Por determinar |

{style="table-layout:auto"}

## Correcciones en Adobe Analytics

* Se han corregido los siguientes problemas de clasificaciones: AN-347682; AN-348396; AN-348625; AN-348668; AN-348926; AN-348936; AN-349040; AN-349191; AN-349195; AN-349443; AN-349697; AN-349758; AN-349862; AN-350051; AN-350054; AN-350208; AN-350497; AN-350525; AN-351067
* Se han corregido los siguientes problemas de Data Warehouse: AN-346862; AN-349409; AN-349926; AN-350629; AN-350996
* Se han corregido los siguientes problemas de fuentes de datos: AN-346727; AN-348282; AN-348334; AN-348725; AN-348726; AN-348823; AN-349081; AN-349207; AN-349307; AN-349539; AN-349710; AN-349729; AN-349742; AN-349878; AN-349943; AN-350527;
* Se han corregido los siguientes problemas relacionados con fuentes de datos: AN-350038
* Se han corregido los siguientes problemas de Analysis Workspace: AN-342953; AN-346346; AN-349590; AN-349717; AN-350057; AN-350697; AN-350904
* Se han corregido los siguientes problemas del Report Builder: AN-348903; AN-350691
* Se han solucionado los siguientes problemas de A4T: AN-347690; AN-350853

### Otras correcciones de Analytics

AN-346470; AN-346850; AN-347227; AN-348145; AN-348564; AN-349001; AN-349008; AN-349211; AN-349719; AN-350523;

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

* [Notas de la versión anteriores de 2024](/help/release-notes/2024.md)
* [Notas de la versión de Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=es)
* [Notas de la versión de Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=es)
* Las últimas actualizaciones de la versión para los [productos de Adobe Experience Cloud](https://business.adobe.com/es/products/adobe-experience-cloud-products.html)

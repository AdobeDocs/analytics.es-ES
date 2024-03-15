---
title: Notas de la versión de Adobe Analytics actual
description: Ver las notas de la versión actuales de Adobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 416725e01f469e3fafc1d52971535ab63e998f5f
workflow-type: tm+mt
source-wordcount: '1167'
ht-degree: 25%

---

# Notas de la versión actuales de Adobe Analytics (marzo de 2024)

**Última actualización**: jueves, 13 de marzo de 2024

Estas notas de la versión abarcan el periodo de lanzamiento del 12 de marzo de 2024 a abril de 2024. Las versiones de Adobe Analytics funcionan con un [modelo de entrega continua](releases.md) que permite un enfoque más escalable y gradual de la implementación de funcionalidades. Por lo tanto, estas notas de la versión se actualizan varias veces al mes. Compruébelas regularmente.

## Nuevas funciones o mejoras {#features}

| Función | Descripción | [Inicio del despliegue](releases.md) | [Disponibilidad general](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **actualización de AppMeasurement** | [Versión de AppMeasurement v2.26.0](/help/implement/appmeasurement-updates.md) está disponible. | | martes, 04 de marzo de 2024 |
| **Nueva columna disponible en la página de aterrizaje Proyectos** | El **[!UICONTROL Último uso]** ahora está disponible al ver la pestaña Proyectos en la [Página de aterrizaje de Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/analyze/landing.html?lang=es). <p>Esta información puede ayudarle a determinar si un proyecto es valioso para los usuarios de su organización, ya que muestra la fecha y la hora en que se abrió por última vez.</p> <p>Anteriormente, la variable **[!UICONTROL Último uso]** solo estaba disponible en el Administrador de métricas calculadas, el Administrador de segmentos y el Administrador de alertas.</p> |  | jueves, 13 de marzo de 2024 |
| **Compatibilidad de Analytics con indicadores de consentimiento requeridos por Google para DMA** | Debido a las nuevas regulaciones europeas de privacidad, Google requiere que los datos recopilados en Europa que se les enviaron indiquen si se otorgaron dos tipos particulares de consentimiento. **A partir del 6 de marzo**, Google ya no aceptará datos de evento que no indiquen que se haya concedido el consentimiento correspondiente. Adobe Analytics ha lanzado la compatibilidad para capturar estos datos mediante una nueva variable adConsent. Puede ver la nueva variable enumerada en la variable [IU de informes de privacidad](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/privacy-reporting.md). Si desea activar esto y ya tiene la privacidad habilitada para las variables de consentimiento anteriores, deberá volver a habilitar la privacidad. |  | jueves, 13 de marzo de 2024 |
| **Uso del Report Builder incluido en la columna &quot;Utilizado en&quot; del Administrador de métricas calculadas y del Administrador de segmentos** | Al ver el **Utilizado en** en el Administrador de métricas calculadas o en el Administrador de segmentos, los datos de uso ya están disponibles para el Report Builder.<p>Anteriormente, los datos de uso del Administrador de segmentos solo estaban disponibles para Alertas, Proyectos, Proyectos programados y Métricas calculadas; mientras que los datos de uso del Administrador de métricas calculadas solo estaban disponibles para Alertas, Proyectos y Proyectos programados.</p> |  | Finales de marzo o principios de abril |
| **Utilice las mismas cuentas de nube para las fuentes de datos, la Data Warehouse y los conjuntos de clasificaciones** | Las cuentas y ubicaciones de nube que cree ahora se pueden usar para exportar datos (con Fuentes de datos e Data Warehouse) e importar datos (con conjuntos de clasificaciones).<p> **Cambios al configurar cuentas:** Los usuarios pueden Configurar cuentas de importación y exportación de la nube y Configurar ubicaciones de importación y exportación de la nube que se puedan utilizar para cualquiera de los siguientes fines:<ul><li>Importación de datos con conjuntos de clasificaciones</li><li>Exportación de datos con fuentes de datos</li><li>Exportación de datos con Data Warehouse.</li></ul><p>**Cambios al administrar cuentas**: los usuarios pueden utilizar la página Ubicaciones (en Componentes > Ubicaciones) para ver y administrar todas las cuentas y ubicaciones que crean, independientemente del lugar donde se crearon. <p>Anteriormente, la página Ubicaciones solo se aplicaba a las cuentas creadas para importar datos con conjuntos de clasificaciones.</p> | | Abril de 2024 |
| **Los administradores pueden administrar todas las ubicaciones de su organización** | Una nueva opción de la página Ubicaciones permite a los administradores ver y administrar todas las ubicaciones de la organización. <p>Anteriormente, los administradores solo podían ver y administrar las ubicaciones que habían creado.</p> |  | Abril de 2024 |
| **El Activity Map de utiliza menos llamadas al servidor para el SDK web** | Actualmente, los eventos de vínculo de Activity Map se cuentan como eventos propios y conllevan un coste adicional. <p>Esta mejora toma algunos eventos de vínculo y los empaqueta en la siguiente visita, de forma similar a como el AppMeasurement gestiona los eventos.</p> |  | jueves, 03 de abril de 2024 |
| **Aumento de los umbrales de poco tráfico predeterminados** | Entrada **mediados de abril de 2024**, el Adobe empezará a aumentar los umbrales de poco tráfico predeterminados del grupo de informes de la siguiente manera: ![umbrales de poco tráfico](assets/thresholds.png) Esto solo afecta a las variables que actualmente están configuradas por debajo de los nuevos umbrales. Estos cambios se realizarán gradualmente y esperamos que el trabajo se complete antes de que finalice el **finales de mayo**. A medida que se desplieguen estos aumentos, es posible que observe cambios en las variables de alta cardinalidad:<ul><li>Pueden estar disponibles más valores de dimensión para la creación de informes.</li><li>Los segmentos y las métricas calculadas pueden incluir más datos.</li><li>Los grupos de informes virtuales basados en segmentos pueden incluir más datos.</li><li>Las exportaciones de clasificación pueden incluir más datos.</li></ul> | | Mediados de abril de 2024 |

{style="table-layout:auto"}

## Correcciones en Adobe Analytics

* Se han corregido los siguientes problemas de clasificaciones: AN-335632; AN-337559; AN-340164; AN-340370; AN-341089; AN-341211; AN-341284; AN-341469; AN-341481; AN-341760; AN-341778; AN-342144; AN-342258; AN-342338, AN-342400
* Se han corregido los siguientes problemas del Generador de reglas de clasificación: AN-340921; AN-341269; AN-341292; AN-341467; AN-341666; AN-342145; AN-342329
* Se ha corregido el siguiente problema de alertas inteligentes: AN-340736
* Se ha corregido el siguiente problema de segmentación: AN-336242
* Se han corregido los siguientes problemas de Data Warehouse: AN-335354; AN-339446; AN-339774; AN-340221; AN-340599; AN-341277; AN-342009; AN-342088; AN-342592
* Se han corregido los siguientes problemas de fuentes de datos: AN-335508; AN-340887; AN-341050; AN-341208; AN-341403; AN-341479; AN-341524; AN-341661; AN-342000; AN-342125; AN-342256; AN-342301; AN-342410; AN-342502; AN-342525
* Se ha corregido el siguiente problema con el Report Builder: AN-340540
* Se han corregido los siguientes problemas de Analysis Workspace: AN-295889; AN-330981; AN-338818; AN-339730; AN-341114; AN-341520;

### Otras correcciones de Analytics

AN-312198; AN-338009; AN-339549; AN-333970; AN-334790; AN-336461; AN-336572; AN-339549; AN-341119; AN-341246; AN-341268; AN-341272; AN-341475; AN-341547; AN-341558; AN-341680; AN-342017;

## Avisos importantes para los administradores de Adobe Analytics {#admin}

| Aviso | Fecha de incorporación o actualización | Descripción |
| ----------- | ---------- | ---------- |
| **Adiciones de miembros de objeto de API de Adobe** | 17 de enero de 2024 | El Adobe puede agregar miembros de solicitud y respuesta opcionales (pares de nombre/valor) a objetos de API existentes en cualquier momento y sin previo aviso ni cambios en el control de versiones. El Adobe recomienda que consulte la documentación de la API de cualquier herramienta de terceros que integre con nuestras API para que dichas adiciones se ignoren en el procesamiento, si no se comprenden. Si se implementan correctamente, estas adiciones son cambios interactivos para la implementación. Adobe no quitará los parámetros ni añadirá los parámetros necesarios sin antes proporcionar una notificación estándar mediante las notas de la versión. |
| **`getPageLoadTime`complemento obsoleto** | 10 de enero de 2024 | Este complemento ya no es compatible.  Su código utiliza el método performance.timing, que (según MDN) ha quedado [obsoleto](https://developer.mozilla.org/en-US/docs/Web/API/PerformanceTiming).  Se ha iniciado el trabajo en un complemento actualizado. |

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

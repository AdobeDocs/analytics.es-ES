---
title: Notas de la versión de Adobe Analytics actual
description: Ver las notas de la versión actuales de Adobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 93099d36a65ca2bf16fbd6342f01bfecdc8c798e
workflow-type: ht
source-wordcount: '1077'
ht-degree: 100%

---

# Notas de la versión actuales de Adobe Analytics (enero de 2024)

**Última actualización**: 10 de enero de 2024

Estas notas de la versión abarcan el periodo de lanzamiento de enero de 2024 al 13 de febrero de 2024.  Las versiones de Adobe Analytics funcionan con un [modelo de entrega continua](releases.md) que permite un enfoque más escalable y gradual de la implementación de funcionalidades. Por lo tanto, estas notas de la versión se actualizan varias veces al mes. Compruébelas regularmente.

## Nuevas funciones o mejoras {#features}

| Función | Descripción | [Inicio del despliegue](releases.md) | [Disponibilidad general](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Actualizaciones de Data Warehouse** | Ya están disponibles las siguientes mejoras de Data Warehouse:<ul><li>Al crear una solicitud de Data Warehouse, los usuarios ahora pueden poner las solicitudes a disposición de todos los usuarios de la organización habilitando la nueva opción denominada [!UICONTROL **Poner a disposición de los usuarios de su organización**].<p>Para obtener más información, consulte [Configuración general de solicitudes de Data Warehouse](/help/export/data-warehouse/create-request/dw-general-settings.md).</p></li><li>Al crear o administrar destinos de informes de Data Warehouse, los administradores del sistema ahora pueden mostrar cuentas y ubicaciones creadas por usuarios de la organización habilitando la opción llamada [!UICONTROL **Mostrar todos los destinos**].<p>Para obtener más información, consulte [Configuración del destino de un informe para una solicitud de Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md).</p></li> | N/A | 10 de enero de 2024 |
| **Actualizaciones de la visualización Resumen de métricas clave** | Al utilizar la visualización Resumen de métricas clave, el intervalo de fechas de comparación ahora se puede actualizar automáticamente, en función de si la opción Intervalo de fechas de comparación que elija es relativa al intervalo de fechas principal o fija. [Más información](/help/analyze/analysis-workspace/visualizations/key-metric.md). | N/A | 17 de enero de 2024 |

{style="table-layout:auto"}

## Correcciones en Adobe Analytics

* Se han solucionado los siguientes problemas de clasificación: AN-314821; AN-326839; AN-332079; AN-332704; AN-332812; AN-332902; AN-332975; AN-333300; AN-333023; AN-333033; AN-333174; AN-333910; AN-334097; AN-334208; AN-334373; AN-334439; AN-334698; AN-334838; AN-334848; AN-334987; AN-335046; AN-335082; AN-335202; AN-335203; AN-335254; AN-335322; AN-335552; AN-335591; AN-335603; AN-335610; AN-335617; AN-335699; AN-335891; AN-335901; AN-336063; AN-336072; AN-336193; AN-336479; AN-336684; AN-336801; AN-337370; AN-337398
* Se han solucionado los siguientes problemas del Generador de reglas de clasificación: AN-332390; AN-332573; AN-332718; AN-332927; AN-333248; AN-333953; AN-334647; AN-334736; AN-334910; AN-335642; AN-335683; AN-335811; AN-336033; AN-336569; AN-336852; AN-336875; AN-336902; AN-337190;
* Se han solucionado los siguientes problemas de A4T: AN-334564; AN-336178;
* Se han solucionado los siguientes problemas de Uso de llamadas al servidor: AN-332568; AN-333105; AN-333167; AN-333983; AN-334209; AN-334278
* Se han solucionado los siguientes problemas de Data Warehouse: AN-333010; AN-333076; AN-330227; AN-331580; AN-333350; AN-334291; AN-334283; AN-334287; AN-334301; AN-334385; AN-334453; AN-334977; AN-335079; AN-335171; AN-335245; AN-335426; AN-335680; AN-335818; AN-336087; AN-337308;
* Se han solucionado los siguientes problemas de Fuentes de datos: AN-332241; AN-332366; AN-332617; AN-332654; AN-332702; AN-332723; AN-333014; AN-333166; AN-334037; AN-334125; AN-334211; AN-334216; AN-334235; AN-334976; AN-335158; AN-335368; AN-335408; AN-335468; AN-335471; AN-335528; AN-335596; AN-335662; AN-335733; AN-335883; AN-335894; AN-335968; AN-336098; AN-336192; AN-336243; AN-336659; AN-336977; AN-337117; AN-337219; AN-337262; AN-337393; AN-337462; AN-337854
* Se han solucionado los siguientes problemas del Report Builder: AN-335246; AN-336311;
* Se han solucionado los siguientes problemas de Analysis Workspace: AN-323760; AN-324191; AN-324913; AN-330126; AN-332808; AN-333168; AN-333382; AN-334839; AN-336040; AN-337043;

### Otras correcciones

AN-323975; AN-325383; AN-325809; AN-326787; AN-331611; AN-331818; AN-332124; AN-332272; AN-332911; AN-333070; AN-333302; AN-333377; AN-333904; AN-333928; AN-333968; AN-334056; AN-334099; AN-334191; AN-334207; AN-334776; AN-335206; AN-335294; AN-335320; AN-335394; AN-335443; AN-335967; AN-336099; AN-337452; AN-337463

## Avisos importantes para los administradores de Adobe Analytics {#admin}

| Aviso | Fecha de incorporación o actualización | Descripción |
| ----------- | ---------- | ---------- |
| Adiciones de miembros de objeto de API de Adobe | 17 de enero de 2024 | Adobe puede añadir miembros de solicitud y respuesta opcionales (pares de nombre/valor) a objetos de API existentes sin previo aviso ni cambios en las versiones. Estas adiciones deben ser cambios importantes para la implementación. Adobe recomienda que se consulte la documentación de la API de cualquier herramienta de terceros que se integre con nuestras API para que dichas adiciones se ignoren en el procesamiento si no se comprenden. Adobe no quitará los parámetros ni añadirá los parámetros necesarios sin antes proporcionar una notificación estándar mediante las notas de la versión. |
| `getPageLoadTime` complemento obsoleto | 10 de enero de 2024 | Este complemento ya no es compatible.  Su código utiliza el método performance.timing, que (según MDN) ha quedado [obsoleto](https://developer.mozilla.org/en-US/docs/Web/API/PerformanceTiming).  Se ha iniciado el trabajo en un complemento actualizado. |

{style="table-layout:auto"}

## Avisos de final de la vida útil {#eol}

| Final de la vida útil de producto o función | Fecha de incorporación o actualización | Descripción |
| --- | --- | --- |
| **EOL para [!DNL Reports & Analytics]** | 10 de enero de 2024 | A partir del **17 de enero de 2024**, Adobe tiene la intención de descatalogar [!DNL Reports & Analytics] y los informes y funciones que lo acompañaban. Los informes, las visualizaciones y la tecnología subyacente que alimentan [!DNL Reports & Analytics] ya no cumplen los estándares tecnológicos de Adobe. La mayoría de las funciones de [!DNL Reports & Analytics] están disponibles en [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=es). Desde el lanzamiento de Analysis Workspace en 2015, las funcionalidades y capacidades de [!DNL Reports & Analytics] se han trasladado a Analysis Workspace y se ha alcanzado un umbral de paridad de flujo de trabajo. [Este aviso](https://spark.adobe.com/page/6WnF8JK6IRDhf/) explica el proceso de finalización de la vida útil.<p>El 17 de enero de 2024, finalizaremos muchas de las funciones de Reports &amp; Analytics asociadas, incluidas, entre otras, las siguientes: Informes programados, Extractos de datos e Informes DL.  A partir del 17 de enero de 2024, ya no se enviarán los informes programados.  Además, ya no podrá programar informes futuros después del 17 de enero de 2024. |
| **Funcionalidad del final de vida útil de las [!UICONTROL Listas de publicación]** | 10 de enero de 2024 | Como parte del final de la vida útil de Reports &amp; Analytics, [!UICONTROL Listas de publicación] llegó al final de su vida útil el **17 de enero de 2024**.  No podrá crear [!UICONTROL Listas de publicación] nuevas ni acceder a las existentes para enviar o programar proyectos de [!UICONTROL Analysis Workspace]. |
| **Fin de la vida útil para Data Workbench** | 2 de enero de 2024 | Adobe tiene planeado el fin de la vida útil de Data Workbench con fecha de aplicación el **31 de diciembre de 2023**.  Consulte [Anuncio del fin de la vida útil de Data Workbench](https://express.adobe.com/page/GSu6oKOD88GAj/) para obtener más información. Póngase en contacto con el Administrador de cuentas de Adobe de su organización si tiene alguna pregunta. |
| **Migración a las credenciales de servidor a servidor de Adobe I/O OAuth** | 11 de mayo de 2023 | Los clientes de la API de Adobe Analytics y Livestream que utilizan las credenciales de JWT de Adobe I/O deben migrar a las credenciales de servidor a servidor de Adobe I/O OAuth de forma predeterminada el **1 de enero de 2025**. Adobe I/O no permitirá que se creen nuevas credenciales de JWT a partir del 1 de mayo de 2024. Los clientes que utilizan JWT deben crear una nueva credencial de servidor a servidor OAuth o migrar su credencial JWT existente a una credencial de servidor a servidor OAuth. Los clientes también deben actualizar sus aplicaciones cliente para utilizar las nuevas credenciales de servidor a servidor de OAuth. <ul><li>[Migración de credenciales de cuenta de servicio (JWT)](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[Guía de implementación para aplicaciones nuevas y antiguas con OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[Uso de las nuevas credenciales de servidor a servidor de OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[Preguntas frecuentes](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |

{style="table-layout:auto"}

## AppMeasurement

Para obtener las últimas actualizaciones de las versiones de AppMeasurement (2.25.0), consulte las [notas de la versión de AppMeasurement para JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=es).


## Recursos relacionados

* [Notas de la versión anteriores de 2023](/help/release-notes/2023.md)
* [Notas de la versión de Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=es)
* [Notas de la versión de Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=es)
* Las últimas actualizaciones de la versión para los [productos de Adobe Experience Cloud](https://business.adobe.com/es/products/adobe-experience-cloud-products.html)

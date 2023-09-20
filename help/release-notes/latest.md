---
title: Notas de la versión de Adobe Analytics actual
description: Ver las notas de la versión actuales de Adobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 2998ab3ecb83e14be38333a2836f863667babfee
workflow-type: tm+mt
source-wordcount: '899'
ht-degree: 88%

---

# Notas de la versión actuales de Adobe Analytics (septiembre de 2023)

**Última actualización**: 13 de septiembre de 2023

Las notas de la versión de septiembre abarcan el período de lanzamiento del 13 de septiembre de 2023 al 3 de octubre de 2023. Las versiones de Adobe Analytics funcionan con un [modelo de entrega continua](releases.md) que permite un enfoque más escalable y gradual de la implementación de funcionalidades. Por lo tanto, estas notas de la versión se actualizan varias veces al mes. Compruébelas regularmente.

## Nuevas funciones o mejoras {#features}

| Función | Descripción | [Inicio del despliegue](releases.md) | [Disponibilidad general](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Clasificaciones en la API 2.0** | Proporciona métodos de la API de Adobe Analytics 2.0 para guardar, eliminar, recuperar, importar y exportar datos del conjunto de clasificación. [Más información](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/classifications/) | N/A | 13 de septiembre de 2023 |
| **Compatibilidad con nuevo campo de `correlationID` para clasificaciones de A4T** | El campo de `_experience.decisioning.propositions.scopeDetails.correlationID` ahora está disponible en el esquema del conector de origen de Adobe Analytics. Se va a agregar este ID para facilitar la unión de los datos de clasificación para las actividades y los eventos de experiencia de Adobe Target. | N/A | 13 de septiembre de 2023 |
| **Mejoras del Data Warehouse** | Al crear una solicitud de Data Warehouse, ahora puede configurar una cuenta de la nube para usarla como destino del informe. Los siguientes tipos de cuenta de nube están disponibles para enviar datos:<ul><li>Amazon S3</li><li>Google Cloud Platform</li><li>Azure SAS</li><li>Azure RBAC</li><li>Correo electrónico (esta opción estaba disponible anteriormente)</li></ul>FTP, SFTP, Azure Blob y S3 siguen estando disponibles como destinos de informe, pero ya no se recomiendan.<p>También se ha mejorado la experiencia del usuario al crear y administrar solicitudes de Data Warehouse. Para obtener más información, consulte [Creación de una solicitud de Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md) y [Administrar solicitudes de Data Warehouse](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/data-warehouse-requests-manage.html?lang=es). | 13 de septiembre de 2023 | 4 de octubre de 2023 |
| **Nuevas columnas disponibles al administrar componentes** | Las siguientes columnas nuevas ya están disponibles al administrar componentes:<ul><li>Utilizado en<p>Esta columna está disponible en la variable [Administrador de métricas calculadas](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-manager.md) y el [Administrador de segmentos](/help/components/segmentation/segmentation-workflow/seg-manage.md).</p></li><li>Último uso<p>Esta columna está disponible en la variable [Administrador de métricas calculadas](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-manager.md), el [Administrador de segmentos](/help/components/segmentation/segmentation-workflow/seg-manage.md), y el [Administrador de alertas](/help/components/c-alerts/alert-manager.md).</p></li></ul><p>Esta información puede ayudarle a determinar si un componente es valioso para los usuarios de su organización, dónde se utiliza y si debe eliminarse o modificarse. Puede utilizar el diccionario de datos junto con esta información para ayudarle a realizar un seguimiento y comprender mejor cómo se utilizan los componentes en su organización.</p> | 20 de septiembre de 2023 | 4 de octubre de 2023 |

{style="table-layout:auto"}

## Correcciones en Adobe Analytics

* Se ha corregido un problema que impedía que los datos de clasificación se mostraran en Workspace. (AN-326827)

## Otras correcciones

AN-314882; AN-315591; AN-318165; AN-318559; AN-319031; AN-319244; AN-321657; AN-321759; AN-323099; AN-323596; AN-323640; AN-324442; AN-324921; AN-324953; AN-324977; AN-324979; AN-325124; AN-325395; AN-325433; AN-325535; AN-325693; AN-325720; AN-325835; AN-325880; AN-325957; AN-325984; AN-326054; AN-326065; AN-326136; AN-326155; AN-326162; AN-326235; AN-326317; AN-326344; AN-326357; AN-326359; AN-326433; AN-326438; AN-326440; AN-326461; AN-326464; AN-326523; AN-326553; AN-326606; AN-326635; AN-326642; AN-326652; AN-326678; AN-326769; AN-326777; AN-326830; AN-326938; AN-326949; AN-327081; AN-327082; AN-327085; AN-327103; AN-327198; AN-327225; AN-327275; AN-327358; AN-327423; AN-327561; AN-327755; AN-327896; AN-327922; AN-328128; AN-328300; AN-328428; AN-328518; AN-328554

## Avisos importantes para los administradores de Adobe Analytics {#admin}

| Aviso | Fecha de incorporación o actualizada | Descripción |
| ----------- | ---------- | ---------- |
| N/A | N/A | N/A |

{style="table-layout:auto"}

## Avisos de final de la vida útil {#eol}

| Final de la vida útil de producto o función | Fecha de incorporación o actualización | Descripción |
| --- | --- | --- |
| **Migración a las credenciales de servidor a servidor de Adobe I/O OAuth** | 11 de mayo de 2023 | Los clientes de la API de Adobe Analytics y Livestream que utilizan las credenciales de JWT de Adobe I/O deben migrar a las credenciales de servidor a servidor de Adobe I/O OAuth de forma predeterminada el **1 de enero de 2025**. Adobe I/O no permitirá que se creen nuevas credenciales de JWT a partir del 1 de mayo de 2024. Los clientes que utilizan JWT deben crear una nueva credencial de servidor a servidor OAuth o migrar su credencial JWT existente a una credencial de servidor a servidor OAuth. Los clientes también deben actualizar sus aplicaciones cliente para utilizar las nuevas credenciales de servidor a servidor de OAuth. <ul><li>[Migración de credenciales de cuenta de servicio (JWT)](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[Guía de implementación para aplicaciones nuevas y antiguas con OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[Uso de las nuevas credenciales de servidor a servidor de OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[Preguntas frecuentes](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |
| **EOL para [!DNL Reports & Analytics]** | 7 de marzo de 2023 | A partir del **31 de diciembre de 2023**, Adobe tiene la intención de descatalogar [!DNL Reports & Analytics] y sus informes y funciones correspondientes. Los informes, las visualizaciones y la tecnología subyacente que alimentan [!DNL Reports & Analytics] ya no cumplen los estándares tecnológicos de Adobe. La mayoría de las funciones de [!DNL Reports & Analytics] están disponibles en [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=es). Desde el lanzamiento de Analysis Workspace en 2015, las funcionalidades y capacidades de [!DNL Reports & Analytics] se han trasladado a Analysis Workspace y se ha alcanzado un umbral de paridad de flujo de trabajo. [Este aviso](https://spark.adobe.com/page/6WnF8JK6IRDhf/) explica el proceso de finalización de la vida útil.<p>El 31 de diciembre de 2023, finalizaremos muchas de las funciones de Reports &amp; Analytics asociadas, incluidas, entre otras, las siguientes: Informes programados, Extractos de datos e Informes DL. A partir del 31 de diciembre de 2023, ya no se enviarán los informes programados. En **abril de 2023**, cualquier informe que estuviera programado para caducar después del 31 de diciembre de 2023 se actualizará automáticamente y se revertirá para que caduque el 31 de diciembre de 2023. Además, ya no puede programar informes futuros después del 31 de diciembre de 2023. |
| **Funcionalidad del final de vida útil de las [!UICONTROL Listas de publicación]** | 29 de septiembre de 2022 | Como parte del final de la vida útil de Reports &amp; Analytics, las [!UICONTROL Listas de publicación] están programadas para llegar al final de su vida útil en **diciembre de 2023**. No podrá crear [!UICONTROL Listas de publicación] nuevas ni acceder a las existentes para enviar o programar proyectos de [!UICONTROL Analysis Workspace]. |
| **Fin de la vida útil para Data Workbench** | 14 de septiembre de 2022 | Adobe tiene planeado el fin de la vida útil de Data Workbench con fecha de aplicación el **31 de diciembre de 2023**. Consulte [Anuncio del fin de la vida útil de Data Workbench](https://experienceleague.adobe.com/docs/data-workbench/using/eol.html?lang=es) para obtener más información. Póngase en contacto con el Administrador de cuentas de Adobe de su organización si tiene alguna pregunta. |

{style="table-layout:auto"}

## AppMeasurement

Para obtener las últimas actualizaciones de las versiones de AppMeasurement (2.24.0), consulte las [notas de la versión de AppMeasurement para JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=es).


## Recursos relacionados

* [Notas de la versión anteriores de 2022](/help/release-notes/2022.md)
* [Notas de la versión de Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=es)
* [Notas de la versión de Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=es)
* Las últimas actualizaciones de la versión para los [productos de Adobe Experience Cloud](https://business.adobe.com/es/products/adobe-experience-cloud-products.html)

---
title: Notas de la versión de Adobe Analytics actual
description: Ver las notas de la versión actuales de Adobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 1bd654eef37ac242cf4076e133e482f6a5990cc9
workflow-type: tm+mt
source-wordcount: '800'
ht-degree: 68%

---

# Notas de la versión actuales de Adobe Analytics (septiembre de 2023)

**Última actualización**: 13 de septiembre de 2023

Las notas de la versión de septiembre abarcan el período de lanzamiento del 13 de septiembre de 2023 al 3 de octubre de 2023. Las versiones de Adobe Analytics funcionan con un [modelo de entrega continua](releases.md) que permite un enfoque más escalable y gradual de la implementación de funcionalidades. Por lo tanto, estas notas de la versión se actualizan varias veces al mes. Compruébelas regularmente.

## Nuevas funciones o mejoras {#features}

| Función | Descripción | [Inicio del despliegue](releases.md) | [Disponibilidad general](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Clasificación en la API 2.0** | Proporciona métodos de la API de Adobe Analytics 2.0 para guardar, eliminar, recuperar, importar y exportar datos del conjunto de clasificación. [Más información](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/classifications/) | N/A | 13 de septiembre de 2023 |
| **Compatibilidad con nuevos `correlationID` Campo para clasificaciones de A4T** | El `_experience.decisioning.propositions.scopeDetails.correlationID` El campo ahora está disponible en el esquema del conector de origen de Adobe Analytics. Estamos agregando este ID para facilitar la combinación de los datos de clasificación para las actividades y los eventos de experiencia de Adobe Target. | N/A | 13 de septiembre de 2023 |
| **Mejoras del Data Warehouse** | Al crear una solicitud de Data Warehouse, ahora puede configurar una cuenta de la nube para usarla como destino del informe. Los siguientes tipos de cuenta de nube están disponibles para enviar datos:<ul><li>Amazon S3</li><li>Google Cloud Platform</li><li>Azure SAS</li><li>Azure RBAC</li><li>Correo electrónico (esta opción estaba disponible anteriormente)</li></ul>FTP, SFTP, Azure Blob y S3 siguen estando disponibles como destinos de informe, pero ya no se recomiendan.<p>También se ha mejorado la experiencia del usuario al crear y administrar solicitudes de Data Warehouse. Para obtener más información, consulte [Creación de una solicitud de Data Warehouse](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/create-request/t-dw-create-request.html) y [Administrar solicitudes de Data Warehouse](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/data-warehouse-requests-manage.html?lang=es). | 13 de septiembre de 2023 | 4 de octubre de 2023 |

{style="table-layout:auto"}

## Correcciones en Adobe Analytics

* Se ha corregido un problema que impedía que los datos de clasificación se mostraran en Workspace. (AN-326827)

## Otras correcciones

AN-314882; AN-315591; AN-318165; AN-318559; AN-319031; AN-319244; AN-321657; AN-321759; AN-323099 AN-323596 AN-AN-324442 AN-AN; AN-AN-AN; AN-AN; AN-AN; AN-AN;-AN; Y-AN-AN; Y-AN-324921; AN-AN; Y-AN-AN; Y-AN-AN; Y-AN-AN-AN; Y-AN-AN-AN; Y-AN-AN; Y-323640; AN-; AN-; AN-324953; AN-324977; AN-324979; AN-325124; AN-AN; AN-AN-AN; AN-AN-AN; AN-AN-AN; AN-AN-AN; AN-AN-AN; AN-AN-AN; AN-AN; AN-AN; AN-AN; AN-AN; AN-AN; AN-AN; AN-AN; AN-AN; AN-AN; AN-AN; AN-AN; AN-AN; AN-AN; AN-325395;-AN;-AN;-325433;-AN;-AN-325535 325693 325720 325835 325880 325957 325984 326054 326065 326136 326155 326162 326235 326317 326344 326357 326359 326433 326438 326440 326461 326464 326523 326553 326606 326635 326642 326652 326678 326769 326777 326830 326938 326949 327081 327082 327085 327103 327198 327225 327275 327358 327423 327561 327755 327896 327922 328128 328300 328428 328518 328554; AN-

## Avisos importantes para los administradores de Adobe Analytics {#admin}

| Aviso | Fecha de incorporación o actualizada | Descripción |
| ----------- | ---------- | ---------- |
| N/A | N/A | N/A |

{style="table-layout:auto"}

## Avisos de final de la vida útil {#eol}

| Final de la vida útil de producto o función | Fecha de incorporación o actualización | Descripción |
| --- | --- | --- |
| **Migración a las credenciales de servidor a servidor de Adobe I/O OAuth** | 11 de mayo de 2023 | Los clientes de la API de Adobe Analytics y Livestream que utilizan las credenciales de JWT de Adobe I/O deben migrar a las credenciales de servidor a servidor de Adobe I/O OAuth de forma predeterminada el **1 de enero de 2025**. Adobe I/O no permitirá que se creen nuevas credenciales de JWT a partir del 1 de mayo de 2024. Los clientes que utilizan JWT deben crear una nueva credencial de servidor a servidor OAuth o migrar su credencial JWT existente a una credencial de servidor a servidor OAuth. Los clientes también deben actualizar sus aplicaciones cliente para utilizar las nuevas credenciales de servidor a servidor de OAuth. <ul><li>[Migración de credenciales de cuenta de servicio (JWT)](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[Guía de implementación para aplicaciones nuevas y antiguas con OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[Uso de las nuevas credenciales de servidor a servidor de OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[Preguntas frecuentes](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |
| **EOL para [!DNL Reports & Analytics]** | 7 de marzo de 2023 | A partir del **31 de diciembre de 2023**, Adobe tiene la intención de descatalogar [!DNL Reports & Analytics] y sus informes y funciones correspondientes. Los informes, las visualizaciones y la tecnología subyacente que alimentan [!DNL Reports & Analytics] ya no cumplen los estándares tecnológicos de Adobe. La mayoría de las funciones de [!DNL Reports & Analytics] están disponibles en [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=es). Desde el lanzamiento de Analysis Workspace en 2015, las funcionalidades y capacidades de [!DNL Reports & Analytics] se han trasladado a Analysis Workspace y se ha alcanzado un umbral de paridad de flujo de trabajo. [Este aviso](https://spark.adobe.com/page/6WnF8JK6IRDhf/) explica el proceso de finalización de la vida útil.<p>El 31 de diciembre de 2023, finalizaremos muchas de las funciones de Reports &amp; Analytics asociadas, incluidas, entre otras, las siguientes: Informes programados, Extractos de datos e Informes DL. A partir del 31 de diciembre de 2023, ya no se enviarán los informes programados. Entrada **Abril de 2023**, todos los informes que estuvieran programados para caducar más allá del 31 de diciembre de 2023 se actualizaron automáticamente y se volvieron a caducar el 31 de diciembre de 2023. Además, ya no puede programar informes futuros después del 31 de diciembre de 2023. |
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

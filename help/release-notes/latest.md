---
title: Notas de la versión de Adobe Analytics actual
description: Ver las notas de la versión actuales de Adobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 698b8f6cb9529f9742c2e3d9f1556b7913ebf0bb
workflow-type: tm+mt
source-wordcount: '652'
ht-degree: 93%

---

# Notas de la versión actual de Adobe Analytics (julio de 2025)

**Última actualización**: jueves, 30 de julio de 2025

Estas notas de la versión cubren el período comprendido entre el 7 de julio y el 15 de agosto de 2025. Las versiones de Adobe Analytics funcionan con un [modelo de entrega continua](releases.md) que permite un enfoque más escalable y gradual de la implementación de funcionalidades. Por lo tanto, estas notas de la versión se actualizan varias veces al mes. Compruébelas regularmente.

## Nuevas funciones o mejoras {#features}

| Función | Descripción | [Inicio del despliegue](releases.md) | [Disponibilidad general](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Campos TNT de transmisión en directo con algoritmos** | La transmisión en directo se está actualizando para garantizar que la tecnología siga siendo moderna y estable. Como parte de esa actualización, si su campo TNT tiene un algoritmo, empezaremos a incorporar el campo TNT en la salida de transmisión en directo. Sin embargo, esto incluye solo los elementos anteriormente admitidos: `campaignId`, `recipeId`, `trafficType`, `actionId` y `actionName`. El esquema TNT general de transmisión en directo permanece sin cambios. |   | 7 de julio de 2025 |
| **Navegación actualizada a la interfaz de usuario de Atributos del cliente** | Ahora se puede acceder directamente a la interfaz de usuario de Atributos del cliente desde el selector de aplicaciones en Adobe Experience Cloud. Seleccione **[!UICONTROL Atributos del cliente]** en el menú desplegable (en lugar de ir a [!UICONTROL Personas] > [!UICONTROL Atributos del cliente]) y actualice sus marcadores.  La actualización incluye algunas mejoras en la IU de. | 1 de julio de 2025 | viernes, 31 de julio de 2025 |

## Correcciones en Adobe Analytics

**Activity Map**: AN-360987
**Analysis Workspace**: AN-378094; AN-380979; AN-382908; AN-387652;
**Clasificaciones**: AN-382412; AN-383157; AN-384616; AN-384803; AN-385933; AN-387320; AN-387351; AN-387832; AN-387833; AN-387839; AN-387915;
**Recopilación de datos**: AN-387661
**Fuentes de datos**: AN-375172; AN-384369; AN-387859; AN-387952; AN-388155;
**Plataforma**: AN-382813; AN-386627; AN-386815
**Privacidad**: AN-384390
**Report Builder**: AN-388035
**Creación de informes**: AN-380441
**Informes programados**: AN-378280; AN-378331
**Comparación de segmentos**: AN-368766


## Avisos de final de la vida útil {#eol}

| Final de la vida útil de producto o función | Fecha de incorporación o actualización | Descripción |
| --- | --- | --- |
| **Report Builder heredado** | 18 de junio de 2025 | El complemento heredado de Report Builder se eliminará en junio de 2026. Todos los usuarios deberían empezar a actualizar sus libros heredados al [nuevo Report Builder](https://experienceleague.adobe.com/es/docs/analytics/analyze/report-builder/rb-overview). El nuevo Report Builder está disponible para los clientes de Adobe Analytics y Customer Journey Analytics. Tiene [casi paridad de características](https://experienceleague.adobe.com/es/docs/analytics/analyze/report-builder/convert-workbooks#unsupported), además de muchas nuevas características convenientes y mejoras en la interfaz de usuario. Para facilitar el proceso de actualización, el nuevo Report Builder incluye una sencilla función de conversión de libros. El nuevo Report Builder solo está disponible como complemento en Microsoft Store. Muchas organizaciones requieren un proceso de aprobación interno para poder poner el complemento a disposición de los usuarios. Deje tiempo para este proceso y empiece a trabajar con su organización ahora para asegurarse de que dispone de tiempo suficiente para actualizar los libros antes de la fecha límite. |
| **Acceso a través de dominios heredados o a través de SSO heredado** | 10 de abril de 2025 | Adobe tiene previsto actualizar el modo en que los usuarios acceden a Adobe Analytics para mejorar la seguridad y optimizar el inicio de sesión. Como parte de este esfuerzo, el acceso a través de dominios heredados o a través del SSO heredado, incluido `my.omniture.com`, se suspenderá permanentemente el **2 de enero de 2026**. Después de esta fecha, las credenciales de inicio de sesión heredadas y el SSO heredado dejarán de funcionar. Se solicitará a todos los usuarios que inicien sesión a través de `experience.adobe.com` mediante sus ID de Adobe Experience. Si necesita ayuda con relación a su ID de Experience Cloud, póngase en contacto con el administrador de Adobe Analytics de su organización o con el [Servicio de atención al cliente de Adobe](https://helpx.adobe.com/contact.html?lang=es). |
| **API de Adobe Analytics (versión 1.4)** | 17 de julio de 2024 | El **12 de agosto de 2026**, los siguientes servicios de la API heredada de Analytics llegarán al final de su vida útil y se cerrarán, y las integraciones actuales creadas con estos servicios dejarán de funcionar:<ul><li>API de Adobe Analytics (versión 1.4)</li><li>Autenticación WSSE de Adobe Analytics</li></ul><p>Las integraciones que usan la API de Adobe Analytics (versión 1.4) deben migrarse a la [API de Adobe Analytics 2.0](https://developer.adobe.com/analytics-apis/docs/2.0/), mientras que las integraciones de WSSE deben migrarse a un protocolo de autenticación basado en OAuth en [Adobe Developer Console](https://developer.adobe.com/console).</p><p>Consulte las [preguntas frecuentes sobre el final de la vida útil de la API de Adobe Analytics 1.4](/help/admin/c-admin-api/c-admin-14-api-eol.md) para obtener respuestas a dudas comunes y más indicaciones.</p> |


## AppMeasurement

Para obtener las últimas actualizaciones de las versiones de AppMeasurement, consulte las [notas de la versión de AppMeasurement](https://github.com/adobe/appmeasurement/releases).


## Recursos relacionados

* [Notas de la versión anteriores de 2025](/help/release-notes/2025.md)
* [Notas de la versión de Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=es)
* [Notas de la versión de la colección de medios de streaming](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=es)
* Las últimas actualizaciones de la versión para los [productos de Adobe Experience Cloud](https://business.adobe.com/products/adobe-experience-cloud-products.html?lang=es)

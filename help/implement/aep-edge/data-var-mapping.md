---
title: Asignación de variables de objetos de datos a Adobe Analytics
description: Vea qué campos de objeto de datos Experience Platform Edge asigna automáticamente a las variables de Analytics.
feature: Implementation Basics
role: Admin, Developer
exl-id: 45b2fbbc-73ca-40b3-9484-b406ae99fdad
source-git-commit: 59d9dd8055a13046d05ac4c3b5261a6c5a919b5c
workflow-type: tm+mt
source-wordcount: '541'
ht-degree: 2%

---

# Asignación de variables de objetos de datos a Adobe Analytics

En la tabla siguiente se muestran las variables de objetos de datos que Adobe Experience Platform Edge Network asigna automáticamente a Adobe Analytics. Si utiliza estas rutas de campo de objeto de datos, no es necesaria ninguna configuración adicional para enviar datos a Adobe Analytics.

Se recomienda utilizar estos campos si tiene intención de utilizar Customer Journey Analytics en el futuro. Este método de implementación permite a su organización enviar datos a Adobe mediante Web SDK sin ajustarse a un esquema XDM. Cuando su organización esté lista para enviar datos a Adobe Experience Platform, puede usar [Asignación de secuencia de datos](https://experienceleague.adobe.com/es/docs/experience-platform/datastreams/data-prep#mapping) para apuntar los campos de objeto de datos a sus respectivos campos XDM.

## Prioridades de valor

La mayoría de los campos de objeto de datos de esta tabla coinciden con un [campo XDM asignado](xdm-var-mapping.md). Si establece un campo de objeto de datos determinado y su campo XDM respectivo, el campo de objeto de datos tiene prioridad. Por ejemplo, si el campo `data.__adobe.analytics.events` está presente, sobrescribe todos los campos de objeto XDM relacionados con el evento.

Algunos campos de objetos de datos también admiten su [valor de parámetro de consulta](../validate/query-parameters.md) respectivo como valores abreviados. Puede utilizar de forma intercambiable campos de objeto de datos estándar y campos de objeto de datos abreviados, siempre y cuando cada uno de ellos sea para variables únicas. Evite establecer un campo de objeto de datos estándar y su campo de objeto de datos abreviado respectivo al mismo tiempo. Adobe no puede garantizar qué campo tiene prioridad.

## Asignación de campos de objeto de datos

Las actualizaciones anteriores de esta tabla se encuentran en el [historial de confirmaciones de esta página en GitHub](https://github.com/AdobeDocs/analytics.es-ES/commits/main/help/implement/aep-edge/data-var-mapping.md). Al igual que las variables de AppMeasurement, todos los campos de objetos de datos distinguen entre mayúsculas y minúsculas.

| Ruta del campo del objeto de datos | Variable y descripción de Analytics |
| --- | --- |
| `data.__adobe.analytics.browserHeight` | La dimensión [Altura del explorador](../../components/dimensions/browser-height.md). También se admite el campo abreviado `data.__adobe.analytics.bh`. |
| `data.__adobe.analytics.browserWidth` | Dimensión [Ancho del explorador](../../components/dimensions/browser-width.md). También se admite el campo abreviado `data.__adobe.analytics.bw`. |
| `data.__adobe.analytics.campaign` | La dimensión [Código de seguimiento](../../components/dimensions/tracking-code.md). También se admite el campo abreviado `data.__adobe.analytics.v0`. |
| `data.__adobe.analytics.channel` | La dimensión [sección del sitio](../../components/dimensions/site-section.md). También se admite el campo abreviado `data.__adobe.analytics.ch`. |
| `data.__adobe.analytics.colorDepth` | La dimensión [Profundidad de color](../../components/dimensions/color-depth.md). También se admite el campo abreviado `data.__adobe.analytics.c`. |
| `data.__adobe.analytics.connectionType` | La dimensión [Tipo de conexión](../../components/dimensions/connection-type.md). También se admite el campo abreviado `data.__adobe.analytics.ct`. |
| `data.__adobe.analytics.contextData` | [Variables de datos de contexto](/help/implement/vars/page-vars/contextdata.md). |
| `data.__adobe.analytics.cookiesEnabled` | La dimensión [Compatibilidad con cookies](../../components/dimensions/cookie-support.md). También se admite el campo abreviado `data.__adobe.analytics.k`. |
| `data.__adobe.analytics.currencyCode` | La variable de implementación [`currencyCode`](../vars/config-vars/currencycode.md). También se admite el campo abreviado `data.__adobe.analytics.cc`. |
| `data.__adobe.analytics.dynamicVariablePrefix` | La variable de implementación [`dynamicVariablePrefix`](../vars/config-vars/dynamicvariableprefix.md). |
| `data.__adobe.analytics.eVar1` - `data.__adobe.analytics.eVar250` | [eVar](../../components/dimensions/evar.md) dimensiones. También se admiten los campos abreviados `data.__adobe.analytics.v1` - `data.__adobe.analytics.v250`. |
| `data.__adobe.analytics.events` | [Eventos personalizados](../../components/metrics/custom-events.md). Dé a este campo un formato similar al de la variable de implementación [`events`](../vars/page-vars/events/events-overview.md). |
| `data.__adobe.analytics.javaEnabled` | La dimensión [Java habilitado](../../components/dimensions/java-enabled.md). También se admite el campo abreviado `data.__adobe.analytics.v`. |
| `data.__adobe.analytics.latitude` | Ayuda a establecer las dimensiones del ciclo de vida móvil [Location](../../components/dimensions/lifecycle-dimensions.md). También se admite el campo abreviado `data.__adobe.analytics.lat`. |
| `data.__adobe.analytics.linkName` | La dimensión [Vínculo personalizado](../../components/dimensions/custom-link.md), [Vínculo de descarga](../../components/dimensions/download-link.md) o [Vínculo de salida](../../components/dimensions/exit-link.md), según el valor de `data.__adobe.analytics.linkType`. También se admite el campo abreviado `data.__adobe.analytics.pev2`. |
| `data.__adobe.analytics.linkURL` | La variable de implementación [`linkURL`](../vars/config-vars/linkurl.md). También se admite el campo abreviado `data.__adobe.analytics.pev1`. |
| `data.__adobe.analytics.linkType` | Determina el tipo de vínculo en el que se hizo clic. Los valores válidos incluyen `o` (vínculos personalizados), `d` (vínculos de descarga) y `e` (vínculos de salida). También se admite el campo abreviado `data.__adobe.analytics.pe`. |
| `data.__adobe.analytics.list1` - `data.__adobe.analytics.list3` | [`list`](/help/implement/vars/page-vars/list.md) variables de implementación. También se admiten los campos abreviados `data.__adobe.analytics.l1` - `data.__adobe.analytics.list3`. |
| `data.__adobe.analytics.longitude` | Ayuda a establecer las dimensiones del ciclo de vida móvil [Location](../../components/dimensions/lifecycle-dimensions.md). También se admite el campo abreviado `data.__adobe.analytics.lon`. |
| `data.__adobe.analytics.pageName` | La dimensión [Página](/help/components/dimensions/page.md). |
| `data.__adobe.analytics.pageURL` | La dimensión [URL de la página](/help/components/dimensions/page-url.md). También se admite el campo abreviado `data.__adobe.analytics.g`. |
| `data.__adobe.analytics.pageType` | La variable de implementación [`pageType`](../vars/page-vars/pagetype.md). |
| `data.__adobe.analytics.prop1` - `data.__adobe.analytics.prop75` | [Prop](../../components/dimensions/prop.md) dimensiones. También se admiten los campos abreviados `data.__adobe.analytics.c1` - `data.__adobe.analytics.c75`. |
| `data.__adobe.analytics.purchaseID` | La variable de implementación [`purchaseID`](../vars/page-vars/purchaseid.md). |
| `data.__adobe.analytics.products` | La variable de implementación [`products`](../vars/page-vars/products.md), con un formato similar. |
| `data.__adobe.analytics.referrer` | La dimensión [Referente](/help/components/dimensions/referrer.md). |
| `data.__adobe.analytics.resolution` | La dimensión [Resolución del monitor](../../components/dimensions/monitor-resolution.md). También se admite el campo abreviado `data.__adobe.analytics.s`. |
| `data.__adobe.analytics.server` | La dimensión [Servidor](/help/components/dimensions/server.md). |
| `data.__adobe.analytics.transactionID` | La variable de implementación [`transactionID`](../vars/page-vars/transactionid.md). También se admite el campo abreviado `data.__adobe.analytics.xact`. |
| `data.__adobe.analytics.zip` | La dimensión [Código postal](../../components/dimensions/zip-code.md). |

{style="table-layout:auto"}

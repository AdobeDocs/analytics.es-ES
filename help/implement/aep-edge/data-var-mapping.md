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

En la tabla siguiente se muestran las variables de objetos de datos que el Edge Network de Adobe Experience Platform asigna automáticamente a Adobe Analytics. Si utiliza estas rutas de campo de objeto de datos, no es necesaria ninguna configuración adicional para enviar datos a Adobe Analytics.

Se recomienda utilizar estos campos si tiene intención de utilizar Customer Journey Analytics en el futuro. Este método de implementación permite a su organización enviar datos al Adobe mediante el SDK web sin ajustarse a un esquema XDM. Cuando su organización esté lista para enviar datos a Adobe Experience Platform, puede utilizar [Asignación de flujo de datos](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/data-prep#mapping) para apuntar los campos de objeto de datos a sus respectivos campos XDM.

## Prioridades de valor

La mayoría de los campos de objeto de datos de esta tabla coinciden con un [campo XDM asignado](xdm-var-mapping.md). Si establece un campo de objeto de datos determinado y su campo XDM respectivo, el campo de objeto de datos tiene prioridad. Por ejemplo, si el campo `data.__adobe.analytics.events` está presente, sobrescribe todos los campos de objeto XDM relacionados con el evento.

Algunos campos de objetos de datos también admiten sus respectivos [Valor del parámetro de consulta](../validate/query-parameters.md) como valores abreviados. Puede utilizar de forma intercambiable campos de objeto de datos estándar y campos de objeto de datos abreviados, siempre y cuando cada uno de ellos sea para variables únicas. Evite establecer un campo de objeto de datos estándar y su campo de objeto de datos abreviado respectivo al mismo tiempo. El Adobe no puede garantizar qué campo tiene prioridad.

## Asignación de campos de objeto de datos

Las actualizaciones anteriores de esta tabla se encuentran en el [historial de confirmaciones en GitHub](https://github.com/AdobeDocs/analytics.en/commits/main/help/implement/aep-edge/data-var-mapping.md). Al igual que las variables de AppMeasurement, todos los campos de objetos de datos distinguen entre mayúsculas y minúsculas.

| Ruta del campo del objeto de datos | Variable y descripción de Analytics |
| --- | --- |
| `data.__adobe.analytics.browserHeight` | El [Altura del explorador](../../components/dimensions/browser-height.md) dimensión. El campo abreviado `data.__adobe.analytics.bh` también es compatible. |
| `data.__adobe.analytics.browserWidth` | El [Anchura del explorador](../../components/dimensions/browser-width.md) dimensión. El campo abreviado `data.__adobe.analytics.bw` también es compatible. |
| `data.__adobe.analytics.campaign` | El [Código de seguimiento](../../components/dimensions/tracking-code.md) dimensión. El campo abreviado `data.__adobe.analytics.v0` también es compatible. |
| `data.__adobe.analytics.channel` | El [Sección del sitio](../../components/dimensions/site-section.md) dimensión. El campo abreviado `data.__adobe.analytics.ch` también es compatible. |
| `data.__adobe.analytics.colorDepth` | El [Profundidad de color](../../components/dimensions/color-depth.md) dimensión. El campo abreviado `data.__adobe.analytics.c` también es compatible. |
| `data.__adobe.analytics.connectionType` | El [Tipo de conexión](../../components/dimensions/connection-type.md) dimensión. El campo abreviado `data.__adobe.analytics.ct` también es compatible. |
| `data.__adobe.analytics.contextData` | [Variables de datos de contexto](/help/implement/vars/page-vars/contextdata.md). |
| `data.__adobe.analytics.cookiesEnabled` | El [Compatibilidad con cookies](../../components/dimensions/cookie-support.md) dimensión. El campo abreviado `data.__adobe.analytics.k` también es compatible. |
| `data.__adobe.analytics.currencyCode` | El [`currencyCode`](../vars/config-vars/currencycode.md) variable de implementación. El campo abreviado `data.__adobe.analytics.cc` también es compatible. |
| `data.__adobe.analytics.dynamicVariablePrefix` | El [`dynamicVariablePrefix`](../vars/config-vars/dynamicvariableprefix.md) variable de implementación. |
| `data.__adobe.analytics.eVar1` - `data.__adobe.analytics.eVar250` | [eVar](../../components/dimensions/evar.md) dimensiones. Los campos abreviados `data.__adobe.analytics.v1` - `data.__adobe.analytics.v250` también son compatibles. |
| `data.__adobe.analytics.events` | [Eventos personalizados](../../components/metrics/custom-events.md). Dé un formato similar a este campo [`events`](../vars/page-vars/events/events-overview.md) variable de implementación. |
| `data.__adobe.analytics.javaEnabled` | El [Habilitado para Java](../../components/dimensions/java-enabled.md) dimensión. El campo abreviado `data.__adobe.analytics.v` también es compatible. |
| `data.__adobe.analytics.latitude` | Ayuda a establecer el [Ubicación](../../components/dimensions/lifecycle-dimensions.md) dimensiones del ciclo vital móvil. El campo abreviado `data.__adobe.analytics.lat` también es compatible. |
| `data.__adobe.analytics.linkName` | El [Vínculo personalizado](../../components/dimensions/custom-link.md), [Vínculo de descarga](../../components/dimensions/download-link.md), o [Vínculo de salida](../../components/dimensions/exit-link.md) dimensión, según el valor de `data.__adobe.analytics.linkType`. El campo abreviado `data.__adobe.analytics.pev2` también es compatible. |
| `data.__adobe.analytics.linkURL` | El [`linkURL`](../vars/config-vars/linkurl.md) variable de implementación. El campo abreviado `data.__adobe.analytics.pev1` también es compatible. |
| `data.__adobe.analytics.linkType` | Determina el tipo de vínculo en el que se hizo clic. Los valores válidos incluyen `o` (Vínculos personalizados), `d` (Vínculos de descarga), y `e` (Vínculos de salida). El campo abreviado `data.__adobe.analytics.pe` también es compatible. |
| `data.__adobe.analytics.list1` - `data.__adobe.analytics.list3` | [`list`](/help/implement/vars/page-vars/list.md) variables de implementación. Los campos abreviados `data.__adobe.analytics.l1` - `data.__adobe.analytics.list3` también son compatibles. |
| `data.__adobe.analytics.longitude` | Ayuda para establecer el [Ubicación](../../components/dimensions/lifecycle-dimensions.md) dimensiones del ciclo vital móvil. El campo abreviado `data.__adobe.analytics.lon` también es compatible. |
| `data.__adobe.analytics.pageName` | La dimensión [Página](/help/components/dimensions/page.md). |
| `data.__adobe.analytics.pageURL` | El [URL de página](/help/components/dimensions/page-url.md) dimensión. El campo abreviado `data.__adobe.analytics.g` también es compatible. |
| `data.__adobe.analytics.pageType` | El [`pageType`](../vars/page-vars/pagetype.md) variable de implementación. |
| `data.__adobe.analytics.prop1` - `data.__adobe.analytics.prop75` | [Prop](../../components/dimensions/prop.md) dimensiones. Los campos abreviados `data.__adobe.analytics.c1` - `data.__adobe.analytics.c75` también son compatibles. |
| `data.__adobe.analytics.purchaseID` | El [`purchaseID`](../vars/page-vars/purchaseid.md) variable de implementación. |
| `data.__adobe.analytics.products` | El [`products`](../vars/page-vars/products.md) variable de implementación, con un formato similar. |
| `data.__adobe.analytics.referrer` | La dimensión [Referente](/help/components/dimensions/referrer.md). |
| `data.__adobe.analytics.resolution` | El [Resolución del monitor](../../components/dimensions/monitor-resolution.md) dimensión. El campo abreviado `data.__adobe.analytics.s` también es compatible. |
| `data.__adobe.analytics.server` | La dimensión [Servidor](/help/components/dimensions/server.md). |
| `data.__adobe.analytics.transactionID` | El [`transactionID`](../vars/page-vars/transactionid.md) variable de implementación. El campo abreviado `data.__adobe.analytics.xact` también es compatible. |
| `data.__adobe.analytics.zip` | El [Código postal](../../components/dimensions/zip-code.md) dimensión. |

{style="table-layout:auto"}

---
title: Asignación de campos de objeto de datos a Adobe Analytics
description: Vea qué campos de objeto de datos de Experience Platform Edge se asignan automáticamente a las variables de Analytics.
feature: Implementation Basics
role: Admin, Developer
exl-id: 45b2fbbc-73ca-40b3-9484-b406ae99fdad
source-git-commit: b3546e67cccc37cbdb89db2e80b3b34b2dbe417b
workflow-type: tm+mt
source-wordcount: '592'
ht-degree: 77%

---

# Asignación de campos de objeto de datos a Adobe Analytics

En la tabla siguiente se muestra el campo de objeto de datos que Adobe Experience Platform Edge Network asigna automáticamente a Adobe Analytics. Si utiliza estas rutas de campo de objetos de datos, no es necesaria ninguna configuración adicional para enviar datos a Adobe Analytics.

Se recomienda utilizar estos campos si tiene intención de utilizar Customer Journey Analytics en el futuro. Este método de implementación permite a su organización enviar datos a Adobe mediante SDK web sin ajustarse a un esquema XDM. Cuando su organización esté lista para enviar datos a Adobe Experience Platform, puede usar [Asignación de secuencia de datos](https://experienceleague.adobe.com/es/docs/experience-platform/datastreams/data-prep#mapping) para apuntar los campos de objeto de datos a sus respectivos campos XDM.

## Prioridades de valor

La mayoría de los campos de objeto de datos de esta tabla corresponden a un [campo XDM asignado](xdm-var-mapping.md). Durante la ingesta de Adobe Analytics, los valores se asignan primero de XDM a variables de Analytics. A continuación, se asignan los campos de objeto de datos reconocidos y se sobrescriben los valores establecidos anteriormente cuando se asignan a la misma variable de Analytics. Por ejemplo, si `data.__adobe.analytics.events` está presente, reemplaza todo el conjunto de eventos que, de lo contrario, se derivarían de XDM; los eventos no se combinan en ambos orígenes. Una cadena vacía (`""`) en un campo de objeto de datos deja en blanco su variable de Analytics asignada para la visita, incluso si el campo XDM correspondiente contiene un valor.

Algunos campos de objeto de datos también admiten su [valor de parámetro de consulta](../validate/query-parameters.md) respectivo como valores abreviados. Puede utilizar de forma intercambiable campos de objeto de datos estándar y campos de objeto de datos abreviados, siempre y cuando cada uno de ellos sea para variables únicas. Evite establecer un campo de objeto de datos estándar y su campo de objeto de datos abreviado respectivo al mismo tiempo. Adobe no puede garantizar qué campo tiene prioridad.

## Asignación de campo de objeto de datos

Las actualizaciones anteriores de esta tabla se encuentran en el [historial de confirmaciones en GitHub](https://github.com/AdobeDocs/analytics.en/commits/main/help/implement/aep-edge/data-var-mapping.md) de esta página. Al igual que las variables de AppMeasurement, todos los campos de objeto de datos distinguen entre mayúsculas y minúsculas.

| Ruta del campo del objeto de datos | Descripción y variable de Analytics |
| --- | --- |
| `data.__adobe.analytics.browserHeight` | Dimensión [Altura del explorador](../../components/dimensions/browser-height.md). También se admite el campo abreviado `data.__adobe.analytics.bh`. |
| `data.__adobe.analytics.browserWidth` | Dimensión [Anchura del explorador](../../components/dimensions/browser-width.md). También se admite el campo abreviado `data.__adobe.analytics.bw`. |
| `data.__adobe.analytics.campaign` | Dimensión [Código de seguimiento](../../components/dimensions/tracking-code.md). También se admite el campo abreviado `data.__adobe.analytics.v0`. |
| `data.__adobe.analytics.channel` | Dimensión [Sección del sitio](../../components/dimensions/site-section.md). También se admite el campo abreviado `data.__adobe.analytics.ch`. |
| `data.__adobe.analytics.colorDepth` | Dimensión [Profundidad de color](../../components/dimensions/color-depth.md). También se admite el campo abreviado `data.__adobe.analytics.c`. |
| `data.__adobe.analytics.connectionType` | Dimensión [Tipo de conexión](../../components/dimensions/connection-type.md). También se admite el campo abreviado `data.__adobe.analytics.ct`. |
| `data.__adobe.analytics.contextData` | [Variables de datos de contexto](/help/implement/vars/page-vars/contextdata.md). |
| `data.__adobe.analytics.cookiesEnabled` | Dimensión [Compatibilidad con cookies](../../components/dimensions/cookie-support.md). También se admite el campo abreviado `data.__adobe.analytics.k`. |
| `data.__adobe.analytics.currencyCode` | Variable de implementación [`currencyCode`](../vars/config-vars/currencycode.md). También se admite el campo abreviado `data.__adobe.analytics.cc`. |
| `data.__adobe.analytics.dynamicVariablePrefix` | Variable de implementación [`dynamicVariablePrefix`](../vars/config-vars/dynamicvariableprefix.md). |
| `data.__adobe.analytics.eVar1` - `data.__adobe.analytics.eVar250` | Dimensiones [eVar](../../components/dimensions/evar.md). También se admiten los campos abreviados `data.__adobe.analytics.v1` - `data.__adobe.analytics.v250`. |
| `data.__adobe.analytics.events` | [Eventos personalizados](../../components/metrics/custom-events.md). Dé a este campo un formato similar al de la variable de implementación [`events`](../vars/page-vars/events/events-overview.md). |
| `data.__adobe.analytics.javaEnabled` | Dimensión [Java habilitado](../../components/dimensions/java-enabled.md). También se admite el campo abreviado `data.__adobe.analytics.v`. |
| `data.__adobe.analytics.latitude` | Ayuda a establecer las dimensiones del ciclo de vida móvil [Ubicación](../../components/dimensions/lifecycle-dimensions.md). También se admite el campo abreviado `data.__adobe.analytics.lat`. |
| `data.__adobe.analytics.linkName` | La dimensión [Vínculo personalizado](../../components/dimensions/custom-link.md), [Vínculo de descarga](../../components/dimensions/download-link.md) o [Vínculo de salida](../../components/dimensions/exit-link.md), según el valor de `data.__adobe.analytics.linkType`. También se admite el campo abreviado `data.__adobe.analytics.pev2`. |
| `data.__adobe.analytics.linkURL` | Variable de implementación [`linkURL`](../vars/config-vars/linkurl.md). También se admite el campo abreviado `data.__adobe.analytics.pev1`. |
| `data.__adobe.analytics.linkType` | Determina el tipo de vínculo en el que se hizo clic. Los valores válidos incluyen `o` (vínculos personalizados), `d` (vínculos de descarga) y `e` (vínculos de salida). También se admite el campo abreviado `data.__adobe.analytics.pe`. |
| `data.__adobe.analytics.list1` - `data.__adobe.analytics.list3` | [`list`](/help/implement/vars/page-vars/list.md) variables de implementación. También se admiten los campos abreviados `data.__adobe.analytics.l1` - `data.__adobe.analytics.list3`. |
| `data.__adobe.analytics.longitude` | Ayuda a establecer las dimensiones del ciclo de vida móvil [Ubicación](../../components/dimensions/lifecycle-dimensions.md). También se admite el campo abreviado `data.__adobe.analytics.lon`. |
| `data.__adobe.analytics.pageName` | La dimensión [Página](/help/components/dimensions/page.md). |
| `data.__adobe.analytics.pageURL` | Dimensión [URL de la página](/help/components/dimensions/page-url.md). También se admite el campo abreviado `data.__adobe.analytics.g`. |
| `data.__adobe.analytics.pageType` | Variable de implementación [`pageType`](../vars/page-vars/pagetype.md). |
| `data.__adobe.analytics.prop1` - `data.__adobe.analytics.prop75` | Dimensiones [Prop](../../components/dimensions/prop.md). También se admiten los campos abreviados `data.__adobe.analytics.c1` - `data.__adobe.analytics.c75`. |
| `data.__adobe.analytics.purchaseID` | Variable de implementación [`purchaseID`](../vars/page-vars/purchaseid.md). |
| `data.__adobe.analytics.products` | Variable de implementación [`products`](../vars/page-vars/products.md), con un formato similar. |
| `data.__adobe.analytics.referrer` | La dimensión [Referente](/help/components/dimensions/referrer.md). |
| `data.__adobe.analytics.resolution` | Dimensión [Resolución del monitor](../../components/dimensions/monitor-resolution.md). También se admite el campo abreviado `data.__adobe.analytics.s`. |
| `data.__adobe.analytics.server` | La dimensión [Servidor](/help/components/dimensions/server.md). |
| `data.__adobe.analytics.transactionID` | Variable de implementación [`transactionID`](../vars/page-vars/transactionid.md). También se admite el campo abreviado `data.__adobe.analytics.xact`. |
| `data.__adobe.analytics.zip` | Dimensión [Código postal](../../components/dimensions/zip-code.md). |

{style="table-layout:auto"}

---
title: Parámetros de consulta de recopilación de datos
description: Enumera todos los parámetros de cadena de consulta utilizados en solicitudes de imagen.
translation-type: tm+mt
source-git-commit: edf3ac3ebc99444b86bcd9239cef9ed84d797565
workflow-type: tm+mt
source-wordcount: '648'
ht-degree: 75%

---


# Parámetros de consulta de recopilación de datos

En la tabla siguiente se muestran todos los parámetros de cadena de consulta que Adobe utiliza en las solicitudes de imagen. Esta información se puede utilizar al depurar con [analizadores de paquetes](packet-monitor.md), al [codificar solicitudes de imagen](../other/hardcoded.md) o al usar [variables dinámicas](../vars/page-vars/dynamic-variables.md).

| Parámetro | Variable de implementación de Analytics | Descripción |
| --- | --- | --- |
| `aamlh` | Ninguna | Indicación de ubicación de Audience Manager. Usado en la integración de Experience Cloud Shared Profile. |
| `aamb` | Ninguna | Blob de Audience Manager. Usado en la integración de Experience Cloud Shared Profile. |
| `aid` | Ninguna | ID de visitante de Analytics. |
| `AQB` | Ninguna | Indica el inicio de una solicitud de imagen de una cadena de consulta. |
| `AQE` | Ninguna | Indica el final de una solicitud de imagen, lo que significa que no se truncó la solicitud. |
| `bh` | Ninguna | Altura del explorador (en píxeles). Used in the [Browser height](/help/components/dimensions/browser-height.md) dimension. |
| `bw` | Ninguna | Anchura del explorador (en píxeles). Used in the [Browser width](/help/components/dimensions/browser-width.md) dimension. |
| `c` | Ninguna | Calidad de color (en bits). Used in the [Color depth](/help/components/dimensions/color-depth.md) dimension. |
| `c.` | [`contextData`](../vars/page-vars/contextdata.md) | Indica el inicio de las variables de datos de contexto. Nunca contiene un valor. |
| `.c` | [`contextData`](../vars/page-vars/contextdata.md) | Indica el final de las variables de datos de contexto. Nunca contiene un valor. |
| `c1` - `c75` | [`prop1` - `prop75`](../vars/page-vars/prop.md) | [Props](/help/components/dimensions/prop.md)o variables de tráfico personalizadas. |
| `cc` | [`currencyCode`](../vars/config-vars/currencycode.md) | El tipo de moneda usado en la visita. |
| `cdp` | [`cookieDomainPeriods`](../vars/config-vars/cookiedomainperiods.md) | Número de puntos de un dominio. Se utiliza para ayudar a almacenar las cookies correctamente. |
| `ce` | [`charSet`](../vars/config-vars/charset.md) | La codificación de caracteres de la solicitud de imagen. |
| `cl` | [`cookieLifetime`](../vars/config-vars/cookielifetime.md) | La duración de la cookie del visitante. |
| `ch` | [`channel`](../vars/page-vars/channel.md) | Used in the [Site sections](/help/components/dimensions/site-section.md) dimension. |
| `cp` | Ninguna | Used in the [Hit Type](/help/components/dimensions/hit-type.md) dimension. |
| `ct` | Ninguna | Used in the [Connection Type](/help/components/dimensions/connection-type.md) dimension. |
| `D` | [`dynamicVariablePrefix`](../vars/config-vars/dynamicvariableprefix.md) | Indica lo que se debe utilizar para variables dinámicas. |
| `ev` | [`events`](../vars/page-vars/events/events-overview.md) | Abreviatura de la cadena de consulta `events`. |
| `events` | [`events`](../vars/page-vars/events/events-overview.md) | Lista de eventos de la página separados por comas. Se utiliza en la mayoría de [las métricas](/help/components/metrics/overview.md). |
| `g` | [`pageURL`](../vars/page-vars/pageurl.md) | Dirección URL actual de la página, hasta 255 bytes. Used in the [Page URL](/help/components/dimensions/page-url.md) dimension. |
| `-g` | [`pageURL`](../../components/dimensions/page-url.md) | Las direcciones URL superiores a 255 bytes se dividen. Los primeros 255 bytes aparecen en el parámetro `g` y todos los bytes restantes aparecen en el parámetro `-g`. |
| `gn` | [`pageName`](../vars/page-vars/pagename.md) | Abreviatura de la cadena de consulta `pageName`. |
| `gt` | [`pageType`](../vars/page-vars/pagetype.md) | Abreviatura de la cadena de consulta `pageType`. |
| `h1` - `h5` | [`hier1` - `hier5`](../vars/page-vars/hier.md) | Dimensiones de jerarquía. |
| `hp` | Ninguna | Ya no se utiliza. En versiones anteriores de Adobe Analytics, se determinó si la dirección URL actual era la página principal del explorador. |
| `j` | Ninguna | Versión de JavaScript instalada en el explorador. |
| `k` | Ninguna | Used in the [Cookie support](/help/components/dimensions/cookie-support.md) dimension. |
| `l1` - `l3` | [`list1` - `list3`](../vars/page-vars/list.md) | Variables de lista. |
| `mid` | Ninguna | ID de visitante de Experience Cloud. |
| `ndh` | Ninguna | Marca que indica si la solicitud de imagen se originó en AppMeasurement. |
| `ns` | [`visitorNameSpace`](../vars/config-vars/visitornamespace.md) | Ayuda a determinar dónde se configuran las cookies. |
| `oid` | [`s_objectID`](../vars/page-vars/s-objectid.md) | Identificador de objeto de la última página. Se utiliza en Activity Map. |
| `ot` | Ninguna | Nombre del objeto de la última página. Se utiliza en versiones anteriores de Activity Map. |
| `p` | Ninguna | Ya no se utiliza. Lista de complementos utilizados en el explorador. |
| `pageName` | [`pageName`](../vars/page-vars/pagename.md) | Used in the [Page](/help/components/dimensions/page.md) dimension. |
| `pageType` | [`pageType`](../vars/page-vars/pagetype.md) | Used in the [Pages not found](/help/components/dimensions/pages-not-found.md) dimension. |
| `pccr` | Ninguna | Solo se configura para visitantes nuevos y siempre se establece como `true`. Ayuda a evitar redirecciones infinitas. |
| `pe` | [`linkType`](../vars/config-vars/linktype.md) | Determina el tipo de vínculo personalizado. Necesario para vínculos [](/help/components/dimensions/custom-link.md)personalizados, vínculos [de](/help/components/dimensions/download-link.md)descarga y vínculos [de](/help/components/dimensions/exit-link.md)salida. |
| `pev1` | Ninguna | Dirección URL en la que se produjo el vínculo personalizado. |
| `pev2` | [`linkName`](../vars/config-vars/linkname.md) | Nombre reconocible del vínculo personalizado. |
| `pev3` | Ninguna | Ya no se utiliza. Hitos rastreados en versiones anteriores de informes de vídeo. |
| `pf` | Ninguna | Indicador de plataforma; solo para uso de Adobe. No se debe alterar. |
| `pid` | Ninguna | Identificador de página de la última página. Se utiliza en versiones anteriores de Activity Map. |
| `pidt` | Ninguna | Tipo de identificador de página de la última página. Se utiliza en versiones anteriores de Activity Map. |
| `pl` | [`products`](../vars/page-vars/products.md) | Abreviatura de la cadena de consulta `products`. |
| `products` | [`products`](../vars/page-vars/products.md) | Variable Products. Se utiliza en las dimensiones [Producto](/help/components/dimensions/product.md) y [Categoría](/help/components/dimensions/category.md) . |
| `purchaseID` | [`purchaseID`](../vars/page-vars/purchaseid.md) | Se utiliza para la deduplicación de compras. |
| `r` | [`referrer`](../vars/page-vars/referrer.md) | URL de referencia de la visita. Se utiliza en dimensiones de fuentes de tráfico, como [Remitente del reenvío](/help/components/dimensions/referrer.md) y dominio de [referencia](/help/components/dimensions/referring-domain.md) |
| `s` | Ninguna | Resolución de pantalla, en `width x height`. Used in the [Monitor resolutions](/help/components/dimensions/monitor-resolution.md) dimension. |
| `server` | [`server`](../vars/page-vars/server.md) | [Dimensión de servidor.](/help/components/dimensions/server.md) |
| `sv` | [`server`](../vars/page-vars/server.md) | Abreviatura de la cadena de consulta `server`. |
| `state` | [`state`](../vars/page-vars/state.md) | Dimensión de estado. |
| `t` | Ninguna | Fecha y hora generadas de la visita. Utiliza el formato `dd/mm/yyyy hh:mm:ss w o`.<br>- `dd/mm/yyyy hh:mm:ss` es el formato de fecha y hora en JavaScript. El mes `0` es enero, mientras que el mes `11` es diciembre.<br>- `w` es el día de la semana. `0` es domingo, mientras que `6` es sábado.<br>- `o` es el desplazamiento negativo GMT en minutos. Por ejemplo, `420` es GMT-7. |
| `ts` | [`timestamp`](../vars/page-vars/timestamp.md) | Marca de hora personalizada establecida con la visita. Se suele usar para el seguimiento sin conexión. |
| `v` | Ninguna | Used in the [Java enabled](/help/components/dimensions/java-enabled.md) dimension. |
| `v0` | [`campaign`](../vars/page-vars/campaign.md) | [Dimensión Código de seguimiento.](/help/components/dimensions/tracking-code.md) |
| `v1` - `v250` | [`evar1` - `eVar250`](../vars/page-vars/evar.md) | [eVars](/help/components/dimensions/evar.md)o dimensiones de conversión personalizadas. |
| `vid` | [`visitorID`](../vars/config-vars/visitorid.md) | Variable de ID de visitante. |
| `vmk` | `vmk` | Ya no se utiliza. Clave de migración de Visitante, que ayuda a migrar las implementaciones de cookies de terceros a cookies de origen. |
| `vvp` | `variableProvider` | Se utiliza en Data Connectors. |
| `xact` | [`transactionID`](../vars/page-vars/transactionid.md) | Se utiliza con las fuentes de datos para enlazar datos en línea y sin conexión. |
| `zip` | [`zip`](../vars/page-vars/zip.md) | Used in the [Zip code](/help/components/dimensions/zip-code.md) dimension. |

---
title: Parámetros de consulta de recopilación de datos
description: Enumera todos los parámetros de cadena de consulta utilizados en solicitudes de imagen.
translation-type: ht
source-git-commit: edf3ac3ebc99444b86bcd9239cef9ed84d797565
workflow-type: ht
source-wordcount: '648'
ht-degree: 100%

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
| `bh` | Ninguna | Altura del explorador (en píxeles). Se utiliza en la dimensión [Altura del explorador](/help/components/dimensions/browser-height.md). |
| `bw` | Ninguna | Anchura del explorador (en píxeles). Se utiliza en la dimensión [Anchura del explorador](/help/components/dimensions/browser-width.md). |
| `c` | Ninguna | Calidad de color (en bits). Se utiliza en la dimensión [Profundidad de color](/help/components/dimensions/color-depth.md). |
| `c.` | [`contextData`](../vars/page-vars/contextdata.md) | Indica el inicio de las variables de datos de contexto. Nunca contiene un valor. |
| `.c` | [`contextData`](../vars/page-vars/contextdata.md) | Indica el final de las variables de datos de contexto. Nunca contiene un valor. |
| `c1` - `c75` | [`prop1` - `prop75`](../vars/page-vars/prop.md) | [Props](/help/components/dimensions/prop.md) o variables de tráfico personalizadas. |
| `cc` | [`currencyCode`](../vars/config-vars/currencycode.md) | El tipo de moneda usado en la visita. |
| `cdp` | [`cookieDomainPeriods`](../vars/config-vars/cookiedomainperiods.md) | Número de puntos de un dominio. Se utiliza para ayudar a almacenar las cookies correctamente. |
| `ce` | [`charSet`](../vars/config-vars/charset.md) | La codificación de caracteres de la solicitud de imagen. |
| `cl` | [`cookieLifetime`](../vars/config-vars/cookielifetime.md) | La duración de la cookie del visitante. |
| `ch` | [`channel`](../vars/page-vars/channel.md) | Se utiliza en la dimensión [Secciones del sitio](/help/components/dimensions/site-section.md). |
| `cp` | Ninguna | Se utiliza en la dimensión [Tipo de visita](/help/components/dimensions/hit-type.md). |
| `ct` | Ninguna | Se utiliza en la dimensión [Tipo de conexión](/help/components/dimensions/connection-type.md). |
| `D` | [`dynamicVariablePrefix`](../vars/config-vars/dynamicvariableprefix.md) | Indica lo que se debe utilizar para variables dinámicas. |
| `ev` | [`events`](../vars/page-vars/events/events-overview.md) | Abreviatura de la cadena de consulta `events`. |
| `events` | [`events`](../vars/page-vars/events/events-overview.md) | Lista de eventos de la página separados por comas. Utilizado por la mayoría de las [métricas](/help/components/metrics/overview.md). |
| `g` | [`pageURL`](../vars/page-vars/pageurl.md) | Dirección URL actual de la página, hasta 255 bytes. Se utiliza en la dimensión [URL de la página](/help/components/dimensions/page-url.md). |
| `-g` | [`pageURL`](../../components/dimensions/page-url.md) | Las direcciones URL superiores a 255 bytes se dividen. Los primeros 255 bytes aparecen en el parámetro `g` y todos los bytes restantes aparecen en el parámetro `-g`. |
| `gn` | [`pageName`](../vars/page-vars/pagename.md) | Abreviatura de la cadena de consulta `pageName`. |
| `gt` | [`pageType`](../vars/page-vars/pagetype.md) | Abreviatura de la cadena de consulta `pageType`. |
| `h1` - `h5` | [`hier1` - `hier5`](../vars/page-vars/hier.md) | Dimensiones de jerarquía. |
| `hp` | Ninguna | Ya no se utiliza. En versiones anteriores de Adobe Analytics, se determinó si la dirección URL actual era la página principal del explorador. |
| `j` | Ninguna | Versión de JavaScript instalada en el explorador. |
| `k` | Ninguna | Utilizada en la dimensión [Compatibilidad con cookies](/help/components/dimensions/cookie-support.md). |
| `l1` - `l3` | [`list1` - `list3`](../vars/page-vars/list.md) | Variables de lista. |
| `mid` | Ninguna | ID de visitante de Experience Cloud. |
| `ndh` | Ninguna | Marca que indica si la solicitud de imagen se originó en AppMeasurement. |
| `ns` | [`visitorNameSpace`](../vars/config-vars/visitornamespace.md) | Ayuda a determinar dónde se configuran las cookies. |
| `oid` | [`s_objectID`](../vars/page-vars/s-objectid.md) | Identificador de objeto de la última página. Se utiliza en Activity Map. |
| `ot` | Ninguna | Nombre del objeto de la última página. Se utiliza en versiones anteriores de Activity Map. |
| `p` | Ninguna | Ya no se utiliza. Lista de complementos utilizados en el explorador. |
| `pageName` | [`pageName`](../vars/page-vars/pagename.md) | Se utiliza en la dimensión [Página](/help/components/dimensions/page.md). |
| `pageType` | [`pageType`](../vars/page-vars/pagetype.md) | Se utiliza en la dimensión [Páginas no encontradas](/help/components/dimensions/pages-not-found.md). |
| `pccr` | Ninguna | Solo se configura para visitantes nuevos y siempre se establece como `true`. Ayuda a evitar redireccionamientos infinitos. |
| `pe` | [`linkType`](../vars/config-vars/linktype.md) | Determina el tipo de vínculo personalizado. Necesario para [Vínculos personalizados](/help/components/dimensions/custom-link.md), [Vínculos de descarga](/help/components/dimensions/download-link.md) y [Vínculos de salida](/help/components/dimensions/exit-link.md). |
| `pev1` | Ninguna | Dirección URL en la que se produjo el vínculo personalizado. |
| `pev2` | [`linkName`](../vars/config-vars/linkname.md) | Nombre reconocible del vínculo personalizado. |
| `pev3` | Ninguna | Ya no se utiliza. Hitos rastreados en versiones anteriores de informes de vídeo. |
| `pf` | Ninguna | Indicador de plataforma; solo para uso de Adobe. No se debe alterar. |
| `pid` | Ninguna | Identificador de página de la última página. Se utiliza en versiones anteriores de Activity Map. |
| `pidt` | Ninguna | Tipo de identificador de página de la última página. Se utiliza en versiones anteriores de Activity Map. |
| `pl` | [`products`](../vars/page-vars/products.md) | Abreviatura de la cadena de consulta `products`. |
| `products` | [`products`](../vars/page-vars/products.md) | Variable Products. Se utiliza en las dimensiones [Producto](/help/components/dimensions/product.md) y [Categoría](/help/components/dimensions/category.md). |
| `purchaseID` | [`purchaseID`](../vars/page-vars/purchaseid.md) | Se utiliza para la deduplicación de compras. |
| `r` | [`referrer`](../vars/page-vars/referrer.md) | URL de referencia de la visita. Se utiliza en dimensiones de fuentes de tráfico, como [Remitente del reenvío](/help/components/dimensions/referrer.md) y [dominio de referencia](/help/components/dimensions/referring-domain.md) |
| `s` | Ninguna | Resolución de pantalla, en `width x height`. Se utiliza en la dimensión [Resoluciones del monitor](/help/components/dimensions/monitor-resolution.md). |
| `server` | [`server`](../vars/page-vars/server.md) | Dimensión de [Servidor](/help/components/dimensions/server.md). |
| `sv` | [`server`](../vars/page-vars/server.md) | Abreviatura de la cadena de consulta `server`. |
| `state` | [`state`](../vars/page-vars/state.md) | Dimensión de estado. |
| `t` | Ninguna | Fecha y hora generadas de la visita. Utiliza el formato `dd/mm/yyyy hh:mm:ss w o`.<br>- `dd/mm/yyyy hh:mm:ss` es el formato de fecha y hora en JavaScript. El mes `0` es enero, mientras que el mes `11` es diciembre.<br>- `w` es el día de la semana. `0` es domingo, mientras que `6` es sábado.<br>- `o` es el desplazamiento negativo GMT en minutos. Por ejemplo, `420` es GMT-7. |
| `ts` | [`timestamp`](../vars/page-vars/timestamp.md) | Marca de hora personalizada establecida con la visita. Se suele usar para el seguimiento sin conexión. |
| `v` | Ninguna | Se utiliza en la dimensión [Java Enabled](/help/components/dimensions/java-enabled.md). |
| `v0` | [`campaign`](../vars/page-vars/campaign.md) | Dimensión [Código de seguimiento](/help/components/dimensions/tracking-code.md). |
| `v1` - `v250` | [`evar1` - `eVar250`](../vars/page-vars/evar.md) | [eVars](/help/components/dimensions/evar.md) o dimensiones de conversión personalizadas. |
| `vid` | [`visitorID`](../vars/config-vars/visitorid.md) | Variable de ID de visitante. |
| `vmk` | `vmk` | Ya no se utiliza. Clave de migración de Visitante, que ayudó a migrar las implementaciones de cookies de terceros a cookies de origen. |
| `vvp` | `variableProvider` | Se utiliza en Data Connectors. |
| `xact` | [`transactionID`](../vars/page-vars/transactionid.md) | Se utiliza con las fuentes de datos para enlazar datos en línea y sin conexión. |
| `zip` | [`zip`](../vars/page-vars/zip.md) | Se utiliza en la dimensión [Código postal](/help/components/dimensions/zip-code.md). |

---
title: Parámetros de consulta de recopilación de datos
description: Enumera todos los parámetros de cadena de consulta utilizados en solicitudes de imagen.
feature: Implementation Basics
exl-id: 2eb2ade7-a3db-4b00-8a70-2632d1c0aaaf
role: Admin, Developer, Leader, User
TQID: https://experienceleague.adobe.com/aB92GXPxYSkjcDD9wi0vj47jijqndMbOGaECvXs38-Y
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: c069c44e-5426-4c1a-accc-8028662f2fdeid: e7d92df1-c5ba-4e93-85df-f83171b889beid: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: f8a45b24-4be7-4f1b-909b-60d06b483a20id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: a947d2d7f45d4155a61cbfe0f8110851cca32e60
workflow-type: tm+mt
source-wordcount: 1111
ht-degree: 46%

---

# Parámetros de consulta de recopilación de datos

En la tabla siguiente se muestran todos los parámetros de cadena de consulta que Adobe utiliza en las solicitudes de imagen. Esta información resulta útil cuando se depura con [analizadores de paquetes](packet-monitor.md), cuando se realizan [solicitudes de imagen de codificación](../other/hardcoded.md) o cuando se utilizan [variables dinámicas](../vars/page-vars/dynamic-variables.md).

| Parámetro | Variable de implementación de Analytics | Descripción |
| --- | --- | --- |
| `aamlh` | Ninguno | Sugerencia de ubicación de Audience Manager. Identifica el centro de datos regional utilizado para la sincronización de Audience Manager ID mediante el servicio de ID de visitante. |
| `aamb` | Ninguno | Blob de Audience Manager. Los datos de perfil de Audience Manager codificados pasados durante la sincronización de ID mediante el servicio de ID de visitante. |
| `aid` | Ninguno | El ID de visitante de Analytics heredado, almacenado en la cookie `s_vi`. Sustituido por el parámetro `mid` en implementaciones modernas. |
| `AQB` | Ninguna | Indica el inicio de una solicitud de imagen de una cadena de consulta. |
| `AQE` | Ninguna | Indica el final de una solicitud de imagen, lo que significa que no se truncó la solicitud. |
| `bh` | Ninguna | Altura del explorador (en píxeles). Se utiliza en la dimensión [[!UICONTROL Altura del explorador]](/help/components/dimensions/browser-height.md). |
| `bw` | Ninguna | Anchura del explorador (en píxeles). Se utiliza en la dimensión [[!UICONTROL Anchura del explorador]](/help/components/dimensions/browser-width.md). |
| `c` | Ninguna | Calidad de color (en bits). Se utiliza en la dimensión [[!UICONTROL Profundidad de color]](/help/components/dimensions/color-depth.md). |
| `c.` | [`contextData`](../vars/page-vars/contextdata.md) | Indica el inicio de las variables de datos de contexto. Nunca contiene un valor. |
| `.c` | [`contextData`](../vars/page-vars/contextdata.md) | Indica el final de las variables de datos de contexto. Nunca contiene un valor. |
| `c1` - `c75` | [`prop1` - `prop75`](../vars/page-vars/prop.md) | [Props](/help/components/dimensions/prop.md) o variables de tráfico personalizadas. |
| `cc` | [`currencyCode`](../vars/config-vars/currencycode.md) | El tipo de moneda usado en la visita. |
| `cdp` | [`cookieDomainPeriods`](../vars/config-vars/configuration-variables.md#retired-configuration-variables) | **Ya no se usa.** Número de puntos de un dominio. |
| `ce` | [`charSet`](../vars/config-vars/charset.md) | La codificación de caracteres de la solicitud de imagen. |
| `cl` | [`cookieLifetime`](../vars/config-vars/cookielifetime.md) | La duración de la cookie del visitante. |
| `ch` | [`channel`](../vars/page-vars/channel.md) | Se utiliza en la dimensión [[!UICONTROL Secciones del sitio]](/help/components/dimensions/site-section.md). |
| `cp` | [`customerPerspective`](../vars/page-vars/customerperspective.md) | Especifica si se produjo una visita de una aplicación móvil mientras la aplicación estaba en primer o segundo plano. Se utiliza en la dimensión [[!UICONTROL Tipo de visita]](/help/components/dimensions/hit-type.md). |
| `ct` | Ninguno | Se utiliza en la dimensión [[!UICONTROL Tipo de conexión]](/help/components/dimensions/connection-type.md). |
| `D` | [`dynamicVariablePrefix`](../vars/config-vars/dynamicvariableprefix.md) | Indica lo que se debe utilizar para variables dinámicas. |
| `ev` | [`events`](../vars/page-vars/events/events-overview.md) | Abreviatura del parámetro `events`. |
| `events` | [`events`](../vars/page-vars/events/events-overview.md) | Lista de eventos de la página separados por comas. Utilizado por la mayoría de las [métricas](/help/components/metrics/overview.md). |
| `g` | [`pageURL`](../vars/page-vars/pageurl.md) | Dirección URL actual de la página, hasta 255 bytes. Se utiliza en la dimensión [[!UICONTROL URL de la página]](/help/components/dimensions/page-url.md). |
| `-g` | [`pageURL`](../vars/page-vars/pageurl.md) | Las direcciones URL superiores a 255 bytes se dividen. Los primeros 255 bytes aparecen en el parámetro `g` y todos los bytes restantes aparecen en el parámetro `-g`. |
| `gn` | [`pageName`](../vars/page-vars/pagename.md) | Abreviatura del parámetro `pageName`. |
| `gt` | [`pageType`](../vars/page-vars/pagetype.md) | Abreviatura del parámetro `pageType`. |
| `h.` | [`collectHighEntropyUserAgentHints`](../vars/config-vars/collecthighentropyuseragenthints.md) | Prefijo de varias variables que representan las [sugerencias del cliente](/help/technotes/client-hints.md). |
| `h1` - `h5` | [`hier1` - `hier5`](../vars/page-vars/page-variables.md#retired-page-variables) | **Ya no se usa.** Dimensiones de jerarquía. |
| `hp` | Ninguna | **Ya no se usa.** En versiones anteriores de Adobe Analytics, se determinó si la dirección URL actual era la página principal del explorador. |
| `j` | Ninguna | **Ya no se usa.** Versión de JavaScript instalada en el explorador. |
| `k` | Ninguna | Utilizada en la dimensión [[!UICONTROL Compatibilidad con cookies]](/help/components/dimensions/cookie-support.md). |
| `l1` - `l3` | [`list1` - `list3`](../vars/page-vars/list.md) | Variables de lista. |
| `lat` | Ninguna | **Ya no se usa.** Latitud. Configurado por implementaciones de SDK móvil heredadas; las implementaciones móviles actuales envían geolocalización a través de flujos de datos. |
| `lon` | Ninguno | **Ya no se usa.** Longitud. Configurado por implementaciones de SDK móvil heredadas; las implementaciones móviles actuales envían geolocalización a través de flujos de datos. |
| `lrt` | Ninguno | El &quot;último tiempo de solicitud&quot;, que es el tiempo de ida y vuelta de la última solicitud, en milisegundos. Solo se envía cuando se envía más de una solicitud desde una sola página, como en una aplicación de una sola página (SPA). |
| `mcorgid` | Ninguno | El ID de organización de IMS, que identifica la organización en el servicio de ID de visitante. |
| `mid` | Ninguno | Se utiliza en la dimensión [[!UICONTROL ID de visitante de Experience Cloud]](/help/components/dimensions/experience-cloud-visitor-id.md). |
| `ms_a` | Ninguno | Establecido por Media SDK en `1` cuando los medios de streaming rastreados son audio en lugar de vídeo. |
| `ndh` | Ninguno | Añadido por AppMeasurement a cada solicitud de imagen que genera. Dado que las solicitudes codificadas generalmente lo omiten, su presencia indica que la visita procede de AppMeasurement. |
| `ns` | [`visitorNameSpace`](../vars/config-vars/configuration-variables.md#retired-configuration-variables) | **Ya no se usa.** Ayuda a determinar dónde se configuran las cookies. |
| `oi` | Ninguno | **Ya no se usa.** Instancia de objeto de la última página. Se utiliza en versiones anteriores de Activity Map. |
| `oid` | [`s_objectID`](../vars/page-vars/s-objectid.md) | Identificador de objeto de la última página. Se utiliza en la versión actual de Activity Map. |
| `oidt` | Ninguno | **Ya no se usa.** Tipo de identificador de objeto de la última página. Se utiliza en versiones anteriores de Activity Map. |
| `ot` | Ninguna | **Ya no se usa.** Nombre del objeto de la última página. Se utiliza en versiones anteriores de Activity Map. |
| `p` | Ninguna | **Ya no se usa.** Lista de complementos utilizados en el explorador. |
| `pageName` | [`pageName`](../vars/page-vars/pagename.md) | Se utiliza en la dimensión [[!UICONTROL Página]](/help/components/dimensions/page.md). |
| `pageType` | [`pageType`](../vars/page-vars/pagetype.md) | Se utiliza en la dimensión [[!UICONTROL Páginas no encontradas]](/help/components/dimensions/pages-not-found.md). |
| `pccr` | Ninguna | Indicador de redirección de comprobación de cookies persistentes. Establecido por los servidores de recopilación de datos de Adobe para los nuevos visitantes y siempre establecido en `true`. Cuando se desconoce la compatibilidad con cookies de un nuevo visitante, el servidor de recopilación de datos redirige la solicitud de imagen a sí mismo con este indicador para confirmar que ya se ha producido la comprobación de cookies persistentes. Este parámetro evita las redirecciones infinitas si el visitante rechaza las cookies. |
| `pe` | [`tl()`](../vars/functions/tl-method.md) | Determina el tipo de visita. Los valores válidos incluyen `lnk_o` ([[!UICONTROL vínculo personalizado]](/help/components/dimensions/custom-link.md)), `lnk_d` ([[!UICONTROL vínculo de descarga]](/help/components/dimensions/download-link.md)), `lnk_e` ([[!UICONTROL vínculo de salida]](/help/components/dimensions/exit-link.md)) y `tnt` (una visita de Analytics para Target). |
| `pev1` | [`linkURL`](../vars/config-vars/linkurl.md) | Dirección URL en la que se produjo el vínculo personalizado. |
| `pev2` | [`tl()`](../vars/functions/tl-method.md) | Nombre descriptivo del [vínculo personalizado](/help/components/dimensions/custom-link.md). |
| `pev3` | Ninguno | **Ya no se usa.** Hitos rastreados en versiones anteriores de informes de vídeo. |
| `pf` | Ninguna | Indicador de plataforma; solo para uso de Adobe. No se debe alterar. |
| `pid` | Ninguna | **Ya no se usa.** Identificador de página de la última página. Se utiliza en versiones anteriores de Activity Map. |
| `pidt` | Ninguna | **Ya no se usa.** Tipo de identificador de página de la última página. Se utiliza en versiones anteriores de Activity Map. |
| `pl` | [`products`](../vars/page-vars/products.md) | Abreviatura del parámetro `products`. |
| `products` | [`products`](../vars/page-vars/products.md) | Variable Products. Se utiliza en las dimensiones [[!UICONTROL Producto]](/help/components/dimensions/product.md) y [[!UICONTROL Categoría]](/help/components/dimensions/category.md). |
| `purchaseID` | [`purchaseID`](../vars/page-vars/purchaseid.md) | Se utiliza en la dimensión [[!UICONTROL ID de compra]](/help/components/dimensions/purchase-id.md). |
| `r` | [`referrer`](../vars/page-vars/referrer.md) | URL de referencia de la visita. Se utiliza en dimensiones de fuentes de tráfico como [[!UICONTROL Referente]](/help/components/dimensions/referrer.md) y [[!UICONTROL Dominio de referencia]](/help/components/dimensions/referring-domain.md). |
| `s` | Ninguno | Resolución de pantalla, en `width x height`. Se utiliza en la dimensión [[!UICONTROL Resoluciones del monitor]](/help/components/dimensions/monitor-resolution.md). |
| `sdid` | Ninguno | ID de datos suplementario. Vincula varias visitas que describen el mismo evento, como las visitas de Analytics y Target en una integración de [Analytics for Target](https://experienceleague.adobe.com/en/docs/target/using/integrate/a4t/a4t.html). |
| `server` | [`server`](../vars/page-vars/server.md) | Utilizado en la dimensión [[!UICONTROL Servidor]](/help/components/dimensions/server.md). |
| `sv` | [`server`](../vars/page-vars/server.md) | Abreviatura del parámetro `server`. |
| `state` | [`state`](../vars/page-vars/page-variables.md#retired-page-variables) | **Ya no se usa.** Se registra el estado de EE. UU. en el que entró un visitante, generalmente a través de un formulario de envío o facturación. |
| `t` | Ninguna | Fecha y hora generadas de la visita. Utiliza el formato `dd/mm/yyyy hh:mm:ss w o`.<br>- `dd/mm/yyyy hh:mm:ss` es fecha/hora en JavaScript. El mes `0` es enero, mientras que el mes `11` es diciembre.<br>- `w` es el día de la semana. `0` es domingo, mientras que `6` es sábado.<br>- `o` es el horario GMT negativo en minutos. Por ejemplo, `420` es GMT-7. |
| `tnt` | Ninguno | Carga útil de datos de destino usada en integraciones de [Analytics for Target](https://experienceleague.adobe.com/en/docs/target/using/integrate/a4t/a4t.html). Se envió cuando `pe=tnt`. |
| `ts` | [`timestamp`](../vars/page-vars/timestamp.md) | Marca de hora personalizada establecida con la visita. Se suele usar para el seguimiento sin conexión. |
| `u` | Ninguna | **Ya no se usa.** Marcador de cuenta utilizado en versiones anteriores de Activity Map. |
| `v` | Ninguna | Se utiliza en la dimensión [[!UICONTROL Java Enabled]](/help/components/dimensions/java-enabled.md). |
| `v0` | [`campaign`](../vars/page-vars/campaign.md) | Se utiliza en la dimensión [[!UICONTROL Código de seguimiento]](/help/components/dimensions/tracking-code.md). |
| `v1` - `v250` | [`evar1` - `eVar250`](../vars/page-vars/evar.md) | [eVars](/help/components/dimensions/evar.md) o dimensiones de conversión personalizadas. |
| `vid` | [`visitorID`](../vars/config-vars/visitorid.md) | Variable de anulación de ID de visitante. |
| `vidn` | Ninguno | Establecido por los servidores de recopilación de datos de Adobe para los nuevos visitantes, que acompaña al parámetro `pccr` en la solicitud de imagen redirigida. Contiene el valor de ID de visitante almacenado en la cookie de visitante. |
| `vmf` | [`visitorMigrationServer`](../vars/config-vars/configuration-variables.md#retired-configuration-variables) | **Ya no se usa.** Servidor de migración de visitantes utilizado durante la migración de cookies de terceros a cookies de origen. |
| `vmt` | [`visitorMigrationKey`](../vars/config-vars/configuration-variables.md#retired-configuration-variables) | **Ya no se usa.** Clave de migración de visitante, que ayudó a migrar las implementaciones de cookies de terceros a cookies de origen. |
| `vvp` | Ninguno | **Ya no se usa.** Proveedor de variables utilizado en Data Connectors. |
| `xact` | [`transactionID`](../vars/page-vars/transactionid.md) | Se utiliza con las fuentes de datos para enlazar datos en línea y sin conexión. |
| `zip` | [`zip`](../vars/page-vars/zip.md) | Se utiliza en la dimensión [Código postal](/help/components/dimensions/zip-code.md). |

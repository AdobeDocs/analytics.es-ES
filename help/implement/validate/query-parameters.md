---
title: Parámetros de consulta de recopilación de datos
description: Enumera todos los parámetros de cadena de consulta utilizados en solicitudes de imagen.
translation-type: tm+mt
source-git-commit: 2ffa989156dd9bc4f6ef9a216e8c06425cc39440

---


# Parámetros de consulta de recopilación de datos

En la tabla siguiente se muestran todos los parámetros de cadena de consulta que Adobe utiliza en las solicitudes de imagen. Esta información se puede utilizar al depurar con analizadores [de](packet-monitor.md)paquetes, al [codificar solicitudes](../other/hardcoded.md)de imagen o al usar variables [dinámicas](../vars/page-vars/dynamic-variables.md).

| Parámetro | Variable de implementación de Analytics | Descripción |
| --- | --- | --- |
| `aamlh` | Ninguna | Sugerencia de ubicación de Audience Manager. Se utiliza en la integración de perfiles compartidos de Experience Cloud. |
| `aamb` | Ninguna | Blob de Audience Manager. Se utiliza en la integración de perfiles compartidos de Experience Cloud. |
| `aid` | Ninguna | ID de visitante de Analytics. |
| `AQB` | Ninguna | Indica el comienzo de una cadena de consulta de solicitud de imagen. |
| `AQE` | Ninguna | Indica el final de una solicitud de imagen, lo que significa que la solicitud no se truncó. |
| `bh` | Ninguna | Altura del explorador (en píxeles). Se utiliza en la dimensión Altura del explorador. |
| `bw` | Ninguna | Ancho del explorador (en píxeles). Se utiliza en la dimensión Ancho del explorador. |
| `c` | Ninguna | Calidad del color (en bits). Se utiliza en la dimensión Profundidad de color. |
| `c.` | `contextData` | Indica el inicio de las variables de datos de contexto. Nunca contiene un valor. |
| `.c` | `contextData` | Indica el final de las variables de datos de contexto. Nunca contiene un valor. |
| `c1` - `c75` | `prop1` - `prop75` | Variables de tráfico personalizadas. |
| `cc` | `currencyCode` | Tipo de moneda utilizada en la visita. |
| `cdp` | `cookieDomainPeriods` | Número de puntos de un dominio. Se utiliza para ayudar a almacenar las cookies correctamente. |
| `ce` | `charSet` | La codificación de caracteres de la solicitud de imagen. |
| `cl` | `cookieLifetime` | La duración de la cookie del visitante. |
| `ch` | `channel` | Se utiliza en la dimensión Secciones del sitio. |
| `cp` | Ninguna | Se utiliza en la dimensión Tipo de visita individual. |
| `ct` | Ninguna | Se utiliza en la dimensión Tipo de conexión. |
| `D` | `dynamicVariablePrefix` | Indica lo que se debe utilizar para variables dinámicas. |
| `ev` | `events` | Abreviatura de la cadena de `events` consulta. |
| `events` | `events` | Lista de eventos de la página separados por comas. |
| `g` | `pageURL` | URL actual de la página., hasta 255 bytes. |
| `-g` | `pageURL` | Las direcciones URL superiores a 255 bytes se dividen. Los primeros 255 bytes aparecen en el `g` parámetro y todos los bytes restantes aparecen en el `-g` parámetro. |
| `gn` | `pageName` | Abreviatura de la cadena de `pageName` consulta. |
| `gt` | `pageType` | Abreviatura de la cadena de `pageType` consulta. |
| `h1` - `h5` | `hier1` - `hier5` | Variables de jerarquía. |
| `hp` | Ninguna | Ya no se utiliza. En versiones anteriores de Adobe Analytics, se determinó si la dirección URL actual era la página principal del explorador. |
| `j` | Ninguna | Versión de JavaScript instalada en el explorador. |
| `k` | Ninguna | Se utiliza en la dimensión Compatibilidad con cookies. |
| `l1` - `l3` | `list1` - `list3` | Mostrar variables. |
| `mid` | Ninguna | ID de visitante de Experience Cloud. |
| `ndh` | Ninguna | Marca que indica si la solicitud de imagen se originó en AppMeasurement. |
| `ns` | `visitorNameSpace` | Ayuda a determinar dónde se configuran las cookies. |
| `oid` | `objectID` | Identificador de objeto de la última página. Se utiliza en Activity Map. |
| `ot` | Ninguna | Nombre del objeto de la última página. Se utiliza en versiones anteriores de Activity Map. |
| `p` | Ninguna | Ya no se utiliza. Lista de complementos utilizados en el explorador. |
| `pageName` | `pageName` | Se utiliza en la dimensión Página. |
| `pageType` | `pageType` | Se utiliza en la dimensión Páginas no encontradas. |
| `pccr` | Ninguna | Solo se configura para visitantes nuevos y siempre se establece en `true`. Evita redirecciones infinitas. |
| `pe` | `linkType` | Determina el tipo de vínculo personalizado. |
| `pev1` | Ninguna | Dirección URL en la que se produjo el vínculo personalizado. |
| `pev2` | Ninguna | Nombre descriptivo del vínculo personalizado. |
| `pev3` | Ninguna | Ya no se utiliza. Hitos rastreados en versiones anteriores de informes de vídeo. |
| `pf` | Ninguna | Indicador de plataforma; solo para uso de Adobe. No se debe alterar. |
| `pid` | Ninguna | Identificador de página de la última página. Se utiliza en versiones anteriores de Activity Map. |
| `pidt` | Ninguna | Tipo de identificador de página de la última página. Se utiliza en versiones anteriores de Activity Map. |
| `pl` | `products` | Abreviatura de la cadena de `products` consulta. |
| `products` | `products` | Variable Products. |
| `purchaseID` | `purchaseID` | Se utiliza para anular la duplicación de compras. |
| `r` | `referrer` | Dirección URL de referencia de la visita. |
| `s` | Ninguna | Se utiliza en la dimensión Resoluciones del monitor. Resolución de pantalla, en `width x height`. |
| `server` | `server` | Dimensión de servidor. |
| `sv` | `server` | Abreviatura de la cadena de `server` consulta. |
| `state` | `state` | Dimensión de estado. |
| `t` | Ninguna | Fecha y hora generadas de la visita. Utiliza el formato `dd/mm/yyyy hh:mm:ss w o`.<br>- `dd/mm/yyyy hh:mm:ss` es fecha y hora en JavaScript. El mes `0` es enero, mientras que el mes `11` es diciembre.<br>- `w` es el día de la semana. `0` es domingo, mientras que `6` es sábado.<br>- `o` es el desplazamiento negativo GMT en minutos. Por ejemplo, `420` es GMT-7. |
| `ts` | `timestamp` | Marca de hora personalizada establecida con la visita. Se suele usar para el seguimiento sin conexión. |
| `v` | Ninguna | Se utiliza en la dimensión Java Enabled. |
| `v0` | `campaign` | Dimensión Código de seguimiento. |
| `v1` - `v250` | `evar1` - `eVar250` | Dimensiones de conversión personalizadas. |
| `vid` | `visitorID` | Variable de ID de visitante. |
| `vmk` | `vmk` | Ya no se utiliza. Se ha ayudado a migrar de cookies de terceros a cookies de origen. |
| `vvp` | `variableProvider` | Se utiliza en Conectores de datos. |
| `xact` | `transactionID` | Se utiliza con las fuentes de datos para vincular los datos. |
| `zip` | `zip` | Se utiliza en la dimensión Código postal. |

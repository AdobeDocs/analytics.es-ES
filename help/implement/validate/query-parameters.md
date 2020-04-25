---
title: Parámetros de consulta de recopilación de datos
description: Enumera todos los parámetros de cadena de consulta utilizados en solicitudes de imagen.
translation-type: tm+mt
source-git-commit: 2ffa989156dd9bc4f6ef9a216e8c06425cc39440

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
| `bh` | Ninguna | Altura del explorador (en píxeles). Se utiliza en la dimensión Altura del explorador. |
| `bw` | Ninguna | Anchura del explorador (en píxeles). Se utiliza en la dimensión Ancho del explorador. |
| `c` | Ninguna | Calidad de color (en bits). Se utiliza en la dimensión Profundidad de color. |
| `c.` | `contextData` | Indica el inicio de las variables de datos de contexto. Nunca contiene un valor. |
| `.c` | `contextData` | Indica el final de las variables de datos de contexto. Nunca contiene un valor. |
| `c1` - `c75` | `prop1` - `prop75` | Variables de tráfico personalizadas. |
| `cc` | `currencyCode` | El tipo de moneda usado en la visita. |
| `cdp` | `cookieDomainPeriods` | Número de puntos de un dominio. Se utiliza para ayudar a almacenar las cookies correctamente. |
| `ce` | `charSet` | La codificación de caracteres de la solicitud de imagen. |
| `cl` | `cookieLifetime` | La duración de la cookie del visitante. |
| `ch` | `channel` | Se utiliza en la dimensión Secciones del sitio. |
| `cp` | Ninguna | Se utiliza en la dimensión Tipo de visita. |
| `ct` | Ninguna | Se utiliza en la dimensión Tipo de conexión. |
| `D` | `dynamicVariablePrefix` | Indica lo que se debe utilizar para variables dinámicas. |
| `ev` | `events` | Abreviatura de la cadena de consulta `events`. |
| `events` | `events` | Lista de eventos de la página separados por comas. |
| `g` | `pageURL` | URL actual de la página., hasta 255 bytes. |
| `-g` | `pageURL` | Las direcciones URL superiores a 255 bytes se dividen. Los primeros 255 bytes aparecen en el parámetro `g` y todos los bytes restantes aparecen en el parámetro `-g`. |
| `gn` | `pageName` | Abreviatura de la cadena de consulta `pageName`. |
| `gt` | `pageType` | Abreviatura de la cadena de consulta `pageType`. |
| `h1` - `h5` | `hier1` - `hier5` | Variables de jerarquía. |
| `hp` | Ninguna | Ya no se utiliza. En versiones anteriores de Adobe Analytics, se determinó si la dirección URL actual era la página principal del explorador. |
| `j` | Ninguna | Versión de JavaScript instalada en el explorador. |
| `k` | Ninguna | Utilizada en la dimensión Compatibilidad con cookies. |
| `l1` - `l3` | `list1` - `list3` | Variables de lista. |
| `mid` | Ninguna | ID de visitante de Experience Cloud. |
| `ndh` | Ninguna | Marca que indica si la solicitud de imagen se originó en AppMeasurement. |
| `ns` | `visitorNameSpace` | Ayuda a determinar dónde se configuran las cookies. |
| `oid` | `objectID` | Identificador de objeto de la última página. Se utiliza en Activity Map. |
| `ot` | Ninguna | Nombre del objeto de la última página. Se utiliza en versiones anteriores de Activity Map. |
| `p` | Ninguna | Ya no se utiliza. Lista de complementos utilizados en el explorador. |
| `pageName` | `pageName` | Se utiliza en la dimensión Página. |
| `pageType` | `pageType` | Se utiliza en la dimensión Páginas no encontradas. |
| `pccr` | Ninguna | Solo se configura para visitantes nuevos y siempre se establece como `true`. Evita redirecciones infinitas. |
| `pe` | `linkType` | Determina el tipo de vínculo personalizado. |
| `pev1` | Ninguna | Dirección URL en la que se produjo el vínculo personalizado. |
| `pev2` | Ninguna | Nombre reconocible del vínculo personalizado. |
| `pev3` | Ninguna | Ya no se utiliza. Hitos rastreados en versiones anteriores de informes de vídeo. |
| `pf` | Ninguna | Indicador de plataforma; solo para uso de Adobe. No se debe alterar. |
| `pid` | Ninguna | Identificador de página de la última página. Se utiliza en versiones anteriores de Activity Map. |
| `pidt` | Ninguna | Tipo de identificador de página de la última página. Se utiliza en versiones anteriores de Activity Map. |
| `pl` | `products` | Abreviatura de la cadena de consulta `products`. |
| `products` | `products` | Variable Products. |
| `purchaseID` | `purchaseID` | Se utiliza para la deduplicación de compras. |
| `r` | `referrer` | URL de referencia de la visita. |
| `s` | Ninguna | Se utiliza en la dimensión Resoluciones del monitor. Resolución de pantalla, en `width x height`. |
| `server` | `server` | Dimensión de servidor. |
| `sv` | `server` | Abreviatura de la cadena de consulta `server`. |
| `state` | `state` | Dimensión de estado. |
| `t` | Ninguna | Fecha y hora generadas de la visita. Utiliza el formato `dd/mm/yyyy hh:mm:ss w o`.<br>- `dd/mm/yyyy hh:mm:ss` es el formato de fecha y hora en JavaScript. El mes `0` es enero, mientras que el mes `11` es diciembre.<br>- `w` es el día de la semana. `0` es domingo, mientras que `6` es sábado.<br>- `o` es el desplazamiento negativo GMT en minutos. Por ejemplo, `420` es GMT-7. |
| `ts` | `timestamp` | Marca de hora personalizada establecida con la visita. Se suele usar para el seguimiento sin conexión. |
| `v` | Ninguna | Se utiliza en la dimensión Java Enabled. |
| `v0` | `campaign` | Dimensión Código de seguimiento. |
| `v1` - `v250` | `evar1` - `eVar250` | Dimensiones de conversión personalizadas. |
| `vid` | `visitorID` | Variable de ID de visitante. |
| `vmk` | `vmk` | Ya no se utiliza. Se ha ayudado a migrar de cookies de terceros a cookies de origen. |
| `vvp` | `variableProvider` | Se utiliza en Data Connectors. |
| `xact` | `transactionID` | Se utiliza con las fuentes de datos para vincular los datos. |
| `zip` | `zip` | Se utiliza en la dimensión Código postal. |

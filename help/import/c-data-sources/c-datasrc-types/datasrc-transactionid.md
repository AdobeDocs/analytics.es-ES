---
title: Fuentes de datos de ID de transacción
description: Obtenga información sobre el flujo de trabajo general del uso de fuentes de datos con ID de transacción.
feature: Data Sources
exl-id: 5f26b15c-8d9c-46d5-860f-13fdfa21af2e
source-git-commit: 79294cfc6f86e5a41a39504099cd730f53668725
workflow-type: tm+mt
source-wordcount: '531'
ht-degree: 45%

---

# Fuentes de datos de ID de transacción

Las fuentes de datos de ID de transacción le permiten no solo vista de datos en línea y sin conexión en paralelo, sino también enlazar datos. Requiere el uso de la variable [`transactionID`](/help/implement/vars/page-vars/transactionid.md) en la implementación de Analytics.

Cuando envía una visita en línea que contiene un valor de `transactionID`, Adobe toma una &quot;instantánea&quot; de todas las variables configuradas o persistentes en ese momento. Si se detecta un ID de transacción coincidente cargado a través de fuentes de datos, los datos sin conexión y en línea se vinculan.

Para utilizar transacciones, la visita en línea con un ID de transacción debe haberse enviado y procesado antes de que se envíen los datos de la fuente de datos de transacción con ese ID de transacción. La visita en línea contiene variables (eVars, etc.), pero no eventos, que estaban en la visita en línea guardada con la información del ID de transacción.

Cuando se envía una visita de la fuente de datos de transacción, el ID de transacción de la visita de la transacción de la fuente de datos busca las variables, etc. (no eventos) que estaban asociados con la visita en línea original con ese ID de transacción. Utiliza esas variables en la visita de transacción de la fuente de datos si no hubo ningún valor para una variable pasada en la visita de transacción de la fuente de datos.

## Ejemplo

Si se pasa una visita en línea con el ID de transacción 1256 `evar1=blue`, `evar2=water` y `event1` están configuradas, los datos de transacción del ID de transacción 1256 se guardan con `evar1=blue`, `evar2=water`. No se guarda ningún valor de evento como parte de la información de transacción.

Ahora supongamos que se pasa una visita de transacción de fuente de datos a través del sistema con el ID de transacción 1256 y `evar1=yellow`, `evar3=mountain` y `event2` configurado. El sistema encuentra los datos de transacción guardados y en los conjuntos de visitas de transacción de la fuente de datos `evar2=water` (ya que eso es lo que se estableció en la visita original). No está configurado `evar1=blue` (como en la visita original) porque había un valor para `evar1` (amarillo) ya establecido en la visita de transacción de la fuente de datos.  Por lo tanto, la visita de la transacción de la fuente de datos resulta en tener `evar1=yellow`, `evar2=water` (de la visita en línea original) y `evar3=mountain`. Estos 3 valores de eVar tienen `event2` set : el evento de la visita de transacción de la fuente de datos.

No se obtiene ningún valor de la transacción de origen de datos `event1` se establece cuando se procesa la visita de transacción de origen de datos.

## Flujo de trabajo general de las fuentes de datos de ID de transacción

Utilice el siguiente flujo de trabajo genérico para empezar a usar fuentes de datos de ID de transacción:

1. Cree una fuente de datos (categoría &#39;Genérica&#39; y tipo &#39;Fuente de datos genérica [ID de transacción]&#39;).
1. Siga el asistente de configuración de la fuente de datos para obtener una ubicación de FTP, cargar datos y descargar un archivo de plantilla de fuentes de datos.
1. Actualice la implementación para incluir la variable `transactionID`.
1. Cargue un archivo de fuentes de datos en el sitio FTP con un archivo `.fin`.

## Archivo de carga y código de implementación de ejemplo

Si cargara el siguiente archivo de fuentes de datos e implementara el siguiente código en su sitio, vería los datos vinculados en el sistema de informes. El archivo de fuentes de datos utiliza eVar1 y event1, mientras que la implementación en línea utiliza eVar2 y event2. Dado que la ID de transacción coincide, puede ver datos de event2 para eVar1 y datos de event1 para eVar2.

### Archivo de ejemplo

Descargue la plantilla, actualice los valores y, a continuación, cárguela en la ubicación FTP de las fuentes de datos:

| `#` | `Example eVar1 name` | `Example event 1 name` | `1` |
|---|---|---|---|
| `Date` | `Evar 1` | `Event 1` | `transactionID` |
| `01/01/2020/12/00/00` | `Example eVar1 value` | `1` | `1234` |

### Código de implementación de ejemplo

Para obtener una explicación más detallada sobre el ID de transacción, consulte [`transactionID`](/help/implement/vars/page-vars/transactionid.md) en la guía de usuario de implementación.

```js
var s = s_gi("examplersid");
s.eVar2 = "Example eVar2 value";
s.events = "event2";
s.transactionID = "1234";
s.t();
```

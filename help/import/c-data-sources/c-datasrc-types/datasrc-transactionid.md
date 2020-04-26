---
title: Fuentes de datos de ID de transacción
description: Obtenga información sobre el flujo de trabajo general de uso de fuentes de datos de ID de transacción.
translation-type: tm+mt
source-git-commit: c6f84f470dcf97f49ce7dc9d2c5dd8c65cc6cf67

---


# Fuentes de datos de ID de transacción

Las fuentes de datos de ID de transacción le permiten no sólo vista de datos en línea y sin conexión en paralelo, sino también enlazar los datos. Requiere el uso de la [`transactionID`](/help/implement/vars/page-vars/transactionid.md) variable en la implementación de Analytics.

Cuando envía una visita en línea que contiene un `transactionID` valor, Adobe toma una &quot;instantánea&quot; de todas las variables configuradas o persistentes en ese momento. Si se encuentra un ID de transacción coincidente cargado a través de fuentes de datos, los datos sin conexión y en línea se vinculan. No importa qué fuente de datos se vea primero.

## Flujo de trabajo general de las fuentes de datos de ID de transacción

Utilice el siguiente flujo de trabajo genérico para realizar inicios mediante fuentes de datos de ID de transacción:

1. Cree una fuente de datos (categoría &#39;genérica&#39; y tipo &#39;Fuente de datos genérica (ID de transacción)&#39;).
1. Siga el asistente para la configuración de fuentes de datos para obtener una ubicación de FTP para cargar datos y descargar un archivo de plantilla de fuentes de datos.
1. Actualice la implementación para incluir la `transactionID` variable.
1. Cargue un archivo de fuentes de datos en el sitio FTP con un `.fin` archivo.

## Ejemplo de archivo de carga y código de implementación

Si cargara el siguiente archivo de fuentes de datos e implementara el siguiente código en su sitio, vería los datos vinculados en sistema de informes. El archivo de fuentes de datos utiliza eVar1 y evento1, mientras que la implementación en línea utiliza eVar2 y evento2. Dado que la ID de transacción coincide, puede ver datos de evento2 para eVar1 y datos de evento1 para eVar2.

### Archivo de ejemplo

Descargue la plantilla, actualice los valores y, a continuación, cárguela en la ubicación FTP de los orígenes de datos:

| `#` | `Example eVar1 name` | `Example event 1 name` | `1` |
|---|---|---|---|
| `Date` | `Evar 1` | `Event 1` | `transactionID` |
| `01/01/2020/12/00/00` | `Example eVar1 value` | `1` | `1234` |

### Ejemplo de código de implementación

Para obtener una explicación más detallada sobre el ID de transacción, consulte [`transactionID`](/help/implement/vars/page-vars/transactionid.md) En la guía de usuario Implementación.

```js
var s = s_gi("examplersid");
s.eVar2 = "Example eVar2 value";
s.events = "event2";
s.transactionID = "1234";
s.t();
```

---
title: Fuentes de datos de ID de transacción
description: Obtenga información sobre el flujo de trabajo general del uso de fuentes de datos con ID de transacción.
exl-id: 5f26b15c-8d9c-46d5-860f-13fdfa21af2e
source-git-commit: 1ee6a1e69a277f0d3c0ffd1defca0d4cb098cc6c
workflow-type: tm+mt
source-wordcount: '270'
ht-degree: 92%

---

# Fuentes de datos de ID de transacción

Las fuentes de datos de ID de transacción le permiten no solo vista de datos en línea y sin conexión en paralelo, sino también enlazar datos. Requiere el uso de la variable [`transactionID`](/help/implement/vars/page-vars/transactionid.md) en la implementación de Analytics.

Cuando envía una visita en línea que contiene un valor de `transactionID`, Adobe toma una &quot;instantánea&quot; de todas las variables configuradas o persistentes en ese momento. Si se detecta un ID de transacción coincidente cargado a través de fuentes de datos, los datos sin conexión y en línea se vinculan. No importa qué fuente de datos se vea primero.

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

---
title: Fuentes de datos de ID de transacción
description: Obtenga información sobre el flujo de trabajo general del uso de fuentes de datos con ID de transacción.
feature: Data Sources
exl-id: 5f26b15c-8d9c-46d5-860f-13fdfa21af2e
source-git-commit: 54c88a275b48f2b401be450ce35767ab3ea9d40b
workflow-type: tm+mt
source-wordcount: '426'
ht-degree: 10%

---

# Fuentes de datos de ID de transacción

Las fuentes de datos del ID de transacción son una variación en las fuentes de datos de resumen que le permiten enlazar datos en línea y sin conexión. Requiere el uso de la variable [`transactionID`](/help/implement/vars/page-vars/transactionid.md) en la implementación de Analytics.

* Si una fila de un archivo de fuentes de datos incluye un ID de transacción que coincide con un ID de transacción ya recopilado por AppMeasurement, las dimensiones y métricas se añaden a la visita en línea.
* Si una fila de un archivo de fuente de datos incluye un ID de transacción que no contiene una coincidencia, la fila se trata de manera similar a las fuentes de datos de resumen.

>[!NOTE]
>
>Antes de usar fuentes de datos de ID de transacción, primero debe activarlo en [Configuración general de la cuenta](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/general-acct-settings-admin.md) para el grupo de informes deseado.

Cuando envía una visita en línea que contiene un [`transactionID`](/help/implement/vars/page-vars/transactionid.md) Adobe toma una &quot;instantánea&quot; de todas las variables configuradas o persistentes en ese momento. Si se encuentra un ID de transacción coincidente cargado a través de fuentes de datos, los datos sin conexión y en línea se vinculan.

Las fuentes de datos de ID de transacción tienen las siguientes propiedades:

* Los datos en línea deben recopilarse y procesarse primero. Si se carga una fuente de datos del ID de transacción antes de que un grupo de informes procese una visita que coincida con ese ID de transacción, los datos no se vinculan.
* Los ID de transacción recopilados mediante AppMeasurement caducan al cabo de aproximadamente 90 días. Si su organización necesita una ventana de ID de transacción más larga, póngase en contacto con el Servicio de atención al cliente de Adobe.
* Las fuentes de datos cargadas con un ID de transacción caducado se tratan de forma similar a los datos cargados sin un ID de transacción.
* Si se incluye la misma variable tanto en la visita en línea como en la fuente de datos del ID de transacción, se utiliza el valor de la fuente de datos del ID de transacción.
* Si una variable se incluye en una visita en línea pero no en una visita de fuente de datos de ID de transacción coincidente, se conserva la variable de visita en línea.
* Si establece el mismo ID de transacción en varias visitas en línea, solo la primera incidencia se verá alterada con los datos de una fuente de datos del ID de transacción coincidente.
* Si establece el mismo ID de transacción en varias filas de fuentes de datos para las mismas dimensiones, se utilizará el último elemento de dimensión.

Por ejemplo:

1. Envíe una vista de página desde AppMeasurement donde:
   * `eVar1` es igual que `blue`
   * `eVar2` es igual que `water`
   * `events` es igual que `event1`
   * `transactionID` es igual que `1256`
2. Una vez recopilada y procesada la visita, se carga una fuente de datos de ID de transacción en la que:
   * `eVar1` es igual que `yellow`
   * `eVar3` es igual que `bird`
   * `events` es igual que `event2`
   * `transactionID` es igual que `1256`
3. Una vez procesados los orígenes de datos de la visita, se puede ver un informe en el espacio de trabajo. Los datos mostrarían lo siguiente:
   * `eVar1` es igual que `yellow`
   * `eVar2` es igual que `water`
   * `eVar3` es igual que `bird`
   * `events` es igual que `event2`

El valor de eVar1 `blue` y `event1` no están presentes en los informes, ya que la visita del ID de transacción sobrescribió esos valores respectivos.

---
title: Fuentes de datos de ID de transacción
description: Obtenga información sobre el flujo de trabajo general del uso de fuentes de datos con ID de transacción.
feature: Data Sources
exl-id: 5f26b15c-8d9c-46d5-860f-13fdfa21af2e
role: Admin
source-git-commit: 27bcbd638848650c842ad8d8aaa7ab59e27e900e
workflow-type: tm+mt
source-wordcount: '427'
ht-degree: 7%

---

# Fuentes de datos de ID de transacción

Las fuentes de datos del ID de transacción son una variación de las fuentes de datos de resumen que le permiten enlazar datos en línea y sin conexión. Requiere el uso de la variable [`transactionID`](/help/implement/vars/page-vars/transactionid.md) en la implementación de Analytics.

* Si una fila de un archivo de fuente de datos incluye un ID de transacción que coincide con un ID de transacción ya recopilado por el AppMeasurement, las dimensiones y métricas se anexan a la visita en línea.
* Si una fila de un archivo de fuente de datos incluye un ID de transacción que no coincide, la fila se tratará de manera similar a las fuentes de datos de resumen.

>[!NOTE]
>
>Antes de usar las fuentes de datos del ID de transacción, primero debe habilitarlo en [Configuración general de cuenta](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/general-acct-settings-admin.md) para el grupo de informes deseado.

Cuando envía una visita en línea que contiene un valor de [`transactionID`](/help/implement/vars/page-vars/transactionid.md), el Adobe toma una &quot;instantánea&quot; de todas las variables configuradas o persistentes en ese momento. Si se encuentra un ID de transacción coincidente cargado a través de fuentes de datos, los datos sin conexión y en línea se vinculan.

Las fuentes de datos del ID de transacción tienen las siguientes propiedades:

* Los datos en línea deben ser recopilados y procesados primero. Si se carga una fuente de datos de ID de transacción antes de que un grupo de informes procese una visita que coincida con ese ID de transacción, los datos no se vinculan.
* Los ID de transacción recopilados mediante AppMeasurement caducan después de aproximadamente 90 días. Si su organización necesita una ventana de ID de transacción más larga, póngase en contacto con el Servicio de atención al cliente de Adobe.
* Las fuentes de datos cargadas con un ID de transacción caducado se tratan de manera similar a los datos cargados sin un ID de transacción.
* Si la misma variable se incluye en la fuente de datos de visitas en línea y en la fuente de datos del ID de transacción, se utiliza el valor de la fuente de datos del ID de transacción.
* Si una variable se incluye en una visita en línea pero no en una visita de origen de datos de ID de transacción coincidente, se conserva la variable de visita en línea.
* Si establece el mismo ID de transacción en varias visitas en línea, solo la primera incidencia se modifica con los datos de una fuente de datos de ID de transacción coincidente.
* Si establece el mismo ID de transacción en varias filas de fuente de datos para las mismas dimensiones, se utiliza el último elemento de dimensión.

Por ejemplo:

1. Envía una vista de página desde la AppMeasurement donde:
   * `eVar1` es igual a `blue`
   * `eVar2` es igual a `water`
   * `events` es igual a `event1`
   * `transactionID` es igual a `1256`
2. Una vez que se recopila y procesa la visita, se carga una fuente de datos de ID de transacción donde:
   * `eVar1` es igual a `yellow`
   * `eVar3` es igual a `bird`
   * `events` es igual a `event2`
   * `transactionID` es igual a `1256`
3. Una vez procesada la visita de las fuentes de datos, el informe se verá en el espacio de trabajo. Los datos mostrarían lo siguiente:
   * `eVar1` es igual a `yellow`
   * `eVar2` es igual a `water`
   * `eVar3` es igual a `bird`
   * `events` es igual a `event2`

El valor de eVar 1 `blue` y la métrica `event1` no están presentes en los informes, ya que la visita del ID de transacción sobrescribió esos valores respectivos.

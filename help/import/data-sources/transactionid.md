---
title: Fuentes de datos de ID de transacción
description: Utilice los valores almacenados de una visita en línea para enriquecer las visitas sin conexión que compartan un ID de transacción.
feature: Data Sources
exl-id: 5f26b15c-8d9c-46d5-860f-13fdfa21af2e
role: Admin
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '507'
ht-degree: 8%

---

# Fuentes de datos de ID de transacción

Las fuentes de datos del ID de transacción son una variación de las fuentes de datos de resumen que permiten aplicar valores guardados desde una visita en línea a filas sin conexión que comparten el mismo ID de transacción. Este método es útil cuando captura una transacción en línea pero recibe detalles más tarde de otro sistema. Los ejemplos principales incluyen devoluciones de productos, cancelaciones de reservas o resultados de interacciones del centro de llamadas.

>[!NOTE]
>
>Antes de usar las fuentes de datos del ID de transacción, primero debe habilitarlo en [Configuración general de cuenta](/help/admin/tools/manage-rs/edit-settings/general/general-acct-settings-admin.md) para el grupo de informes deseado.

## Funcionamiento

El concepto de ID de transacción consta de dos partes:

* **Visita en línea**: Cualquier visita completa de Analytics enviada a un grupo de informes (AppMeasurement, Web SDK, API, etc.). En esta visita, usted establece la variable de implementación [`transactionID`](/help/implement/vars/page-vars/transactionid.md).
* **Visita sin conexión**: Una fila cargada a través de fuentes de datos. En el archivo, incluya la columna `transactionID` con un valor que coincida con una visita en línea.

Cuando envía una visita en línea que contiene la variable de implementación `transactionID`, Adobe toma una &quot;instantánea&quot; de las siguientes dimensiones que se establecieron o persistieron en ese momento:

* [Categoría](/help/components/dimensions/category.md)
* [Días antes de la primera compra](/help/components/dimensions/days-before-first-purchase.md)
* [Días desde la última compra](/help/components/dimensions/days-since-last-purchase.md)
* [eVars 1-250](/help/components/dimensions/evar.md)
* Dimensiones específicas de características habilitadas en [Configuración del grupo de informes](/help/admin/tools/manage-rs/report-suites-admin.md) que se comportan de manera similar a las eVars. No se incluyen las dimensiones específicas de funciones que se comportan de manera similar a las props.
* [Variables de lista](/help/implement/vars/page-vars/list.md)
* [Canal de marketing](/help/components/dimensions/marketing-channel.md)
* [Detalles del canal de marketing](/help/components/dimensions/marketing-detail.md)
* [Dimensiones móviles](/help/components/dimensions/mobile-dimensions.md)
* [Dominio de referencia original](/help/components/dimensions/original-referring-domain.md)
* [Producto](/help/components/dimensions/product.md)
* [Dominio de referencia](/help/components/dimensions/referring-domain.md)
* [Motor de búsqueda](/help/components/dimensions/search-engine.md)
* [Palabra clave de búsqueda](/help/components/dimensions/search-keyword.md)
* [Código de seguimiento](/help/components/dimensions/tracking-code.md)
* [Número de visita](/help/components/dimensions/visit-number.md)

>[!NOTE]
>
>Las métricas (como [Pedidos](/help/components/metrics/orders.md) o [Eventos personalizados](/help/components/metrics/custom-events.md)) no se incluyen en la &quot;instantánea&quot;.

Cuando se carga una visita sin conexión a través de fuentes de datos que contienen un ID de transacción coincidente, todas las dimensiones disponibles dentro de la &quot;captura de pantalla&quot; se anexan automáticamente a la fila de la fuente de datos. Si una dimensión determinada está presente en la visita en línea y sin conexión, se utiliza el valor de visita sin conexión.

>[!IMPORTANT]
>
>El concepto de fuentes de datos del ID de transacción solo ayuda a rellenar filas de fuentes de datos (visitas sin conexión). No afectan a la visita en línea ni la cambian.

## Consideraciones del origen de datos del ID de transacción

Las fuentes de datos del ID de transacción tienen las siguientes propiedades:

* Los datos en línea deben ser recopilados y procesados primero. Si se carga una fuente de datos de ID de transacción antes de que un grupo de informes procese una visita que coincida con ese ID de transacción, los datos se tratan como una fuente de datos de resumen.
* Los ID de transacción recopilados de las visitas en línea caducan al cabo de 25 meses.
* Las fuentes de datos cargadas con un ID de transacción caducado se tratan de manera similar a los datos cargados sin un ID de transacción.
* Si establece el mismo ID de transacción en varias visitas en línea, solo se utiliza la &quot;captura de pantalla&quot; de la primera incidencia. Las visitas en línea de ID de transacción duplicados posteriores se procesan como si no tuvieran un ID de transacción.
* Una vez que rellene un valor `transactionID` determinado, la &quot;captura de pantalla&quot; asociada se considerará inmutable hasta que caduque el ID de transacción.
* Si establece el mismo ID de transacción en varias filas de fuentes de datos, las dimensiones disponibles de la visita en línea se anexan a cada visita sin conexión. Las visitas sin conexión para el mismo ID de transacción no saben nada entre sí; los datos no se pasan entre visitas sin conexión.

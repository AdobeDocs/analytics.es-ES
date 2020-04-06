---
description: Pasos que puede seguir como preparación para utilizar fuentes de datos
subtopic: Data sources
title: Preparación para el uso de fuentes de datos
topic: Developer and implementation
uuid: 876ea069-574b-4e23-93b7-e3828bfd90f5
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Preparación para el uso de fuentes de datos

Pasos que puede seguir como preparación para utilizar fuentes de datos

* [Identificar las métricas y ponerles nombre](/help/import/c-data-sources/datasrc-preparing.md#section_0D1DA6D7768E4C4CB6E9A2F4639C0135)
* [Identificar las dimensiones de datos](/help/import/c-data-sources/datasrc-preparing.md#section_8EC6BDC4AA314D9EB85F6FCD8E6ABC0A)
* [Código de seguimiento de campaña](/help/import/c-data-sources/datasrc-preparing.md#section_468222796FF449ABAA90D88EB3264CB1)
* [ID de transacción](/help/import/c-data-sources/datasrc-preparing.md#section_D9513C1204B7496C9B738C5B12CCCFC7)
* [Identificar un intervalo de fechas válido para la fuente de datos](/help/import/c-data-sources/datasrc-preparing.md#section_03AAB1291BDC4403BDC50905A78FDB71)

## Identificar las métricas y ponerles nombre {#section_0D1DA6D7768E4C4CB6E9A2F4639C0135}

Es importante entender las métricas y las mediciones que se encuentran en las fuentes de datos, como *`Off-line Sales Revenue by Product`*, *`Returns by Product`* o *`Ad Impressions by Campaign`*. Estos son los nombres que puede asociar con las métricas de informes (eventos, propiedades y eVars).

Después de determinar las asignaciones de métrica a evento adecuadas para los datos de fuentes de datos, cambie el nombre de los eventos por nombres descriptivos adecuados para la métrica de fuentes de datos asociada.

Consulte Eventos [de](https://marketing.adobe.com/resources/help/es_ES/reference/success_event.html) éxito en la Ayuda de las herramientas de administración.

>[!NOTE] Adobe recomienda encarecidamente usar con las fuentes de datos eventos nuevos vacíos, pero en casos excepcionales puede tener sentido usar un evento preexistente.

## Identificar las dimensiones de datos {#section_8EC6BDC4AA314D9EB85F6FCD8E6ABC0A}

Identifique y recopile los datos (informes) que desee utilizar para desglosar las métricas importadas a través de las fuentes de datos. Estos datos se conocen como *`data dimensions`*.

Por ejemplo: si una métrica de fuentes de datos mide las impresiones de publicidad, es probable que la dimensión de datos sea el código de seguimiento de campaña. Si mide las ventas sin conexión, puede que desee utilizar el código de producto (o SKU) como dimensión de datos.

Las métricas se pueden definir con varias dimensiones de datos, pero entonces deben proveer un valor o una combinación de valores pertinentes a cada dimensión de datos asociada. Por ejemplo, si importa una métrica de ventas sin conexión y la asocia con las dimensiones de datos de *`Product`* y *`Partner`*, la métrica de ventas sin conexión tiene que ser pertinente para cada combinación de producto y socio (por ejemplo, ingresos totales).

>[!NOTE] Es posible importar métricas totales que no se puedan desglosar por ninguna dimensión de datos.

Después de definir las dimensiones de datos que se van a utilizar con un origen de datos, asigne los datos de dimensiones a una variable para integrarlos en los informes de marketing. Utilice los informes estándar (por ejemplo, Producto, Código de seguimiento, Palabra clave de búsqueda) o las variables de tráfico de conversión (eVars).

Al utilizar eVars, puede usar eVars existentes o nuevas como dimensiones de datos. Después de seleccionar una eVar para recibir una dimensión de datos de las fuentes de datos, asegúrese de ponerles un nombre adecuado.

Consulte Eventos [de](https://marketing.adobe.com/resources/help/es_ES/reference/success_event.html) éxito en la Ayuda de Analytics.

## Código de seguimiento de campaña {#section_468222796FF449ABAA90D88EB3264CB1}

Además de importar eventos de éxito, puede importar de forma opcional los valores de eVar asociados. Por ejemplo: si realiza un seguimiento de la actividad en línea con un código de seguimiento de Campaña y tiene códigos de seguimiento de Campaña para las métricas sin conexión, puede importar las métricas con códigos de seguimiento de Campaña. Este enfoque le permite realizar vistas de métricas en línea y sin conexión en los informes de Campaña.

Si no importa métricas de fuentes de datos con un valor de eVar asociado, no podrá realizar la vista de métricas de fuentes de datos desglosadas por eVars. En su lugar, solo puede ver las métricas totales.

## ID de transacción {#section_D9513C1204B7496C9B738C5B12CCCFC7}

El ID de transacción se utiliza para conectar un evento en línea a un evento sin conexión.

## Identificar un intervalo de fechas válido para la fuente de datos {#section_03AAB1291BDC4403BDC50905A78FDB71}

Después de definir las métricas de fuentes de datos (Eventos personalizados) y las dimensiones de datos (eVars), revise el intervalo de fechas de los datos de fuentes de datos que desee importar. No se pueden importar fuentes de datos que queden fuera del rango de los datos de sistema de informes existentes.

Por ejemplo: no puede importar datos de la fuente de datos antes de implementar el seguimiento de datos en línea. Los datos de las fuentes de datos deben desglosarse por día.

---
description: Pasos que puede seguir como preparación para utilizar fuentes de datos
subtopic: Data sources
title: Preparación para el uso de fuentes de datos
topic-fix: Developer and implementation
uuid: 876ea069-574b-4e23-93b7-e3828bfd90f5
exl-id: 3cad7c33-f31c-41a2-9dd2-9535713c7620
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '571'
ht-degree: 100%

---

# Preparación para el uso de fuentes de datos

Pasos que puede seguir como preparación para utilizar fuentes de datos

* [Identificar las métricas y ponerles nombre](/help/import/c-data-sources/datasrc-preparing.md#section_0D1DA6D7768E4C4CB6E9A2F4639C0135)
* [Identificar las dimensiones de datos](/help/import/c-data-sources/datasrc-preparing.md#section_8EC6BDC4AA314D9EB85F6FCD8E6ABC0A)
* [Código de seguimiento de campaña](/help/import/c-data-sources/datasrc-preparing.md#section_468222796FF449ABAA90D88EB3264CB1)
* [ID de transacción](/help/import/c-data-sources/datasrc-preparing.md#section_D9513C1204B7496C9B738C5B12CCCFC7)
* [Identificar un intervalo de fechas válido para la fuente de datos](/help/import/c-data-sources/datasrc-preparing.md#section_03AAB1291BDC4403BDC50905A78FDB71)

## Identificar las métricas y ponerles nombre  {#section_0D1DA6D7768E4C4CB6E9A2F4639C0135}

Es importante entender las métricas y las mediciones que se encuentran en las fuentes de datos, como *`Off-line Sales Revenue by Product`*, *`Returns by Product`* o *`Ad Impressions by Campaign`*. Esos son los nombres que se pueden asociar con las métricas de informes (eventos, propiedades y eVars).

Cuando determine la correspondencia entre métricas y eventos para la fuente de datos, cambie los nombres descriptivos de los eventos para que reflejen mejor las métricas asociadas.

Consulte [Eventos de éxito](https://docs.adobe.com/content/help/es-ES/analytics/admin/admin-tools/success-events/success-event.html) en la ayuda de Herramientas de administración.

>[!NOTE]
>
>Adobe recomienda encarecidamente usar con las fuentes de datos eventos nuevos vacíos, pero en casos excepcionales puede tener sentido usar un evento preexistente.

## Identificar las dimensiones de datos {#section_8EC6BDC4AA314D9EB85F6FCD8E6ABC0A}

Los datos (informes) por los que se quieran desglosar las métricas importadas por medio de fuentes de datos se deben identificar y recopilar. Estos datos se conocen como  *`data dimensions`*.

Por ejemplo, si una métrica de fuentes de datos mide la cantidad de impresiones de anuncios, es probable que se use como dimensión de datos el código de seguimiento de la campaña. Si lo que se miden son las ventas sin conexión, tal vez se podría usar como dimensión de datos el código de producto o el SKU.

Las métricas se pueden definir con varias dimensiones de datos, pero entonces deben proveer un valor o una combinación de valores pertinentes a cada dimensión de datos asociada. Por ejemplo, si importa una métrica de ventas sin conexión y la asocia con las dimensiones de datos  de *`Product`* y *`Partner`*, la métrica de ventas sin conexión tiene que ser pertinente para cada combinación de producto y socio (por ejemplo, ingresos totales).

>[!NOTE]
>
>Es posible importar métricas totales que no se puedan desglosar por ninguna dimensión de datos.

Después de definir las dimensiones de datos que se tienen que utilizar con una fuente de datos, asigne los datos de las dimensiones a una variable para integrarlos en los informes de marketing. Utilice informes estándar (por ejemplo, producto, código de seguimiento, palabra clave de búsqueda) o variables de tráfico de conversiones (eVars).

Cuando se usan eVars como dimensiones de datos, pueden ser eVars nuevas o preexistentes. Después de seleccionar una eVar para que reciba una dimensión desde la fuente de datos, no olvide ponerle un nombre adecuado.

Consulte [Eventos de éxito](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/success-events/success-event.html) en la ayuda de Analytics.

## Código de seguimiento de campaña {#section_468222796FF449ABAA90D88EB3264CB1}

Además de importar eventos de éxito, se pueden importar los valores de eVar correspondientes. Por ejemplo, si para el seguimiento de la actividad en línea se usan códigos de seguimiento de campaña y para las métricas de actividades sin conexión se tienen códigos de seguimiento de campaña, las métricas se pueden importar con los códigos de seguimiento de campaña. Si sigue este método, en los informes de campañas puede ver métricas para las actividades con y sin conexión.

Si no importa las métricas de fuentes de datos con un valor de eVar asociado, no puede ver las métricas desglosadas por eVars, sino que solo ve las métricas totales.

## ID de transacción {#section_D9513C1204B7496C9B738C5B12CCCFC7}

La ID de transacción se usa para conectar los eventos que se producen con conexión con los que se producen sin conexión.

## Identificar un intervalo de fechas válido para la fuente de datos   {#section_03AAB1291BDC4403BDC50905A78FDB71}

Después de definir las métricas de la fuente de datos (eventos personalizados) y las dimensiones de datos (eVars), revise el intervalo de fechas de la fuente de datos que quiera importar. No se pueden importar fuentes de datos cuyo intervalo de fechas exceda el período de los datos ya existentes en los informes.

Por ejemplo, no se pueden importar fuentes de datos anteriores a la implementación del seguimiento de datos con conexión. Las fuentes de datos deben estar desglosadas por día.

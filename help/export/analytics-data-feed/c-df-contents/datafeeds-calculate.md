---
description: Se describe cómo calcular métricas habituales mediante fuentes de datos.
keywords: Data Feed;job;metrics;pre column;post column;bots;date filtering;event string;common;formulas
title: Calcular métricas
topic: Reports and analytics
uuid: a45ea5bb-7c83-468f-b94a-63add78931d7
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '442'
ht-degree: 97%

---


# Uso de fuentes de datos para calcular métricas comunes

Se describe cómo calcular métricas habituales mediante fuentes de datos.

>[!IMPORTANT]
>
>Las visitas normalmente excluidas de Adobe Analytics se incluyen en las fuentes de datos. Se utiliza `exclude_hit > 0` para eliminar visitas excluidas de consultas sobre datos sin procesar. La información con origen de datos también se incluye en las fuentes de datos. Si desea excluir los orígenes de datos, excluya todas las filas con `hit_source = 5,7,8,9`.

## Vistas de páginas

1. Cuente el número de filas donde hay un valor en `post_pagename` o `post_page_url`.

## Visitas

1. Concatenar `post_visid_high`, `post_visid_low`, `visit_num` y `visit_start_time_gmt`.
1. Contar el número único de valores.

>[!NOTE]
>
>Las irregularidades de Internet, las irregularidades del sistema o el uso del ID de visitante personalizado no suelen utilizar los mismos valores `visit_num` para las distintas visitas. Se utiliza `visit_start_time_gmt` al contar las visitas para garantizar que el recuento es correcto.

## Visitantes

Todos los métodos que utiliza Adobe para identificar visitantes únicos (ID de visitante personalizado, servicio de Experience Cloud ID, etc.) se calculan finalmente como un valor en `post_visid_high` y `post_visid_low`. La concatenación de estas dos columnas puede utilizarse como estándar para identificar visitantes únicos independientemente de cómo se identificaron esos visitantes. Si desea saber qué método utilizó Adobe para identificar a un visitante único, utilice la columna `post_visid_type`.

1. Concatenar `post_visid_high` y `post_visid_low`.
2. Contar el número único de valores.

## Vínculos personalizados, de descarga o de salida

1. Contar el número de filas donde:
   * `post_page_event = 100` para vínculos personalizados
   * `post_page_event = 101` para vínculos de descarga
   * `post_page_event = 102` para vínculos de salida

## Eventos personalizados

Todas las métricas se cuentan en la columna `post_event_list` como números enteros delimitados por comas. Utilice `event.tsv` para hacer coincidir valores numéricos con el evento deseado. Por ejemplo, `post_event_list = 1,200` indica que la visita contenía un evento de compra y un evento personalizado 1.

1. Haga un recuento de la cantidad de veces que el valor de la búsqueda de eventos aparece en `post_event_list`.

## Tiempo empleado

Las visitas deben agruparse primero por visita individual y luego, ordenarse según el número de visitas dentro de la visita individual.

1. Concatenar `post_visid_high`, `post_visid_low`, `visit_num` y `visit_start_time_gmt`.
2. Ordene la información por este valor concatenado y, a continuación, aplique una clasificación secundaria por `visit_page_num`.
3. Si una visita no es la última en una visita individual, reste el valor `post_cust_hit_time` del valor `post_cust_hit_time` de la visita subsiguiente.
4. Este número es la cantidad de tiempo empleado (en segundos) para la visita. Se pueden aplicar filtros para centrarse en elementos o eventos de dimensión.

## Pedidos, unidades e ingresos

Si el valor de una visita `currency` no coincide con la moneda de un grupo de informes, se convierte con la tasa de conversión de ese día. La columna `post_product_list` utiliza el valor de moneda convertido, de modo que todas las visitas utilizan la misma moneda en esta columna.

1. Excluya todas las filas en las que `duplicate_purchase = 1`.
2. Incluya solo las filas donde `event_list` contenga el evento de compra.
3. Analice la columna `post_product_list` para extraer todos los datos de precios. La columna `post_product_list` tiene el mismo formato que la variable `s.products`.
4. Calcule la métrica que desee:
   * Cuente el número de filas para calcular los pedidos
   * Sume el número de `quantity` en la cadena de producto para calcular las unidades
   * Sume el número de `price` en la cadena de producto para calcular los ingresos

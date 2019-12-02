---
description: Se describe cómo calcular métricas habituales mediante fuentes de datos.
keywords: Data Feed;job;metrics;pre column;post column;bots;date filtering;event string;common;formulas
solution: Analytics
title: Calcular métricas
topic: Reports and analytics
uuid: a45ea5bb-7c83-468f-b94a-63add78931d7
translation-type: tm+mt
source-git-commit: 7db88bce7b3d0f90fa5b50664d7c0c23904348c0

---


# Utilizar fuentes de datos para calcular métricas comunes

Se describe cómo calcular métricas habituales mediante fuentes de datos.

> [!IMPORTANT] Las visitas normalmente excluidas de Adobe Analytics se incluyen en las fuentes de datos. Se utiliza `exclude_hit > 0` para eliminar visitas excluidas de consultas sobre datos sin procesar. Los datos de fuentes de datos también se incluyen en las fuentes de datos. Si desea excluir las fuentes de datos, excluya todas las filas con `hit_source = 5,7,8,9`.

## Vistas de páginas

1. Contar el número de filas donde está un valor `post_pagename` o `post_page_url`.

## Visitas

1. Concatenar `post_visid_high`, `post_visid_low`, `visit_num`y `visit_start_time_gmt`.
1. Contar el número único de valores.

> [!NOTE] Las irregularidades de Internet, las irregularidades del sistema o el uso de ID de visitante personalizados rara vez pueden utilizar los mismos `visit_num` valores para las distintas visitas. Se utiliza `visit_start_time_gmt` al contar las visitas para asegurarse de que se cuentan.

## Visitantes

Todos los métodos que utiliza Adobe para identificar visitantes únicos (ID de visitante personalizado, servicio de ID de Experience Cloud, etc.) todos se calculan finalmente como un valor en `post_visid_high` y `post_visid_low`. La concatenación de estas dos columnas puede utilizarse como estándar para identificar visitantes únicos independientemente de cómo se identificaron como visitantes únicos. Si desea saber qué método utilizó Adobe para identificar a un visitante único, utilice la columna `post_visid_type`.

1. Concatenar `post_visid_high` y `post_visid_low`.
2. Contar el número único de valores.

## Vínculos personalizados, de descarga o de salida

1. Contar el número de filas donde:
   * `post_page_event = 100` para vínculos personalizados
   * `post_page_event = 101` para vínculos de descarga
   * `post_page_event = 102` para vínculos de salida

## Eventos personalizados

Todas las métricas se cuentan en la `post_event_list` columna como enteros delimitados por comas. Se utiliza `event.tsv` para hacer coincidir valores numéricos con el evento deseado. Por ejemplo, `post_event_list = 1,200` indica que la visita contenía un evento de compra y un evento personalizado 1.

1. Count the number of times the event lookup value appears in `post_event_list`.

## Tiempo empleado

Las visitas deben agruparse primero por visita y luego ordenarse según el número de visitas dentro de la visita.

1. Concatenar `post_visid_high`, `post_visid_low`, `visit_num`y `visit_start_time_gmt`.
2. Ordene por este valor concatenado y, a continuación, aplique una clasificación secundaria por `visit_page_num`.
3. Si una visita no es la última de una visita, reste el `post_cust_hit_time` valor del `post_cust_hit_time` valor de la visita subsiguiente.
4. Este número es la cantidad de tiempo empleado (en segundos) para la visita. Los filtros se pueden aplicar para centrarse en los valores o eventos de dimensión.

## Pedidos, unidades e ingresos

Si el valor de una visita `currency` no coincide con la moneda de un grupo de informes, se convierte con la tasa de conversión de ese día. La columna `post_product_list` utiliza el valor de moneda convertido, de modo que todas las visitas individuales utilizan la misma moneda en esta columna.

1. Exclude all rows where `duplicate_purchase = 1`.
2. Incluir solo las filas donde `event_list` contenga el evento de compra.
3. Analice la `post_product_list` columna para extraer todos los datos de precios. La `post_product_list` columna tiene el mismo formato que la `s.products` variable.
4. Calcule la métrica que desee:
   * Contar el número de filas para calcular los pedidos
   * Sumar el número de unidades `quantity` en la cadena de producto para calcular unidades
   * Sumar el número de `price` en la cadena de producto para calcular los ingresos

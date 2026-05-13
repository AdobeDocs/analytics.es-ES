---
title: Compatibilidad con componentes en Data Warehouse
description: Descubra qué dimensiones y métricas adicionales están disponibles en Data Warehouse y qué otras no se admiten.
feature: Data Warehouse
exl-id: ce7411a4-a720-47b7-90d5-4d867eff4bae
TQID: https://experienceleague.adobe.com/NhSEyPN3093B9M0SngJluJdZScI2lXvRyHkXQd8gg-4
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 580
ht-degree: 47%

---

# Compatibilidad con componentes en Data Warehouse

El procesamiento único en la arquitectura de Data Warehouse permite algunos componentes que no suelen estar disponibles en otras funciones de Adobe Analytics. Debido a su arquitectura única, algunos componentes no están disponibles para su uso en informes o segmentos. Utilice esta página para comprender qué se puede usar y qué no.

## Componentes únicos de Data Warehouse

Algunas dimensiones y métricas que se pueden usar en Data Warehouse no están disponibles cuando se usan otras funcionalidades en Adobe Analytics.

### Dimensiones admitidas exclusivamente

* **Experience Cloud ID**: Para implementaciones que usan el servicio Experience Cloud ID (ECID), un número de 128 bits que consta de dos números concatenados de 64 bits seguidos de 19 dígitos.
* **Dirección URL de la página**: Dirección URL de la página en la que se produjo la visita.
* **ID de compra**: Identificador único de una compra, establecido mediante la variable purchaseID.
* **ID de visitante**: Proporciona el identificador único del visitante. Este valor es el mismo que el valor concatenado de las columnas `visid_high` y `visid_low` de las fuentes de datos. Consulte [Referencia de la columna de datos](../analytics-data-feed/c-df-contents/datafeeds-reference.md) en Fuentes de datos para obtener más información.

### Métricas admitidas de forma exclusiva

* **Visitas**: Esta métrica en el contexto de Data Warehouse excluye las visitas de cookies no persistentes.
* **Visitas - Todos los visitantes**: Esta métrica en el contexto de Data Warehouse se parece más a la métrica de visitas en otras herramientas de Adobe Analytics.

## Componentes no admitidos en Data Warehouse

Algunas dimensiones y métricas no son compatibles con Data Warehouse.

>[!NOTE]
>
>Si una dimensión o métrica no se admite en Data Warehouse, tampoco se admiten los segmentos que utilizan estos componentes. Compruebe siempre la compatibilidad del producto al crear o editar un segmento.

### Dimensiones no admitidas

* AM/PM
* Algunas dimensiones basadas en rutas, entre ellas:
   * Todas las dimensiones de entrada, excepto Página de entrada
   * Todas las dimensiones de salida, excepto Página de salida y Vínculo de salida
   * Profundidad de la visita
   * Frecuencia de retorno
   * Tiempo previo al evento
   * Tiempo empleado en la página - Agrupado
   * Tiempo empleado por visita - General
* Clasificación de todas las páginas de búsqueda
* Variables de jerarquía
* Tipo de visita
* Páginas no encontradas (disponibles como dimensión; no compatibles con la segmentación)
* Búsqueda de pago
* Visitas de página única
* Motivo de exclusión de seguimiento
* Estados estadounidenses

### Métricas no admitidas

* Algunas métricas basadas en rutas, entre ellas:
   * Devoluciones
   * Entradas
   * Salidas
   * Recargas
   * Acceso único
   * Métricas de “tiempo empleado”
* Métricas de participación (como se describe en [Crear una métrica de &quot;participación&quot;](/help/components/calculated-metrics/workflow/c-build-metrics/participation-metric.md))

### Dimensiones compatibles de una manera diferente (formato de fecha no estándar)

Se admiten las siguientes dimensiones basadas en el tiempo:

* Año
* Trimestre
* Mes
* Semana
* Día
* Hora
* Minuto

Sin embargo, la salida de las fechas no es estándar al utilizar dichas dimensiones.

Tenga en cuenta lo siguiente al calcular el resultado de las fechas en Data Warehouse:

* Las dimensiones de fecha se muestran en el siguiente formato: `1YYMMDDHHMM`

* El año (AA) está compensado por 1900. Esto significa que usted agrega `1900` a los primeros 3 valores del campo de fecha.

  Por ejemplo, si el valor del campo Intervalo de fechas de la semana en Data Warehouse es `1250901`, debe agregar 1900 a 125, lo que resulta en el año 2025.

* Todos los meses tienen una base cero, con enero representado por 00, febrero por 01, y así sucesivamente, de la siguiente manera:

   * 00: enero
   * 1 de febrero
   * 02: marzo
   * 3 de abril
   * 04: mayo
   * 05: junio
   * 06: julio
   * 07: agosto
   * 08: septiembre
   * 09: octubre
   * 10 de noviembre
   * 11 de diciembre

  Por ejemplo, si el valor del campo Intervalo de fechas por semana en Data Warehouse es `1250901`, el mes se representa como 09, lo que indica octubre.




## Segmentos como dimensiones en Data Warehouse

Cuando se utiliza un segmento como dimensión en Data Warehouse, el informe devuelve una columna que contiene `"0"` o `"1"`:

* **`"0"`**: El elemento de dimensión no cumplía los criterios del segmento.
* **`"1"`**: El elemento de dimensión cumplía los criterios del segmento.

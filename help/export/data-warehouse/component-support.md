---
title: Compatibilidad con componentes en Data Warehouse
description: Descubra qué dimensiones y métricas adicionales están disponibles en Data Warehouse y qué otras no se admiten.
feature: Data Warehouse
exl-id: ce7411a4-a720-47b7-90d5-4d867eff4bae
source-git-commit: 527a9d5cdcb1ceb32073e2d444b892c0183394c1
workflow-type: tm+mt
source-wordcount: '570'
ht-degree: 45%

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
* Métricas de participación (como se describe en [Crear una métrica de &quot;participación&quot;](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/participation-metric.md))

### Dimensiones compatibles de una manera diferente (formato de fecha no estándar)

Se admiten las siguientes dimensiones basadas en el tiempo:

* Año
* Trimestre
* Mes
* Semana
* Día
* Hora
* Minuto

Sin embargo, el resultado de las fechas no es estándar al utilizar estas dimensiones.

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

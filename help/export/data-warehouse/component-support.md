---
title: Compatibilidad con componentes en Data Warehouse
description: Descubra qué dimensiones y métricas adicionales están disponibles en Data Warehouse y qué otras no se admiten.
feature: Data Warehouse
exl-id: ce7411a4-a720-47b7-90d5-4d867eff4bae
source-git-commit: e00a8e611e137590838b1a58571a563aac53434c
workflow-type: tm+mt
source-wordcount: '381'
ht-degree: 65%

---

# Compatibilidad con componentes en Data Warehouse

El procesamiento único en la arquitectura de Data Warehouse permite algunos componentes que no suelen estar disponibles en otras funciones de Adobe Analytics. Debido a su arquitectura única, algunos componentes no están disponibles para su uso en informes o segmentos. Utilice esta página para comprender qué se puede usar y qué no.

## Componentes únicos de Data Warehouse

Algunas dimensiones y métricas que se pueden usar en Data Warehouse no están disponibles cuando se usan otras funcionalidades en Adobe Analytics.

### Dimensiones admitidas exclusivamente

* **ID de Experience Cloud**: Para implementaciones que utilizan el servicio de ID de Experience Cloud (ECID), un número de 128 bits que consta de dos números concatenados de 64 bits seguidos de 19 dígitos.
* **URL de página**: Dirección URL de la página en la que se produjo la visita.
* **ID de compra**: Identificador único de una compra, establecido mediante la variable purchaseID.
* **ID de visitante**: Proporciona el identificador único del visitante. Este valor es el mismo que el valor concatenado de las columnas `visid_high` y `visid_low` de las fuentes de datos. Consulte [Referencia de la columna de datos](../analytics-data-feed/c-df-contents/datafeeds-reference.md) en Fuentes de datos para obtener más información.

### Métricas admitidas de forma exclusiva

* **Visitas**: Esta métrica en el contexto de la Data Warehouse excluye las visitas de cookies no persistentes.
* **Visitas - Todos los visitantes**: Esta métrica en el contexto de la Data Warehouse se parece más a la métrica de visitas en otras herramientas de Adobe Analytics.

## Componentes no admitidos en Data Warehouse

Algunas dimensiones y métricas no son compatibles con Data Warehouse.

>[!NOTE]
>
>Si una dimensión o métrica no se admite en Data Warehouse, tampoco se admiten los segmentos que utilizan estos componentes. Compruebe siempre la compatibilidad del producto al crear o editar un segmento.

### Dimensiones no admitidas

* Algunas dimensiones basadas en el tiempo, como:
   * AM/PM
   * Día del mes
   * Día de la semana
   * Día del año
   * Hora del día
   * Minuto
   * Mes del año
   * Trimestre del año
   * Día de la semana/Fin de semana
   * Año
* Algunas dimensiones basadas en rutas, entre ellas:
   * Todas las dimensiones de entrada, excepto Página de entrada
   * Todas las dimensiones de salida, excepto Página de salida y Vínculo de salida
   * Profundidad de la visita
   * Frecuencia de retorno
   * Tiempo previo al evento
   * Tiempo empleado en la página - Agrupado
   * Tiempo empleado por visita - General
   * Profundidad de la visita
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


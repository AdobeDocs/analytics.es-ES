---
title: Compatibilidad con componentes en el almacén de datos
description: Descubra qué dimensiones y métricas adicionales están disponibles en el almacén de datos y qué no se admite.
translation-type: tm+mt
source-git-commit: 8f3f11ada9bd12498dc40931cc987aa550b8d655

---


# Compatibilidad con componentes en el almacén de datos

La arquitectura de procesamiento exclusiva del Almacén de datos permite algunos componentes que normalmente no están disponibles en otras capacidades de Adobe Analytics. También debido a su arquitectura única, algunos componentes no están disponibles para su uso en informes o segmentos. Utilice esta página para comprender qué puede utilizarse y qué no.

## Componentes exclusivos del almacén de datos

Algunas dimensiones y métricas se pueden utilizar en el almacén de datos, pero no están disponibles con otras capacidades en Adobe Analytics.

### Dimensiones admitidas exclusivamente

* ID del visitante de Experience Cloud: Para implementaciones que utilizan el servicio Experience Cloud ID (ECID), un número de 128 bits que consta de dos números concatenados de 64 bits relleno a 19 dígitos.
* URL de la página: Dirección URL de la página en la que se produjo la visita.
* ID de compra: Identificador único para una compra, configurado con la variable purchaseid.
* ID de visitante: Proporciona el identificador único del visitante. Este valor es el mismo que el valor concatenado y `visid_high``visid_low` las columnas de las fuentes de datos. Consulte [Referencia de columna Datos](../analytics-data-feed/c-df-contents/datafeeds-reference.md) en Fuentes de datos para obtener más información.

### Las métricas se admiten exclusivamente

* Visitas: Esta métrica en contexto del almacén de datos excluye las visitas de cookies no persistentes.
* Visitas - Todos los visitantes: Esta métrica en contexto del almacén de datos tiene una paridad más cercana con la métrica Visitas en otras herramientas de Adobe Analytics.

## Componentes no admitidos en el almacén de datos

Algunas dimensiones y métricas no son compatibles con el almacén de datos.

> [!NOTE] Si el almacén de datos no admite una dimensión o métrica, los segmentos que utilizan estos componentes tampoco son compatibles. Compruebe siempre la compatibilidad del producto al crear o editar un segmento.

### Dimensiones no admitidas

* Algunas dimensiones basadas en el tiempo, incluyendo:
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
   * Profundidad de acierto
   * Frecuencia de retorno
   * Tiempo previo al evento
   * Tiempo empleado en la página - Agrupado
   * Tiempo empleado por visita - General
   * Profundidad de la visita
* Clasificación de todas las páginas de búsqueda
* Variables de jerarquía
* Tipo de visita
* Páginas no encontradas (disponibles como dimensión; no se admite para la segmentación)
* Búsqueda de pago
* Visitas a una sola página
* Motivo de omisión de seguimiento
* Estados Unidos

### Métricas no admitidas

* Algunas métricas basadas en rutas, incluyendo:
   * Devoluciones
   * Entradas
   * Salidas
   * Recargas
   * Acceso único
   * Métricas de tiempo empleado

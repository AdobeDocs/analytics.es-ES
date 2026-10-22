---
title: Versión de JavaScript
description: Versión de JavaScript admitida por el explorador del visitante.
feature: Dimensions
source-git-commit: a68e13c9232ef8d975fd1256168a0addf677f5ac
workflow-type: tm+mt
source-wordcount: '187'
ht-degree: 10%
---
# Versión de JavaScript

La &quot;versión de JavaScript&quot; [dimension](overview.md) informa de la versión de JavaScript admitida por el explorador del visitante. No informa de la versión de la biblioteca de AppMeasurement.

>[!IMPORTANT]
>
>Esta dimensión solo está disponible en Data Warehouse. Si desea usar la versión de JavaScript en otras soluciones de Analytics, pruebe a copiar el valor en un [eVar](evar.md) en cada visita.

## Rellene esta dimensión con datos

AppMeasurement detecta automáticamente las características de JavaScript en el explorador y envía un valor de versión en el parámetro de cadena de consulta `j`. No hay ninguna variable de implementación que establecer. Esta detección utiliza etiquetas de versión de JavaScript heredadas; no es una medida completa de la compatibilidad con funciones ECMAScript modernas.

| Propiedad | Valor |
| --- | --- |
| **variable de AppMeasurement** | Ninguno (recopilado automáticamente) |
| **Campo Web SDK / XDM** | [`environment.browserDetails.javaScriptVersion`](/help/implement/aep-edge/xdm-var-mapping.md) |
| **Parámetro de consulta** | [`j`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **etiqueta XML** | [`<javaScriptVersion>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Columna de API de inserción de datos en lotes** | [`javaScriptVersion`](https://developer.adobe.com/analytics-collection-apis/methods/bulk-data-insertion/column-reference) |
| **Límite de bytes** | 5 bytes |
| **Persistencia** | Hit |

## Elementos de dimensión

Los elementos de Dimension incluyen los valores de versión de JavaScript recopilados de los navegadores de los visitantes, como `1.5` y `1.6`.

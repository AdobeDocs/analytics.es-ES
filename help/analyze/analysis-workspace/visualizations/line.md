---
description: Utilice la visualización de líneas para representar conjuntos de datos de tendencias (basados en el tiempo)
title: Líneas
uuid: 0508ff29-43fe-4f3a-a5f7-051869271b55
translation-type: tm+mt
source-git-commit: 78ed02b7bb7a4dc042c837817d36fc8ce30dce79
workflow-type: tm+mt
source-wordcount: '407'
ht-degree: 17%

---


# Líneas

Esta visualización representa las métricas con una línea para mostrar cómo cambian los valores con el paso del tiempo. Un gráfico de líneas solo se puede usar cuando se utiliza el tiempo como dimensión.

## Configuración de visualización

>[!IMPORTANT]
>
> Algunos ajustes de visualización de línea, como Añadir línea de tendencia, están actualmente en pruebas limitadas. [Más información](https://docs.adobe.com/content/help/es-ES/analytics/landing/an-releases.html).

Haga clic en el icono de engranaje en la parte superior derecha de la visualización Línea para acceder a la configuración [**de**](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.html#section_D3BB5042A92245D8BF6BCF072C66624B) Visualización disponible. La configuración se clasifica en:

* General: configuración común en los tipos de visualización
* Eje: configuración que afectará al eje x o y de la visualización de líneas
* Superposiciones: opciones para agregar contexto adicional a la serie que se muestra en la visualización de líneas.

### Cambiar la granularidad

Un menú desplegable de granularidad en la [configuración de visualización](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#section_D3BB5042A92245D8BF6BCF072C66624B) le permite cambiar una visualización de tendencias (p. ej., una línea o una barra) de diaria a semanal, mensual, etc.

### Añadir una superposición de línea de tendencia

En Configuración de **visualización > Superposiciones > Añadir línea de tendencia**, puede elegir agregar una línea de tendencia de regresión a la serie de líneas. Las líneas de tendencia ayudan a mostrar un patrón más claro en los datos.

Todos los modelos se ajustan con los mínimos cuadrados normales:

| Modelo | Descripción |
|---|---|
| Lineal | Crea una línea recta de mejor ajuste para conjuntos de datos lineales simples y resulta útil cuando los datos aumentan o disminuyen a una velocidad constante. Ecuación: y = a + b * x |
| Logarítmico | Crea una línea curva que se adapta mejor y resulta útil cuando la velocidad de cambio de los datos aumenta o disminuye rápidamente y luego se alza. Una línea de tendencia logarítmica puede utilizar valores negativos y positivos. Ecuación: y = a + b * log(x) |
| Exponencial | Crea una línea curva y resulta útil cuando los datos suben o disminuyen a tasas de crecimiento constantes. Esta opción no debe utilizarse si los datos contienen valores cero o negativos. Ecuación: y = a +<sup>eb * x |
| Alimentación | Crea una línea curva y resulta útil para conjuntos de datos que comparan mediciones que aumentan a una velocidad específica. Esta opción no debe utilizarse si los datos contienen valores cero o negativos. Ecuación: y = a *<sup>xb |
| cuadrático | Busca el mejor ajuste para un conjunto de datos con forma de parábola (cóncava arriba o abajo). Ecuación: y = a + b * x + c * x<sup>2 |
| Polinomial | Resulta útil cuando el conjunto de datos fluctúa, como analizar las ganancias y pérdidas en un conjunto de datos grande. Ecuación: y = a + b * x + ... + k *<sup>xorder |

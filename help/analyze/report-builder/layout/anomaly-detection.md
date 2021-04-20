---
description: La detección de anomalías usa el modelado estadístico para buscar automáticamente tendencias inesperadas en sus datos. El modelo analiza las métricas y determina un límite inferior, límite superior y rango esperado de valores. Cuando hay un pico o una caída inesperados, el sistema le alerta en el informe.
title: Detección de anomalías
uuid: 02da21b4-3394-471b-97b5-aa1bddf1f445
feature: Report Builder
role: Business Practitioner, Administrator
translation-type: tm+mt
source-git-commit: 894ee7a8f761f7aa2590e06708be82e7ecfa3f6d
workflow-type: tm+mt
source-wordcount: '523'
ht-degree: 99%

---


# Detección de anomalías {#anomaly-detection}

La detección de anomalías usa el modelado estadístico para buscar automáticamente tendencias inesperadas en sus datos. El modelo analiza las métricas y determina un límite inferior, límite superior y rango esperado de valores. Cuando hay un pico o una caída inesperados, el sistema le alerta en el informe.

Algunos ejemplos de anomalías que puede investigar son:

* Caídas drásticas en un valor de pedido promedio
* Picos en pedidos con ingresos bajos
* Picos o caídas en registros de prueba
* Caídas en vistas de páginas de aterrizaje
* Picos en los eventos de almacenamiento de vídeo
* Picos en tasas de bits de vídeo bajas

>[!NOTE]
>
>La detección de anomalías está disponible únicamente cuando selecciona la granularidad de día.

<p class="head"> <b>Métricas de detección de anomalías</b> </p>

La detección de anomalías añade nuevos valores de métricas a cada métrica que seleccione, incluidas:

<table id="table_BF75FC874634498DB6632C12CBD8D533"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Límite inferior </td> 
   <td colname="col2"> <p>Nivel inferior del intervalo de predicción. Los valores por debajo de este nivel se consideran una anomalía. </p> <p>Representa un 95 % de seguridad de que los valores se encontrarán por encima de este nivel. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Previsto </td> 
   <td colname="col2"> <p>El valor predicho en función de los análisis de datos. Este valor también es un punto intermedio entre el límite superior y el límite inferior. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Límite superior </td> 
   <td colname="col2"> <p>Nivel superior del intervalo de predicción. Los valores por encima de este nivel se consideran una anomalía. </p> <p>Representa un 95 % de seguridad de que los valores se encontrarán por debajo de este nivel. </p> </td> 
  </tr> 
 </tbody> 
</table>

Report Builder aplica estos valores a las métricas seleccionadas. Por ejemplo, si selecciona la métrica de vistas de la página y aplica la detección de anomalías, *`Page Views Lower Bound`* límite inferior de vistas de la página.

**Cómo se calcula la detección de anomalías**

La detección de anomalías utiliza un período de prueba para calcular, aprender y generar informes de los datos del intervalo de predicción diariamente. El período de prueba es el periodo histórico que identifica qué es normal y qué es una anomalía y aplica lo que ha aprendido en el periodo de informes. En los informes de marketing, hay disponibles periodos de prueba de 30, 60 y 90 disponibles. En Report Builder, hay disponibles 30 días.

El período de prueba no es necesariamente el mismo que el periodo de informe seleccionado. Un gráfico de informe muestra el periodo de intervalo de fechas que especifique en el calendario.

Para calcular la fecha, se compara el total diario de cada métrica con el período de prueba utilizando cada los siguientes algoritmos:

* Multiplicativo de Holt-Winters (suavizado exponencial triple)
* Suma Holt-Winters (suavizado exponencial triple)
* Tendencia corregida de Holt (suavizado exponencial doble)

Cada algoritmo se aplica para determinar el algoritmo con el menor número de suma de errores al cuadrado (SSE). El error de porcentaje absoluto medio (MAPE, Mean Absolute Percent Error) y el error estándar actual se calculan a continuación para garantizar que el modelo sea estadísticamente válido.

Se pueden ampliar estos algoritmos para proporcionar previsiones predictivas de métricas en periodos futuros.

Como el período de prueba varía en función del inicio del periodo de informe, es posible que vea diferencias en los datos de informe para la misma fecha como parte de dos periodos distintos.

Por ejemplo, si realiza un informe del 1 al 14 de enero y luego realizar un informe del 7 al 21 de enero, es posible que vea unos datos de predicción distintos para las mismas métricas del 7 al 14 de enero en los distintos informes. Esto es como resultado de la diferencia en los periodos de prueba.

| Rango de informes | Período de prueba |
|--- |--- |
| Del 1 al 14 de enero | Del 27 de noviembre al 31 de diciembre |
| Del 7 al 21 de enero | Del 4 de diciembre al 6 de enero |

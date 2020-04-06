---
description: La detección de anomalías utiliza el modelado estadístico para encontrar automáticamente tendencias inesperadas en los datos. El modelo analiza las métricas y determina un límite inferior, límite superior y rango esperado de valores. Cuando se produce un pico o una caída inesperados, el sistema le alerta en el informe.
title: Detección de anomalías
topic: Report builder
uuid: 02da21b4-3394-471b-97b5-aa1bddf1f445
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Detección de anomalías {#anomaly-detection}

La detección de anomalías utiliza el modelado estadístico para encontrar automáticamente tendencias inesperadas en los datos. El modelo analiza las métricas y determina un límite inferior, límite superior y rango esperado de valores. Cuando se produce un pico o una caída inesperados, el sistema le alerta en el informe.

Algunos ejemplos de anomalías que puede investigar son:

* Caídas drásticas en el valor de pedido promedio
* Picos en pedidos con ingresos bajos
* Picos o caídas en los registros de prueba
* Caídas en vistas de página de aterrizaje
* Especies en eventos de búfer de vídeo
* Picos en velocidades de bits de vídeo bajas

>[!NOTE] La detección de anomalías está disponible únicamente cuando selecciona la granularidad de día.

<p class="head"> <b>Métricas de detección de anomalías</b> </p>

La detección de anomalías agrega nuevos valores de métrica para cada métrica seleccionada, incluidos:

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
   <td colname="col2"> <p>Nivel inferior del intervalo de predicción. Los valores por debajo de este nivel se consideran anómalos. </p> <p>Representa un 95 % de confianza en que los valores estarán por encima de este nivel. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Esperado </td> 
   <td colname="col2"> <p>El valor predicho basado en la análisis de datos. Este valor es también el punto medio entre los límites superior e inferior. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Límite superior </td> 
   <td colname="col2"> <p>Nivel superior del intervalo de predicción. Los valores por encima de este nivel se consideran anómalos. </p> <p>Representa un 95 % de confianza en que los valores estarán por debajo de este nivel. </p> </td> 
  </tr> 
 </tbody> 
</table>

Report Builder aplica estos valores a las métricas seleccionadas. Por ejemplo, si selecciona la métrica de vistas de la página y aplica la detección de anomalías, *`Page Views Lower Bound`* límite inferior de vistas de la página.

**Cómo se calcula la detección de anomalías**

La detección de anomalías utiliza un período de prueba para calcular, aprender e informar los datos del intervalo de predicción por día. El período de prueba es el período histórico que identifica lo normal frente a lo anómalo y aplica lo aprendido al período de sistema de informes. En los informes de marketing, hay disponibles períodos de prueba de 30, 60 y 90. En Report Builder, hay disponibles 30 días.

El período de prueba no es necesariamente el mismo que el período de sistema de informes seleccionado. Un gráfico del informe muestra el período de intervalo de fechas especificado en el calendario.

Para calcular los datos, el total diario de cada métrica se compara con el período de prueba utilizando cada uno de los siguientes algoritmos:

* Multiplicativo de Holt-Winters (alisado exponencial triple)
* Aditivo Holt-Winters (alisado exponencial triple)
* Tendencia corregida de Holts (alisado exponencial de Doble)

Cada algoritmo se aplica para determinar el algoritmo con la suma más pequeña de errores al cuadrado (SSE). El error de porcentaje absoluto medio (MAPE) y el error estándar actual se calculan para asegurarse de que el modelo sea estadísticamente válido.

Estos algoritmos se pueden ampliar para proporcionar previsiones predictivas de las métricas en períodos futuros.

Debido a que el período de prueba varía según el inicio del período de sistema de informes, es posible que se observen diferencias en los datos notificados para la misma fecha como parte de dos períodos de tiempo diferentes.

Por ejemplo: si ejecuta un informe del 1 al 14 de enero y luego ejecuta un informe del 7 al 21 de enero, es posible que vea diferentes datos de predicción para la misma métrica entre el 7 y el 14 de enero en los dos informes diferentes. Esto se debe a la diferencia en los períodos de prueba.

| Rango de Sistemas de informes | Período de prueba |
|--- |--- |
| 1 a 14 de enero | 27 de noviembre - 31 de diciembre |
| Del 7 al 21 de enero | 4 de diciembre - 6 de enero |

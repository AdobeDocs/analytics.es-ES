---
description: Marque Mostrar avanzadas para acceder a estas funciones en la lista desplegable Funciones.
title: Funciones avanzadas de referencia
uuid: 7d1071b9-1737-4b7c-b318-87907dae5619
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Referencia: funciones avanzadas

<!-- 

cm_adv_functions.xml

 -->

Access these functions by checking **[!UICONTROL Show Advanced]** in the **[!UICONTROL Functions]** drop-down list.

## Funciones de tabla en comparación con funciones de fila {#section_8977BE40A47E4ED79EB543A9703A4905}

Una función de tabla es una en la que el resultado es el mismo para cada fila de la tabla. Una función de fila es una en la que el resultado es diferente para cada fila de la tabla.

## ¿Qué significa el parámetro Include-Zeros? {#section_C7A2B05929584C65B308FD372CB8E8E3}

Indica si se incluyen ceros en el cálculo. En algunas ocasiones cero significa "nada", pero en ocasiones es importante.

Por ejemplo, si tiene una métrica Ingresos y, a continuación, agrega una métrica Vistas de página al informe, de repente hay más filas para sus ingresos todas con valor de cero. Probablemente no desea que esto afecte a ningún valor MEAN, MIN, QUARTILE, etc. los cálculos que tiene en la columna de ingresos. En este caso, debería marcar el parámetro para incluir ceros.

Por otra parte, si tiene dos métricas en las que está interesado, puede que no sea justo afirmar que una tiene una media superior o mínima porque algunas de sus filas eran ceros, por lo que no debería marcar el parámetro para incluir ceros.

## Y {#concept_E14513FE464F4491AD0D4130D4EE621C}

Devuelve el valor de su argumento. Utilice NO para asegurarse de que un valor no es igual a un valor en concreto.

> [!NOTE] 0 (cero) significa False y cualquier otro valor es True.

```
AND(logical_test1,[logical_test2],...)
```

| Argumento | Descripción |
|---|---|
| *prueba_lógica1* | Requerido. Cualquier valor o expresión que pueda evaluarse como VERDADERO o FALSO. |
| *prueba_lógica2* | Opcional. Condiciones adicionales que desee evaluar como VERDADERO o FALSO |

## Número aproximado de elementos distintos (dimensión) {#concept_000776E4FA66461EBA79910B7558D5D7}

Devuelve el número aproximado de elementos distintos de dimensiones para la dimensión seleccionada. Esta función usa el método HyperLogLog (HLL) de números aproximados de elementos distintos. Está configurada para garantizar que el valor se encuentre en el 5 % del 95 % del valor actual del tiempo.

```
Approximate Count Distinct (dimension)
```

| Argumento |  |
|---|---|
| *dimension* | Dimensión de la que se quiere obtener el número aproximado de elementos distintos. |

## Caso práctico de ejemplo {#section_424E3FC5092948F0A9D655F6CCBA0312}

El número aproximado de elementos distintos (eVar del ID del cliente) es un caso práctico común para esta función.

Definición de una nueva métrica calculada "Clientes aproximados":

![](assets/approx-count-distinct.png)

Así es como se podría usar la métrica “Clientes aproximados” en un informe:

![](assets/approx-customers.png)

## Se excedió la cantidad de valores exclusivos {#section_9C583858A9F94FF7BA054D1043194BAA}

Igual que Count() y RowCount(), Approximate Count Distinct() está sujeto a [límites de “valores exclusivos excedidos”](https://marketing.adobe.com/resources/help/en_US/reference/metrics_uniques_high_numbers.html). Si una dimensión alcanza el límite de “valores exclusivos excedidos” en un mes en concreto, el valor se cuenta como un elemento de dimensión.

## Comparación de funciones de recuento {#section_440FB8FB44374459B2C6AE2DA504FC0B}

La función Approximate Count Distinct() es una mejora de las funciones Count() y RowCount() porque la métrica que se crea puede usarse en cualquier informe dimensional para representar un número aproximado de elementos para una dimensión distinta. Por ejemplo, un recuento de los ID de cliente que se usan en un informe sobre tipos de dispositivos móviles.

Esta función será ligeramente menos precisa que Count() y RowCount() porque usa el método HLL, mientras que Count() y RowCount() son recuentos exactos.

## Arcocoseno (Fila) {#concept_1DA3404F3DDE4C6BAF3DBDD655D79C7B}

Devuelve el arcocoseno o la inversa del coseno de una métrica. El arcocoseno es el ángulo cuyo coseno es un número. El ángulo devuelto se da en radianes dentro del rango de 0 (cero) a pi. Si desea convertir el resultado de radianes a grados, multiplíquelo por 180/PI( ).

```
ACOS(metric)
```

| Argumento |  |
|---|---|
| *métrica* | El coseno del ángulo que desee desde -1 a 1. |

## Arcoseno (Fila) {#concept_90F00DEC46BA47F8A21493647D9668CD}

Devuelve el arcoseno o la inversa del seno de un número. El arcoseno es el ángulo cuyo seno es un número. El ángulo devuelto se da en radianes dentro del rango de -pi/2 a pi/2. Para expresar el arcoseno en grados, multiplique el resultado por 180/PI( ).

```
ASIN(metric) 
```

| Argumento |  |
|---|---|
| *métrica* | El coseno del ángulo que desee desde -1 a 1. |

## Arcotangente (Fila) {#concept_3408520673774A10998E9BD8B909E90C}

Devuelve el arcotangente o la inversa de la tangente de un número. El arcotangente es el ángulo cuya tangente es un número. El ángulo devuelto se da en radianes dentro del rango de -pi/2 a pi/2. Para expresar el arcotangente en grados, multiplique el resultado por 180/PI( ).

```
ATAN(metric)
```

| Argumento |  |
|---|---|
| *métrica* | El coseno del ángulo que desee desde -1 a 1. |

## Regresión exponencial: Y predicha (Fila) {#concept_25615693312B4A7AB09A2921083502AD}

Calcula los valores Y predichos (metric_Y), dados los valores x conocidos (metric_X) usando el método de "mínimos cuadrados" para calcular la línea que mejor se ajusta según la fórmula .

```
ESTIMATE.EXP(metric_X, metric_Y)
```

| Argumento | Descripción |
|---|---|
| *metric_X* | Una métrica que le gustaría designar como datos dependientes. |
| *metric_Y* | Una métrica que le gustaría designar como datos independientes. |

## Cdf-T {#concept_4E2F2673532A48B5AF786521DE428A66}

Devuelve el porcentaje de valores en una distribución t de Student con n grados de libertad que tiene un valor z inferior al de x.

```
cdf_t( -∞, n ) = 0 
cdf_t(  ∞, n ) = 1 
cdf_t( 3, 5 ) ? 0.99865 
cdf_t( -2, 7 ) ? 0.0227501 
cdf_t( x, ∞ ) ? cdf_z( x )
```

## Cdf-Z {#concept_99C97ACC40A94FADBCF7393A17BC2D12}

Devuelve el porcentaje de valores en una distribución normal que tienen un valor de z inferior al valor de x.

```
cdf_z( -∞ ) = 0 
cdf_z( ∞ ) = 1 
cdf_z( 0 ) = 0.5 
cdf_z( 2 ) ? 0.97725 
cdf_z( -3 ) ? 0.0013499 
 
```

## Techo (Fila) {#concept_A14CDB1E419B4AA18D335E5BA2548346}

Devuelve el menor entero igual o mayor que un valor determinado. Por ejemplo, si desea evitar los decimales en una moneda de un informe en los ingresos y un producto tiene el valor de 569,34 $, utilice la fórmula CEILING(*Ingresos*) para redondear hacia arriba al dólar más próximo o 570 $.

```
CEILING(metric)
```

| Argumento | Descripción |
|---|---|
| *métrica* | La métrica que desee redondear. |

## Coseno (Fila) {#concept_DD07AA1FB08145DC89B69D704545FD0A}

Devuelve el coseno de un ángulo determinado. Si el ángulo es en grados, multiplique el ángulo por PI( )/180.

```
COS(metric)
```

| Argumento | Descripción |
|---|---|
| *métrica* | El ángulo en radianes del cual desea el coseno. |

## Raíz cúbica {#concept_BD93EFA45DF7447A8F839E1CA5B5F795}

Devuelve la raíz cúbica positiva de un número. La raíz cúbica de un número es el valor de dicho número elevado a la potencia de 1/3.

```
CBRT(metric)
```

| Argumento | Descripción |
|---|---|
| *métrica* | La métrica de la cual desea la raíz cúbica. |

## Acumulativo {#concept_3D3347797B6344CE88B394C3E39318ED}

Devuelve la suma de X para las últimas N filas (según lo solicite la dimensión, utilizando valores hash para los campos basados en cadenas).

Si N &lt;= 0 utiliza todas las filas anteriores. Como se ordena por la dimensión, solo resulta útil en dimensiones que tienen un orden natural como la fecha o la longitud de ruta.

```
| Date | Rev  | cumul(0,Rev) | cumul(2,Rev) | 
|------+------+--------------+--------------| 
| May  | $500 | $500         | $500         | 
| June | $200 | $700         | $700         | 
| July | $400 | $1100        | $600         | 
 
```

## Media acumulada {#concept_ABB650962DC64FD58A79C305282D3E61}

Devuelve la media de las últimas N filas.

Si N &lt;= 0 utiliza todas las filas anteriores. Como se ordena por la dimensión, solo resulta útil en dimensiones que tienen un orden natural como la fecha o la longitud de ruta.

> [!NOTE] Esto no funciona como es de esperar con métricas de tasa como ingresos/visitante: promedia las tasas en lugar de sumar los ingresos en la última N y sumar los visitantes en la última N y luego dividirlos. En su lugar utilice

```
cumul(revenue)/cumul(visitor)
```

## Igual {#concept_A3B97152B5F74E04A97018B35734BEEB}

Devuelve elementos que coinciden exactamente con un valor numérico o de cadena.

## Regresión exponencial: coeficiente de correlación (Tabla) {#concept_C18BBFA43C1A499293290DF49566D8D8}

Returns the correlation coefficient, *r*, between two metric columns ( *metric_A* and *metric_B*) for the regression equation .

```
CORREL.EXP(metric_X, metric_Y)
```

| Argumento | Descripción |
|---|---|
| *metric_X* | Una métrica que le gustaría correlacionar con *metric_Y*. |
| *metric_Y* | Una métrica que le gustaría correlacionar con *metric_X*. |

## Regresión exponencial: intersección (Tabla) {#concept_0047206C827841AD936A3BE58EEE1514}

Returns the intercept, *b*, between two metric columns ( *metric_X* and *metric_Y*) for

```
INTERCEPT.EXP(metric_X, metric_Y)
```

| Argumento | Descripción |
|---|---|
| *metric_X* | Una métrica que le gustaría designar como datos dependientes. |
| *metric_Y* | Una métrica que le gustaría designar como datos independientes. |

## Regresión exponencial: pendiente (Tabla) {#concept_230991B0371E44308C52853EFA656F04}

Returns the slope, *a*, between two metric columns ( *metric_X* and *metric_Y*) for .

```
SLOPE.EXP(metric_X, metric_Y)
```

| Argumento | Descripción |
|---|---|
| *metric_X* | Una métrica que le gustaría designar como datos dependientes. |
| *metric_Y* | Una métrica que le gustaría designar como datos independientes. |

## Suelo (Fila) {#concept_D368150EC3684077B284EE471463FC31}

Devuelve el mayor entero igual o menor a un valor determinado. Por ejemplo, si desea evitar los decimales en una moneda de un informe en los ingresos y un producto tiene el valor de 569,34 $, utilice la fórmula FLOOR(*Ingresos*) para redondear hacia arriba al dólar más próximo o 569 $.

```
FLOOR(metric)
```

| Argumento | Descripción |
|---|---|
| *métrica* | La métrica que desee redondear. |

## Mayor que {#concept_A83734A0C0C14646B76D2CC5E677C644}

Devuelve elementos cuyo recuento numérico sea mayor que el valor introducido.

## Mayor o igual que {#concept_8CA6DF1F84784D50849BF1C566AE1D37}

Devuelve elementos cuyo recuento numérico sea mayor o igual que el valor introducido.

## Coseno hiperbólico (Fila) {#concept_79DD5681CE9640BDBA3C3F527343CA98}

Devuelve el coseno hiperbólico de un número.

```
COSH(metric)
```

| Argumento | Descripción |
|---|---|
| *métrica* | El ángulo en radianes del cual desea encontrar el coseno hiperbólico. |

## Seno hiperbólico (Fila) {#concept_96230731600C45E3A4E823FE155ABA85}

Devuelve el seno hiperbólico de un número.

```
SINH(metric)
```

| Argumento | Descripción |
|---|---|
| *métrica* | El ángulo en radianes del cual desea encontrar el seno hiperbólico. |

## Tangente hiperbólica (Fila) {#concept_BD249013732F462B9863629D142BCA6A}

Devuelve la tangente hiperbólica de un número.

```
TANH(metric)
```

| Argumento | Descripción |
|---|---|
| *métrica* | El ángulo en radianes del cual desea encontrar la tangente hiperbólica. |

## IF (Fila) {#concept_6BF0F3EAF3EF42C288AEC9A79806C48E}

La función IF devuelve un valor si una condición que haya especificada se evalúa como VERDADERO y otro valor si esa condición se evalúa como FALSO.

```
IF(logical_test, [value_if_true], [value_if_false])
```

| Argumento | Descripción |
|---|---|
| *logical_test* | Requerido. Cualquier valor o expresión que pueda evaluarse como VERDADERO o FALSO. |
| *[value_if_true]* | El valor que desea que sea devuelto si el argumento *logical_test* se evalúa como VERDADERO. (Este argumento es 0 de forma predeterminada si no se incluye). |
| *[value_if_false]* | El valor que desea que sea devuelto si el argumento *logical_test* se evalúa como FALSO. (Este argumento es 0 de forma predeterminada si no se incluye). |

## Menor que {#concept_A4A85C0FDF944AACAD4B8B55699D1B11}

Devuelve elementos cuyo recuento numérico sea menor que el valor introducido.

## Menor o igual que {#concept_99D12154DE4848B1B0A6327C4322D288}

Devuelve elementos cuyo recuento numérico sea menor o igual que el valor introducido.

## Regresión lineal: coeficiente de correlación {#concept_132AC6B3A55248AA9C002C1FBEB55C60}

Y = a X + b. Devuelve el coeficiente de correlación

## Regresión lineal: intercepción {#concept_E44A8D78B802442DB855A07609FC7E99}

Y = a X + b. Devuelve b.

## Regresión lineal: Y predicha {#concept_9612B9BF106D4D278648D2DF92E98EFC}

Y = a X + b. Devuelve Y.

## Regresión lineal: pendiente {#concept_12352982082A4DDF824366B073B4C213}

Y = a X + b. Devuelve a.

## Logaritmo decimal (Fila) {#concept_4C65DF9659164261BE52AA5A95FD6BC1}

Devuelve el logaritmo decimal de un número.

```
LOG10(metric)
```

| Argumento | Descripción |
|---|---|
| *métrica* | El número real positivo del cual desea el logaritmo decimal. |

## Regresión logarítmica: coeficiente de correlación (Tabla) {#concept_F3EB35016B754E74BE41766E46FDC246}

Returns the correlation coefficient, *r*, between two metric columns (*metric_X* and *metric_Y*) for the regression equation [!DNL Y = a ln(X) + b]. Se calcula mediante la ecuación CORREL.

```
CORREL.LOG(metric_X,metric_Y)
```

| Argumento | Descripción |
|---|---|
| *metric_X* | Una métrica que le gustaría correlacionar con *metric_Y*. |
| *metric_Y* | Una métrica que le gustaría correlacionar con *metric_X*. |

## Regresión logarítmica: intersección (Tabla) {#concept_75A3282EDF54417897063DC26D4FA363}

Devuelve la intersección *b* como la regresión con menos cuadrados entre dos columnas de métricas (*metric_X* y *metric_Y*) para la ecuación de regresión [!DNL Y = a ln(X) + b]. Se calcula mediante la ecuación INTERCEPT.

```
INTERCEPT.LOG(metric_X, metric_Y)
```

| Argumento | Descripción |
|---|---|
| *metric_X* | Una métrica que le gustaría designar como datos dependientes. |
| *metric_Y* | Una métrica que le gustaría designar como datos independientes. |

## Regresión de registro: Y predicha (fila) {#concept_5F3A9263BBB84E6098160A4DFB9E3607}

Calculates the predicted [!DNL y] values (metric_Y), given the known [!DNL x] values (metric_X) using the "least squares" method for calculating the line of best fit based on [!DNL Y = a ln(X) + b]. Se calcula mediante la ecuación ESTIMATE.

En el análisis de regresión, esta función calcula los valores [!DNL y] predichos (*metric_Y*), dados los valores [!DNL x] conocidos (*metric_X*) usando el logaritmo para calcular la mejor opción para la ecuación de regresión [!DNL Y = a ln(X) + b]. Los valores [!DNL a] se corresponden con cada valor x y [!DNL b] es un valor constante.

```
ESTIMATE.LOG(metric_X, metric_Y)
```

| Argumento | Descripción |
|---|---|
| *metric_X* | Una métrica que le gustaría designar como datos dependientes. |
| *metric_Y* | Una métrica que le gustaría designar como datos independientes. |

## Regresión logarítmica: pendiente (Tabla) {#concept_B291EFBE121446A6B3B07B262BBD4EF2}

Returns the slope, *a*, between two metric columns (*metric_X* and *metric_Y*) for the regression equation [!DNL Y = a ln(X) + b]. Se calcula mediante la ecuación SLOPE.

```
SLOPE.LOG(metric_A, metric_B)
```

| Argumento | Descripción |
|---|---|
| *metric_A* | Una métrica que le gustaría designar como datos dependientes. |
| *metric_B* | Una métrica que le gustaría designar como datos independientes. |

## Logaritmo natural {#concept_D3BE148A9B84412F8CA61734EB35FF9E}

Devuelve el logaritmo natural de un número. Los logaritmos naturales se basan en la constante *e* (2,71828182845904). El logaritmo natural es la inversa de la función exponencial.

```
LN(metric)
```

| Argumento | Descripción |
|---|---|
| *métrica* | El número real positivo del cual desea el logaritmo natural. |

## NO {#concept_BD954C455A8148A3904A301EC4DC821E}

Devuelve 1 si el número es 0 o devuelve 0 si es otro número.

```
NOT(logical)
```

| Argumento | Descripción |
|---|---|
| *lógico* | Requerido. Un valor o expresión que puede evaluarse como VERDADERO o FALSO. |

Si utiliza NO, es necesario conocer si las expresiones (&lt;, &gt;, =, &lt;&gt; , etc.) devuelven valores 0 o 1.

## Distinto a {#concept_EC010B7A9D2049099114A382D662FC16}

Devuelve todos los elementos que no contienen la coincidencia exacta del valor introducido.

## O (Fila) {#concept_AF81A33A376C4849A4C14F3A380639D2}

Devuelve TRUE si algún argumento es VERDADERO o devuelve FALSE si todos los argumentos son FALSOS.

> [!NOTE] 0 (cero) significa False y cualquier otro valor es True.

```
OR(logical_test1,[logical_test2],...)
```

| Argumento | Descripción |
|---|---|
| *prueba_lógica1* | Requerido. Cualquier valor o expresión que pueda evaluarse como VERDADERO o FALSO. |
| *prueba_lógica2* | Opcional. Condiciones adicionales que desee evaluar como VERDADERO o FALSO |

## Pi {#concept_41258789660D4A33B5FB86228F12ED9C}

Devuelve la constante PI, 3,14159265358979, con una precisión de 15 dígitos.

```
PI()
```

La función [!DNL PI] no tiene argumentos.

## Regresión potencial: coeficiente de correlación (Tabla) {#concept_91EC2CFB5433494F9E0F4FDD66C63766}

Returns the correlation coefficient, *r*, between two metric columns (*metric_X* and *metric_Y*) for [!DNL Y = b*X].

```
CORREL.POWER(metric_X, metric_Y)
```

| Argumento | Descripción |
|---|---|
| *metric_X* | Una métrica que le gustaría correlacionar con *metric_Y*. |
| *metric_Y* | Una métrica que le gustaría correlacionar con *metric_X*. |

## Regresión potencial: intersección (Tabla) {#concept_7781C85597D64D578E19B212BDD1764F}

Returns the intercept, *b*, between two metric columns (*metric_X* and *metric_Y*) for [!DNL Y = b*X].

```
 INTERCEPT.POWER(metric_X, metric_Y)
```

| Argumento | Descripción |
|---|---|
| *metric_X* | Una métrica que le gustaría designar como datos dependientes. |
| *metric_Y* | Una métrica que le gustaría designar como datos independientes. |

## Regresión potencial: Y predicha (Fila) {#concept_CD652C0A921D4EFBA8F180CB8E486B18}

Calculates the predicted [!DNL y] values ( [!DNL metric_Y]), given the known [!DNL x] values ( [!DNL metric_X]) using the "least squares" method for calculating the line of best fit for [!DNL Y = b*X].

```
 ESTIMATE.POWER(metric_X, metric_Y)
```

| Argumento | Descripción |
|---|---|
| *metric_X* | Una métrica que le gustaría designar como datos dependientes. |
| *metric_Y* | Una métrica que le gustaría designar como datos independientes. |

## Regresión potencial: pendiente (Tabla) {#concept_5B9E71B989234694BEB5EEF29148766C}

Returns the slope, *a*, between two metric columns (*metric_X* and *metric_Y*) for [!DNL Y = b*X].

```
SLOPE.POWER(metric_X, metric_Y)
```

| Argumento | Descripción |
|---|---|
| *metric_X* | Una métrica que le gustaría designar como datos dependientes. |
| *metric_Y* | Una métrica que le gustaría designar como datos independientes. |

## Regresión cuadrática: coeficiente de correlación (Tabla) {#concept_9C9101A456B541E69BA29FCEAC8CD917}

Returns the correlation coefficient, *r*, between two metric columns (*metric_X* and *metric_Y*) for [!DNL Y=(a*X+b)]****.

```
CORREL.QUADRATIC(metric_X, metric_Y)
```

| Argumento | Descripción |
|---|---|
| *metric_X* | Una métrica que le gustaría correlacionar con *metric_Y*. |
| *metric_Y* | Una métrica que le gustaría correlacionar con *metric_X*. |

## Regresión cuadrática: intersección (Tabla) {#concept_69DC0FD6D38C40E9876F1FD08EC0E4DE}

Returns the intercept, *b*, between two metric columns (*metric_X* and *metric_Y*) for [!DNL Y=(a*X+b)]****.

```
INTERCEPT.POWER(metric_X, metric_Y)
```

| Argumento | Descripción |
|---|---|
| *metric_X* | Una métrica que le gustaría designar como datos dependientes. |
| *metric_Y* | Una métrica que le gustaría designar como datos independientes. |

## Regresión cuadrática: Y predicha (Fila) {#concept_2F1ED70B1BDE4664A61CC09D30C39CBB}

Calculates the predicted [!DNL y] values (metric_Y), given the known [!DNL x] values (metric_X) using the least squares method for calculating the line of best fit using [!DNL Y=(a*X+b)]**** .

```
ESTIMATE.QUADRATIC(metric_A, metric_B)
```

| Argumento | Descripción |
|---|---|
| *metric_A* | Una métrica que le gustaría designar como datos dependientes. |
| *metric_B* | Una métrica que le gustaría designar como datos dependientes. |

## Regresión cuadrática: pendiente (Tabla) {#concept_0023321DA8E84E6D9BCB06883CA41645}

Returns the slope, *a*, between two metric columns (*metric_X* and metric_Y) for [!DNL Y=(a*X+b)]****.

```
SLOPE.QUADRATIC(metric_X, metric_Y)
```

| Argumento | Descripción |
|---|---|
| *metric_X* | Una métrica que le gustaría designar como datos dependientes. |
| *metric_Y* | Una métrica que le gustaría designar como datos independientes. |

## Regresión recíproca: coeficiente de correlación (Tabla) {#concept_EBEC509A19164B8AB2DBDED62F4BA2A5}

Devuelve el coeficiente de correlación, *r*, entre dos columnas de métricas (*metric_X* y *metric_Y*) para [!DNL Y = a/X+b].

```
CORREL.RECIPROCAL(metric_X, metric_Y)
```

| Argumento | Descripción |
|---|---|
| *metric_X* | Una métrica que le gustaría correlacionar con *metric_Y*. |
| *metric_Y* | Una métrica que le gustaría correlacionar con *metric_X*. |

## Regresión recíproca: intersección (Tabla) {#concept_2DA45B5C69F140EC987649D2C88F19B3}

Returns the intercept, *b*, between two metric columns (*metric_X* and *metric_Y*) for [!DNL Y = a/X+b].

```
INTERCEPT.RECIPROCAL(metric_A, metric_B)
```

| Argumento | Descripción |
|---|---|
| *metric_X* | Una métrica que le gustaría designar como datos dependientes. |
| *metric_Y* | Una métrica que le gustaría designar como datos independientes. |

## Regresión recíproca: Y predicha (Fila) {#concept_2CF4B8F417A84FE98050FE488E227DF8}

Calculates the predicted [!DNL y] values (metric_Y), given the known [!DNL x] values (metric_X) using the least squares method for calculating the line of best fit using [!DNL Y = a/X+b].

```
ESTIMATE.RECIPROCAL(metric_X, metric_Y)
```

| Argumento | Descripción |
|---|---|
| *metric_X* | Una métrica que le gustaría designar como datos dependientes. |
| *metric_Y* | Una métrica que le gustaría designar como datos independientes. |

## Regresión recíproca: pendiente (Tabla) {#concept_8A8B68C9728E42A6BFDC6BD5CBDCCEC5}

Returns the slope, *a*, between two metric columns (*metric_X* and *metric_Y*) for [!DNL Y = a/X+b].

```
SLOPE.RECIPROCAL(metric_X, metric_Y)
```

| Argumento | Descripción |
|---|---|
| *metric_X* | Una métrica que le gustaría designar como datos dependientes. |
| *metric_Y* | Una métrica que le gustaría designar como datos independientes. |

## Seno (Fila) {#concept_21C8C3AA835947A28B53A4E756A7451E}

Devuelve el seno de un ángulo determinado. Si el ángulo es en grados, multiplique el ángulo por PI( )/180.

```
SIN(metric)
```

| Argumento | Descripción |
|---|---|
| *métrica* | El ángulo en radianes del cual desea el seno. |

## Unidad tipificada {#concept_80D2B4CED3D0426896B2412B4FC73BF7}

Es el nombre por el que también se conoce una variable estandarizada, concretamente, la desviación de la media dividida por la desviación estándar

## Prueba T {#concept_A1F78F4A765348E38DBCAD2E8F638EB5}

Realiza una prueba T con una distribución m con una unidad tipificada de col y n grados de libertad.

La firma es `t_test( x, n, m )`. Debajo, simplemente llama `m*cdf_t(-abs(x),n)`. (This is similar to the z-test function which runs `m*cdf_z(-abs(x))`.

Aquí, `m` es la cantidad de colas y `n`, los grados de la libertad. Estos deben ser números (constantes en todo el informe, es decir, que no se modifiquen de fila a fila).

`X` es la estadística t-test y es normalmente una fórmula (por ejemplo, zscore) basada en una métrica y se evaluará en cada fila.

El valor de retorno es la probabilidad de ver la estadística test x dados los grados de libertad y el número de colas.

**Ejemplos:**

1. Úselo para buscar valores atípicos:

   ```
   t_test( zscore(bouncerate), row-count-1, 2)
   ```

1. Combínelo con `if` para ignorar cualquier tasa de devolución alta o baja y haga un recuento de visitas en el resto:

   ```
   if ( t_test( z-score(bouncerate), row-count, 2) < 0.01, 0, visits )
   ```

## Tangente {#concept_C25E00CB17054263AB0460D9EF94A700}

Devuelve la tangente de un ángulo determinado. Si el ángulo es en grados, multiplique el ángulo por PI( )/180.

```
TAN (metric)
```

| Argumento | Descripción |
|---|---|
| *métrica* | El ángulo en radianes del cual desea la tangente. |

## Variable estandarizada (Fila) {#concept_96BEAC79476C49B899DB7E193A5E7ADD}

Devuelve la variable estandarizada, o una puntuación normal, basada en una distribución normal. La variable estandarizada es el número de desviaciones estándar a las que se encuentra una observación con respecto a la media. Una variable estandarizada de 0 (cero) significa que la puntuación es la misma que la media. Una variable estandarizada puede ser positiva o negativa, lo cual indica si está por encima o por debajo de la media y a cuantas desviaciones estándar.

La ecuación de variable estandarizada es:

![](assets/z_score.png)

donde [!DNL x] es la puntuación sin procesar, [!DNL μ] es la media de población y [!DNL σ] es la desviación estándar de la población.

> [!NOTE] [!DNL μ][!DNL σ] (mu) y (sigma) se calculan automáticamente a partir de la métrica.

Puntuación Z(métrica)

<table id="table_AEA3622A58F54EA495468A9402651E1B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Argumento </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <i>métrica</i> </td> 
   <td colname="col2"> <p> Devuelve el valor del primer argumento distinto a cero. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Prueba Z {#concept_2A4ADD6B3AEB4A2E8465F527FAFC4C23}

Realiza una prueba Z con una distribución n con una variable estandarizada de A.

Devuelve la probabilidad de que la fila actual pueda verse por casualidad en la columna.

> [!NOTE] Supone que los valores se distribuyen normalmente.


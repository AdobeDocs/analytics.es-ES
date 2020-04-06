---
description: El Creador de métricas calculadas permite aplicar funciones estadísticas y matemáticas para generar métricas calculadas avanzadas.
title: 'Referencia: funciones básicas'
uuid: 5c2b4a0e-613c-4b27-95b8-01d480aeab78
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Referencia: funciones básicas

El Creador de métricas calculadas permite aplicar funciones estadísticas y matemáticas para generar métricas calculadas avanzadas.

Aquí se encuentra una lista alfabética de las funciones y sus definiciones.

>[!NOTE] Cuando [!DNL metric] se identifica como un argumento en una función, también se permiten otras expresiones de métricas. Por ejemplo, [!DNL MAXV(metrics)] también permite [!DNL MAXV(PageViews + Visits).]

## Funciones de tabla en comparación con funciones de fila {#section_8977BE40A47E4ED79EB543A9703A4905}

Una función de tabla es aquella en la que el resultado es el mismo para cada fila de la tabla. Una función de fila es aquella en la que el resultado es diferente para cada fila de la tabla.

## Valor absoluto (Fila) {#concept_4CC47884F7CA49D5B84AC898EA596673}

Devuelve el valor absoluto de un número. El valor absoluto de un número es el número con signo positivo.

```
ABS(metric)
```

| Argumento | Descripción |
|---|---|
| *métrica* | La métrica de la cual desee el valor absoluto. |

## Máximo de columna {#concept_B25518D717D24F82B65CDE49A153D3A3}

Devuelve el valor más pequeño en un conjunto de elementos de dimensión para una columna de métrica. MAXV realiza una evaluación vertical dentro de una sola columna (métrica) en todos los elementos de dimensión.

```
MAXV(metric)
```

| Argumento | Descripción |
|---|---|
| *métrica* | Una métrica que le gustaría haber evaluado. |

## Mínimo de columna {#concept_5B1033F8ACE9485F9AD3CDC0D146391B}

Devuelve el valor más pequeño en un conjunto de elementos de dimensión para una columna de métrica. MINV realiza una evaluación vertical dentro de una sola columna (métrica) en todos los elementos de dimensión.

```
MINV(metric)
```

| Argumento | Descripción |
|---|---|
| *métrica* | Una métrica que le gustaría haber evaluado. |

## Suma de columna {#concept_391F04FBC3CC43368CA0C5AACE74D4B1}

Añade todos los valores numéricos de una métrica dentro de una columna (en todos los elementos de una dimensión).

```
SUM(metric)
```

| Argumento | Descripción |
|---|---|
| *métrica* | La métrica para la cual desea el valor total o la suma. |

## Recuento (Tabla) {#concept_2C6ED2B88AB74481BD130969FB071A41}

Devuelve el número, o recuento, de valores distintos a cero para una métrica dentro de una columna (el número de elementos únicos incluidos dentro de una dimensión).

```
COUNT(metric)
```

| Argumento | Descripción |
|---|---|
| *métrica* | La métrica que desea contar. |

## Exponente (Fila) {#concept_17554F9D234449FB8DDEE895816B3FF1}

Returns *e* raised to the power of a given number. The constant *e* equals 2.71828182845904, the base of the natural logarithm. EXP is the inverse of LN, the natural logarithm of a number.

```
EXP(metric)
```

| Argumento | Descripción |
|---|---|
| *métrica* | The exponent applied to the base *e*. |

## Exponenciación {#concept_941578534F1E4583B1BEB067C8113A21}

Operador de potencia

<pre>
pow(x,y) = x<sup>y</sup> = x*x*x*… (y veces)
</pre>

## Media (Tabla) {#concept_F4FF950580304D0B99DA7FBB5DB8730A}

Devuelve la media aritmética, o promedio, de una métrica en una columna.

```
MEAN(metric)
```

| Argumento | Descripción |
|---|---|
| *métrica* | La métrica de la cual desee la media. |

## Mediana (Tabla) {#concept_183EC31208524EDB8463D986DE2E895F}

Devuelve la mediana de una métrica en una columna. La mediana es el número situado en el medio de un conjunto de números, es decir, la mitad de los números tienen un valor superior o igual a la mediana, y la otra mitad tienen un valor inferior o igual a esta.

```
MEDIAN(metric)
```

| Argumento | Descripción |
|---|---|
| *métrica* | La métrica de la cual desee la mediana. |

## Módulo {#concept_DE0825D7A51643219CB01F59667EA352}

El resto de col1 / col2, utilizando la división euclidiana.

Devuelve el resto después de dividir x por y.

```
x = floor(x/y) + modulo(x,y)
```

El valor devuelto tiene el mismo signo que la entrada (o es cero).

```
modulo(4,3) = 1 
modulo(-4,3) = -1 
modulo(-3,3) = 0
```

Para obtener siempre un número positivo, utilice

```
modulo(modulo(x,y)+y,y)
```

## Percentil (Tabla) {#concept_51DF57B606D14F898E5010DBA61CA979}

Devuelve el percentil k-th de los valores de una métrica. Puede utilizar esta función para establecer un umbral de aceptación. Por ejemplo, puede decidir si se examinan los elementos de la dimensión cuyo valor es superior al percentil 90.

```
PERCENTILE(metric,k)
```

<table id="table_35CD840ACFB44CD9979881DB8823CC53"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Argumento </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <i>métrica</i> </td> 
   <td colname="col2"> La columna de métrica que define la posición relativa. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>k </p> </td> 
   <td colname="col2"> El valor de percentil en el rango de 0 a 100, ambos incluidos. </td> 
  </tr> 
 </tbody> 
</table>

## Cuartil (Tabla) {#concept_BFD37F0F23A24AD181407142233FA151}

Devuelve el cuartil de los valores de una métrica. Por ejemplo, los cuartiles se pueden usar para encontrar el 25 % de productos que genera más ingresos. MINV, MEDIAN y MAXV devuelven el mismo valor que QUARTILE cuando el cuarto es igual a 0 (cero), 2 y 4, respectivamente.

```
QUARTILE(metric,quart)
```

<table id="table_64EA3DAAE77541439D59FAF0353F83A2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Argumento </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <i>métrica</i> </td> 
   <td colname="col2"> La métrica de la cual desee el valor de cuartil. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>cuarto </p> </td> 
   <td colname="col2"> Indica qué *valor devolver. </td> 
  </tr> 
 </tbody> 
</table>

*If *quart* = 0, QUARTILE returns the minimum value. Si *quart* = 1, QUARTILE muestra el primer cuartil (porcentaje 25). Si *quart* = 2, QUARTILE muestra el primer cuartil (porcentaje 50). Si *quart* = 3, QUARTILE muestra el primer cuartil (porcentaje 75). Si *cuarto* = 4, QUARTILE devuelve el valor máximo.

## Ronda {#concept_2F12F2A6ACD445A0A8FF648AE4D4CB9E}

Devuelve el entero más próximo a un valor determinado. Por ejemplo, si desea evitar los decimales en una moneda de un informe en los ingresos y un producto tiene el valor de 569,34 $, utilice la fórmula Round(*Ingresos*) para redondear al dólar más próximo o 569 $. Un sistema de informes de producto de $569.51 será redondeado al dólar más cercano, o $570.

```
ROUND(metric)
```

| Argumento | Descripción |
|---|---|
| *entero* | La métrica que desee redondear. |

Redondear sin un parámetro de dígitos es lo mismo que redondear con un parámetro de dígitos de 0, lo cual se denomina redondear al entero más próximo. Con un parámetro de dígitos, devuelve este número de dígitos a la derecha del decimal. Si el parámetro de dígitos es negativo, devuelve ceros a la izquierda del decimal.

```
round( 314.15, 0) = 314 
round( 314.15, 1) = 314.1 
round( 314.15, -1) = 310 
round( 314.15, -2) = 300
```

## Recuento de fila {#concept_0DBF5995881C47CF95F793125F3A0E2B}

Devuelve el número de filas de una determinada columna (el número de elementos únicos incluidos dentro de una dimensión). “Únicos excedidos” cuenta como 1.

## Máximo de fila {#concept_984D045D7EDD4A1ABED454CDF2EC23C5}

Máximo de las columnas de cada fila.

## Mínimo de fila {#concept_A6FB9E72C70A43D0B31565E70B8122BD}

Mínimo de las columnas de cada fila.

## Suma de fila {#concept_E9EAB0FC5233498F907E7A078698A98E}

Suma de las columnas de cada fila.

## Raíz cuadrada (Fila) {#concept_6460DFA51EC24527A2317970FB76D404}

Devuelve la raíz cuadrada positiva de un número. La raíz cuadrada de un número corresponde al valor de dicho número elevado a la potencia de 1/2.

```
SQRT(metric)
```

| Argumento | Descripción |
|---|---|
| *entero* | La métrica de la cual desee la raíz cuadrada. |

## Desviación estándar (Tabla) {#concept_A383A8BCC6FA42D7B73F7C83997D782A}

Devuelve la desviación estándar, o raíz cuadrada de la varianza, en función de una población de datos de ejemplo.

La ecuación para STDEV es:

![](assets/std_dev.png)

donde x es la media de la muestra (*métrica*) y *n* es el tamaño de la muestra.

```
STDEV(metric)
```

<table id="table_8BCF2E4B02434AABAAD026FB3C4E8B2F"> 
 <tbody> 
  <tr> 
   <td> <b> Argumento</b> </td> 
   <td> <b> Descripción</b> </td> 
  </tr> 
  <tr> 
   <td> <b> <i> métrica</i></b> </td> 
   <td> <p> La métrica de la cual desee la desviación estándar. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Varianza (Tabla) {#concept_269751EDC5A34E689112AE16E04A11B0}

Devuelve la varianza en función de una población de datos de ejemplo.

La ecuación para VARIANCE es:

![](assets/variance_eq.png)

donde x es la media de la muestra, MEAN(*métrica*) y *n* es el tamaño de la muestra.

```
VARIANCE(metric)
```

| Argumento | Descripción |
|---|---|
| *métrica* | La métrica de la cual desee la variación. |

Para calcular una varianza, observe toda una columna de números. A partir de esa lista de números, calcule primero el promedio. Una vez que tenga el promedio, vaya a través de cada entrada y haga lo siguiente:

1. Reste el promedio del número.

2. Multiplique el resultado por sí mismo.

3. Súmelo al total.

Una vez que haya repetido toda la columna, tendrá un solo total. A continuación, divida ese total por el número de elementos de la columna. Ese número es la varianza de la columna. Es un solo número. Sin embargo, se muestra como una columna de números.

Por ejemplo, supongamos que tiene una columna de tres elementos:

1

2

3

El promedio de esta columna es 2. La varianza de la columna será ((1 - 2)² + (2 - 2)² + (3 - 2)²/3 = 2/3. En la Análisis ad hoc, este aspecto será el siguiente:

1 2/3

2 2/3

3 2/3

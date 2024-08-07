---
description: El Creador de métricas calculadas permite aplicar funciones estadísticas y matemáticas para generar métricas calculadas avanzadas.
title: 'Referencia: funciones básicas'
feature: Calculated Metrics
exl-id: 1a49435c-96d1-4617-bd1a-a5d3b74e3ebd
source-git-commit: f4032ac06c9057635dd0526ad046c4640c6350bf
workflow-type: tm+mt
source-wordcount: '1084'
ht-degree: 100%

---

# Referencia: funciones básicas

El Creador de métricas calculadas permite aplicar funciones estadísticas y matemáticas para generar métricas calculadas avanzadas.

Aquí se encuentra una lista alfabética de las funciones y sus definiciones.

>[!NOTE]
>
>Cuando [!DNL metric] se identifica como un argumento en una función, también se permiten otras expresiones de métricas. Por ejemplo, [!DNL MAXV(metrics)] también permite [!DNL MAXV(PageViews + Visits)].

## Funciones de tabla en comparación con funciones de fila {#section_8977BE40A47E4ED79EB543A9703A4905}

Una función de tabla es una en la que el resultado es el mismo para cada fila de la tabla. Una función de fila es una en la que el resultado es diferente para cada fila de la tabla.

## Valor absoluto (Fila) {#concept_4CC47884F7CA49D5B84AC898EA596673}

Devuelve el valor absoluto de un número. El valor absoluto de un número es el número con un valor positivo.

```
ABS(metric)
```

| Argumento | Descripción |
|---|---|
| *métrica* | La métrica de la cual desea el valor absoluto. |

## Máximo de columna {#concept_B25518D717D24F82B65CDE49A153D3A3}

Devuelve el mayor valor en un conjunto de elementos de una dimensión para una columna de métrica. MAXV evalúa de forma vertical dentro de una única columna (métrica) entre elementos de dimensión.

```
MAXV(metric)
```

| Argumento | Descripción |
|---|---|
| *métrica* | Una métrica que le gustaría evaluar. |

## Mínimo de columna {#concept_5B1033F8ACE9485F9AD3CDC0D146391B}

Devuelve el menor valor en un conjunto de elementos de una dimensión para una columna de métrica. MINV evalúa de forma vertical dentro de una única columna (métrica) entre elementos de dimensión.

```
MINV(metric)
```

| Argumento | Descripción |
|---|---|
| *métrica* | Una métrica que le gustaría evaluar. |

## Suma de columna {#concept_391F04FBC3CC43368CA0C5AACE74D4B1}

Suma todos los valores numéricos de una métrica dentro de una columna (entre los elementos de una dimensión).

```
SUM(metric)
```

| Argumento | Descripción |
|---|---|
| *métrica* | La métrica de la cual desea el valor total o la suma. |

## Recuento (Tabla) {#concept_2C6ED2B88AB74481BD130969FB071A41}

Devuelve un número, o recuento, de valores distintos de cero para una métrica dentro de una columna (el número de elementos únicos incluidos dentro de una dimensión).

```
COUNT(metric)
```

| Argumento | Descripción |
|---|---|
| *métrica* | La métrica que desea contar. |

## Exponente (Fila) {#concept_17554F9D234449FB8DDEE895816B3FF1}

Devuelve *e* elevado a la potencia de un número determinado. La constante *e* es igual a 2,71828182845904, la base del logaritmo natural. EXP es la inversa de LN, el logaritmo natural de un número.

```
EXP(metric)
```

| Argumento | Descripción |
|---|---|
| *métrica* | El exponente aplicado a la base *e*. |

## Exponenciación {#concept_941578534F1E4583B1BEB067C8113A21}

Operador de potencia

```
pow(x,y) = x<sup>y</sup> = x*x*x*… (y times)
```

## Media (Tabla) {#concept_F4FF950580304D0B99DA7FBB5DB8730A}

Devuelve la media aritmética, o el promedio, de una métrica en una columna.

```
MEAN(metric)
```

| Argumento | Descripción |
|---|---|
| *métrica* | La métrica de la cual desea la media. |

## Mediana (Tabla) {#concept_183EC31208524EDB8463D986DE2E895F}

Devuelve la mediana de una métrica en una columna. La mediana es el número central de un conjunto de números; es decir, la mitad de los valores son mayores o iguales que la mediana y la mitad son menores o iguales que la mediana.

```
MEDIAN(metric)
```

| Argumento | Descripción |
|---|---|
| *métrica* | La métrica de la cual desea la mediana. |

## Módulo {#concept_DE0825D7A51643219CB01F59667EA352}

El resto de la columna 1/columna 2, utilizando la división euclídea.

Devuelve el resto tras dividir x entre y.

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

Devuelve el percentil k-ésimo de los valores de una métrica. Puede utilizar esta función para establecer un umbral de aceptación. Por ejemplo, puede decidir si se examinan los elementos de la dimensión cuyo valor es superior al percentil 90.

```
PERCENTILE(metric,k)
```

| Argumento | Descripción |
| --- | --- |
| *métrica* | La columna de métrica que define la posición relativa. |
| *k* | El valor en porcentaje dentro del rango de 0 a 100, ambos incluidos. |

## Cuartil (Tabla) {#concept_BFD37F0F23A24AD181407142233FA151}

Devuelve el cuartil de los valores de una métrica. Por ejemplo, los cuartiles se pueden utilizar para encontrar el primer 25 % de los productos que generan los mayores ingresos. MINV, MEDIAN y MAXV devuelven el mismo valor que QUARTILE cuando el cuartil es igual a 0 (cero), 2 y 4, respectivamente.

```
QUARTILE(metric,quart)
```

| Argumento | Descripción |
| --- | --- |
| *métrica* | La métrica de la cual desea el valor de cuartil. |
| *cuarto* | Indica qué *valor debe devolver. |

&#42;Si *cuarto* = 0, QUARTILE devuelve el valor mínimo. Si *cuarto* = 1, QUARTILE muestra el primer cuartil (porcentaje 25). Si *cuarto* = 2, QUARTILE muestra el primer cuartil (porcentaje 50). Si *cuarto* = 3, QUARTILE muestra el primer cuartil (porcentaje 75). Si *cuarto* = 4, QUARTILE devuelve el valor máximo.

## Ronda {#concept_2F12F2A6ACD445A0A8FF648AE4D4CB9E}

Devuelve el entero más próximo a un valor determinado. Por ejemplo, si desea evitar los decimales en una moneda de un informe en los ingresos y un producto tiene el valor de 569,34 $, utilice la fórmula Round(*Revenue*) para redondear al dólar más próximo o 569 $. Un producto de 569,51 $ se redondeará al dólar más cercano o 570 $.

```
ROUND(metric)
```

| Argumento | Descripción |
|---|---|
| *entero* | La métrica que desee redondear. |

Redondear sin un parámetro de dígito es lo mismo que redondear con un parámetro de dígito de 0, es decir, redondear al entero más próximo. Con un parámetro de dígito devuelve ese número de dígitos a la derecha del decimal. Si el dígito es negativo, devuelve ceros a la izquierda del decimal.

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

Devuelve la raíz cuadrada positiva de un número. La raíz cuadrada de un número es el valor de dicho número elevado a la potencia de 1/2.

```
SQRT(metric)
```

| Argumento | Descripción |
| --- | --- |
| *entero* | La métrica de la cual desea la raíz cuadrada. |

## Desviación estándar (Tabla) {#concept_A383A8BCC6FA42D7B73F7C83997D782A}

Devuelve la desviación estándar, o la raíz cuadrada de la varianza, de una recopilación de datos de muestra.

La ecuación de STDEV es:

![](assets/std_dev.png)

Donde *x* es el valor de cada muestra (*métrica*), *x̄* es la media de la población y *n* es el tamaño de la población.

```
STDEV(metric)
```

| Argumento | Descripción |
| --- | --- |
| *métrica* | La métrica de la cual desee la desviación estándar. |

## Varianza (Tabla) {#concept_269751EDC5A34E689112AE16E04A11B0}

Devuelve la varianza de una recopilación de datos de muestra.

La ecuación de VARIANCE es:

![](assets/variance_eq.png)

Donde *x* es el valor de cada muestra (*métrica*), *x̄* es la media de la población y *n* es el tamaño de la población.

```
VARIANCE(metric)
```

| Argumento | Descripción |
| --- | --- |
| *métrica* | La métrica de la cual desea la varianza. |

Para calcular una varianza para ver una columna entera de números. A partir de una lista de números, calcule primero el promedio. Cuando tenga el promedio, examine cada entrada y realice lo siguiente:

1. Reste el promedio del número.
1. Multiplique el resultado por sí mismo.
1. Súmelo al total.

Cuando repita la operación sobre toda la columna, obtendrá un único total. A continuación, divida el total entre el número de elementos de la columna. El número resultante es la varianza de la columna. Esta es un número único, aunque aparece como una columna de números.

A modo de ejemplo, suponga que tiene una columna de tres elementos:

1

2

3

El promedio de esta columna es 2. La variación de la columna será ((1 - 2)<sup>2</sup> + (2 - 2)<sup>2</sup> + (3 - 2)<sup>2</sup>/3 = 2/3.

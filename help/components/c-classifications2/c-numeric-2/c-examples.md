---
description: Ejemplos para proporcionar orientación sobre la importación de clasificaciones numéricas 2.
subtopic: Classifications
title: Ejemplos
topic: Admin tools
uuid: 0553d07f-87c1-4372-90ce-7118a6393a01
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Ejemplos

Ejemplos para proporcionar orientación sobre la importación de clasificaciones numéricas 2.

<!-- 

c_example_1__rate.xml

 -->

En este caso, ha creado la clasificación en el [!UICONTROL Classification Conversion] administrador y desea importar los valores de enero:

| Clave | MyText | `~MyCost` | `~MyCost^~id~` | `~MyCost^~value~` |
|---|---|---|---|---|
| Product 1 | Text1 | `Cost1_jan_var` |  | `.2` |
| Product 2 | Text2 | `Cost2_jan_var` |  | `.3` |

| `~MyCost^~period~` | `~MyCost^~rate~` | `~MyCost^~hinge~` |
|---|---|---|
| 2010/01/01 - 2010/01/31 | ingresos | ingresos |
| 2010/01/01 - 2010/01/31 | ingresos | ingresos |

En enero, Product1 tenía un coste del 20% de sus ingresos (aparece en `~MyCost^~value~`) y Product2 tenía un coste del 30% de sus ingresos. Como está importando una fila nueva, `~MyCost^~id~` está en blanco.

## Resultado {#section_E0569289C9B34C479C7D2CD9ECBF866E}

Aquí se muestra un ejemplo de los resultados del informe:

Período: Ene 2010

Informe: Productos

| Productos | Ingresos | MyCost |
|---|---|---|
| Product 1 | $10,000.23 | $2000.05 |
| Product 2 | $9,000.04 | $2700.01 |

<!-- 

c_example_2__rate.xml

 -->

| Clave | MyText | `~MyCost` | `~MyCost^~id~` | `~MyCost^~value~` |
|---|---|---|---|---|
| Product 1 | Text1 | `Cost1_jan_var` | 1 | .2 |
| Product 2 | Text2 | `Cost2_jan_var` | 2 | .3 |
| Product 1 | Text1 | `Cost1_feb_var` |  | .15 |
| Product 2 | Text2 | `Cost2_feb_var` |  | .25 |

| `~MyCost^~period~` | `~MyCost^~rate~` | `~MyCost^~hinge~` |
|---|---|---|
| 2010/01/01 - 2010/01/31 | ingresos | ingresos |
| 2010/01/01 - 2010/01/31 | ingresos | ingresos |
| 2010/02/01 - 2010/02/28 | ingresos | ingresos |
| 2010/02/01 - 2010/02/28 | ingresos | ingresos |

En febrero, el coste del usuario para Product1 bajó al 15% de los ingresos y el de Product2 bajó al 25% de sus ingresos.

## Resultado {#section_23DF5353AC1B478C88647F222703352C}

Aquí se muestra un ejemplo de los resultados del informe:

Período: Ene 2010

Informe: Productos

| Productos | Ingresos | MyCost |
|---|---|---|
| Product 1 | $10,000.23 | $2000.05 |
| Product 2 | $9,000.04 | $2700.01 |

Período: Febrero de 2010

Informe: Productos

| Productos | Ingresos | MyCost |
|---|---|---|
| Product 1 | $15,500.75 | $2325.11 |
| Product 2 | $12,300.52 | $3075.13 |

Período: 1 de enero de 2010 - 28 de febrero de 2010

Informe: Productos

| Productos | Ingresos | MyCost |
|---|---|---|
| Product 1 | $25,500.98 | $4325.16 |
| Product 2 | $21,300.56 | $5,775.14 |

<!-- 

c_example_3__fixed.xml

 -->

Por lo tanto, importaría los siguientes datos:

| Clave | MyText | `~MyCost` | `~MyCost^~id~` | `~MyCost^~value~` |
|---|---|---|---|---|
| Product 1 | Text1 | `Cost1_mar_fixed` |  | 3000.00 |
| Product 2 | Text2 | `Cost2_jan_fixed` |  | 2.000,00 |

| `~MyCost^~period~` | `~MyCost^~rate~` | `~MyCost^~hinge~` |
|---|---|---|
| 2010/03/01 - 2010/03/31 | fijo | ninguno |
| 2010/03/01 - 2010/03/31 | fijo | ninguno |

## Resultado {#section_674B57ADB8284B878F9E670038C31464}

Aquí se muestra un ejemplo de los resultados del informe:

Período: Marzo de 2010

Informe: Productos

| Productos | Ingresos | MyCost |
|---|---|---|
| Product 1 | $11,023.75 | $3000.00 |
| Product 2 | $8,000.12 | $2.000,00 |

<!-- 

c_example_4__(advanced)_multiple_row_per_time_period.xml

 -->

En este ejemplo, se agrega un cargo de envío de 500 $ a Product1 para enero y un cargo de envío de 600 $ para febrero.

| Clave | MyText | `~MyCost` | `~MyCost^~id~` | `~MyCost^~value~` |
|---|---|---|---|---|
| Product 1 | Text1 | `Cost1_jan_var` | 1 | .2 |
| Product 1 | Text1 | `Cost2_jan_fixed` |  | 500 |
| Product 1 | Text1 | `Cost1_feb_var` | 2 | .15 |
| Product 1 | Text1 | `Cost2_feb_fixed` |  | 600 |

| `~MyCost^~period~` | `~MyCost^~rate~` | `~MyCost^~hinge~` |
|---|---|---|
| 2010/01/01 - 2010/01/31 | ingresos | ingresos |
| 2010/01/01 - 2010/01/31 | fijo | ninguno |
| 2010/02/01 - 2010/01/31 | ingresos | ingresos |
| 2010/02/01 - 2010/01/31 | fijo | ninguno |

Las filas importadas anteriormente tienen un ID, que indica que no son costes nuevos.

## Resultado {#section_2096084176614B9AA60F97D5853CB9EA}

Aquí se muestra un ejemplo de los resultados del informe:

Período: Ene 2010

Informe: Productos

| Productos | Ingresos | MyCost |
|---|---|---|
| Product 1 | $10,000.23 | $2500.05 |

>[!NOTE] esta función es para que los usuarios avanzados aproximen los valores. La información resultante no deberá tratarse como valores exactos.

<!-- 

c_example_5__identical_rate_hinge.xml

 -->

El siguiente ejemplo ilustra:

| Clave | MyText | `~MyCost` | `~MyCost^~id~` | `~MyCost^~value~` |
|---|---|---|---|---|
| Product 1 | Text1 | `Cost1_mar_var` |  | 1 |

| `~MyCost^~period~` | `~MyCost^~rate~` | `~MyCost^~hinge~` |
|---|---|---|
| 2010/03/01 - 2010/03/31 | pedido | pedido |

## Resultado {#section_39E24ECCC3B34C9AADC25572662750E5}

Aquí se muestra un ejemplo de los resultados del informe:

Período: Marzo de 2010

Informe: Productos por página

| Productos por página | Pedidos | MyCost |
|---|---|---|
| Product 1 | 1000 | $1000.00 |
| Página de inicio | 600 | $600 |
| Carro de compras | 400 | $400 |

<!-- 

c_example_5__fixed_no_hinge.xml

 -->

| Clave | MyText | `~MyCost` | `~MyCost^~id~` | `~MyCost^~value~` |
|---|---|---|---|---|
| Product 1 | Text1 | `Cost1_mar_fixed` |  | 3000.00 |
| Product 2 | Text2 | `Cost2_mar_fixed` |  | 2.000,00 |

| `~MyCost^~period~` | `~MyCost^~rate~` | `~MyCost^~hinge~` |
|---|---|---|
| 2010/03/01 - 2010/03/31 | fijo | ninguno |
| 2010/03/01 - 2010/03/31 | fijo | ninguno |

## Resultado {#section_7F5F5970077D4E14A5DC91495E23540D}

Aquí se muestra un ejemplo de los resultados del informe:

Período: Marzo de 2010

Informe: Productos por página

| Productos por página | Pedidos | MyCost |
|---|---|---|
| Product 1 | 1000 | $3000.00 |
| Página de inicio | 600 | 0 |
| Carro de compras | 400 | 0 |

<!-- 

c_example_7__fixed_hinge.xml

 -->

En este caso, importaría los siguientes datos:

| Clave | MyText | `~MyCost` | `~MyCost^~id~` | `~MyCost^~value~` |
|---|---|---|---|---|
| Product 1 | Text1 | `Cost1_mar_fixed` |  | 3000.00 |
| Product 2 | Text2 | `Cost2_mar_fixed` |  | 2.000,00 |

| `~MyCost^~period~` | `~MyCost^~rate~` | `~MyCost^~hinge~` |
|---|---|---|
| 2010/03/01 - 2010/03/31 | fijo | ingresos |
| 2010/03/01 - 2010/03/31 | fijo | ingresos |

## Resultado {#section_5953BB6FD0CE4EF69D1D60B8B1203431}

Aquí se muestra un ejemplo de los resultados del informe:

Período: Marzo de 2010

Informe: Productos por página

| Productos por página | Pedidos | MyCost |
|---|---|---|
| Product 1 | 1000 | $3000.00 |
| Página de inicio | 600 | $1800.00 |
| Carro de compras | 400 | $1200.00 |

<!-- 

c_example_7_continued__different_rate_hinge.xml

 -->

En este caso, se importan los siguientes datos de archivo:

| Clave | MyText | `~MyCost` | `~MyCost^~id~` | `~MyCost^~value~` |
|---|---|---|---|---|
| Product 1 | Text1 | Cost1_mar_fixed |  | 3 |

| `~MyCost^~period~` | `~MyCost^~rate~` | `~MyCost^~hinge~` |
|---|---|---|
| 2010/03/01 - 2010/03/31 | pedido | ingresos |

## Resultado {#section_6E2604D9A3B0455585EFF0F80FF54127}

Aquí se muestra un ejemplo de los resultados del informe:

Período: Marzo de 2010

Informe: Productos por página

| Productos por página | Pedidos | MyCost |
|---|---|---|
| Product 1 | 1000 | $3000.00 |
| Página de inicio | 600 | $1,000.00 |
| Carro de compras | 400 | $2,000.00 |


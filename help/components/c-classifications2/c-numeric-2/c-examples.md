---
description: Ejemplos que ofrecen información sobre cómo importar clasificaciones numéricas 2.
seo-description: Ejemplos que ofrecen información sobre cómo importar clasificaciones numéricas 2.
seo-title: Ejemplos
solution: Analytics
subtopic: Clasificaciones
title: Ejemplos
topic: Herramientas de administración
uuid: 0553 d 07 f -87 c 1-4372-90 ce -7118 a 6393 a 01
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Ejemplos

Ejemplos que ofrecen información sobre cómo importar clasificaciones numéricas 2.

<!-- 

c_example_1__rate.xml

 -->

En este caso, se ha creado la clasificación en el administrador de [!UICONTROL conversión de clasificaciones] y se desea importar los valores de enero:

| Clave | MyText | `~MyCost` | `~MyCost^~id~` | `~MyCost^~value~` |
|---|---|---|---|---|
| Product1 | Text1 | `Cost1_jan_var` |  | `.2` |
| Product2 | Text2 | `Cost2_jan_var` |  | `.3` |

| `~MyCost^~period~` | `~MyCost^~rate~` | `~MyCost^~hinge~` |
|---|---|---|
| 2010/01/01 - 2010/01/31 | revenue | revenue |
| 2010/01/01 - 2010/01/31 | revenue | revenue |

In January, Product1 had a cost of 20% of its revenue (shown in `~MyCost^~value~`) and Product2 had a cost of 30% of its revenue. Because you are importing a new row, `~MyCost^~id~` is blank.

## Resultado {#section_E0569289C9B34C479C7D2CD9ECBF866E}

Aquí se muestra un ejemplo del resultado del informe:

Periodo: Ene 2010

Informe: Productos

| Productos | Ingresos | MyCost |
|---|---|---|
| Product1 | 10 000,23 $ | 2.000,05 $ |
| Product2 | 9000,04 $ | 2.700,01 $ |

<!-- 

c_example_2__rate.xml

 -->

| Clave | MyText | `~MyCost` | `~MyCost^~id~` | `~MyCost^~value~` |
|---|---|---|---|---|
| Product1 | Text1 | `Cost1_jan_var` | 1 | .2 |
| Product2 | Text2 | `Cost2_jan_var` | 2 | .3 |
| Product1 | Text1 | `Cost1_feb_var` |  | .15 |
| Product2 | Text2 | `Cost2_feb_var` |  | .25 |

| `~MyCost^~period~` | `~MyCost^~rate~` | `~MyCost^~hinge~` |
|---|---|---|
| 2010/01/01 - 2010/01/31 | revenue | revenue |
| 2010/01/01 - 2010/01/31 | revenue | revenue |
| 2010/02/01 - 2010/02/28 | revenue | revenue |
| 2010/02/01 - 2010/02/28 | revenue | revenue |

En febrero, el coste del usuario para Product1 bajó al 15% de los ingresos y el de Product2 bajó al 25% de sus ingresos.

## Resultado {#section_23DF5353AC1B478C88647F222703352C}

Aquí se muestra un ejemplo del resultado del informe:

Periodo: Ene 2010

Informe: Productos

| Productos | Ingresos | MyCost |
|---|---|---|
| Product1 | 10 000,23 $ | 2.000,05 $ |
| Product2 | 9000,04 $ | 2.700,01 $ |

Periodo: Feb 2010

Informe: Productos

| Productos | Ingresos | MyCost |
|---|---|---|
| Product1 | 15 500,75 $ | 2.325,11 $ |
| Product2 | 12 300,52 $ | 3.075,13 $ |

Periodo: 1 de enero de 2010 - 28 de febrero de 2010

Informe: Productos

| Productos | Ingresos | MyCost |
|---|---|---|
| Product1 | 25 500,98 $ | 4.325,16 $ |
| Product2 | 21 300,56 $ | 5.775,14 $ |

<!-- 

c_example_3__fixed.xml

 -->

Por ello, importaría los siguientes datos:

| Clave | MyText | `~MyCost` | `~MyCost^~id~` | `~MyCost^~value~` |
|---|---|---|---|---|
| Product1 | Text1 | `Cost1_mar_fixed` |  | 3.000,00 |
| Product2 | Text2 | `Cost2_jan_fixed` |  | 2.000,00 |

| `~MyCost^~period~` | `~MyCost^~rate~` | `~MyCost^~hinge~` |
|---|---|---|
| 2010/03/01 - 2010/03/31 | fijo | ninguno |
| 2010/03/01 - 2010/03/31 | fijo | ninguno |

## Resultado {#section_674B57ADB8284B878F9E670038C31464}

Aquí se muestra un ejemplo del resultado del informe:

Periodo: Mar 2010

Informe: Productos

| Productos | Ingresos | MyCost |
|---|---|---|
| Product1 | 11 023,75 $ | 3.000,00 $ |
| Product2 | 8000,12 $ | 2.000,00 $ |

<!-- 

c_example_4__(advanced)_multiple_row_per_time_period.xml

 -->

En este ejemplo, se añade un cargo de envío de 500 $ a Product1 para enero y un cargo de envío de 600 $ para febrero.

| Clave | MyText | `~MyCost` | `~MyCost^~id~` | `~MyCost^~value~` |
|---|---|---|---|---|
| Product1 | Text1 | `Cost1_jan_var` | 1 | .2 |
| Product1 | Text1 | `Cost2_jan_fixed` |  | 500 |
| Product1 | Text1 | `Cost1_feb_var` | 2 | .15 |
| Product1 | Text1 | `Cost2_feb_fixed` |  | 600 |

| `~MyCost^~period~` | `~MyCost^~rate~` | `~MyCost^~hinge~` |
|---|---|---|
| 2010/01/01 - 2010/01/31 | revenue | revenue |
| 2010/01/01 - 2010/01/31 | fijo | ninguno |
| 2010/02/01 - 2010/01/31 | revenue | revenue |
| 2010/02/01 - 2010/01/31 | fijo | ninguno |

Las filas importadas anteriormente tienen un ID, que indica que no son costes nuevos.

## Resultado {#section_2096084176614B9AA60F97D5853CB9EA}

Aquí se muestra un ejemplo del resultado del informe:

Periodo: Ene 2010

Informe: Productos

| Productos | Ingresos | MyCost |
|---|---|---|
| Product1 | 10 000,23 $ | 2.500,05 $ |

>[!NOTE]
>
>Esta función es para que los usuarios avanzados aproximen los valores. La información resultante no deberá tratarse como valores exactos.

<!-- 

c_example_5__identical_rate_hinge.xml

 -->

Este ejemplo muestra lo siguiente:

| Clave | MyText | `~MyCost` | `~MyCost^~id~` | `~MyCost^~value~` |
|---|---|---|---|---|
| Product1 | Text1 | `Cost1_mar_var` |  | 1 |

| `~MyCost^~period~` | `~MyCost^~rate~` | `~MyCost^~hinge~` |
|---|---|---|
| 2010/03/01 - 2010/03/31 | order | order |

## Resultado {#section_39E24ECCC3B34C9AADC25572662750E5}

Aquí se muestra un ejemplo del resultado del informe:

Periodo: Mar 2010

Informe: Productos por página

| Productos por página | Pedidos | MyCost |
|---|---|---|
| Product1 | 1000 | 1.000,00 $ |
| Página principal | 600 | 600 $ |
| Carro de compras | 400 | 400 $ |

<!-- 

c_example_5__fixed_no_hinge.xml

 -->

| Clave | MyText | `~MyCost` | `~MyCost^~id~` | `~MyCost^~value~` |
|---|---|---|---|---|
| Product1 | Text1 | `Cost1_mar_fixed` |  | 3.000,00 |
| Product2 | Text2 | `Cost2_mar_fixed` |  | 2.000,00 |

| `~MyCost^~period~` | `~MyCost^~rate~` | `~MyCost^~hinge~` |
|---|---|---|
| 2010/03/01 - 2010/03/31 | fijo | ninguno |
| 2010/03/01 - 2010/03/31 | fijo | ninguno |

## Resultado {#section_7F5F5970077D4E14A5DC91495E23540D}

Aquí se muestra un ejemplo del resultado del informe:

Periodo: Mar 2010

Informe: Productos por página

| Productos por página | Pedidos | MyCost |
|---|---|---|
| Product1 | 1000 | 3.000,00 $ |
| Página principal | 600 | 0 |
| Carro de compras | 400 | 0 |

<!-- 

c_example_7__fixed_hinge.xml

 -->

En este caso, se importarían los siguientes datos:

| Clave | MyText | `~MyCost` | `~MyCost^~id~` | `~MyCost^~value~` |
|---|---|---|---|---|
| Product1 | Text1 | `Cost1_mar_fixed` |  | 3.000,00 |
| Product2 | Text2 | `Cost2_mar_fixed` |  | 2.000,00 |

| `~MyCost^~period~` | `~MyCost^~rate~` | `~MyCost^~hinge~` |
|---|---|---|
| 2010/03/01 - 2010/03/31 | fijo | revenue |
| 2010/03/01 - 2010/03/31 | fijo | revenue |

## Resultado {#section_5953BB6FD0CE4EF69D1D60B8B1203431}

Aquí se muestra un ejemplo del resultado del informe:

Periodo: Mar 2010

Informe: Productos por página

| Productos por página | Pedidos | MyCost |
|---|---|---|
| Product1 | 1000 | 3.000,00 $ |
| Página principal | 600 | 1.800,00 $ |
| Carro de compras | 400 | 1.200,00 $ |

<!-- 

c_example_7_continued__different_rate_hinge.xml

 -->

En este caso, se importan los siguientes datos de archivo:

| Clave | MyText | `~MyCost` | `~MyCost^~id~` | `~MyCost^~value~` |
|---|---|---|---|---|
| Product1 | Text1 | Cost1_mar_fixed |  | 3 |

| `~MyCost^~period~` | `~MyCost^~rate~` | `~MyCost^~hinge~` |
|---|---|---|
| 2010/03/01 - 2010/03/31 | order | revenue |

## Resultado {#section_6E2604D9A3B0455585EFF0F80FF54127}

Aquí se muestra un ejemplo del resultado del informe:

Periodo: Mar 2010

Informe: Productos por página

| Productos por página | Pedidos | MyCost |
|---|---|---|
| Product1 | 1000 | 3.000,00 $ |
| Página principal | 600 | 1000,00 $ |
| Carro de compras | 400 | 2000,00 $ |


---
description: Las reglas de clasificación buscan términos no clasificados de forma periódica. Cuando se encuentra una coincidencia de regla, las reglas agregan los términos automáticamente a las tablas de datos de clasificación. Las reglas de clasificación también permiten sobrescribir las claves existentes.
seo-description: Las reglas de clasificación buscan términos no clasificados de forma periódica. Cuando se encuentra una coincidencia de regla, las reglas agregan los términos automáticamente a las tablas de datos de clasificación. Las reglas de clasificación también permiten sobrescribir las claves existentes.
seo-title: Reglas de clasificación
solution: Analytics
subtopic: Clasificaciones
title: Reglas de clasificación
topic: Herramientas de administración
uuid: 08685919-216d-448b-b886-3adf5ff5405e
translation-type: tm+mt
source-git-commit: 646d6e01d0f0201c78117ee9bf9ff64fda9a026a

---


# Reglas de clasificación

Las reglas de clasificación buscan términos no clasificados de forma periódica. Cuando se encuentra una coincidencia de regla, las reglas agregan los términos automáticamente a las tablas de datos de clasificación. Las reglas de clasificación también permiten sobrescribir las claves existentes.

## Reglas de clasificación {#concept_CF2F64BD96454FBFAA84638FC7DEA263}

Las reglas de clasificación buscan términos no clasificados de forma periódica. Cuando se encuentra una coincidencia de regla, las reglas agregan los términos automáticamente a las tablas de datos de clasificación. Las reglas de clasificación también permiten sobrescribir las claves existentes.

**[!UICONTROL Analytics]** &gt; **[!UICONTROL Administración]** &gt; Generador de reglas **[!UICONTROL de clasificación]**

El Generador de reglas permite crear una *`classification rule set`*, que es una lista de *`classification rules`*. La regla que coincida con los criterios especificados realizará una acción.

Las reglas de clasificación resultan adecuadas para:

* **Correo electrónico** y **anuncios en pantalla**: al crear reglas de clasificación pueden agruparse campañas de anuncios en pantalla individuales, y esto permite comprobar los resultados de las campañas de visualización frente a las de correo electrónico.

* **Códigos de seguimiento**: con las reglas de clasificación pueden aplicarse categorías a los valores clave derivados de cadenas de códigos de seguimiento, y hacerlos coincidir con los criterios específicos definidos.
* **Términos de búsqueda**: las [expresiones regulares](../../../components/c-classifications2/crb/classification-quickstart-rules.md#concept_8A63F9BCF9484963962E14E6286D312D) y los comodines simplifican la clasificación de los términos de búsqueda. Por ejemplo: si un término de búsqueda contiene *`baseball`*, puede establecer una *`Sports League`* clasificación en *`MLB`*.

Por ejemplo, imaginemos el código de seguimiento siguiente para un ID de campaña de correo electrónico:

`em:Summer:2013:Sale`.

Pueden definirse un máximo de tres reglas en un conjunto de reglas para identificar los elementos de la cadena y, a continuación, clasificar los valores:

| Seleccionar tipo de regla | Introducir criterios de coincidencia | Configurar clasificación | Para |
|---|---|---|---|
| Comienza con | em: | Canal | Correo electrónico |
| Finaliza con | Venta | Tipo | Venta |
| Contiene | 2013 | Año | 2013 |

## Cómo procesar las reglas {#concept_A67A23F523844D37898583C632DB9D25}

Información relevante sobre cómo procesar las reglas de clasificación.

<!-- 

about_classification_rules.xml

 -->

* [Información relevante sobre las reglas](/help/components/c-classifications2/crb/classification-rule-builder.md)
* [¿En qué casos las reglas no clasifican claves?](/help/components/c-classifications2/crb/classification-rule-builder.md)
* [Acerca de la prioridad de las reglas](../../../components/c-classifications2/crb/classification-quickstart-rules.md#concept_93527FEB3C9B48FB96FB7DF857E5F980)

>[!NOTE]
>
>The [!UICONTROL Rule Builder] does not support Numeric 2 classifications.

## Información relevante sobre las reglas {#section_0BD46702FBEC4D98A4DD2EA0BD428046}

* Specify [group permissions](https://marketing.adobe.com/resources/help/en_US/reference/?f=groups) for classifications in [!UICONTROL Admin Tools].

* **Expresiones** regulares: La ayuda está disponible en Expresiones [regulares en Reglas](../../../components/c-classifications2/crb/classification-quickstart-rules.md#concept_8A63F9BCF9484963962E14E6286D312D)de clasificación.

* **Grupos de informes**: para elegir una clasificación, primero debe seleccionarse como mínimo un grupo de informes. No se podrá aplicar el grupo de informes hasta que se cree el conjunto de reglas y se asigne una variable.

   Para probar el conjunto de reglas, debe comprobarse el efecto que este ejerce sobre las claves del informe (la variable que se clasifica). (La [clave](../../../components/c-classifications2/c-classifications-importer/c-saint-data-files.md#concept_0B77B3079B5C414F9956058688990443) es la variable que se clasifica, o la primera columna de la tabla de carga de clasificaciones).

* **Prioridad de las reglas**: si una clave coincide con varias reglas que definen la misma clasificación (en la columna [!UICONTROL Configurar clasificación]), se utilizará la última de estas reglas. See [About Rule Priority](../../../components/c-classifications2/crb/classification-quickstart-rules.md#concept_93527FEB3C9B48FB96FB7DF857E5F980).

* **Límites en el número de reglas**: no se ha definido ningún límite para el número de reglas que pueden crearse. No obstante, un número de reglas elevado puede afectar al rendimiento del explorador.
* **Procesamiento**: Las reglas se procesan a intervalos regulares, según el volumen del tráfico relacionado con la clasificación.

   Las reglas activas se procesan cada cuatro horas y los datos de clasificación suelen examinarse de forma mensual. Las reglas comprueban automáticamente la existencia de nuevos valores y cargan las clasificaciones a través del importador.

* **Sobrescritura de las clasificaciones existentes**: consulte [¿En qué casos las reglas no clasifican las claves?](../../../components/c-classifications2/crb/classification-quickstart-rules.md#section_4481E88CA28246B6B19EA16E2D83A3A8) Si es necesario, puede eliminar o eliminar las clasificaciones existentes mediante el importador.

## ¿En qué casos las reglas no clasifican claves?{#section_4481E88CA28246B6B19EA16E2D83A3A8}

Cuando se activan las reglas, pueden sobrescribirse las clasificaciones existentes. En las situaciones siguientes, una regla de clasificación no clasifica ninguna [clave](../../../components/c-classifications2/c-classifications-importer/c-saint-data-files.md#concept_0B77B3079B5C414F9956058688990443) (variable) si:

* La clave ya se ha clasificado y no se selecciona [Sobrescriba las clasificaciones para](../../../components/c-classifications2/crb/classification-rule-definitions.md#overwrite_classifications).

   Las clasificaciones pueden sobrescribirse al [](../../../components/c-classifications2/crb/classification-quickstart-rules.md#task_86F216DFD2534FA181E64ABDF306782B) Agregar y activar una regla, y al activar una integración de Data Connectors. (En el caso de los Data Connectors, las reglas son creadas por socios en el Centro de desarrolladores y se muestran en la [!UICONTROL Clasificación del Generador de reglas]).

* Las claves clasificadas no aparecen en los datos una vez transcurrido el lapso de tiempo especificado al sobrescribir una clave, ni siquiera tras habilitar [Sobrescriba las clasificaciones para](../../../components/c-classifications2/crb/classification-rule-definitions.md#overwrite_classifications).
* La clave no se clasifica y nunca se transfiere a [!DNL Adobe Analytics] después del lapso de tiempo a partir de un mes antes.

   >[!NOTE]
   >
   >En los informes, las clasificaciones se aplican a cualquier intervalo de tiempo especificado, siempre que exista una clave. El intervalo de fecha de un informe no afecta a su generación.

![](assets/overwrite_keys.png)

## Expresiones regulares en las reglas de clasificación {#concept_8A63F9BCF9484963962E14E6286D312D}

Las expresiones regulares sirven para hacer coincidir los valores de cadena que tienen un mismo formato con una clasificación. Por ejemplo, puede crear una clasificación a partir de caracteres específicos de un código de seguimiento. Según se considere conveniente, pueden hacerse coincidir patrones de caracteres, palabras o caracteres determinados.

<!-- 

regex_classification_rules.xml

 -->

* [Expresión regular: ejemplo de código de seguimiento](../../../components/c-classifications2/crb/classification-quickstart-rules.md#section_2EF7951398EB4C2F8E52CEFAB4032669)
* [Expresión regular: clasificación de un carácter específico](../../../components/c-classifications2/crb/classification-quickstart-rules.md#section_5D300C03FA484BADACBFCA983E738ACF)
* [Expresiones regulares: hacer coincidir códigos de seguimiento de distinta longitud](../../../components/c-classifications2/crb/classification-quickstart-rules.md#section_E86F5BF5C2F44ABC8FFCE3EA67EE3BB2)
* [Expresiones regulares: ejemplo de "No contiene"](../../../components/c-classifications2/crb/classification-quickstart-rules.md#section_FCA88A612A4E4B099458E3EF7B60B59C)
* [Expresiones regulares: tabla de referencia](../../../components/c-classifications2/crb/classification-quickstart-rules.md#section_0211DCB1760042099CCD3ED7A665D716)

>[!NOTE]
>
>La práctica recomendada es que las expresiones regulares se adapten mejor a los códigos de seguimiento que utilizan delimitadores.

## Expresión regular: ejemplo de código de seguimiento {#section_2EF7951398EB4C2F8E52CEFAB4032669}

>[!NOTE]
>
>If the tracking code is URL encoded, it will **not** be classified by the Rules Builder.

En este ejemplo, imaginemos que debe clasificarse el ID de campaña siguiente:

[!UICONTROL Sample Key]: `em:JuneSale:20130601`

Los elementos del código de seguimiento que deben clasificarse son:

* `em` = email
* `JuneSale` = nombre de campaña
* `20130601` = date

[!UICONTROL Regular Expression]: `^(.+)\:(.+)\:(.+)$`

Correlación entre la expresión regular y el ID de campaña:

![](assets/regex.png)

[!UICONTROL Grupos de coincidencias]: muestra la correspondencia entre la expresión regular y los caracteres del ID de campaña para poder clasificar una posición en este ID.

![](assets/regex_tracking_code.png)

This example tells the rule that the campaign date `20140601` is at the third group `(.+)`, identified by `$3`.

**[!UICONTROL Generador de reglas]**

En el [!UICONTROL Generador de reglas], la regla debe configurarse como se muestra:

| Seleccionar tipo de regla | Introducir criterios de coincidencia | Configurar clasificación | Para |
|---|---|---|---|
| Expresión regular | &amp;Hat;(.+)\:(.+)\:(.+)$ | Fecha de campaña | $3 |

**Sintaxis**

| Expresión regular | Cadena o resultados de coincidencias | Grupos de coincidencias correspondientes |
|--- |--- |--- |
| `^(.+)\:(.+)\:(.+)$` | em:JuneSale:20130601 | `$0`:: em:JuneSale:20130601 `$1`: em `$2`: JuneSale `$3`: 20130601 |
| Creación de la sintaxis | `^` = inicia la línea () = agrupa los caracteres y permite extraer los caracteres coincidentes entre paréntesis.  `(.+)` = captura uno ( . ) y ( + ) ya \ = inicio de una cadena.  `$` = indica que el carácter (o grupo de caracteres) precedente es el último de la línea. |

Consulte [Expresiones regulares: tabla de referencia](../../../components/c-classifications2/crb/classification-quickstart-rules.md#section_0211DCB1760042099CCD3ED7A665D716) para obtener más información sobre el significado de los caracteres de las expresiones regulares.

## Expresión regular: clasificación de un carácter específico {#section_5D300C03FA484BADACBFCA983E738ACF}

Una de las utilidades de las expresiones regulares es clasificar un carácter específico de una cadena de caracteres. Por ejemplo, imaginemos que el código de seguimiento siguiente contiene dos caracteres importantes:

[!UICONTROL Sample Key]: `4s3234`

* `4` = nombre de marca
* `s` = identifica un motor de búsqueda (por ejemplo, Google)

![](assets/regex_char_position.png)

**[!UICONTROL Generador de reglas]**

En el [!UICONTROL Generador de reglas], la regla debe configurarse como se muestra:

| Seleccionar tipo de regla | Introducir criterios de coincidencia | Configurar clasificación | Para |
|--- |--- |--- |--- |
| Expresión regular | `^.(s).*$` | Marca y motor | `$0` Captura los dos primeros caracteres para el nombre de marca y el motor de búsqueda. |
| Expresión regular | `^.(s).*$` | Motor de búsqueda | `$1` Captura el segundo carácter de Google. |

## Expresiones regulares: hacer coincidir códigos de seguimiento de distinta longitud {#section_E86F5BF5C2F44ABC8FFCE3EA67EE3BB2}

En este ejemplo se muestra cómo identificar caracteres específicos entre delimitadores de dos puntos si se dispone de códigos de seguimiento de distinta longitud. Adobe recomienda utilizar una expresión regular para código de seguimiento.

Claves de muestra:

* `a:b`
* `a:b:c`
* `a:b:c:d`

**Sintaxis**

![](assets/regex_b.png)

![](assets/regex_varying_length.png)

**[!UICONTROL Generador de reglas]**

En el [!UICONTROL Generador de reglas], la regla debe configurarse como se muestra:

| Seleccionar tipo de regla | Introducir criterios de coincidencia | Configurar clasificación | Para |
|--- |--- |--- |--- |
| Expresión regular Para cadena de coincidencia a:b | `^([^\:]+)\:([^\:]+)$` | a | `$1` |
| Expresión regular Para cadena de coincidencia a:b | `^([^\:]+)\:([^\:]+)$` | b | `$2` |
| Expresión regular Para cadena de coincidencia a:b:c | `^([^\:]+)\:([^\:]+)\:([^\:]+)$` | a | `$1` |
| Expresión regular Para cadena de coincidencia a:b:c | `^([^\:]+)\:([^\:]+)\:([^\:]+)$` | b | `$2` |
| Expresión regular Para cadena de coincidencia a:b:c | `^([^\:]+)\:([^\:]+)\:([^\:]+)$` | c | `$3` |
| Expresión regular Para cadena de coincidencia a:b:c:d | `^([^\:]+)\:([^\:]+)\:([^\:]+)\:([^\:])$` | d | `$4` |

## Expresiones regulares: ejemplo de "No contiene"{#section_FCA88A612A4E4B099458E3EF7B60B59C}

En este ejemplo se muestra una expresión regular que coincide con todas las cadenas que no contienen caracteres específicos (en este caso, `13`).

Expresión regular:

`^(?!.*13.*).*$`

Cadenas de prueba:

```
a:b:
a:b:1313
c:d:xoxo
c:d:yoyo
```

Resultados de coincidencias:

```
a:b:
c:d:xoxo
c:d:yoyo
```

In this result, `a:b:1313` does not indicate a match.

## Expresiones regulares: tabla de referencia {#section_0211DCB1760042099CCD3ED7A665D716}

| Expresión | Descripción |
|---|---|
| `(?ms)` | Hace que toda la expresión regular coincida con una entrada de varias líneas, lo que permite que el comodín coincida con cualquier carácter de línea nueva. |
| (`?i`) | Hace que toda la expresión regular no distinga mayúsculas de minúsculas. |
| [`abc`] | Un solo carácter de: a, b o c. |
| [`^abc`] | Cualquier carácter individual distinto de: a, b o c. |
| [`a-z`] | Cualquier carácter individual del intervalo a-z. |
| [`a-zA-Z`] | Cualquier carácter individual del intervalo a-z o A-Z. |
| `^` | Inicio de línea (coincide con el comienzo de la línea). |
| `$` | Coincide con el final de la línea (o antes de una nueva línea al final). |
| `\A` | Inicio de cadena. |
| `\z` | Final de cadena. |
| `.` | Coincide cualquier carácter (excepto una nueva línea). |
| `\s` | Cualquier carácter de espacio en blanco. |
| `\S` | Cualquier carácter que no sea un espacio en blanco. |
| `\d` | Cualquier dígito. |
| `\D` | Cualquier carácter que no sea un dígito. |
| `\w` | Cualquier carácter de palabra (letra, número o guión bajo). |
| `\W` | Cualquier carácter que no sea de palabra. |
| `\b` | Cualquier límite de palabra. |
| `(...)` | Capturar todo lo incluido. |
| `(a|b)` | a o b. |
| `a?` | Cero o uno de a. |
| `a*` | Cero o más de a. |
| `a+` | Uno o más de a. |
| `a{3}` | Exactamente 3 de a. |
| `a{3,}` | 3 o más de a. |
| `a{3,6}` | Entre 3 y 6 de a. |

Un buen recurso para probar la validez de la expresión regular es https://rubular.com/.

## Acerca de la prioridad de las reglas {#concept_93527FEB3C9B48FB96FB7DF857E5F980}

Si una clave que define la misma columna de clasificación que se muestra en la columna [!UICONTROL Configurar clasificación] coincide con varias reglas, se utilizará la última. En este caso puede resultar interesante clasificar los artículos de mayor relevancia al final del conjunto de reglas.

<!-- 

rule_priority.xml

 -->

Si se crean varias reglas que no comparten clasificación, el orden de procesamiento no es relevante.

A continuación se muestra un ejemplo de regla de término de búsqueda que clasifica los tipos de búsqueda por un atleta:

| Número de regla | Tipo de regla | Coincidencias | Configurar clasificación | Para |
|---|---|---|---|---|
| 1 | Contiene | Cowboys | Tipo de búsqueda | Equipo |
| 2 | Contiene | Fantasy | Tipo de búsqueda | Fantasy |
| 3 | Contiene | Romo | Tipo de búsqueda | Jugador |

Si un usuario busca *`Cowboys fantasy Tony Romo`*, the term *`Player`* is classified, because it matches the last given classification shown in the Set Classification column.

Del mismo modo, supongamos que se configuran hasta dos reglas en un conjunto para los términos de búsqueda siguientes:

| Número de regla | Tipo de regla | Coincidencias | Configurar clasificación | Para |
|---|---|---|---|---|
| 1 | Contiene | Cowboys | Ciudad | Dallas |
| 2 | Contiene | Broncos | Ciudad | Denver |

Un usuario busca *`Cowboys vs. Broncos`*. Si el Generador de reglas encuentra un conflicto en la coincidencia de reglas, se aplicará a la búsqueda la clasificación de la segunda regla (Denver).

## Add a Classification Rule to a Rule Set {#task_86F216DFD2534FA181E64ABDF306782B}

<!-- 

t_classification_rule.xml

 -->

Instrucciones sobre cómo agregar o editar una regla de clasificación.

Para agregar nuevas reglas, debe establecerse la coincidencia entre una condición y una clasificación. Seguidamente, debe especificarse la acción.

>[!NOTE]
>
>En este procedimiento, debe aplicar las reglas a uno o más grupos de informes. El número recomendado de reglas por conjunto de reglas está entre 500 y 1000, aunque no hay límites. Si el número de reglas supera las 100, considere la posibilidad de simplificar el conjunto de reglas mediante [subclasificaciones](../../../components/c-classifications2/c-sub-classifications.md#concept_19EE5513A7DC43C38CC396E96F306CFE).

1. [Crear un conjunto](../../../components/c-classifications2/crb/classification-rule-set.md#task_86F216DFD2534FA181E64ABDF306782B) de reglas de clasificación.
1. On the rule set page, click **[!UICONTROL Add Rule]**.

   ![](assets/add_rule.png)

1. Next to **[!UICONTROL Report Suites]**, click **[!UICONTROL Add Suites]** to specify one or more report suites to assign to this rule set.

   Se muestra la página **[!UICONTROL Seleccionar grupos de informes].**

   >[!NOTE]
   Los grupos de informes se muestran en esta página *`only`* cuando se cumplen las siguientes condiciones:        &gt;

   * Los grupos de informes tienen como mínimo una clasificación definida para la variable en [!UICONTROL Herramientas de administración].
   (Consulte *`Variable`* en Conjuntos [de reglas de](../../../components/c-classifications2/crb/classification-rule-set.md#concept_CD3D510F5070486584F3BB535AE41524) clasificación para obtener una explicación sobre este requisito previo).

   * Ha seleccionado el grupo de informes en la página Grupos **[!UICONTROL de informes]** disponibles, que se muestra después de hacer clic en [Agregar conjunto](/help/components/c-classifications2/crb/classification-rule-set.md) de reglas para crear el conjunto de reglas.


1. Especifique si desea sobrescribir los valores existentes:

   | **Las reglas sobrescriben los valores existentes** | (Configuración predeterminada) Sobrescriba siempre las claves de clasificación existentes, incluidas las clasificaciones cargadas mediante el importador (SAINT). |
   |---|---|
   | **Las reglas solo sobrescriben los valores no establecidos** | Rellene solo las celdas vacías (no establecidas). Las clasificaciones existentes no cambiarán. |

1. [Defina la regla o las reglas](../../../components/c-classifications2/crb/classification-rule-definitions.md#section_4A5BF384EEEE4994B6DC888339833529).

   ![Resultado de los pasos](assets/classification_rules_page.png)

   Para obtener ejemplos de creación de reglas, consulte Generador [de reglas de](/help/components/c-classifications2/crb/classification-rule-builder.md) clasificación y Expresiones [regulares en Reglas](../../../components/c-classifications2/crb/classification-quickstart-rules.md#concept_8A63F9BCF9484963962E14E6286D312D)de clasificación.

   >[!NOTE]
   >
   >Si una clave coincide con varias reglas que establecen la misma clasificación (en la columna Configurar clasificación), se utiliza la última regla que coincida con la clasificación. See **About Rule Priority** above for more information about sorting rules.

1. [Pruebe el conjunto de reglas](../../../components/c-classifications2/crb/classification-quickstart-rules.md#task_618A1E7CC8664E728F312250E8367158).
1. After testing, click **[!UICONTROL Active]** to validate and activate the rule.

   Al activar una regla, se genera y se carga automáticamente el archivo.

   Field definitions: See [Classification Rule Builder](../../../components/c-classifications2/crb/classification-rule-definitions.md#concept_6CAEFB1CA4564E2CA5808097C11EF468) for complete definitions of interface options on this page.

## Test a Classification Rule Set {#task_618A1E7CC8664E728F312250E8367158}

<!-- 

t_classifications_test_rule.xml

 -->

Instrucciones sobre cómo probar un conjunto de reglas o de reglas de clasificación. Al ejecutar una prueba se comprueban todas las reglas de un conjunto.

1. [Crear un conjunto](../../../components/c-classifications2/crb/classification-rule-set.md#task_86F216DFD2534FA181E64ABDF306782B) de reglas de clasificación.
1. En el [!UICONTROL Generador de reglas de clasificación], haga clic en el nombre del conjunto de reglas.
1. Asegúrese de que el conjunto de reglas esté asociado con un grupo de informes.
1. On the rule editor, click **[!UICONTROL Test Rule Set]**.

   ![Resultado de los pasos](assets/classification_test_rule_set.png)

1. Escriba o pegue claves de prueba en el campo [!UICONTROL Claves de muestra.]

   Entre las claves de muestra se encuentran:

   * Códigos de seguimiento
   * Palabras clave o expresiones de búsqueda
   Consulte [Expresiones regulares en reglas de clasificación](../../../components/c-classifications2/crb/classification-quickstart-rules.md#concept_8A63F9BCF9484963962E14E6286D312D) para obtener información sobre pruebas de expresiones regulares.
1. Click **[!UICONTROL Run Test]**.

   Las reglas que coinciden se muestran en la tabla [!UICONTROL Resultados].
1. (Optional) Click **[!UICONTROL Activate]** to activate the rule, and to overwrite existing classifications.

   Consulte para obtener más información sobre el uso de reglas para sobrescribir clasificaciones existentes.

## Validate and Activate Classification Rules {#task_2B4FA41F1EE64F4AAC6170C5EFC066AC}

<!-- 

t_validate_rules.xml

 -->

Instrucciones sobre cómo validar y activar reglas de clasificación.

1. [Cree un conjunto](../../../components/c-classifications2/crb/classification-rule-set.md#task_86F216DFD2534FA181E64ABDF306782B) de reglas de clasificación y luego [agregue reglas](../../../components/c-classifications2/crb/classification-quickstart-rules.md#task_86F216DFD2534FA181E64ABDF306782B) de clasificación al conjunto.
1. On the rule editor, click **[!UICONTROL Activate]**.

   ![](assets/overwrite_keys.png)

1. (Optional) To overwrite classifications, enable **[!UICONTROL Overwrite classifications for]** *`<selection>`*.

   Esta opción permite sobrescribir las clasificaciones existentes de las claves afectadas.

   Consulte la [página Reglas](../../../components/c-classifications2/crb/classification-rule-definitions.md#section_4A5BF384EEEE4994B6DC888339833529) para ver una definición de esta opción.

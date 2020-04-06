---
description: Las reglas de clasificación buscan términos no clasificados de forma regular. Si se encuentra una coincidencia de regla, las reglas agregan los términos automáticamente a las tablas de datos de clasificación. También puede utilizar reglas de clasificación para sobrescribir claves existentes.
subtopic: Classifications
title: Reglas de clasificación
topic: Admin tools
uuid: 08685919-216d-448b-b886-3adf5ff5405e
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Reglas de clasificación

Las reglas de clasificación buscan términos no clasificados de forma regular. Si se encuentra una coincidencia de regla, las reglas agregan los términos automáticamente a las tablas de datos de clasificación. También puede utilizar reglas de clasificación para sobrescribir claves existentes.

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Classification Rule Builder]**

El Generador de reglas permite crear una *`classification rule set`*, que es una lista de *`classification rules`*. Una regla coincide con los criterios especificados y, a continuación, realiza una acción.

Las reglas de clasificación son convenientes para:

* **Correo electrónico** y anuncios **** en pantalla: Cree reglas de clasificación para agrupar campañas de anuncios en pantalla individuales de modo que pueda obtener información sobre el rendimiento de las campañas de visualización con respecto a las campañas de correo electrónico.

* **Códigos** de seguimiento: Cree reglas de clasificación para categorizar los valores clave derivados de cadenas en códigos de seguimiento y hacerlos coincidir con los criterios específicos que defina.
* **Términos de búsqueda**: las  [expresiones regulares](/help/components/c-classifications2/crb/classification-quickstart-rules.md) y los comodines simplifican la clasificación de los términos de búsqueda. Por ejemplo, si un término de búsqueda contiene *`baseball`*, puede establecer una *`Sports League`* clasificación en *`MLB`*.

Por ejemplo, imaginemos el código de seguimiento siguiente para un ID de campaña de correo electrónico:

`em:Summer:2013:Sale`.

Pueden definirse un máximo de tres reglas en un conjunto de reglas para identificar los elementos de la cadena y, a continuación, clasificar los valores:

| Seleccionar tipo de regla | Introducir criterios de coincidencia | Configurar clasificación | Hasta |
|---|---|---|---|
| Comienza con | em: | Canal | Correo electrónico |
| Finaliza con | Venta | Tipo | Venta |
| Contiene | 2013 | Año | 2013 |

## Cómo procesar las reglas {#how-rules-are-processed}

Información importante sobre cómo se procesan las reglas de clasificación.

<!-- 

about_classification_rules.xml

 -->

* [Información importante sobre las reglas](/help/components/c-classifications2/crb/classification-rule-builder.md)
* [¿Cuándo las reglas no clasifican las claves?](/help/components/c-classifications2/crb/classification-rule-builder.md)
* [Acerca de la prioridad de las reglas](/help/components/c-classifications2/crb/classification-quickstart-rules.md)

>[!NOTE] El [!UICONTROL Rule Builder] no admite clasificaciones numéricas 2.

## Información importante sobre las reglas

* Especifique los permisos [de](https://marketing.adobe.com/resources/help/es_ES/reference/groups.html) grupo para las clasificaciones en [!UICONTROL Admin Tools].

* **Expresiones regulares**: La ayuda está disponible en [Expresiones regulares en Reglas de clasificación](/help/components/c-classifications2/crb/classification-quickstart-rules.md).

* **Grupos** de informes: No puede elegir una clasificación hasta que se seleccione por lo menos un grupo de informes. No puede aplicar el grupo de informes hasta que no haya creado el conjunto de reglas y asignado una variable.

   Cuando pruebe el conjunto de reglas, utilice las claves (la variable que se está clasificando) del informe para ver cómo se verán afectadas por el conjunto de reglas. (The [key](/help/components/c-classifications2/c-classifications-importer/c-saint-data-files.md) is the variable being classified, or the first column in the classification upload table.)

* **Prioridad** de regla: Si una clave coincide con varias reglas que establecen la misma clasificación (en la [!UICONTROL Set Classification] columna), se utiliza la última regla que coincida con la clasificación. Consulte [Acerca de la prioridad de las reglas](/help/components/c-classifications2/crb/classification-quickstart-rules.md).

* **Límites en el número de reglas**: No existe ningún límite establecido para el número de reglas que puede crear. Sin embargo, un gran número de reglas puede afectar al rendimiento del explorador.
* **Procesamiento**: Las reglas se procesan a intervalos frecuentes, según el volumen de tráfico relacionado con la clasificación.

   Las reglas activas se procesan cada cuatro horas, y los datos de clasificación suelen examinarse un mes después. Las reglas comprueban automáticamente la existencia de nuevos valores y cargan las clasificaciones mediante el importador.

* **Sobrescritura de las clasificaciones existentes**: consulte [¿En qué casos las reglas no clasifican las claves?](/help/components/c-classifications2/crb/classification-quickstart-rules.md) Si es necesario, puede eliminar las clasificaciones existentes mediante el importador.

## ¿Cuándo las reglas no clasifican las claves?

Al activar las reglas, puede sobrescribir las clasificaciones existentes. En las situaciones siguientes, una regla de clasificación no clasifica ninguna  [clave](/help/components/c-classifications2/c-classifications-importer/c-saint-data-files.md) (variable) si:

* La clave ya se ha clasificado y no se selecciona [Sobrescriba las clasificaciones para](/help/components/c-classifications2/crb/classification-rule-definitions.md).

   Las clasificaciones pueden sobrescribirse al  [ Agregar y activar](/help/components/c-classifications2/crb/classification-quickstart-rules.md) una regla, y al activar una integración de Data Connectors. (En el caso de los conectores de datos, los socios crean las reglas en el Centro de desarrollo y se muestran en la [!UICONTROL Classification Rule Builder]).

* Una clave clasificada no ha aparecido en los datos después de un intervalo de tiempo especificado al sobrescribir una clave, incluso después de habilitar [Sobrescribir clasificaciones](/help/components/c-classifications2/crb/classification-rule-definitions.md).
* La clave no se clasifica y nunca se transfiere a [!DNL Adobe Analytics] después del lapso de tiempo a partir de un mes antes.

   >[!NOTE]
   >
   >En los informes, las clasificaciones se aplican a cualquier lapso de tiempo especificado, siempre que exista una clave. El intervalo de fecha de un informe no afecta a su generación.

![](assets/overwrite_keys.png)

## Expresiones regulares en las reglas de clasificación {#regex-in-classification-rules}

Utilice expresiones regulares para hacer coincidir valores de cadena formateados de forma coherente con una clasificación. Por ejemplo, puede crear una clasificación a partir de caracteres específicos en un código de seguimiento. Puede hacer coincidir determinados caracteres, palabras o patrones de caracteres.

<!-- 

regex_classification_rules.xml

 -->

* [Expresión regular: ejemplo de código de seguimiento](/help/components/c-classifications2/crb/classification-quickstart-rules.md#section_2EF7951398EB4C2F8E52CEFAB4032669)
* [Expresión regular: clasificación de un carácter específico ](/help/components/c-classifications2/crb/classification-quickstart-rules.md#section_5D300C03FA484BADACBFCA983E738ACF)
* [Expresiones regulares: hacer coincidir códigos de seguimiento de distinta longitud](/help/components/c-classifications2/crb/classification-quickstart-rules.md#section_E86F5BF5C2F44ABC8FFCE3EA67EE3BB2)
* [Expresiones regulares: ejemplo de &quot;No contiene&quot; ](/help/components/c-classifications2/crb/classification-quickstart-rules.md#section_FCA88A612A4E4B099458E3EF7B60B59C)
* [Expresiones regulares: tabla de referencia](/help/components/c-classifications2/crb/classification-quickstart-rules.md#section_0211DCB1760042099CCD3ED7A665D716)

>[!NOTE] Como práctica recomendada, las expresiones regulares funcionan mejor con los códigos de seguimiento con delimitadores.

## Expresión regular: ejemplo de código de seguimiento {#section_2EF7951398EB4C2F8E52CEFAB4032669}

>[!NOTE] Si el código de seguimiento tiene codificación URL, el Generador de reglas **no** lo clasificará.

En este ejemplo, imaginemos que debe clasificarse el ID de campaña siguiente:

[!UICONTROL Sample Key]: `em:JuneSale:20130601`

Los elementos del código de seguimiento que deben clasificarse son:

* `em` = email
* `JuneSale` = Nombre de la campaña
* `20130601` = date

[!UICONTROL Regular Expression]: `^(.+)\:(.+)\:(.+)$`

Correlación entre la expresión regular y el ID de campaña:

![](assets/regex.png)

[!UICONTROL Match Groups]:: Muestra cómo se corresponde la expresión normal con los caracteres de ID de campaña, para poder clasificar una posición en el ID de campaña.

![](assets/regex_tracking_code.png)

Este ejemplo indica a la regla que la fecha de la campaña `20140601` se encuentra en el tercer grupo `(.+)`, identificado por `$3`.

**[!UICONTROL Rule Builder]**

In the [!UICONTROL Rule Builder], configure the rule as follows:

| Seleccionar tipo de regla | Introducir criterios de coincidencia | Configurar clasificación | Hasta |
|---|---|---|---|
| Expresión regular | &amp;Hat;(.+)\:(.+)\:(.+)$ | Fecha de Campaña | $3 |

**Sintaxis**

| Expresión regular | Cadena o resultado de coincidencia | Grupos de coincidencias correspondientes |
|--- |--- |--- |
| `^(.+)\:(.+)\:(.+)$` | em:JuneSale:20130601 | `$0`: em:JuneSale:20130601  `$1`: em  `$2`: JuneSale  `$3`: 20130601 |
| Creación de la sintaxis | `^` = comienza la línea  () = agrupa los caracteres y permite extraer los coincidentes entre paréntesis.  `(.+)` = captura uno ( . ) carácter y ( + ) más  \ = inicio de una cadena.  `$` = indica que el carácter (o grupo de caracteres) precedente es el último de la línea. |

Consulte [Expresiones regulares: tabla de referencia](/help/components/c-classifications2/crb/classification-quickstart-rules.md#section_0211DCB1760042099CCD3ED7A665D716) para obtener más información sobre el significado de los caracteres de las expresiones regulares.

## Expresión regular: clasificación de un carácter específico  {#section_5D300C03FA484BADACBFCA983E738ACF}

Una forma de utilizar una expresión normal es clasificar un carácter específico en una cadena de caracteres. Por ejemplo, supongamos que el siguiente código de seguimiento contiene dos caracteres importantes:

[!UICONTROL Sample Key]: `4s3234`

* `4` = nombre de la marca.
* `s` = identifica un motor de búsqueda (por ejemplo, Google)

![](assets/regex_char_position.png)

**[!UICONTROL Rule Builder]**

In the [!UICONTROL Rule Builder], configure the rule as follows:

| Seleccionar tipo de regla | Introducir criterios de coincidencia | Configurar clasificación | Hasta |
|--- |--- |--- |--- |
| Expresión regular | `^.(s).*$` | Marca y motor | `$0` (Registra los dos primeros caracteres del nombre de la marca y el motor de búsqueda.) |
| Expresión regular | `^.(s).*$` | Motor de búsqueda | `$1` (Registra el segundo carácter de Google.) |

## Expresiones regulares: hacer coincidir códigos de seguimiento de distinta longitud {#section_E86F5BF5C2F44ABC8FFCE3EA67EE3BB2}

Este ejemplo muestra cómo identificar caracteres específicos entre delimitadores de dos puntos cuando tiene códigos de seguimiento de distintas longitudes. Adobe recomienda utilizar una expresión regular para cada código de seguimiento.

Claves de muestra:

* `a:b`
* `a:b:c`
* `a:b:c:d`

**Sintaxis**

![](assets/regex_b.png)

![](assets/regex_varying_length.png)

**[!UICONTROL Rule Builder]**

In the [!UICONTROL Rule Builder], configure the rule as follows:

| Seleccionar tipo de regla | Introducir criterios de coincidencia | Configurar clasificación | Hasta |
|--- |--- |--- |--- |
| Expresión regular: Para cadena de coincidencia a:b | `^([^\:]+)\:([^\:]+)$` | a | `$1` |
| Expresión regular: Para cadena de coincidencia a:b | `^([^\:]+)\:([^\:]+)$` | b | `$2` |
| Expresión regular: Para la cadena de coincidencia a:b:c | `^([^\:]+)\:([^\:]+)\:([^\:]+)$` | a | `$1` |
| Expresión regular: Para la cadena de coincidencia a:b:c | `^([^\:]+)\:([^\:]+)\:([^\:]+)$` | b | `$2` |
| Expresión regular: Para la cadena de coincidencia a:b:c | `^([^\:]+)\:([^\:]+)\:([^\:]+)$` | c | `$3` |
| Expresión regular: Para la cadena de coincidencia a:b:c:d | `^([^\:]+)\:([^\:]+)\:([^\:]+)\:([^\:])$` | d | `$4` |

## Expresiones regulares: ejemplo de &quot;No contiene&quot; {#section_FCA88A612A4E4B099458E3EF7B60B59C}

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

Resultados de la coincidencia:

```
a:b:
c:d:xoxo
c:d:yoyo
```

En este resultado, `a:b:1313` no indica una coincidencia.

## Expresiones regulares: tabla de referencia {#section_0211DCB1760042099CCD3ED7A665D716}

| Expresión | Descripción |
|---|---|
| `(?ms)` | Hace que toda la expresión regular coincida con una entrada de varias líneas, permitiendo que el . comodín que coincida con cualquier carácter de nueva línea |
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
| `(a|b)` | a o b |
| `a?` | Cero o uno de a. |
| `a*` | Cero o más de a. |
| `a+` | Uno o más de a. |
| `a{3}` | Exactamente 3 de a. |
| `a{3,}` | 3 o más de a. |
| `a{3,6}` | Entre 3 y 6 de a. |

Se ofrece un buen recurso para probar la validez de las expresiones regulares en https://rubular.com/.

## Acerca de la prioridad de las reglas

Si una clave coincide con varias reglas y establece la misma columna de clasificación que se muestra en la columna, se utiliza la última regla. [!UICONTROL Set Classification] Como tal, es posible que desee clasificar el último elemento más importante del conjunto de reglas.

<!-- 

rule_priority.xml

 -->

Si crea varias reglas que no comparten la misma clasificación, el orden de procesamiento no importa.

Lo que sigue a un ejemplo de regla de término de búsqueda que clasifica los tipos de búsqueda de un atleta:

| Número de regla | Tipo de regla | Buscar coincidencias | Configurar clasificación | Hasta |
|---|---|---|---|---|
| 1 | Contiene | Cowboys | Tipo de búsqueda | Equipo |
| 2 | Contiene | Fantasy | Tipo de búsqueda | Fantasy |
| 3 | Contiene | Romo | Tipo de búsqueda | Reproductor |

Si un usuario busca  *`Cowboys fantasy Tony Romo`*, el término *`Player`* se clasifica porque coincide con la última clasificación proporcionada que aparece en la columna Configurar clasificación.

Del mismo modo, supongamos que configura dos reglas en un conjunto para los siguientes términos de búsqueda:

| Número de regla | Tipo de regla | Buscar coincidencias | Configurar clasificación | Hasta |
|---|---|---|---|---|
| 1 | Contiene | Cowboys | Ciudad | Dallas |
| 2 | Contiene | Broncos | Ciudad | Denver |

Un usuario busca  *`Cowboys vs. Broncos`*. Si el Generador de reglas encuentra un conflicto en la coincidencia de reglas, se aplicará a la búsqueda la clasificación de la segunda regla (Denver).

## Agregar una regla de clasificación a un conjunto de reglas {#add-classification-to-rule-set}

<!-- 

t_classification_rule.xml

 -->

Instrucciones sobre cómo agregar o editar una regla de clasificación.

Añada las reglas haciendo coincidir una condición con una clasificación y especificando la acción.

>[!NOTE]
>
>En este procedimiento deben aplicarse reglas a uno o varios grupos de informes. El número recomendado de reglas por conjunto de reglas está entre 500 y 1000, aunque no hay límites. Si el número de reglas supera las 100, considere la posibilidad de simplificar el conjunto de reglas mediante  [subclasificaciones](/help/components/c-classifications2/c-sub-classifications.md).

1. [Crear un conjunto de reglas de clasificación](/help/components/c-classifications2/crb/classification-rule-set.md) .
1. On the rule set page, click **[!UICONTROL Add Rule]**.

   ![](assets/add_rule.png)

1. Next to **[!UICONTROL Report Suites]**, click **[!UICONTROL Add Suites]** to specify one or more report suites to assign to this rule set.

   Se muestra la **[!UICONTROL Select Report Suites]** página.

   >[!NOTE]
   Los grupos de informes se muestran en esta página *`only`* cuando se cumplen las siguientes condiciones:        >

   * The report suites have at least one classification defined for that variable in [!UICONTROL Admin Tools].
   (Consulte *`Variable`* en [Conjuntos de reglas de clasificación](/help/components/c-classifications2/crb/classification-rule-set.md) para obtener una explicación sobre este requisito previo).

   * You selected the report suite on the **[!UICONTROL Available Report Suites]** page, which displays after you click [Add Rule Set](/help/components/c-classifications2/crb/classification-rule-set.md) to create the rule set.


1. Especifique si desea sobrescribir los valores existentes:

   | **Las reglas sobrescriben todos los valores existentes** | (Configuración predeterminada) Sobrescriba siempre las claves de clasificación existentes, incluidas las clasificaciones cargadas mediante el importador (SAINT). |
   |---|---|
   | **Las reglas sobrescriben únicamente los valores no configurados** | Rellene únicamente las celdas en blanco (sin definir). Las clasificaciones existentes no se cambiarán. |

1. [Defina la regla o las reglas](/help/components/c-classifications2/crb/classification-rule-definitions.md#section_4A5BF384EEEE4994B6DC888339833529).

   ![Resultado de pasos](assets/classification_rules_page.png)

   Para ver ejemplos sobre la creación de reglas, consulte [Generador de reglas de clasificación](/help/components/c-classifications2/crb/classification-rule-builder.md) y [Expresiones regulares en Reglas de clasificación](/help/components/c-classifications2/crb/classification-quickstart-rules.md).

   >[!NOTE]
   >
   >Si una clave coincide con varias reglas que definen la misma clasificación (en la columna Configurar clasificación), se utilizará la última de estas reglas. Consulte **Acerca de la prioridad de las reglas** para obtener más información sobre cómo ordenar las reglas.

1. [Pruebe el conjunto de reglas](/help/components/c-classifications2/crb/classification-quickstart-rules.md).
1. After testing, click **[!UICONTROL Active]** to validate and activate the rule.

   Al activar una regla, se genera y se carga automáticamente el archivo.

   Definiciones de campo: Consulte [Generador de reglas de clasificación](/help/components/c-classifications2/crb/classification-rule-definitions.md) para acceder a las definiciones de las opciones de la interfaz de esta página.

## Probar un conjunto de reglas de clasificación

<!-- 

t_classifications_test_rule.xml

 -->

Instrucciones sobre cómo probar una regla de clasificación o un conjunto de reglas. La ejecución de una prueba comprueba todas las reglas de un conjunto.

1. [Crear un conjunto de reglas de clasificación](/help/components/c-classifications2/crb/classification-rule-set.md) .
1. En el [!UICONTROL Classification Rule Builder], haga clic en el nombre del conjunto de reglas.
1. Asegúrese de que el conjunto de reglas esté asociado con un grupo de informes.
1. On the rule editor, click **[!UICONTROL Test Rule Set]**.

   ![Resultado](assets/classification_test_rule_set.png)

1. Type or paste test keys in the [!UICONTROL Sample Keys] field.

   Entre las claves de muestra se incluyen:

   * Códigos de seguimiento
   * Palabras clave o frases de búsqueda
   See [Regular Expressions in Classification Rules](/help/components/c-classifications2/crb/classification-quickstart-rules.md) for information about testing regular expressions.
1. Haga clic en **[!UICONTROL Run Test]**.

   Rules that match are displayed in the [!UICONTROL Results] table.
1. (Optional) Click **[!UICONTROL Activate]** to activate the rule, and to overwrite existing classifications.

   Consulte para obtener más información sobre el uso de reglas para sobrescribir clasificaciones existentes.

## Validar y activar reglas de clasificación

<!-- 

t_validate_rules.xml

 -->

Instrucciones sobre cómo validar y activar reglas de clasificación.

1. [Cree un conjunto de reglas de clasificación](/help/components/c-classifications2/crb/classification-rule-set.md) y luego [agregue reglas de clasificación](/help/components/c-classifications2/crb/classification-quickstart-rules.md) al conjunto.
1. On the rule editor, click **[!UICONTROL Activate]**.

   ![](assets/overwrite_keys.png)

1. (Opcional) Para sobrescribir las clasificaciones, habilite **[!UICONTROL Overwrite classifications for]***`<selection>`*.

   Esta opción le permite sobrescribir las clasificaciones existentes para las claves afectadas.

   Consulte la página [](/help/components/c-classifications2/crb/classification-rule-definitions.md#section_4A5BF384EEEE4994B6DC888339833529) Reglas para obtener una definición de esta opción.

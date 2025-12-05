---
title: Reglas de conjuntos de clasificaciones
description: Aprenda a utilizar las reglas de conjuntos de clasificaciones para definir reglas para los datos de clasificación.
feature: Classifications
hide: true
hidefromtoc: true
source-git-commit: 9192849bf9fd9a72d2ad7ae2f9727a13201a2a33
workflow-type: tm+mt
source-wordcount: '1578'
ht-degree: 12%

---


# La clasificación establece reglas

Las reglas se utilizan para admitir clasificaciones automáticas en escenarios en los que la dimensión clave cambia constantemente. La actualización de clasificaciones mediante carga o automatización se convierte en un proceso engorroso o retrasa la clasificación adecuada de los nuevos valores de dimensión. Por ejemplo, campañas internas, códigos de seguimiento o SKU de productos. La dimensión debe contener valores que le permitan aplicar una o más reglas para poder derivar datos de clasificación de los valores.

Las reglas se definen en el contexto de un conjunto de clasificaciones, lo que implica que las reglas se aplican (cuando se activan) a todas las combinaciones de grupo de informes y dimensión clave suscritas al conjunto de clasificaciones. Esta implementación es algo diferente de cómo funciona el generador de reglas de clasificación heredado. En el Generador de reglas de clasificación, defina una o más reglas como parte de un conjunto de reglas por separado y, a continuación, asocie el conjunto de reglas a uno o más grupos de informes. En la nueva interfaz, las reglas del conjunto de clasificaciones también se denominan conjunto de reglas, pero se definen en la misma interfaz en la que se configuran otros atributos del conjunto de clasificaciones.


Para definir un conjunto de reglas para un conjunto de clasificaciones:

1. Seleccione **[!UICONTROL Componentes]** en la barra de menús superior de Adobe Analytics y, a continuación, seleccione **[!UICONTROL Conjuntos de clasificaciones]**.
1. En **[!UICONTROL Conjuntos de clasificaciones]**, seleccione la pestaña **[!UICONTROL Conjuntos de clasificaciones]**.
1. En el administrador **[!UICONTROL Conjuntos de clasificaciones]**, seleccione el conjunto de clasificaciones para el que desea definir las reglas.
1. En el cuadro de diálogo **[!UICONTROL Conjunto de clasificaciones: _nombre del conjunto de clasificaciones_]**, seleccione la pestaña **[!UICONTROL Reglas]**.

   * Si accede a la interfaz **[!UICONTROL Rules]** por primera vez para un conjunto de clasificaciones o ha decidido seguir utilizando la interfaz heredada del generador de reglas, aparece un cuadro de diálogo que le permite seleccionar cómo empezar. Las opciones son:

      * **Migrar reglas existentes**. Importe las reglas de clasificación actuales y continúe trabajando con ellas en la nueva interfaz. Las reglas existentes se conservarán y convertirán al nuevo formato.
         * Seleccione **[!UICONTROL Migrar reglas]** para continuar.
         * En el diálogo **[!UICONTROL Confirmar migración]**, lea las implicaciones de la migración.
            * Seleccione **[!UICONTROL Migrar reglas]** para confirmar la migración. Una vez completada la migración, use la [interfaz del conjunto de reglas](#rule-set-interface) para crear nuevas reglas y editar las reglas migradas existentes.
            * Seleccione **[!UICONTROL Cancelar]** para cancelar la migración

      * **Empiece de nuevo**. Cree nuevas reglas de clasificación desde cero con el nuevo generador de reglas. Seleccione esta opción si desea volver a diseñar la lógica de clasificación o empezar de nuevo con nuevas reglas de clasificación.
         * Seleccione **[!UICONTROL Crear nuevas reglas]** para continuar.
         * En el cuadro de diálogo **[!UICONTROL Confirmar inicio reciente]**, lea las implicaciones de un nuevo inicio.
            * Seleccione **[!UICONTROL Comenzar de nuevo]** para confirmar un nuevo inicio y descartar las reglas existentes. Use la [interfaz del conjunto de reglas](#rule-set-interface) para crear nuevas reglas.
            * Seleccione **[!UICONTROL Cancelar]** para cancelar.


      * **Usar interfaz heredada**. Continúe utilizando la interfaz anterior del generador de reglas. Puede migrar a la nueva experiencia en cualquier momento cuando esté listo.
         * Seleccione **[!UICONTROL Ir a la interfaz heredada]** para continuar. Se le dirigirá a la interfaz heredada de **[!UICONTROL Generador de reglas de clasificación]**.

   * Si ya ha migrado reglas o ha creado nuevas reglas para un conjunto de clasificaciones, acaba directamente en la interfaz del conjunto de reglas.



## Interfaz del conjunto de reglas

Al crear o editar reglas, se utiliza la interfaz Conjunto de reglas.

![Interfaz del conjunto de reglas](assets/rulesets-ui.png)

| | Nombre | Descripción |
|---|---|---|
| 1 | **[!UICONTROL Funciones]** | Utiliza el área **[!UICONTROL Funciones]** para seleccionar y arrastrar y soltar las funciones en el generador de conjuntos de reglas. |
| 2 | **Generador de conjuntos de reglas** | El conjunto de reglas se crea mediante una o varias reglas. Una regla es la implementación de una función y siempre está asociada a una sola función. Una función puede tener varios operadores. Para crear una regla, arrastre y suelte una función en el generador de conjuntos de reglas. El tipo de función define la interfaz de la regla. <br/>Consulte la [interfaz de reglas](#rule-interface) para obtener más información.<br/>Puede insertar funciones en cualquier lugar, y las funciones se ejecutan en secuencia para determinar los valores finales de las clasificaciones.<br/>Use **[!UICONTROL Contraer todo]** para contraer todas las reglas y use **[!UICONTROL Expandir todo]** para expandir todas las reglas. |
| 3 | **[!UICONTROL Estado]** | Mostrar el estado y la última fecha de modificación del conjunto de reglas. <br/>Seleccione **[!UICONTROL Activar]** para activar el conjunto de reglas. <br/>Seleccione **[!UICONTROL Desactivar]** para desactivar el conjunto de reglas. |
| 4 | **[!UICONTROL Retrospectiva]** | Especifique la ventana retrospectiva para el conjunto de reglas.<br/>Seleccione una opción (de 1 mes a 6 meses) en el menú desplegable.<br/>Seleccione **[!UICONTROL Realizar retrospectiva]** para realizar una retrospectiva utilizando el período retrospectivo seleccionado. |
| 5 | **[!UICONTROL Opciones de prueba]** | Utilice valores de dimensión clave de muestra para probar las clasificaciones: <ul><li>Agregue o pegue valores en el área de texto **[!UICONTROL Claves de muestra]**.<br/>Compruebe **[!UICONTROL Recordar claves de ejemplo]** para asegurarse de que las claves de ejemplo persisten en un uso diferente de la interfaz del conjunto de reglas.</li><li>Seleccione **[!UICONTROL Probar conjunto de reglas]** para probar el conjunto de reglas.</li></ul> |


## Interfaz de regla

Puede definir cada regla individual dentro del conjunto de reglas en la interfaz de reglas. La interfaz de consta de los siguientes elementos:

![Interfaz de regla](assets/rule-ui.png)

| | Descripción |
|---|---|
| 1 | Nombre de la función seleccionada y entrada introducida para la función. |
| 2 | Entrada de la función seleccionada. La entrada depende de la función seleccionada. Por ejemplo, para la función Expresión regular, la entrada es una expresión regular y para la función Split, la entrada es un token. Introduzca la entrada adecuada para la función específica. Por ejemplo, `^(.+)\:(.+)\:(.+)$` para una expresión regular que identifica tres clasificaciones en un código de campaña interno. |
| 3 | Cada operación establece una clasificación específica en un valor. <br/>Seleccione una clasificación del menú desplegable **[!UICONTROL Establecer clasificación]** e introduzca un valor para **[!UICONTROL to]**. <br/>Use ![CrossSize400](/help/assets/icons/CrossSize400.svg) para eliminar una operación de la lista. |
| 4 | Seleccione ![Agregar](/help/assets/icons/Add.svg) **[!UICONTROL Agregar operación]** para agregar una operación adicional a la función. |
| 5 | Seleccione ![ChevronDown](/help/assets/icons2/ChevronDown.svg) para contraer la regla. Seleccione ![ChevronLeft](/help/assets/icons/ChevronLeft.svg) para expandir la regla.<br/>Seleccione ![CrossSize400](/help/assets/icons/CrossSize400.svg) para eliminar la regla. |

## Referencia de función

Para cada función admitida, consulte los detalles siguientes sobre los casos de uso de entrada y muestra necesarios.


### Comienza con...

Establece una clasificación basada en un valor específico con el que comienza la dimensión clave.

+++ Detalles 

#### Entrada requerida

Escriba un valor para **[!UICONTROL Comienza con]**. Por ejemplo: `em`.

#### Caso de uso

Desea definir una regla para asignar automáticamente `Email` como un valor a la clasificación **[!UICONTROL Channel]** cuando el valor de la dimensión clave Internal Campaign comience por `em` (por ejemplo: `em:FY2025:Summer Sale`).

>[!BEGINTABS]

>[!TAB Regla]

![Regla - Comienza Con](assets/rule-startswith.png)

>[!TAB Resultados de pruebas]

![Regla - Comienza Con Los Resultados De La Prueba](assets/rule-startswith-test.png)

>[!ENDTABS]

+++



### Finaliza con...

Establece una clasificación basada en un valor específico con el que termina la dimensión clave.

+++ Detalles 

#### Entrada requerida

Escriba un valor para **[!UICONTROL Finaliza con]**. Por ejemplo: `2025`.

#### Caso de uso

Desea definir una regla para asignar automáticamente `2025` como un valor a la clasificación **[!UICONTROL Year]** cuando el valor de la dimensión clave Internal Campaign contenga `2025` (por ejemplo: `em:Summer Sale:FY2025`).

>[!BEGINTABS]

>[!TAB Regla]

![Regla - Finaliza Con](assets/rule-endswith.png)

>[!TAB Resultados de pruebas]

![Regla - Termina Con Resultados De Prueba](assets/rule-endswith-test.png)

>[!ENDTABS]

+++


### Contiene..

Establece una clasificación basada en un valor específico que contiene la dimensión clave.

+++ Detalles 

#### Entrada requerida

Escriba un valor para **[!UICONTROL Contiene]**. Por ejemplo: `Winter`.

#### Caso de uso

Desea definir una regla para asignar automáticamente `Winter Sale` como un valor a la clasificación **[!UICONTROL Type]** cuando el valor de la dimensión clave Internal Campaign contenga `Winter` (por ejemplo: `fb:Winter:FY2024`).


>[!BEGINTABS]

>[!TAB Regla]

![Regla - Contiene](assets/rule-contains.png)

>[!TAB Resultados de pruebas]

![Regla: contiene resultados](assets/rule-contains-test.png)

>[!ENDTABS]

+++


### Coincidencias

Establece una clasificación basada en un valor específico con el que coincide la dimensión clave.

+++ Detalles 

#### Entrada requerida

Escriba un valor para **[!UICONTROL Match]**. Por ejemplo: `em:FY2025:Summer`.

#### Caso de uso

Desea definir una regla para asignar automáticamente `Email` como valor a la clasificación **[!UICONTROL Channel]**, `Summer Sale`como valor a la clasificación **[!UICONTROL Type]** y `2025` a la clasificación **[!UICONTROL Year]** cuando el valor de la dimensión clave Internal Campaign coincida con `em:FY2025:Summer`.


>[!BEGINTABS]

>[!TAB Regla]

![Regla - Coincide](assets/rule-match.png)

>[!TAB Resultados de pruebas]

![Regla - Coincide](assets/rule-match.png)

>[!ENDTABS]

+++


### Expresión regular

Establece una o varias clasificaciones en función de una expresión regular aplicada al valor de dimensión clave.

+++ Detalles 

#### Entrada requerida

Escriba un valor para **[!UICONTROL Expresión regular]**. Por ejemplo: `^(.+)\:(.+)\:FY(.+)$`.

#### Caso de uso

Desea definir una regla para asignar automáticamente valores a las clasificaciones **[!UICONTROL Channel]**, **[!UICONTROL Type]** y **[!UICONTROL Year]** aplicando la expresión regular `^(.+)\:(.+)\:FY(.+)$` y utilizando grupos de coincidencia (`$1`, `$2` y `$3`) a los valores de la dimensión clave Campaña interna.

>[!BEGINTABS]

>[!TAB Regla]

![Regla - Expresión regular](assets/rule-regex.png)

>[!TAB Resultados de pruebas]

![Regla - Resultados de prueba de expresión regular](assets/rule-regex-test.png)

>[!ENDTABS]


#### Tabla de referencia {#section_0211DCB1760042099CCD3ED7A665D716}

| Expresión regular | Descripción |
|---|---|
| `(?ms)` | Hace que toda la expresión regular coincida con una entrada de varias líneas, lo que permite que el comodín coincida con cualquier carácter de línea nueva. |
| `(?i)` | Hace que toda la expresión regular no distinga mayúsculas de minúsculas. |
| `[abc]` | Un solo carácter de: a, b o c. |
| `[^abc]` | Cualquier carácter individual distinto de: a, b o c. |
| `[a-z]` | Cualquier carácter individual del intervalo a-z. |
| `[a-zA-Z]` | Cualquier carácter individual del intervalo a-z o A-Z. |
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
| `(a\b)` | a o b |
| `a?` | Cero o uno de a. |
| `a*` | Cero o más de a. |
| `a+` | Uno o más de a. |
| `a{3}` | Exactamente 3 de a. |
| `a{3,}` | 3 o más de a. |
| `a{3,6}` | Entre 3 y 6 de a. |

+++


## Prioridad de reglas

Si un valor de dimensión clave coincide con varias reglas y el conjunto de reglas contiene reglas con la misma operación Establecer clasificación, la última regla determina el valor de la clasificación. Por lo tanto, debe clasificar la operación de clasificación de conjuntos más importante como parte de la última regla del conjunto de reglas.

Si crea varias reglas que no comparten la misma operación Establecer clasificación, el orden de procesamiento no importa.


### Ejemplo

Desea clasificar con la clasificación **[!UICONTROL Escriba]** cómo buscan los usuarios un atleta usando la cadena de búsqueda como dimensión clave. Por ejemplo, con este conjunto de reglas:

![Prioridad de reglas](assets/rule-priority.png)

* Cuando un usuario busca `Cowboys Fantasy Tony Romo`, `Romo` se clasifica como **[!UICONTROL Tipo]**.
* Cuando un usuario busca `Cowboys Fantasy Tony Romeo`, `Fantasy`se clasifica como **[!UICONTROL Tipo]**.
* Cuando un usuario busca `Cowboys vs. Broncos`, `Team`se clasifica como **[!UICONTROL Tipo]**.


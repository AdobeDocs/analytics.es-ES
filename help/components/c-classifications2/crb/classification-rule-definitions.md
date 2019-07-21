---
description: Definiciones de los elementos de la interfaz en las páginas del Generador de reglas de clasificación.
seo-description: Definiciones de los elementos de la interfaz en las páginas del Generador de reglas de clasificación.
seo-title: 'Reglas de clasificación: definiciones'
solution: Analytics
subtopic: Clasificaciones
title: 'Reglas de clasificación: definiciones'
topic: Herramientas de administración
uuid: 77 af 8669-6 e 11-435 c -9 cc 3-b 03 eb 627 c 855
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Reglas de clasificación: definiciones

Definiciones de los elementos de la interfaz en las páginas del Generador de reglas de clasificación.

## Página Reglas {#section_4A5BF384EEEE4994B6DC888339833529}

Esta página muestra las reglas de un conjunto de reglas.

![](assets/classification_rules_page.png)

**Definiciones**

<table id="table_2B3A8BB7BDE14836ACA6A1D444B011CD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Seleccionar grupos de informes y variables </p> </td> 
   <td colname="col2"> <p><b>Grupo de informes</b> </p> <p>Los grupos de informes a los que se aplica el conjunto de reglas. </p> <p><b>Variable</b> </p> <p>Al crear un conjunto de reglas de clasificación solo puede aplicarse una variable. Si se desea crear varios conjuntos de reglas para una variable, debe aplicarse cada uno de estos conjuntos a varios grupos de informes. </p> <p>Nota: Solo puede usar las variables a las que tenga acceso en sus grupos de informes. Las variables se mostrarán en el panel <span class="wintitle">Nuevo conjunto de reglas</span> solo después de haber definido como mínimo una clasificación para la variable. </p> <p>For example, to make <span class="term"> Pages</span> available as a variable to the rule set, ensure that the report suite has <a href="https://marketing.adobe.com/resources/help/en_US/reference/traffic_classifications.html" format="http" scope="external"> traffic classifications</a> implemented for <span class="term"> Page</span>. </p> <p> El usuario puede crear clasificaciones en variables desde <span class="uicontrol">Administradores</span> &gt; <span class="uicontrol">Grupos de informes</span> &gt; <span class="uicontrol">Tráfico</span> &gt; <span class="uicontrol">Clasificaciones de tráfico</span> (o <span class="uicontrol">Conversión</span> &gt; <span class="uicontrol">Clasificaciones de las conversiones</span>). A continuación, debe seleccionar la variable y hacer clic en <span class="uicontrol">Agregar clasificación</span>. </p> <p>Consulte <a href="https://marketing.adobe.com/resources/help/en_US/reference/index.html?f=traffic_classification_admin" format="https" scope="external">Clasificaciones de tráfico</a> y <a href="https://marketing.adobe.com/resources/help/en_US/reference/index.html?f=conversion_classifications" format="https" scope="external">Clasificaciones de las conversiones</a> en la ayuda del administrador. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Activar</span> </p> </td> 
   <td colname="col2"> <p>Valida y activa una regla. Las reglas activas se procesan a diario y los datos de clasificación suelen examinarse de forma mensual. Las reglas comprueban automáticamente la existencia de nuevos valores y cargan las clasificaciones. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Desactivar</span> </p> </td> 
   <td colname="col2"> <p>Desactiva las reglas para editarlas y probarlas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Configurar grupos de informes y variables </p> </td> 
   <td colname="col2"> <p>Muestra la página <span class="wintitle">Grupos de informes disponibles</span>, en la que puede seleccionar uno o más grupos de informes disponibles para usarlos para todos sus conjuntos de reglas. (Esta página también se muestra la primera vez que ejecuta el <span class="wintitle">enerador de reglas de clasificación</span>). </p> <p>Esta función sirve para ayudar a reducir el tiempo de carga del grupo de informes, en el caso de que tenga cientos de grupos de informes disponibles. </p> <p>The report suites you select here are made available at the rule level, when you click <span class="uicontrol"> Add Suites</span> when creating a rule. </p> <p>Note: A report suite becomes available <span class="term"> only</span> when the report suites have at least one classification defined for the variable in <span class="wintitle"> Admin Tools</span>. <p>(See <span class="term"> Variable</span> in <a href="../../../components/c-classifications2/crb/classification-rule-set.md#concept_CD3D510F5070486584F3BB535AE41524" format="dita" scope="local"> Classification Rule Sets</a> for an explanation about this prerequisite.) </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Las reglas sobrescriben los valores existentes </p> </td> 
   <td colname="col2"> <p> (Configuración predeterminada) Sobrescriba siempre las claves de clasificación existentes, incluidas las clasificaciones cargadas mediante el importador (SAINT). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Las reglas solo sobrescriben los valores no establecidos </p> </td> 
   <td colname="col2"> <p>Rellene solo las celdas vacías (no establecidas). Las clasificaciones existentes no cambiarán. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ventana retroactiva </p> </td> 
   <td colname="col2"> <p>A la hora de activar y validar reglas, puede especificar si estas reglas deben sobrescribir las clasificaciones existentes de las claves afectadas. (Solo resultan afectadas las claves clasificadas que se han pasado previamente a <span class="keyword">Adobe Analytics</span> en el lapso de tiempo especificado). </p> <p>If you to not specify a <span class="term"> lookback window</span>, the rules look back roughly one month (depending on current day of the month.) Las clasificaciones existentes no se sobrescriben nunca, salvo que active esa opción. </p> <p><b>Centro de desarrolladores</b>: los socios pueden crear reglas de clasificación en el <span class="wintitle">Centro de desarrolladores</span>. Estas reglas se implementan cuando el cliente activa una integración. En el <span class="wintitle">Centro de desarrolladores</span>, la opción <span class="uicontrol">Sobrescribir desde</span> permite al socio especificar si el cliente puede determinar el valor de sobrescritura al activar o editar una integración. </p> <p>See <a href="../../../components/c-classifications2/crb/classification-quickstart-rules.md#concept_A67A23F523844D37898583C632DB9D25" format="dita" scope="local"> How Rules Are Processed</a> for more information about rule processing. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <a href="../../../components/c-classifications2/crb/classification-quickstart-rules.md#task_86F216DFD2534FA181E64ABDF306782B" format="dita" scope="local"> Agregar regla </a> </td> 
   <td colname="col2"> <p>Permite agregar reglas al conjunto de reglas. </p> <p>Nota: Si se encuentran dos o más coincidencias para un valor en un conjunto de reglas, el sistema clasifica el valor con la última regla. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Borrador</span> </td> 
   <td colname="col2"> Permite especificar que una regla se encuentra en modo borrador. El estado de borrador permite probar una regla antes de ejecutarla. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Duplicar</span> </td> 
   <td colname="col2"> Duplica (copia) un conjunto de reglas para aplicarlo a otra variable o a la misma en otro grupo de informes. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="../../../components/c-classifications2/crb/classification-quickstart-rules.md#task_618A1E7CC8664E728F312250E8367158" format="dita" scope="local"> Conjunto de reglas de la prueba </a> </p> </td> 
   <td colname="col2"> <p>Permite probar la validez de un conjunto de reglas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Condición de coincidencia</span> </td> 
   <td colname="col2"> Especifica las condiciones para una regla. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Acción de clasificación</span> </td> 
   <td colname="col2"> <p>Especifica la acción que debe realizarse al detectar la condición de coincidencia. </p> <p>Por ejemplo, si se define un nombre de campaña en $2, lo que identifica la posición 2 de un código de seguimiento como nombre de campaña. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> #</span> </td> 
   <td colname="col2"> <p>El número de la regla. </p> <p>Consulte <a href="../../../components/c-classifications2/crb/classification-quickstart-rules.md#concept_A67A23F523844D37898583C632DB9D25" format="dita" scope="local"> Cómo procesar las reglas</a> para obtener más información. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Seleccionar tipo de regla</span> </td> 
   <td colname="col2"> <p>Se aplica cada conjunto de reglas a una variable específica. Las selecciones válidas son: </p> 
    <ul id="ul_6A8E06BB4AF2402B99C215823CB3D59D"> 
     <li id="li_5C702D4F460841D38A59621A5161A3BC">Comienza con </li> 
     <li id="li_8052A741D9F34A2FBC136C181600193E">Finaliza con </li> 
     <li id="li_D0FA6EA4F09644FFBC9E6BC568BE80AC">Contiene </li> 
     <li id="li_48675FE5253942ED887C6A72D1DCEF54"> <a href="../../../components/c-classifications2/crb/classification-quickstart-rules.md#concept_8A63F9BCF9484963962E14E6286D312D" format="dita" scope="local"> Expresión regular </a> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Introducir criterios de coincidencia</span> </td> 
   <td colname="col2"> El patrón de texto que se busca en una clave. Estos criterios pueden ser términos de búsqueda, caracteres o expresiones regulares. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Configurar clasificación</span> </td> 
   <td colname="col2"> La columna de clasificación que debe definirse si se cumplen los criterios de coincidencia. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Hasta</span> </td> 
   <td colname="col2"> El valor que debe especificarse para la columna de clasificación seleccionada si se cumplen los criterios de coincidencia. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Filtro </td> 
   <td colname="col2"> Permite buscar reglas. </td> 
  </tr> 
 </tbody> 
</table>

## Página Expresión regular {#section_C932A5469E774841B2229965A154163C}

En la página [!UICONTROL Expresión regular] puede editar las expresiones de este tipo.

![](assets/regex_tracking_code.png)

**Definiciones**

| Elemento | Descripción |
|---|---|
| Clave de muestra | La cadena de prueba que debe utilizarse. Por ejemplo, puede crear una clasificación a partir de caracteres específicos de un código de seguimiento. Según se considere conveniente, pueden hacerse coincidir patrones de caracteres, palabras o caracteres determinados. |
| Grupos de coincidencias | Muestra la correspondencia entre una expresión regular y los caracteres de un ID de campaña para poder clasificar una posición en este ID. |
| Resultados de coincidencias | Muestra los elementos de una cadena que coinciden con la expresión regular. |

Consulte [Expresiones regulares en las reglas de clasificación](../../../components/c-classifications2/crb/classification-quickstart-rules.md#concept_8A63F9BCF9484963962E14E6286D312D).

## Página Pruebas {#section_EC926F97901C4E65901413F9683AA70A}

Esta página permite probar las reglas de un conjunto.

**Definiciones**

| Elemento | Descripción |
|---|---|
| Ejecutar prueba | Para probar el conjunto de reglas, debe comprobarse el efecto que este ejerce sobre las claves del informe. |
| Filtro | Filtra los valores en el panel [!UICONTROL Resultados]. |


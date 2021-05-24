---
description: Definiciones de los elementos de la interfaz en las páginas del Generador de reglas de clasificación.
subtopic: Classifications
title: Definiciones de reglas de clasificación
feature: Herramientas de administración
uuid: 77af8669-6e11-435c-9cc3-b03eb627c855
exl-id: 514501d1-7e1b-45da-b8fe-c68331e59dab
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '880'
ht-degree: 100%

---

# Definiciones de reglas de clasificación

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
   <td colname="col2"> <p><b>Grupo de informes</b> </p> <p>Los grupos de informes a los que se aplica el conjunto de reglas. </p> <p><b>Variable</b> </p> <p>Al crear un conjunto de reglas de clasificación solo puede aplicarse una variable. Si se desea crear varios conjuntos de reglas para una variable, debe aplicarse cada uno de estos conjuntos a varios grupos de informes. </p> <p>Nota: Solo puede usar las variables a las que tenga acceso en sus grupos de informes. Las variables se mostrarán en el panel <span class="wintitle">Nuevo conjunto de reglas</span> solo después de haber definido como mínimo una clasificación para la variable. </p> <p> El usuario puede crear clasificaciones en variables desde <span class="uicontrol">Administradores</span> &gt; <span class="uicontrol">Grupos de informes</span> &gt; <span class="uicontrol">Tráfico</span> &gt; <span class="uicontrol">Clasificaciones de tráfico</span> (o <span class="uicontrol">Conversión</span> &gt; <span class="uicontrol">Clasificaciones de las conversiones</span>). A continuación, debe seleccionar la variable y hacer clic en <span class="uicontrol">Agregar clasificación</span>. </p> <p>Consulte <a href="https://docs.adobe.com/content/help/es-ES/analytics/admin/admin-tools/traffic-variables/traffic-classifications.html"  >Clasificaciones de tráfico</a> y <a href="https://docs.adobe.com/content/help/es-ES/analytics/admin/admin-tools/conversion-variables/conversion-classifications.html"  >Clasificaciones de las conversiones</a> en la ayuda del administrador. </p> </td> 
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
   <td colname="col2"> <p>Muestra la página <span class="wintitle">Grupos de informes disponibles</span>, en la que puede seleccionar uno o más grupos de informes disponibles para usarlos para todos sus conjuntos de reglas. (Esta página también se muestra la primera vez que ejecuta el <span class="wintitle">enerador de reglas de clasificación</span>). </p> <p>Esta función sirve para ayudar a reducir el tiempo de carga del grupo de informes, en el caso de que tenga cientos de grupos de informes disponibles. </p> <p>Los grupos de informes que seleccione aquí están disponibles al nivel de regla, cuando hace clic en <span class="uicontrol">Agregar grupos</span> al crear una regla. </p> <p>Nota: Un grupo de informes <span class="term"> solo</span> estará disponible cuando los grupos de informes tengan al menos una clasificación definida para la variable en las <span class="wintitle"> Herramientas de administración</span>. <p>(Consulte <span class="term">Variable</span> en <a href="/help/components/classifications/crb/classification-rule-set.md"  >Conjuntos de reglas de clasificación</a> para obtener una explicación sobre este requisito previo). </p> </p> </td> 
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
   <td colname="col2"> <p>A la hora de activar y validar reglas, puede especificar si estas reglas deben sobrescribir las clasificaciones existentes de las claves afectadas. (Solo resultan afectadas las claves clasificadas que se han pasado previamente a <span class="keyword">Adobe Analytics</span> en el lapso de tiempo especificado). </p> <p>Si no especifica ningún <span class="term">período de retrospectiva</span>, las reglas se aplican, aproximadamente, al mes anterior (depende del día actual del mes). Las clasificaciones existentes no se sobrescriben nunca, salvo que active esa opción. </p> <p><b>Centro de desarrolladores</b>: los socios pueden crear reglas de clasificación en el <span class="wintitle">Centro de desarrolladores</span>. Estas reglas se implementan cuando el cliente activa una integración. En el <span class="wintitle">Centro de desarrolladores</span>, la opción <span class="uicontrol">Sobrescribir desde</span> permite al socio especificar si el cliente puede determinar el valor de sobrescritura al activar o editar una integración. </p> <p>Consulte <a href="/help/components/classifications/crb/classification-quickstart-rules.md"  >Procesamiento de reglas</a> para obtener más información sobre cómo se procesan las reglas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <a href="/help/components/classifications/crb/classification-quickstart-rules.md"  > Agregar regla </a> </td> 
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
   <td colname="col1"> <p> <a href="/help/components/classifications/crb/classification-quickstart-rules.md"  > Conjunto de reglas de la prueba </a> </p> </td> 
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
   <td colname="col2"> <p>El número de la regla. </p> <p>Consulte <a href="/help/components/classifications/crb/classification-quickstart-rules.md"  > Cómo procesar las reglas</a> para obtener más información. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Seleccionar tipo de regla</span> </td> 
   <td colname="col2"> <p>Se aplica cada conjunto de reglas a una variable específica. Las selecciones válidas son: </p> 
    <ul id="ul_6A8E06BB4AF2402B99C215823CB3D59D"> 
     <li id="li_5C702D4F460841D38A59621A5161A3BC">Comienza con </li> 
     <li id="li_8052A741D9F34A2FBC136C181600193E">Finaliza con </li> 
     <li id="li_D0FA6EA4F09644FFBC9E6BC568BE80AC">Contiene </li> 
     <li id="li_48675FE5253942ED887C6A72D1DCEF54"> <a href="/help/components/classifications/crb/classification-quickstart-rules.md"  > Expresión regular </a> </li> 
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

Consulte [Expresiones regulares en las reglas de clasificación](/help/components/classifications/crb/classification-quickstart-rules.md).

## Página Pruebas {#section_EC926F97901C4E65901413F9683AA70A}

Esta página permite probar las reglas de un conjunto.

**Definiciones**

| Elemento | Descripción |
|---|---|
| Ejecutar prueba | Para probar el conjunto de reglas, debe comprobarse el efecto que este ejerce sobre las claves del informe. |
| Filtro | Filtra los valores en el panel [!UICONTROL Resultados]. |

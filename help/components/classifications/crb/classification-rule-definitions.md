---
description: Definiciones de los elementos de la interfaz en las páginas del Generador de reglas de clasificación.
title: Definiciones de reglas de clasificación
feature: Classifications
exl-id: 514501d1-7e1b-45da-b8fe-c68331e59dab
TQID: https://experienceleague.adobe.com/8SDdKOvF-Mk9jQCb7YWXt0NCl0dspfscnHL02y1cxKM
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32id: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 861
ht-degree: 67%

---

# Definiciones de reglas de clasificación (heredadas)

{{classification-rulebuilder-deprecation}}

Definiciones de los elementos de la interfaz en las páginas del Generador de reglas de clasificación.

## Página Reglas

Esta página muestra las reglas en un conjunto de reglas.

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
   <td colname="col2"> <p><b>Grupo de informes</b> </p> <p>Los grupos de informes a los que se aplica el conjunto de reglas. </p> <p><b>Variable</b> </p> <p>Solo se puede aplicar una variable al crear un conjunto de reglas de clasificación. Si se desea crear varios conjuntos de reglas para una variable, debe aplicarse cada uno de estos conjuntos a varios grupos de informes. </p> <p>Nota: Solo puede usar las variables a las que tenga acceso en sus grupos de informes. Las variables se mostrarán en el panel <span class="wintitle">Nuevo conjunto de reglas</span> solo después de haber definido como mínimo una clasificación para la variable. </p> <p> El usuario puede crear clasificaciones en variables desde <span class="uicontrol">Administradores</span> &gt; <span class="uicontrol">Grupos de informes</span> &gt; <span class="uicontrol">Tráfico</span> &gt; <span class="uicontrol">Clasificaciones de tráfico</span> (o <span class="uicontrol">Conversión</span> &gt; <span class="uicontrol">Clasificaciones de las conversiones</span>). A continuación, debe seleccionar la variable y hacer clic en <span class="uicontrol">Agregar clasificación</span>. </p> <p>Consulte <a href="/help/admin/tools/manage-rs/edit-settings/c-traffic-variables/traffic-classifications.md"  >Clasificaciones de tráfico</a> y <a href="/help/admin/tools/manage-rs/edit-settings/conversion-var-admin/conversion-classifications.md"  >Clasificaciones de las conversiones</a> en la ayuda del administrador. </p> </td> 
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
   <td colname="col1"> <p>Ventana de retroactividad </p> </td> 
   <td colname="col2"> <p>A la hora de activar y validar reglas, puede especificar si estas reglas deben sobrescribir las clasificaciones existentes de las claves afectadas. (Solo resultan afectadas las claves clasificadas que se han pasado previamente a <span class="keyword">Adobe Analytics</span> en el lapso de tiempo especificado). </p> <p>Si no desea especificar una ventana retrospectiva de <span class="term"></span>, las reglas se aplican aproximadamente al mes anterior (dependiendo del día actual del mes). Las clasificaciones existentes no se sobrescriben nunca, salvo que active esta opción. </p> <p><b>Centro de desarrolladores</b>: los socios pueden crear reglas de clasificación en el <span class="wintitle">Centro de desarrolladores</span>. Estas reglas se implementan cuando el cliente activa una integración. En el <span class="wintitle">Centro de desarrolladores</span>, la opción <span class="uicontrol">Sobrescribir desde</span> permite al socio especificar si el cliente puede determinar el valor de sobrescritura al activar o editar una integración. </p> <p>Consulte <a href="/help/components/classifications/crb/classification-quickstart-rules.md"  >Procesamiento de reglas</a> para obtener más información sobre cómo se procesan las reglas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <a href="/help/components/classifications/crb/classification-quickstart-rules.md"  > Agregar regla </a> </td> 
   <td colname="col2"> <p>Permite agregar reglas al conjunto de reglas. </p> <p>Nota: Si se encuentran dos o más coincidencias para un valor en un conjunto de reglas, el sistema clasifica el valor con la última regla. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Borrador</span> </td> 
   <td colname="col2"> Permite especificar que una regla está en modo de borrador. El estado de borrador permite probar la regla antes de ejecutarla. </td> 
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
   <td colname="col2"> <p>Especifica la acción que debe realizarse cuando se produce la condición coincidente. </p> <p>Por ejemplo, establece un Nombre de campaña en $2, que identifica la posición 2 en un código de seguimiento como el Nombre de campaña. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> #</span> </td> 
   <td colname="col2"> <p>El número de regla. </p> <p>Consulte <a href="/help/components/classifications/crb/classification-quickstart-rules.md"  > Cómo se procesan las reglas</a> para obtener más información. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Seleccionar tipo de regla</span> </td> 
   <td colname="col2"> <p>Cada conjunto de reglas se aplica a una variable específica. Las selecciones válidas son: </p> 
    <ul id="ul_6A8E06BB4AF2402B99C215823CB3D59D"> 
     <li id="li_5C702D4F460841D38A59621A5161A3BC">Comienza con </li> 
     <li id="li_8052A741D9F34A2FBC136C181600193E">Finaliza con </li> 
     <li id="li_D0FA6EA4F09644FFBC9E6BC568BE80AC">Contiene </li> 
     <li id="li_48675FE5253942ED887C6A72D1DCEF54"> <a href="/help/components/classifications/crb/classification-quickstart-rules.md"  > Expresión regular </a> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Introducir criterios de coincidencia</span> </td> 
   <td colname="col2"> Patrón de texto que busca en una clave. Estos criterios pueden ser términos de búsqueda, caracteres o expresiones regulares. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Configurar clasificación</span> </td> 
   <td colname="col2"> La columna de clasificación que debe definirse si se cumplen los criterios de coincidencia. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Hasta</span> </td> 
   <td colname="col2"> El valor que desea especificar para la columna de clasificación seleccionada si se cumplen los criterios de coincidencia. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Filtro </td> 
   <td colname="col2"> Le permite buscar reglas. </td> 
  </tr> 
 </tbody> 
</table>

## Página Expresión regular {#section_C932A5469E774841B2229965A154163C}

Puede editar expresiones regulares en la página [!UICONTROL Expresión regular].

![](assets/regex_tracking_code.png)

**Definiciones**

| Elemento | Descripción |
|---|---|
| Clave de muestra | Cadena de prueba que se va a utilizar. Por ejemplo, puede crear una clasificación a partir de caracteres específicos de un código de seguimiento. Según se considere conveniente, pueden hacerse coincidir patrones de caracteres, palabras o caracteres determinados. |
| Grupos de coincidencias | Muestra la correspondencia entre la expresión regular y los caracteres del ID de campaña para poder clasificar una posición en dicho ID. |
| Resultados de coincidencias | Muestra las partes de una cadena que coinciden correctamente con la expresión regular. |

Consulte [Expresiones regulares en las reglas de clasificación](/help/components/classifications/crb/classification-quickstart-rules.md).

## Página Pruebas {#section_EC926F97901C4E65901413F9683AA70A}

Esta página permite probar las reglas de un conjunto.

**Definiciones**

| Elemento | Descripción |
|---|---|
| Ejecutar prueba | Cuando pruebe el conjunto de reglas, utilice las claves del informe para ver cómo se verán afectadas por el conjunto de reglas. |
| Filtro | Filtra los valores en el panel [!UICONTROL Resultados]. |

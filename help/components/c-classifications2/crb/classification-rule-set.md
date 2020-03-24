---
description: Un conjunto de reglas es un grupo de reglas de clasificación para una variable específica. Se aplica una variable al conjunto de reglas. Si desea crear varios conjuntos de reglas para una variable, debe aplicar cada conjunto de reglas a varios grupos de informes.
subtopic: Classifications
title: Conjuntos de reglas de clasificación
topic: Admin tools
uuid: c4d7b77c-fa98-44be-955f-9aee7f73480b
translation-type: tm+mt
source-git-commit: 0e97e28ffb2bf94acfb382c3f97ff30b31321467

---


# Conjuntos de reglas de clasificación

Un conjunto de reglas es un grupo de reglas de clasificación para una variable específica. Se aplica una variable al conjunto de reglas. Si desea crear varios conjuntos de reglas para una variable, debe aplicar cada conjunto de reglas a varios grupos de informes.

## Conjuntos de reglas de clasificación

Un conjunto de reglas es un grupo de reglas de clasificación para una variable específica. Se aplica una variable al conjunto de reglas. Si desea crear varios conjuntos de reglas para una variable, debe aplicar cada conjunto de reglas a varios grupos de informes.

## Página Clasificación del Generador de reglas  {#section_C60B0888C76D49C596EF19F11808B718}

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Classification Rule Builder]**

Los campos y las opciones siguientes están disponibles en la [!UICONTROL Classifications Rule Builder].

<table id="table_A5D92409969747E39E041216A5AA32CD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><a href="/help/components/c-classifications2/crb/classification-rule-set.md"  > Agregar conjunto de reglas</a> </p> </td> 
   <td colname="col2"> <p>Crea un conjunto de reglas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Reglas </p> </td> 
   <td colname="col2"> Muestra el número de reglas incluidas en el conjunto. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Estado </p> </td> 
   <td colname="col2"> Muestra el estado de actividad del conjunto de reglas, como Borrador o Activo. Las reglas activas se procesan diariamente y los datos de clasificación suelen examinarse un mes antes. Las reglas comprueban automáticamente la existencia de nuevos valores y cargan las clasificaciones. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Cambiado por última vez </p> </td> 
   <td colname="col2"> Indica cuándo se editó el conjunto de reglas. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Duplicar </p> </td> 
   <td colname="col2"> Duplica (copia) un conjunto de reglas para aplicarlo a otra variable o a la misma en otro grupo de informes. </td> 
  </tr> 
 </tbody> 
</table>

## Crear un conjunto de reglas de clasificación {#create-classification-rule-set}

Nombre el conjunto de reglas de clasificación, aplique la variable y especifique la configuración de sobrescritura.

1. (Requisito previo) Defina la estructura de clasificación en **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**.

   (Consulte [Clasificaciones](https://marketing.adobe.com/resources/help/en_US/reference/classifications.html) en la ayuda de Herramientas de administración para agregar clasificaciones).

   Variables will display in the [!UICONTROL New Rule Set] panel only after they have at least one classification defined for that variable.

   Puede crear clasificaciones en una variable en **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > **[!UICONTROL Traffic]** > **[!UICONTROL Traffic Classifications]** (o **[!UICONTROL Conversion]** > **[!UICONTROL Conversion Classifications]**). Then select the variable, then click **[!UICONTROL Add Classification]**.

1. Para crear el conjunto de reglas, haga clic en **[!UICONTROL Admin]** > **[!UICONTROL Classification Rule Builder]** > **[!UICONTROL Add Rule Set]**.

   ![](assets/new_rule_set.png)

1. Asigne un nombre al conjunto de reglas y haga clic en **[!UICONTROL Create Rule Set]**.
1. Seleccione el conjunto de reglas para editar.

   ![](assets/classification_rules_page.png)

1. Haga clic en **[!UICONTROL Select Report Suites and Variables]**.

   El grupo de informes y la lista de variables se rellenan con todas las variables clasificadas disponibles en todos los grupos de informes de la compañía de inicio de sesión. Una sola variable en un grupo de informes puede pertenecer a un solo conjunto de reglas.

   See *`Variable`* in the definitions for the [Classification Rule Builder](/help/components/c-classifications2/crb/classification-rule-definitions.md) page for more information.
1. Specify the report suites and variables to use, then click **[!UICONTROL Save]**.
1. Después, [agregue las reglas de clasificación](/help/components/c-classifications2/crb/classification-rule-set.md) al conjunto de reglas.

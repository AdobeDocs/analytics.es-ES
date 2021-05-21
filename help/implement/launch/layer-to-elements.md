---
title: Asignación de objetos de capa de datos a elementos de datos
description: Configure Launch para que se lea desde la capa de datos.
exl-id: b7594084-cb5f-408e-8a76-0a0815cc7553
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '306'
ht-degree: 100%

---

# Asignación de objetos de capa de datos a elementos de datos

Una vez que la organización haya establecido e implementado una capa de datos en el sitio, puede asignar objetos de capa de datos a elementos de datos dentro de Launch.

## Requisitos previos

[Crear una capa de datos](../prepare/data-layer.md): asegúrese de que exista una capa de datos en el sitio. Aunque técnicamente puede asignar cualquier objeto JavaScript o crear secuencias de comandos de elementos CSS directamente desde la página, Adobe recomienda esta práctica como último recurso. Si el diseño del sitio cambia, los selectores CSS utilizados en Launch dejan de funcionar, lo que provoca la pérdida de datos.

## Uso de Adobe Experience Platform Launch para crear elementos de datos

[Los elementos de datos](https://docs.adobe.com/content/help/es-ES/launch/using/reference/manage-resources/data-elements.html#create-a-data-element) son componentes de Launch que se pueden usar en toda la herramienta. Puede asignar valores de variables en la extensión de Adobe Analytics mediante elementos de datos.

1. Vaya a [Adobe Experience Platform Launch](https://launch.adobe.com) e inicie sesión si se le solicita.
1. Haga clic en la propiedad de Launch.
1. Haga clic en la pestaña **[!UICONTROL Elementos de datos]** y, a continuación, haga clic en **[!UICONTROL Agregar elemento de datos]**.

   ![crear elemento de datos](assets/createelement.png)

1. Escriba un nombre para el elemento de datos. Puede ser una etiqueta simple que corresponde a una variable de JavaScript en la capa de datos que desee rastrear.
1. En el menú desplegable de **[!UICONTROL Extensión]**, seleccione **[!UICONTROL Principal]**.
1. En el menú desplegable **[!UICONTROL Tipo de elemento de datos]**, seleccione **[!UICONTROL Variable JavaScript]**. Aparece un campo de texto a la derecha que le permite introducir la variable JavaScript para asignarla a este elemento de datos.
1. Introduzca la variable de JavaScript que desee, normalmente dentro de la capa de datos. Por ejemplo, si la capa de datos de su organización coincide estrechamente con la práctica recomendada de Adobe, podría ser un valor de `digitalData.page.pageInfo.pageName`. Puede utilizar la consola del explorador para validar la sintaxis y los valores de las variables de JavaScript.
1. Haga clic en **[!UICONTROL Guardar]**.

## Pasos siguientes

[Asigne elementos de datos a variables de Analytics:](elements-to-variable.md) asigne elementos de datos a variables de Analytics para que pueda utilizarlos como dimensiones en Analysis Workspace.

---
title: Asignación de objetos de capa de datos a elementos de datos
description: Configure Launch para que lea desde la capa de datos.
translation-type: tm+mt
source-git-commit: 283fcd5832abe4c09caa332c2ebc3a22029e6707

---


# Asignación de objetos de capa de datos a elementos de datos

Una vez que la organización haya establecido e implementado una capa de datos en el sitio, puede asignar objetos de capa de datos a elementos de datos dentro de Launch.

## Requisitos previos

[Crear una capa](../prepare/data-layer.md)de datos: Asegúrese de que existe una capa de datos en el sitio. Aunque técnicamente puede asignar cualquier objeto JavaScript o crear secuencias de comandos de elementos CSS directamente desde la página, Adobe recomienda esta práctica como último recurso. Si el diseño del sitio cambia, los selectores CSS utilizados en Launch dejan de funcionar, lo que provoca la pérdida de datos.

## Uso de Adobe Experience Platform Launch para crear elementos de datos

[Los elementos](https://docs.adobe.com/content/help/en/launch/using/reference/manage-resources/data-elements.html#create-a-data-element) de datos son componentes de Launch que se pueden utilizar en toda la herramienta. Puede asignar valores de variables en la extensión de Adobe Analytics mediante elementos de datos.

1. Vaya a [Adobe Experience Platform Launch](https://launch.adobe.com) e inicie sesión si se le solicita.
1. Haga clic en la propiedad Launch que desee.
1. Click the [!UICONTROL Data Elements] tab, then click [!UICONTROL Add Data Element].

   ![crear elemento de datos](assets/createelement.png)

1. Escriba un nombre para el elemento de datos. Puede ser una etiqueta simple que corresponde a una variable de JavaScript en la capa de datos que desee rastrear.
1. En la [!UICONTROL Extension] lista desplegable, seleccione [!UICONTROL Core].
1. En la [!UICONTROL Data Element Type] lista desplegable, seleccione [!UICONTROL JavaScript Variable]. Aparece un campo de texto a la derecha que le permite introducir la variable JavaScript para asignarla a este elemento de datos.
1. Introduzca la variable de JavaScript que desee, normalmente dentro de la capa de datos. Por ejemplo, si la capa de datos de su organización coincide estrechamente con la práctica recomendada de Adobe, podría ser un valor `digitalData.page.pageInfo.pageName`. Puede utilizar la consola del explorador para validar la sintaxis y los valores de las variables JavaScript.
1. Haga clic en [!UICONTROL Save].

## Pasos siguientes

[Asigne elementos de datos a variables](elements-to-variable.md)de Analytics: Asigne elementos de datos a variables de Analytics para que pueda utilizarlos como dimensiones en Analysis Workspace.

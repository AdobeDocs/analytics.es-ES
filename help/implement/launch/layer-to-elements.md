---
title: Asignación de objetos de capa de datos a elementos de datos
description: Configure las etiquetas para que se lean desde la capa de datos.
feature: Launch Implementation
exl-id: b7594084-cb5f-408e-8a76-0a0815cc7553
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '357'
ht-degree: 100%

---

# Asignación de objetos de capa de datos a elementos de datos

Una vez que la organización haya establecido e implementado una capa de datos en el sitio, puede asignar objetos de capa de datos a elementos de datos dentro de las etiquetas.

>[!NOTE]
>Adobe Experience Platform Launch se ha convertido en un conjunto de tecnologías de recopilación de datos en Experience Platform. Como resultado, se han implementado varios cambios terminológicos en la documentación del producto. Consulte el siguiente [documento](https://experienceleague.adobe.com/docs/experience-platform/tags/term-updates.html?lang=es) para obtener una referencia consolidada de los cambios terminológicos.

## Requisitos previos

[Crear una capa de datos](../prepare/data-layer.md): asegúrese de que exista una capa de datos en el sitio. Aunque técnicamente puede asignar cualquier objeto JavaScript o crear secuencias de comandos de elementos CSS directamente desde la página, Adobe recomienda esta práctica como último recurso. Si el diseño del sitio cambia, los selectores de CSS utilizados en las etiquetas dejan de funcionar, lo que provoca la pérdida de datos.

## Uso de etiquetas para crear elementos de datos

Los [elementos de datos](https://experienceleague.adobe.com/docs/experience-platform/tags/ui/data-elements.html?lang=es) son componentes de la IU de recopilación de datos que se pueden usar en toda la herramienta. Puede asignar valores de variables en la extensión de Adobe Analytics mediante elementos de datos.

1. Inicie sesión en la [IU de recopilación de datos](https://experience.adobe.com/data-collection) con sus credenciales de Adobe ID.
1. Haga clic en la propiedad de etiquetas deseada.
1. Haga clic en la pestaña **[!UICONTROL Elementos de datos]** y, a continuación, haga clic en **[!UICONTROL Agregar elemento de datos]**.

   ![crear elemento de datos](assets/createelement.png)

1. Escriba un nombre para el elemento de datos. Puede ser una etiqueta simple que corresponde a una variable de JavaScript en la capa de datos que desee rastrear.
1. En el menú desplegable de **[!UICONTROL Extensión]**, seleccione **[!UICONTROL Principal]**.
1. En el menú desplegable **[!UICONTROL Tipo de elemento de datos]**, seleccione **[!UICONTROL Variable JavaScript]**. Aparece un campo de texto a la derecha que le permite introducir la variable JavaScript para asignarla a este elemento de datos.
1. Introduzca la variable de JavaScript que desee, normalmente dentro de la capa de datos. Por ejemplo, si la capa de datos de su organización coincide estrechamente con la práctica recomendada de Adobe, podría ser un valor de `digitalData.page.pageInfo.pageName`. Puede utilizar la consola del explorador para validar la sintaxis y los valores de las variables de JavaScript.
1. Haga clic en **[!UICONTROL Guardar]**.

## Pasos siguientes

[Asigne elementos de datos a variables de Analytics:](elements-to-variable.md) asigne elementos de datos a variables de Analytics para que pueda utilizarlos como dimensiones en Analysis Workspace.

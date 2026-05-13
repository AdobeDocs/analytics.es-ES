---
title: Asignación de objetos de capa de datos a elementos de datos
description: Configure las etiquetas para que se lean desde la capa de datos.
feature: Tags
exl-id: b7594084-cb5f-408e-8a76-0a0815cc7553
role: Admin, Developer
TQID: https://experienceleague.adobe.com/MmwNCdmt9TwNojJEyzbfTukeh4sKITk06gY-EBzjZPw
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: c153fd90-23e1-4614-81d3-3cc7571227f7
subfeature_v2: id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 312
ht-degree: 93%

---

# Asignación de objetos de capa de datos a elementos de datos

Una vez que la organización haya establecido e implementado una capa de datos en el sitio, puede asignar objetos de capa de datos a elementos de datos dentro de las etiquetas.

## Requisitos previos

[Crear una capa de datos](../prepare/data-layer.md): asegúrese de que exista una capa de datos en el sitio. Aunque técnicamente puede asignar cualquier objeto JavaScript o crear secuencias de comandos de elementos CSS directamente desde la página, Adobe recomienda esta práctica como último recurso. Si el diseño del sitio cambia, los selectores de CSS utilizados en las etiquetas dejan de funcionar, lo que provoca la pérdida de datos.

## Uso de etiquetas para crear elementos de datos

Los [elementos de datos](https://experienceleague.adobe.com/docs/experience-platform/tags/ui/data-elements.html?lang=es) son componentes de la Recopilación de datos de Adobe Experience Platform que se pueden usar en toda la herramienta. Puede asignar valores de variables en la extensión de Adobe Analytics mediante elementos de datos.

1. Inicie sesión en la [Recopilación de datos de Adobe Experience Platform](https://experience.adobe.com/data-collection) con sus credenciales de Adobe ID.
1. Haga clic en la propiedad de etiquetas deseada.
1. Haga clic en la pestaña **[!UICONTROL Elementos de datos]** y, a continuación, haga clic en **[!UICONTROL Agregar elemento de datos]**.

   ![crear elemento de datos](assets/createelement.png)

1. Escriba un nombre para el elemento de datos. Puede ser una etiqueta simple que corresponde a una variable de JavaScript en la capa de datos que desee rastrear.
1. En la lista desplegable **[!UICONTROL Extensión]**, seleccione **[!UICONTROL Principal]**.
1. En la lista desplegable **[!UICONTROL Tipo de elemento de datos]**, seleccione **[!UICONTROL Variable de JavaScript]**. Aparece un campo de texto a la derecha que le permite introducir la variable JavaScript para asignarla a este elemento de datos.
1. Introduzca la variable de JavaScript que desee, normalmente dentro de la capa de datos. Por ejemplo, si la capa de datos de su organización coincide estrechamente con la práctica recomendada de Adobe, podría ser un valor de `digitalData.page.pageInfo.pageName`. Puede utilizar la consola del explorador para validar la sintaxis y los valores de las variables de JavaScript.
1. Haga clic en **[!UICONTROL Guardar]**.

## Pasos siguientes

[Asigne elementos de datos a variables de Analytics:](elements-to-variable.md) asigne elementos de datos a variables de Analytics para que pueda utilizarlos como dimensiones en Analysis Workspace.

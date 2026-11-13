---
title: Asignación de objetos de capa de datos a elementos de datos
description: Configure las etiquetas para que se lean desde la capa de datos.
feature: Tags
exl-id: b7594084-cb5f-408e-8a76-0a0815cc7553
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/MmwNCdmt9TwNojJEyzbfTukeh4sKITk06gY-EBzjZPw'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
    internal-label: Analysis Workspace
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
    internal-label: Components
  - id: df312454-73c4-43f6-a90e-18f5043f074c
    internal-label: Tags
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: 7151dca7425bfb99271db71a3132485f85941a5e
workflow-type: tm+mt
source-wordcount: '407'
ht-degree: 46%
---
# Asignación de objetos de capa de datos a elementos de datos

Una vez que la organización haya establecido e implementado una capa de datos en el sitio, puede asignar objetos de capa de datos a elementos de datos dentro de las etiquetas.

## Requisitos previos

[Crear una capa de datos](../prepare/data-layer.md): asegúrese de que exista una capa de datos en el sitio. Aunque técnicamente puede asignar cualquier objeto JavaScript o crear secuencias de comandos de elementos CSS directamente desde la página, Adobe recomienda esta práctica como último recurso. Si el diseño del sitio cambia, los selectores de CSS utilizados en las etiquetas dejan de funcionar, lo que provoca la pérdida de datos.

## Uso de etiquetas para crear elementos de datos

Los [elementos de datos](https://experienceleague.adobe.com/docs/experience-platform/tags/ui/data-elements.html?lang=es) son componentes de la Recopilación de datos de Adobe Experience Platform que se pueden usar en toda la herramienta. Puede asignar valores de variables en la extensión de Adobe Analytics mediante elementos de datos.

Los pasos siguientes utilizan la [extensión de capa de datos del cliente de Adobe](https://experienceleague.adobe.com/es/docs/experience-platform/tags/extensions/client/client-data-layer/overview), que debe estar instalada en su propiedad de etiquetas.

1. Inicie sesión en la [Recopilación de datos de Adobe Experience Platform](https://experience.adobe.com/data-collection) con sus credenciales de Adobe ID.
1. Seleccione la propiedad de etiquetas que desee.
1. Seleccione la ficha **[!UICONTROL Elementos de datos]** y, a continuación, seleccione **[!UICONTROL Agregar elemento de datos]**.

   ![crear elemento de datos](assets/createelement.png)

1. Escriba un nombre para el elemento de datos, como `Page name`.
1. En la lista desplegable **[!UICONTROL Extensión]**, seleccione **[!UICONTROL Capa de datos del cliente de Adobe]**.
1. En la lista desplegable **[!UICONTROL Tipo de elemento de datos]**, seleccione **[!UICONTROL Estado calculado de la capa de datos]**.
1. En **[!UICONTROL Valor devuelto]**, seleccione **[!UICONTROL Ruta específica]** y, a continuación, escriba la ruta al valor en la capa de datos, como `page.name`. Para validar una ruta de acceso, ejecute `adobeDataLayer.getState("page.name")` en la consola del explorador.
1. Seleccione **[!UICONTROL Guardar]**.

Utilice estos elementos de datos en reglas que incluyan los déclencheur de evento **[!UICONTROL inserción de capa de datos]** de la extensión, de modo que la capa de datos se haya cargado y contenga los datos de la inserción. Consulte [Tipos de elementos de datos](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/client-data-layer/data-element-types#computed-state).

### Capas de datos basadas en objetos {#object-based}

Si la capa de datos es un objeto JavaScript, como un objeto CEDDL `digitalData`, use el tipo de elemento de datos **[!UICONTROL Variable JavaScript]** de la extensión **[!UICONTROL Core]** en su lugar. Escriba la ruta al valor, como `digitalData.page.pageInfo.pageName`. Este tipo de elemento de datos no puede leer la capa de datos del cliente de Adobe, que almacena sus datos en un estado calculado en lugar de en las propiedades de objeto.

## Pasos siguientes

[Asigne elementos de datos a variables de Analytics:](elements-to-variable.md) asigne elementos de datos a variables de Analytics para que pueda utilizarlos como dimensiones en Analysis Workspace.

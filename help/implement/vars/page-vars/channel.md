---
title: canal
description: Rellene la dimensión “Secciones del sitio”.
feature: Variables
exl-id: f494a051-a296-4f1c-9044-04a8b59376fa
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '199'
ht-degree: 74%

---

# canal

La variable `channel` generalmente almacena la sección del sitio en la que se encuentra una página determinada. Es útil determinar qué grupos del sitio son los más populares. Esta variable rellena la dimensión “Secciones del sitio”.

## Canal mediante el SDK web

El canal es [asignado para Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html) en el campo XDM `web.webPageDetails.siteSection`.

## Canal con la extensión Adobe Analytics

Puede establecer Canal durante la configuración de la extensión de Analytics (variables globales) o en reglas.

1. Iniciar sesión en [Recopilación de datos de Adobe Experience Platform](https://experience.adobe.com/data-collection) uso de sus credenciales de Adobe ID.
2. Haga clic en la propiedad de etiquetas deseada.
3. Vaya a la pestaña [!UICONTROL Reglas] y, a continuación, haga clic en la regla que desee (o cree una regla).
4. En [!UICONTROL Acciones], haga clic en una acción existente de [!UICONTROL Adobe Analytics: Establecer variables] o haga clic en el icono “+”.
5. Establezca el menú desplegable [!UICONTROL Extensión] en Adobe Analytics y el [!UICONTROL tipo de acción] en [!UICONTROL Establecer variables].
6. Busque la sección [!UICONTROL Canal].

Puede establecer Canal en cualquier valor de cadena o elemento de datos.

## s.channel en AppMeasurement y el editor de código personalizado de la extensión de Analytics

La variable `s.channel` es una cadena que generalmente contiene la sección del sitio de la página. Tiene un valor máximo de 100 bytes. Los valores más largos se truncan.

```js
s.channel = "Example site section";
```

Si utiliza la `digitalData` [capa de datos](../../prepare/data-layer.md):

```js
s.channel = digitalData.page.category.primaryCategory;
```

---
title: canal
description: Rellene la dimensión “Secciones del sitio”.
feature: Appmeasurement Implementation
exl-id: f494a051-a296-4f1c-9044-04a8b59376fa
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '194'
ht-degree: 75%

---

# canal

La variable `channel` generalmente almacena la sección del sitio en la que se encuentra una página determinada. Es útil determinar qué grupos del sitio son los más populares. Esta variable rellena la dimensión “Secciones del sitio”.

## Canal mediante Web SDK

El canal está asignado a las siguientes variables:

* [objeto XDM](/help/implement/aep-edge/xdm-var-mapping.md): `web.webPageDetails.siteSection`
* [Objeto de datos](/help/implement/aep-edge/data-var-mapping.md): `data.__adobe.analytics.channel` o `data.__adobe.analytics.ch`

## Canal con la extensión de Adobe Analytics

Puede establecer Canal durante la configuración de la extensión de Analytics (variables globales) o en reglas.

1. Inicie sesión en la [Recopilación de datos de Adobe Experience Platform](https://experience.adobe.com/data-collection) con sus credenciales de Adobe ID.
2. Haga clic en la propiedad de etiquetas deseada.
3. Vaya a la pestaña [!UICONTROL Reglas] y, a continuación, haga clic en la regla que desee (o cree una regla).
4. En [!UICONTROL Acciones], haga clic en una acción existente de [!UICONTROL Adobe Analytics: Establecer variables] o haga clic en el icono “+”.
5. Establezca la lista desplegable [!UICONTROL Extension] en Adobe Analytics y [!UICONTROL Action Type] en [!UICONTROL Set Variables].
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

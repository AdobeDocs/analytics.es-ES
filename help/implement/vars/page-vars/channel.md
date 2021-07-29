---
title: canal
description: Rellene la dimensión “Secciones del sitio”.
exl-id: f494a051-a296-4f1c-9044-04a8b59376fa
source-git-commit: 1a49c2a6d90fc670bd0646d6d40738a87b74b8eb
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 87%

---

# canal

La variable `channel` generalmente almacena la sección del sitio en la que se encuentra una página determinada. Es útil determinar qué grupos del sitio son los más populares. Esta variable rellena la dimensión “Secciones del sitio”.

## Canal que utiliza etiquetas en Adobe Experience Platform

Puede establecer Canal durante la configuración de la extensión de Analytics (variables globales) o en reglas.

1. Inicie sesión en la [interfaz de usuario de recopilación de datos](https://experience.adobe.com/data-collection) con sus credenciales de Adobe ID.
2. Haga clic en la propiedad deseada.
3. Vaya a la pestaña [!UICONTROL Reglas] y, a continuación, haga clic en la regla que desee (o cree una regla).
4. En [!UICONTROL Acciones], haga clic en una acción existente de [!UICONTROL Adobe Analytics: Establecer variables] o haga clic en el icono “+”.
5. Establezca el menú desplegable [!UICONTROL Extensión] en Adobe Analytics y el [!UICONTROL tipo de acción] en [!UICONTROL Establecer variables].
6. Busque la sección [!UICONTROL Canal].

Puede establecer Canal en cualquier valor de cadena o elemento de datos.

## s.channel en el editor de código personalizado de AppMeasurement y 

La variable `s.channel` es una cadena que generalmente contiene la sección del sitio de la página. Tiene un valor máximo de 100 bytes. Los valores más largos se truncan.

```js
s.channel = "Example site section";
```

Si utiliza la `digitalData` [capa de datos](../../prepare/data-layer.md):

```js
s.channel = digitalData.page.category.primaryCategory;
```

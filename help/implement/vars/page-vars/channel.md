---
title: canal
description: Rellene la dimensión “Secciones del sitio”.
translation-type: tm+mt
source-git-commit: ec6d8e6a3cef3a5fd38d91775c83ab95de47fd55
workflow-type: tm+mt
source-wordcount: '169'
ht-degree: 97%

---


# canal

La variable `channel` generalmente almacena la sección del sitio en la que se encuentra una página determinada. Es útil determinar qué grupos del sitio son los más populares. Esta variable rellena la dimensión “Secciones del sitio”.

## Canal en Adobe Experience Platform Launch

Puede establecer Canal durante la configuración de la extensión de Analytics (variables globales) o en reglas.

1. Inicie sesión en [launch.adobe.com](https://launch.adobe.com) con sus credenciales de Adobe ID.
2. Haga clic en la propiedad deseada.
3. Vaya a la pestaña [!UICONTROL Reglas] y, a continuación, haga clic en la regla que desee (o cree una regla).
4. En [!UICONTROL Acciones], haga clic en una acción existente de [!UICONTROL Adobe Analytics: Establecer variables] o haga clic en el icono “+”.
5. Establezca el menú desplegable [!UICONTROL Extensión] en Adobe Analytics y el [!UICONTROL tipo de acción] en [!UICONTROL Establecer variables].
6. Busque la sección [!UICONTROL Canal].

Puede establecer Canal en cualquier valor de cadena o elemento de datos.

## s.channel en el editor de código personalizado de AppMeasurement y Launch

La variable `s.channel` es una cadena que generalmente contiene la sección del sitio de la página. Tiene un valor máximo de 100 bytes. Los valores más largos se truncan.

```js
s.channel = "Example site section";
```

Si utiliza la capa `digitalData` [de](../../prepare/data-layer.md)datos:

```js
s.channel = digitalData.page.category.primaryCategory;
```

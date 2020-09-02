---
title: pageURL
description: Omitir la dirección URL de la página registrada automáticamente en el sitio.
translation-type: tm+mt
source-git-commit: ec6d8e6a3cef3a5fd38d91775c83ab95de47fd55
workflow-type: tm+mt
source-wordcount: '272'
ht-degree: 81%

---


# pageURL

AppMeasurement registra automáticamente la dirección URL de la página en cada visita. Si desea omitir la dirección URL de la página registrada automáticamente por AppMeasurement, puede utilizar esta variable. No es necesario configurar esta variable en la mayoría de los casos.

>[!NOTE]
>
>Esta variable no es una dimensión disponible en Analysis Workspace. Solo está disponible en Data Warehouse y en Data Feeds. Además, los servidores de recopilación de datos de Adobe eliminan esta dimensión de todas las solicitudes de imagen de seguimiento [de](/help/implement/vars/functions/tl-method.md) vínculos. Si desea utilizar la dirección URL de la página como dimensión en Analysis Workspace o desea esta dimensión en las visitas de seguimiento de vínculos, considere pasar la `pageURL` variable a un [eVar](evar.md) en cada visita.

## Dirección URL en Adobe Experience Platform Launch

Launch completa automáticamente la dirección URL de la página. Sin embargo, puede establecer la anulación de la dirección URL de la página al configurar la extensión de Analytics (variables globales) o en reglas.

1. Inicie sesión en [launch.adobe.com](https://launch.adobe.com) con sus credenciales de Adobe ID.
2. Haga clic en la propiedad deseada.
3. Vaya a la pestaña **[!UICONTROL Reglas]** y, a continuación, haga clic en la regla que desee (o cree una regla).
4. En **[!UICONTROL Acciones]**, haga clic en una acción existente de **[!UICONTROL Adobe Analytics: Establecer variables]** o haga clic en el icono “+”.
5. Establezca el menú desplegable **[!UICONTROL Extensión]** en Adobe Analytics y el **[!UICONTROL tipo de acción]** en **[!UICONTROL Establecer variables]**.
6. Busque la sección **[!UICONTROL Dirección URL de la página]**.

Puede establecer la dirección URL de la página en cualquier valor de cadena.

## “s.pageURL” en el editor de código personalizado de AppMeasurement y Launch

La variable `s.pageURL` es una cadena que contiene la dirección URL de la página. AppMeasurement registra automáticamente esta variable, aunque puede anular su valor si lo desea.

```js
s.pageURL = "https://example.com";
```

Si desea utilizar la dirección URL de la página como dimensión en los informes, pruebe a utilizar lo siguiente en la implementación:

```js
// Set eVar1 to page URL without protocol or query strings
s.eVar1 = window.location.hostname + window.location.pathname;
```

Si utiliza la capa `digitalData` [de](../../prepare/data-layer.md)datos:

```js
s.pageURL = digitalData.page.pageInfo.destinationURL;
```

---
title: pageURL
description: Omitir la dirección URL de la página registrada automáticamente en el sitio.
feature: Variables
exl-id: 411f894d-c31f-4d07-9568-b0b02786735d
role: Admin, Developer
source-git-commit: 5ef92db2f5edb5fded497dddedd56abd49d8a019
workflow-type: tm+mt
source-wordcount: '306'
ht-degree: 79%

---

# pageURL

AppMeasurement registra automáticamente la dirección URL de la página en cada visita. Si desea omitir la dirección URL de la página registrada automáticamente por AppMeasurement, puede utilizar esta variable. No es necesario configurar esta variable en la mayoría de los casos.

>[!NOTE]
>
>Esta variable no es una dimensión disponible en Analysis Workspace. Solo está disponible en Data Warehouse y en Data Feeds. Además, los servidores de recopilación de datos de Adobe eliminan esta dimensión de todas las solicitudes de imagen de [seguimiento de vínculos](/help/implement/vars/functions/tl-method.md). Si desea utilizar la dirección URL de la página como dimensión en Analysis Workspace o desea tener esta dimensión en las visitas de seguimiento de vínculos, considere pasar la variable `pageURL` a una [eVar](evar.md) en cada visita.

## Dirección URL de la página mediante el SDK web

La dirección URL de la página está asignada a las siguientes variables:

* [Objeto XDM](/help/implement/aep-edge/xdm-var-mapping.md): `xdm.web.webPageDetails.URL`
* [Objeto de datos](/help/implement/aep-edge/data-var-mapping.md): `data.__adobe.analytics.pageURL` o `data.__adobe.analytics.g`

## Dirección URL de la página con la extensión Adobe Analytics

La extensión de Analytics en la recopilación de datos de Adobe Experience Platform rellena automáticamente la dirección URL de la página. Sin embargo, puede establecer la anulación de la dirección URL de la página al configurar la extensión de Analytics (variables globales) o en reglas.

1. Inicie sesión en la [Recopilación de datos de Adobe Experience Platform](https://experience.adobe.com/data-collection) con sus credenciales de Adobe ID.
2. Haga clic en la propiedad de etiquetas deseada.
3. Vaya a la pestaña **[!UICONTROL Reglas]** y, a continuación, haga clic en la regla que desee (o cree una regla).
4. En **[!UICONTROL Acciones]**, haga clic en una acción existente de **[!UICONTROL Adobe Analytics: Establecer variables]** o haga clic en el icono “+”.
5. Configure las variables **[!UICONTROL Extensión]** lista desplegable para Adobe Analytics y la variable **[!UICONTROL Tipo de acción]** hasta **[!UICONTROL Establecer variables]**.
6. Busque la sección **[!UICONTROL Dirección URL de la página]**.

Puede establecer la dirección URL de la página en cualquier valor de cadena.

## s.pageURL en el AppMeasurement y el editor de código personalizado de la extensión de Analytics

La variable `s.pageURL` es una cadena que contiene la dirección URL de la página. AppMeasurement registra automáticamente esta variable, aunque puede anular su valor si lo desea.

```js
s.pageURL = "https://example.com";
```

Si desea utilizar la dirección URL de la página como dimensión en los informes, pruebe a utilizar lo siguiente en la implementación:

```js
// Set eVar1 to page URL without protocol or query strings
s.eVar1 = window.location.hostname + window.location.pathname;
```

Si utiliza la `digitalData` [capa de datos](../../prepare/data-layer.md):

```js
s.pageURL = digitalData.page.pageInfo.destinationURL;
```

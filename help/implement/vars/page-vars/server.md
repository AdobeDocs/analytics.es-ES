---
title: servidor
description: Rellene la dimensión “Servidores”.
feature: Variables
exl-id: 7904c3c2-9a91-497e-89d0-9eed9ae7a902
role: Admin, Developer
source-git-commit: 5ef92db2f5edb5fded497dddedd56abd49d8a019
workflow-type: tm+mt
source-wordcount: '183'
ht-degree: 74%

---

# servidor

La variable `server` generalmente almacena el nombre de host del sitio. Normalmente se utiliza en grupos de informes que contienen datos de varios dominios. Desde el punto de vista de la funcionalidad es idéntico a una prop.

## Servidor con el SDK web

El servidor está asignado a las siguientes variables:

* [objeto XDM](/help/implement/aep-edge/xdm-var-mapping.md): `xdm.web.webPageDetails.server`
* [Objeto de datos](/help/implement/aep-edge/data-var-mapping.md): `data.__adobe.analytics.server`

## Servidor con la extensión de Adobe Analytics

Puede configurar el servidor durante la configuración de la extensión de Analytics (variables globales) o en reglas.

1. Inicie sesión en la [Recopilación de datos de Adobe Experience Platform](https://experience.adobe.com/data-collection) con sus credenciales de Adobe ID.
2. Haga clic en la propiedad de etiquetas deseada.
3. Vaya a la pestaña [!UICONTROL Reglas] y, a continuación, haga clic en la regla que desee (o cree una regla).
4. En [!UICONTROL Acciones], haga clic en una acción existente de [!UICONTROL Adobe Analytics: Establecer variables] o haga clic en el icono “+”.
5. Establezca la lista desplegable [!UICONTROL Extension] en Adobe Analytics y [!UICONTROL Action Type] en [!UICONTROL Set Variables].
6. Busque la sección [!UICONTROL Servidor].

Puede establecer el servidor en cualquier valor de cadena o elemento de datos.

## s.server en el AppMeasurement y el editor de código personalizado de la extensión de Analytics

La variable `s.server` es una cadena que generalmente contiene el nombre de host del sitio. Tiene un valor máximo de 100 bytes. Los valores más largos se truncan.

```js
// Set the server variable to a static string
s.server = "Example server";

// Automatically set the server variable to the site's hostname
s.server = window.location.hostname;
```

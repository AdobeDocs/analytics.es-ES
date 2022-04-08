---
title: servidor
description: Rellene la dimensión “Servidores”.
feature: Variables
exl-id: 7904c3c2-9a91-497e-89d0-9eed9ae7a902
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: ht
source-wordcount: '163'
ht-degree: 100%

---

# servidor

La variable `server` generalmente almacena el nombre de host del sitio. Normalmente se utiliza en grupos de informes que contienen datos de varios dominios. Desde el punto de vista de la funcionalidad es idéntico a una prop.

## Servidor con etiquetas en Adobe Experience Platform

Puede configurar el servidor durante la configuración de la extensión de Analytics (variables globales) o en reglas.

1. Inicie sesión en la [IU de recopilación de datos](https://experience.adobe.com/data-collection) con sus credenciales de Adobe ID.
2. Haga clic en la propiedad deseada.
3. Vaya a la pestaña [!UICONTROL Reglas] y, a continuación, haga clic en la regla que desee (o cree una regla).
4. En [!UICONTROL Acciones], haga clic en una acción existente de [!UICONTROL Adobe Analytics: Establecer variables] o haga clic en el icono “+”.
5. Establezca el menú desplegable [!UICONTROL Extensión] en Adobe Analytics y el [!UICONTROL tipo de acción] en [!UICONTROL Establecer variables].
6. Busque la sección [!UICONTROL Servidor].

Puede establecer el servidor en cualquier valor de cadena o elemento de datos.

## “s.server” en el editor de código personalizado de AppMeasurement y 

La variable `s.server` es una cadena que generalmente contiene el nombre de host del sitio. Tiene un valor máximo de 100 bytes. Los valores más largos se truncan.

```js
// Set the server variable to a static string
s.server = "Example server";

// Automatically set the server variable to the site's hostname
s.server = window.location.hostname;
```

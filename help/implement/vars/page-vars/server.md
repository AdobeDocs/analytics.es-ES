---
title: servidor
description: Rellene la dimensión “Servidores”.
exl-id: 7904c3c2-9a91-497e-89d0-9eed9ae7a902
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '159'
ht-degree: 100%

---

# servidor

La variable `server` generalmente almacena el nombre de host del sitio. Normalmente se utiliza en grupos de informes que contienen datos de varios dominios. Desde el punto de vista de la funcionalidad es idéntico a una prop.

## Servidor en Adobe Experience Platform Launch

Puede configurar el servidor durante la configuración de la extensión de Analytics (variables globales) o en reglas.

1. Inicie sesión en [launch.adobe.com](https://launch.adobe.com) con sus credenciales de Adobe ID.
2. Haga clic en la propiedad deseada.
3. Vaya a la pestaña [!UICONTROL Reglas] y, a continuación, haga clic en la regla que desee (o cree una regla).
4. En [!UICONTROL Acciones], haga clic en una acción existente de [!UICONTROL Adobe Analytics: Establecer variables] o haga clic en el icono “+”.
5. Establezca el menú desplegable [!UICONTROL Extensión] en Adobe Analytics y el [!UICONTROL tipo de acción] en [!UICONTROL Establecer variables].
6. Busque la sección [!UICONTROL Servidor].

Puede establecer el servidor en cualquier valor de cadena o elemento de datos.

## “s.server” en el editor de código personalizado de AppMeasurement y Launch

La variable `s.server` es una cadena que generalmente contiene el nombre de host del sitio. Tiene un valor máximo de 100 bytes. Los valores más largos se truncan.

```js
// Set the server variable to a static string
s.server = "Example server";

// Automatically set the server variable to the site's hostname
s.server = window.location.hostname;
```

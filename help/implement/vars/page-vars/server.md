---
title: servidor
description: Rellene la dimensión “Servidores”.
feature: Appmeasurement Implementation
exl-id: 7904c3c2-9a91-497e-89d0-9eed9ae7a902
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/P0txq9O6mdXQ-avevETR0BTLRf3kQHAaN9HBFki8XKQ'
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 187
ht-degree: 82%

---

# servidor

La variable `server` generalmente almacena el nombre de host del sitio. Normalmente se utiliza en grupos de informes que contienen datos de varios dominios. Desde el punto de vista de la funcionalidad es idéntico a una prop.

## Servidor con Web SDK

El servidor está asignado a las siguientes variables:

* [objeto XDM](/help/implement/aep-edge/xdm-var-mapping.md): `xdm.web.webPageDetails.server`
* [Objeto de datos](/help/implement/aep-edge/data-var-mapping.md): `data.__adobe.analytics.server`

## Servidor con la extensión de Adobe Analytics

Puede configurar el servidor durante la configuración de la extensión de Analytics (variables globales) o en reglas.

1. Inicie sesión en la [Recopilación de datos de Adobe Experience Platform](https://experience.adobe.com/data-collection) con sus credenciales de Adobe ID.
2. Haga clic en la propiedad de etiquetas deseada.
3. Vaya a la pestaña [!UICONTROL Reglas] y, a continuación, haga clic en la regla que desee (o cree una regla).
4. En [!UICONTROL Acciones], haga clic en una acción existente de [!UICONTROL Adobe Analytics: Establecer variables] o haga clic en el icono “+”.
5. Establezca la lista desplegable [!UICONTROL Extensión] en Adobe Analytics y el [!UICONTROL tipo de acción] en [!UICONTROL Establecer variables].
6. Busque la sección [!UICONTROL Servidor].

Puede establecer el servidor en cualquier valor de cadena o elemento de datos.

## s.server en AppMeasurement y el editor de código personalizado de la extensión de Analytics

La variable `s.server` es una cadena que generalmente contiene el nombre de host del sitio. Tiene un valor máximo de 100 bytes. Los valores más largos se truncan.

```js
// Set the server variable to a static string
s.server = "Example server";

// Automatically set the server variable to the site's hostname
s.server = window.location.hostname;
```

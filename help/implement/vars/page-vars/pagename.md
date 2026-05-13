---
title: pageName
description: El nombre de la página del sitio.
feature: Appmeasurement Implementation
exl-id: 24ac40a9-f0e7-4534-abf2-2397f5fe16c2
role: Admin, Developer
TQID: https://experienceleague.adobe.com/8afiyqnZrImK-YJ-GvQGu0H4fzhcJrMh20QN2WbO0T0
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 262
ht-degree: 86%

---

# pageName

La variable `pageName` generalmente almacena el nombre de una página determinada. Es útil determinar qué páginas individuales son más populares. Esta variable rellena la dimensión [Página](/help/components/dimensions/page.md).

Si esta variable no está definida en una llamada de seguimiento de página determinada, se utiliza la variable [`pageURL`](pageurl.md) en su lugar.

>[!NOTE]
>
>Los servidores de recopilación de datos de Adobe eliminan esta dimensión de todas las solicitudes de imagen de [seguimiento de vínculos](/help/implement/vars/functions/tl-method.md). Si desea que esta dimensión aparezca en las visitas de seguimiento de vínculos, considere la posibilidad de copiar esta dimensión en una [eVar](evar.md).

## Nombre de página con Web SDK

El nombre de página está asignado a las siguientes variables:

* [objeto XDM](/help/implement/aep-edge/xdm-var-mapping.md): `xdm.web.webPageDetails.name`
* [Objeto de datos](/help/implement/aep-edge/data-var-mapping.md): `data.__adobe.analytics.pageName`

## Nombre de página con la extensión Adobe Analytics

Puede definir el nombre de la página al configurar la extensión de Analytics (variables globales) o en reglas.

1. Inicie sesión en la [Recopilación de datos de Adobe Experience Platform](https://experience.adobe.com/data-collection) con sus credenciales de Adobe ID.
2. Haga clic en la propiedad de etiquetas deseada.
3. Vaya a la pestaña [!UICONTROL Reglas] y, a continuación, haga clic en la regla que desee (o cree una regla).
4. En [!UICONTROL Acciones], haga clic en una acción existente de [!UICONTROL Adobe Analytics: Establecer variables] o haga clic en el icono “+”.
5. Establezca la lista desplegable [!UICONTROL Extensión] en Adobe Analytics y el [!UICONTROL tipo de acción] en [!UICONTROL Establecer variables].
6. Busque la sección [!UICONTROL Nombre de la página].

Puede establecer el nombre de la página en cualquier valor de cadena, incluidos los elementos de datos.

## s.pageName en AppMeasurement y el editor de código personalizado de la extensión de Analytics

La variable `s.pageName` es una cadena que generalmente contiene el nombre de la página. Tiene un valor máximo de 100 bytes. Los valores más largos se truncan. Este truncamiento incluye instancias a las que se recupera `pageURL` si esta variable está en blanco.

```js
// Set page name to a static value
s.pageName = "Example page name";

// Set page name to the page's title
s.pageName = window.document.title;
```

Si utiliza la `digitalData` [capa de datos](../../prepare/data-layer.md):

```js
s.pageName = digitalData.page.pageInfo.pageName;
```

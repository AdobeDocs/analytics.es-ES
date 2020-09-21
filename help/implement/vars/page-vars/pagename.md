---
title: pageName
description: El nombre de la página del sitio.
translation-type: tm+mt
source-git-commit: ec6d8e6a3cef3a5fd38d91775c83ab95de47fd55
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# pageName

La variable `pageName` generalmente almacena el nombre de una página determinada. Es útil determinar qué páginas individuales son más populares. This variable populates the [Page](/help/components/dimensions/page.md) dimension.

Si esta variable no está definida en una llamada de seguimiento de página determinada, se utiliza la variable [`pageURL`](pageurl.md) en su lugar.

>[!NOTE]
>
>Los servidores de recopilación de datos de Adobe eliminan esta dimensión de todas las solicitudes de imagen de seguimiento [de](/help/implement/vars/functions/tl-method.md) vínculos. Si desea que esta dimensión aparezca en las visitas de seguimiento de vínculos, considere copiar esta dimensión en un [eVar](evar.md).

## Nombre de página en Adobe Experience Platform Launch

Puede definir el nombre de la página al configurar la extensión de Analytics (variables globales) o en reglas.

1. Inicie sesión en [launch.adobe.com](https://launch.adobe.com) con sus credenciales de Adobe ID.
2. Haga clic en la propiedad deseada.
3. Vaya a la pestaña [!UICONTROL Reglas] y, a continuación, haga clic en la regla que desee (o cree una regla).
4. En [!UICONTROL Acciones], haga clic en una acción existente de [!UICONTROL Adobe Analytics: Establecer variables] o haga clic en el icono “+”.
5. Establezca el menú desplegable [!UICONTROL Extensión] en Adobe Analytics y el [!UICONTROL tipo de acción] en [!UICONTROL Establecer variables].
6. Busque la sección [!UICONTROL Nombre de la página].

Puede establecer el nombre de la página en cualquier valor de cadena, incluidos los elementos de datos.

## “s.pageName” en el editor de código personalizado de AppMeasurement y Launch

La variable `s.pageName` es una cadena que generalmente contiene el nombre de la página. Tiene un valor máximo de 100 bytes. Los valores más largos se truncan. Este truncamiento incluye instancias a las que se recupera `pageURL` si esta variable está en blanco.

```js
// Set page name to a static value
s.pageName = "Example page name";

// Set page name to the page's title
s.pageName = window.document.title;
```

Si utiliza la capa `digitalData` [de](../../prepare/data-layer.md)datos:

```js
s.pageName = digitalData.page.pageInfo.pageName;
```

---
title: sa
description: Cambie el grupo de informes en cualquier momento de la implementación.
feature: Variables
exl-id: 524857a7-c820-4985-86c7-fcf21a0809bd
role: Admin, Developer
source-git-commit: bfafc1f8eddf82b34fb45e3d6197213f0cee0d97
workflow-type: tm+mt
source-wordcount: '430'
ht-degree: 42%

---

# sa

El método `sa()` permite cambiar dinámicamente un grupo de informes en la página en cualquier momento. Si desea enviar datos a distintos grupos de informes sin una recarga de página, puede utilizar este método.

## Gestión de grupos de informes mediante el SDK web

El SDK web funciona enviando datos a un conjunto de datos específico, que reenvía datos a los grupos de informes de Analytics deseados. Un único conjunto de datos puede reenviar datos a varios grupos de informes. Esta sección se aplica tanto a la extensión del SDK web como a la implementación manual del SDK web.

1. Inicie sesión en la [Recopilación de datos de Adobe Experience Platform](https://experience.adobe.com/data-collection) con sus credenciales de Adobe ID.
1. Haga clic en **[!UICONTROL Datastreams]** a la izquierda.
1. Haga clic en la secuencia de datos deseada o en **[!UICONTROL Nueva secuencia de datos]**.
1. Haga clic en **[!UICONTROL Agregar servicio]** y, a continuación, seleccione **[!UICONTROL Adobe Analytics]**.
1. Introduzca el ID del grupo de informes deseado. Si desea enviar los mismos datos a varios grupos de informes, haga clic en **[!UICONTROL Agregar grupo de informes]**.
1. Una vez que se especifiquen todos los grupos de informes deseados, haga clic en **[!UICONTROL Guardar]**.

## Establezca la secuencia de datos deseada mediante la extensión del SDK web

La extensión del SDK web proporciona una lista desplegable de secuencia de datos para cada entorno. También puede introducir manualmente el ID de flujo de datos.

1. Inicie sesión en la [Recopilación de datos de Adobe Experience Platform](https://experience.adobe.com/data-collection) con sus credenciales de Adobe ID.
1. Haga clic en la propiedad de etiquetas deseada.
1. Vaya a la pestaña [!UICONTROL Extensions] y, a continuación, haga clic en el botón **[!UICONTROL Configure]** en [!UICONTROL Adobe Experience Platform Web SDK].
1. En [!UICONTROL Flujos de datos], elija el flujo de datos deseado en la lista desplegable de cada entorno.
1. Haga clic en **[!UICONTROL Guardar]**.

## Establezca el conjunto de datos deseado manualmente implementando el SDK web

Establezca la variable de configuración `datastreamId` en el ID de flujo de datos. El ID de flujo de datos se encuentra a la derecha al ver un flujo de datos en la recopilación de datos de Adobe Experience Platform.

```js
alloy("configure", {
  datastreamId: "example-a01f-4458-8cec-ef61de241c93",
  orgId: "ADB3LETTERSANDNUMBERS@AdobeOrg"
});
```

Consulte [Configurar el SDK web](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=es) en la documentación del SDK web para obtener más información.

## Cambiar el grupo de informes con la extensión Adobe Analytics

No existe una manera flexible de cambiar el grupo de informes en la interfaz. Puede configurar el grupo de informes en el acordeón de [!UICONTROL Administración de biblioteca] al configurar la extensión de Adobe Analytics. Sin embargo, no puede cambiar ni actualizar el grupo de informes mediante reglas. Si desea actualizar los valores de los grupos de informes una vez configurados, utilice el editor de código personalizado siguiendo la sintaxis de AppMeasurement.

## s.sa() en el AppMeasurement y el editor de código personalizado de la extensión de Analytics

Llame al método `s.sa()` para cambiar el grupo de informes de destino. Su único argumento es una cadena que contiene un ID de grupo de informes o varios ID de grupo de informes delimitadas por una coma. Se requiere el argumento del ID del grupo de informes. No utilice espacios en el argumento de cadena.

```js
s.sa("examplersid");
```

Por ejemplo, puede cambiar el grupo de informes si el usuario realiza una acción específica en el sitio.

```js
// Instantiate the tracking object
var s = s_gi("examplersid");

// If the visitor plays a video, you can add a video report suite
s.sa("examplersid,videorsid");

// Then send an image request
s.t();
```

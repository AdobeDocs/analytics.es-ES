---
title: sa
description: Cambie el grupo de informes en cualquier momento de la implementación.
feature: Variables
exl-id: 524857a7-c820-4985-86c7-fcf21a0809bd
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '438'
ht-degree: 38%

---

# sa

El método `sa()` permite cambiar dinámicamente un grupo de informes en la página en cualquier momento. Si desea enviar datos a distintos grupos de informes sin una recarga de página, puede utilizar este método.

## Administración de grupos de informes mediante el SDK web

El SDK web funciona enviando datos a un almacén de datos específico, que reenvía datos a los grupos de informes de Analytics que desee. Un solo almacén de datos puede reenviar datos a varios grupos de informes. Esta sección se aplica tanto a la extensión del SDK web como a la implementación manual del SDK web.

1. Iniciar sesión en [Recopilación de datos de Adobe Experience Platform](https://experience.adobe.com/data-collection) uso de sus credenciales de Adobe ID.
1. Haga clic en **[!UICONTROL Datastreams]** a la izquierda.
1. Haga clic en el conjunto de datos deseado o haga clic en **[!UICONTROL Nuevo conjunto de datos]**.
1. Haga clic en **[!UICONTROL Añadir servicio]** y, a continuación, seleccione **[!UICONTROL Adobe Analytics]**.
1. Introduzca la ID del grupo de informes que desee. Si desea enviar los mismos datos a varios grupos de informes, haga clic en **[!UICONTROL Agregar grupo de informes]**.
1. Una vez introducidos todos los grupos de informes deseados, haga clic en **[!UICONTROL Guardar]**.

## Establezca el conjunto de datos deseado mediante la extensión Web SDK

La extensión del SDK web proporciona un menú desplegable de Datastream para cada entorno. Como alternativa, puede introducir manualmente el ID de almacén de datos.

1. Iniciar sesión en [Recopilación de datos de Adobe Experience Platform](https://experience.adobe.com/data-collection) uso de sus credenciales de Adobe ID.
1. Haga clic en la propiedad de etiquetas deseada.
1. Vaya a la [!UICONTROL Extensiones] y, a continuación, haga clic en la pestaña **[!UICONTROL Configurar]** botón debajo de [!UICONTROL SDK web de Adobe Experience Platform].
1. En [!UICONTROL Datastreams], elija el conjunto de datos deseado en la lista desplegable de cada entorno.
1. Haga clic en **[!UICONTROL Guardar]**.

## Establezca el conjunto de datos deseado implementando manualmente el SDK web

Configure las variables `edgeConfigId` a ID de almacén de datos. El ID de almacén de datos se encuentra a la derecha cuando se visualiza un conjunto de datos en la recopilación de datos de Adobe Experience Platform.

```js
alloy("configure", {
  "edgeConfigId": "example-a01f-4458-8cec-ef61de241c93",
});
```

Consulte [Configuración del SDK web](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=es) en la documentación del SDK web para obtener más información.

## Cambiar grupo de informes con la extensión de Adobe Analytics

No existe una manera flexible de cambiar el grupo de informes en la interfaz. Puede configurar el grupo de informes en el acordeón de [!UICONTROL Administración de biblioteca] al configurar la extensión de Adobe Analytics. Sin embargo, no puede cambiar ni actualizar el grupo de informes mediante reglas. Si desea actualizar los valores de los grupos de informes una vez configurados, utilice el editor de código personalizado siguiendo la sintaxis de AppMeasurement.

## s.sa() en AppMeasurement y el editor de código personalizado de la extensión de Analytics

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

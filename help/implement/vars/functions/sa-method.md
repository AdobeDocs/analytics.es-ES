---
title: sa
description: Cambie el grupo de informes en cualquier momento de la implementación.
translation-type: tm+mt
source-git-commit: f179292abae9cf7986d61da89a86e3e88111943e

---


# sa

El `sa` método permite cambiar dinámicamente un grupo de informes en cualquier momento de la página. Si desea enviar datos a distintos grupos de informes sin una recarga de página, puede utilizar este método.

## Uso del método sa en Adobe Experience Platform Launch

No existe una manera flexible de cambiar el grupo de informes en la interfaz. Puede configurar el grupo de informes en el acordeón Administración [!UICONTROL de] biblioteca al configurar la extensión de Adobe Analytics. Sin embargo, no puede cambiar ni actualizar el grupo de informes mediante reglas. Si desea actualizar los valores de los grupos de informes una vez configurados, utilice el editor de código personalizado siguiendo la sintaxis de AppMeasurement.

## s.sa() en el editor de código personalizado AppMeasurement e Launch

Llame al `s.sa()` método para cambiar el grupo de informes de destino. Su único argumento es una cadena que contiene una ID de grupo de informes o varias ID de grupo de informes delimitadas por una coma. Se requiere el argumento de la ID del grupo de informes. No utilice espacios en el argumento de cadena.

```js
s.sa("examplersid");
```

## Ejemplo

Puede cambiar el grupo de informes si el usuario realiza una acción específica en el sitio.

```js
// Instantiate the tracking object
var s = s_gi("examplersid");

// If the visitor plays a video, you can add a video report suite
s.sa("examplersid,videorsid");

// Then send an image request
s.t();
```

---
title: state
description: Rellene el “Informe de estado del visitante” en Reports and Analytics.
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# state

>[!IMPORTANT] Esta variable desaparece y no es una dimensión disponible en Analysis Workspace. En su lugar, utilice la dimensión “Estados de EE. UU.”, que AppMeasurement registra automáticamente en función de la ubicación del visitante.

En versiones anteriores de Adobe Analytics, la variable `state` se utilizaba cuando los visitantes rellenaban la información de envío en sitios de venta al por menor. Desde el punto de vista funcional, es idéntico a una prop, pero no está disponible en Analysis Workspace.

## Estado en Adobe Experience Platform Launch

Puede establecer el estado al configurar la extensión de Analytics (variables globales) o en reglas.

1. Inicie sesión en [launch.adobe.com](https://launch.adobe.com) con sus credenciales de Adobe ID.
2. Haga clic en la propiedad deseada.
3. Go to the [!UICONTROL Rules] tab, then click the desired rule (or create a rule).
4. En [!UICONTROL Actions], haga clic en una [!UICONTROL Adobe Analytics - Set Variables] acción existente o en el icono &#39;+&#39;.
5. Establezca el [!UICONTROL Extension] menú desplegable en Adobe Analytics y el valor [!UICONTROL Action Type] en [!UICONTROL Set Variables].
6. Locate the [!UICONTROL State] section.

Puede establecer el estado en cualquier valor de cadena o elemento de datos.

## “s.state” en el editor de código personalizado de AppMeasurement y Launch

La variable `s.state` es una cadena que generalmente contiene el estado o la provincia del visitante. Son válidos tanto los nombres de estado completos como los códigos de dos letras. Tiene un valor máximo de 50 bytes. Los valores más largos se truncan. Aparece como una cadena vacía de manera predeterminada.

```js
s.state = "Utah";
```

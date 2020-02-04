---
title: Estado
description: Rellene el 'Informe de estado del visitante' en Informes y análisis.
translation-type: tm+mt
source-git-commit: f75c6759feb6576017733f1aac5bff2e21d4b0af

---


# state

> [!IMPORTANT] Esta variable se retira y no es una dimensión disponible en Analysis Workspace. En su lugar, utilice la dimensión &#39;Estados de EE.UU.&#39;, que AppMeasurement recopila automáticamente en función de la ubicación del visitante.

En versiones anteriores de Adobe Analytics, la `state` variable se utilizaba cuando los visitantes rellenaban la información de envío en sitios minoristas. Funcionalmente es idéntico a una propiedad, pero no está disponible en Analysis Workspace.

## Estado en Adobe Experience Platform Launch

Puede establecer el estado al configurar la extensión de Analytics (variables globales) o en reglas.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. Haga clic en la propiedad que desee.
3. Vaya a la ficha [!UICONTROL Reglas] y, a continuación, haga clic en la regla que desee (o cree una regla).
4. En [!UICONTROL Acciones], haga clic en una acción existente de [!UICONTROL Adobe Analytics - Establecer variables] o haga clic en el icono &#39;+&#39;.
5. Defina el menú desplegable [!UICONTROL Extensión] en Adobe Analytics y el tipo [!UICONTROL de] acción en [!UICONTROL Establecer variables].
6. Busque la sección [!UICONTROL Estado] .

Puede establecer state en cualquier valor de cadena o elemento de datos.

## s.state en el editor de código personalizado AppMeasurement e Launch

La `s.state` variable es una cadena que generalmente contiene el estado o la provincia del visitante. Los nombres de estado completos o los códigos de dos letras son válidos. Tiene un valor máximo de 50 bytes; los valores más largos se truncan. Su valor predeterminado es una cadena vacía.

```js
s.state = "Utah";
```

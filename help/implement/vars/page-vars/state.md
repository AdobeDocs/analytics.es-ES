---
title: state
description: Rellene el “Informe de estado del visitante” en Reports and Analytics.
translation-type: ht
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: ht
source-wordcount: '215'
ht-degree: 100%

---


# state

>[!IMPORTANT]
>
>Esta variable desaparece y no es una dimensión disponible en Analysis Workspace. En su lugar, utilice la dimensión “Estados de EE. UU.”, que AppMeasurement registra automáticamente en función de la ubicación del visitante.

En versiones anteriores de Adobe Analytics, la variable `state` se utilizaba cuando los visitantes rellenaban la información de envío en sitios de venta al por menor. Desde el punto de vista funcional, es idéntico a una prop, pero no está disponible en Analysis Workspace.

## Estado en Adobe Experience Platform Launch

Puede establecer el estado al configurar la extensión de Analytics (variables globales) o en reglas.

1. Inicie sesión en [launch.adobe.com](https://launch.adobe.com) con sus credenciales de Adobe ID.
2. Haga clic en la propiedad deseada.
3. Vaya a la pestaña [!UICONTROL Reglas] y, a continuación, haga clic en la regla que desee (o cree una regla).
4. En [!UICONTROL Acciones], haga clic en una acción existente de [!UICONTROL Adobe Analytics: Establecer variables] o haga clic en el icono “+”.
5. Establezca el menú desplegable [!UICONTROL Extensión] en Adobe Analytics y el [!UICONTROL tipo de acción] en [!UICONTROL Establecer variables].
6. Busque la sección [!UICONTROL Estado].

Puede establecer el estado en cualquier valor de cadena o elemento de datos.

## “s.state” en el editor de código personalizado de AppMeasurement y Launch

La variable `s.state` es una cadena que generalmente contiene el estado o la provincia del visitante. Son válidos tanto los nombres de estado completos como los códigos de dos letras. Tiene un valor máximo de 50 bytes. Los valores más largos se truncan. Aparece como una cadena vacía de manera predeterminada.

```js
s.state = "Utah";
```

---
title: state
description: Rellene el “Informe de estado del visitante” en Reports & Analytics.
feature: Variables
exl-id: a6e3f30b-b5d1-48f8-8961-8e9c6d4d29da
source-git-commit: 25eccb2b9fe3827e62b0ae98d9bebf7a97b239f5
workflow-type: tm+mt
source-wordcount: '223'
ht-degree: 87%

---

# state

>[!IMPORTANT]
>
>Esta variable desaparece y no es una dimensión disponible en Analysis Workspace. En su lugar, utilice la dimensión “Estados de EE. UU.”, que AppMeasurement registra automáticamente en función de la ubicación del visitante.

En versiones anteriores de Adobe Analytics, la variable `state` se utilizaba cuando los visitantes rellenaban la información de envío en sitios de venta al por menor. Desde el punto de vista funcional, es idéntico a una prop, pero no está disponible en Analysis Workspace.

## Estado con la extensión de Adobe Analytics

Puede establecer el estado al configurar la extensión de Analytics (variables globales) o en reglas.

1. Iniciar sesión en [Recopilación de datos de Adobe Experience Platform](https://experience.adobe.com/data-collection) uso de sus credenciales de Adobe ID.
2. Haga clic en la propiedad de etiquetas deseada.
3. Vaya a la pestaña [!UICONTROL Reglas] y, a continuación, haga clic en la regla que desee (o cree una regla).
4. En [!UICONTROL Acciones], haga clic en una acción existente de [!UICONTROL Adobe Analytics: Establecer variables] o haga clic en el icono “+”.
5. Establezca el menú desplegable [!UICONTROL Extensión] en Adobe Analytics y el [!UICONTROL tipo de acción] en [!UICONTROL Establecer variables].
6. Busque la sección [!UICONTROL Estado].

Puede establecer el estado en cualquier valor de cadena o elemento de datos.

## s.state en AppMeasurement y el editor de código personalizado de la extensión de Analytics

La variable `s.state` es una cadena que generalmente contiene el estado o la provincia del visitante. Son válidos tanto los nombres de estado completos como los códigos de dos letras. Tiene un valor máximo de 50 bytes. Los valores más largos se truncan. Aparece como una cadena vacía de manera predeterminada.

```js
s.state = "Utah";
```

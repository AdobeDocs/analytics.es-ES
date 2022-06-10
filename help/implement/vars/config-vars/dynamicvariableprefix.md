---
title: dynamicVariablePrefix
description: Permite personalizar la cadena que identifica las variables dinámicas.
feature: Variables
exl-id: fe208723-0cf2-4899-be7a-8f23c6501c11
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '257'
ht-degree: 71%

---

# dynamicVariablePrefix

Las variables dinámicas son un concepto abreviado que permite copiar valores de una variable a otra. Son útiles para valores de variables largos, ya que ayudan a reducir la longitud de la dirección URL de una solicitud de imagen. Consulte [Variables dinámicas](../page-vars/dynamic-variables.md) para obtener más información sobre este concepto.

De forma predeterminada, las variables dinámicas utilizan el prefijo `D=`. La variable `dynamicVariablePrefix` permite personalizar la cadena que identifica las variables dinámicas. Distingue entre mayúsculas y minúsculas.

## Prefijo de variable dinámica que utiliza el SDK web

El SDK web no utiliza el formato de variable dinámica. En su lugar, puede utilizar la asignación de conjunto de datos para rellenar varios campos de destino con un solo campo de origen. Consulte [Variables dinámicas que utilizan el SDK web](../page-vars/dynamic-variables.md#dynamic-variables-using-the-web-sdk) para obtener más información.

## Prefijo de variable dinámica que utiliza la extensión Adobe Analytics

El prefijo de variable dinámica es un campo situado en el acordeón de [!UICONTROL Variables globales] al configurar la extensión de Adobe Analytics.

1. Iniciar sesión en [Recopilación de datos de Adobe Experience Platform](https://experience.adobe.com/data-collection) uso de sus credenciales de Adobe ID.
1. Haga clic en la propiedad de etiquetas deseada.
1. Vaya a la pestaña [!UICONTROL Extensiones] y, a continuación, haga clic en el botón **[!UICONTROL Configurar]** en Adobe Analytics.
1. Expanda el acordeón de [!UICONTROL Variables globales], que muestra el campo [!UICONTROL Prefijo de variable dinámica].

Este campo contiene `D=` de forma predeterminada. Puede cambiar el valor si desea utilizar un prefijo de variable dinámica diferente. Puede utilizar cualquier valor que desee, siempre que coincida con la codificación de caracteres del sitio.

## s.dynamicVariablePrefix en AppMeasurement y el editor de código personalizado de la extensión de Analytics

La variable `s.dynamicVariablePrefix` es una cadena que puede contener cualquier secuencia de caracteres. Si esta variable no está definida, AppMeasurement utiliza la cadena `D=` de forma predeterminada.

```js
// An example that changes the dynamic variable prefix
s.dynamicVariablePrefix="..";

// This eVar uses the above customized dynamic variable prefix to set eVar to page URL
s.eVar1="..g";
```

---
title: dynamicVariablePrefix
description: Permite personalizar la cadena que identifica las variables dinámicas.
feature: Appmeasurement Implementation
exl-id: fe208723-0cf2-4899-be7a-8f23c6501c11
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '275'
ht-degree: 70%

---

# dynamicVariablePrefix

Las variables dinámicas son un concepto abreviado que permite copiar valores de una variable a otra. Son útiles para valores de variables largos, ya que ayudan a reducir la longitud de la dirección URL de una solicitud de imagen. Consulte [Variables dinámicas](../page-vars/dynamic-variables.md) para obtener más información sobre este concepto.

De forma predeterminada, las variables dinámicas utilizan el prefijo `D=`. La variable `dynamicVariablePrefix` permite personalizar la cadena que identifica las variables dinámicas. Distingue entre mayúsculas y minúsculas.

## Prefijo de variable dinámica mediante Web SDK

Web SDK no utiliza el formato de variable dinámica. En su lugar, puede utilizar la asignación de secuencia de datos para rellenar varios campos de destino con un único campo de Source. Consulte [Variables dinámicas que utilizan Web SDK](../page-vars/dynamic-variables.md#dynamic-variables-using-the-web-sdk) para obtener más información.

Si envía datos directamente a Adobe Analytics sin ajustarse a un esquema, utiliza la variable siguiente:

* [Objeto de datos](/help/implement/aep-edge/data-var-mapping.md): `data.__adobe.dynamicVariablePrefix`

## Prefijo de variable dinámica con la extensión Adobe Analytics

El prefijo de variable dinámica es un campo situado en el acordeón de [!UICONTROL Variables globales] al configurar la extensión de Adobe Analytics.

1. Inicie sesión en la [Recopilación de datos de Adobe Experience Platform](https://experience.adobe.com/data-collection) con sus credenciales de Adobe ID.
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

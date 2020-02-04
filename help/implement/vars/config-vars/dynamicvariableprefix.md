---
title: dynamicVariablePrefix
description: Permite personalizar la cadena que identifica las variables dinámicas.
translation-type: tm+mt
source-git-commit: 03a4c0d5e080219a7fd96dff33ce122669351ac3

---


# dynamicVariablePrefix

Las variables dinámicas son un concepto abreviado que permite copiar valores de una variable a otra. Son útiles para valores de variables largos, ya que ayudan a reducir la longitud de la dirección URL de una solicitud de imagen. Consulte Variables [](../page-vars/dynamic-variables.md) dinámicas para obtener más información sobre este concepto.

De forma predeterminada, las variables dinámicas utilizan el prefijo `D=`. La `dynamicVariablePrefix` variable permite personalizar la cadena que identifica las variables dinámicas. Distingue entre mayúsculas y minúsculas.

## Prefijo de variable dinámica en el lanzamiento de la plataforma Adobe Experience

Prefijo de variable dinámica es un campo situado bajo el acordeón Variables  globales al configurar la extensión de Adobe Analytics.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. Haga clic en la propiedad que desee.
3. Vaya a la ficha [!UICONTROL Extensiones] y, a continuación, haga clic en el botón [!UICONTROL Configurar] en Adobe Analytics.
4. Expanda el acordeón Variables  globales, que muestra el campo Prefijo [!UICONTROL de variable] dinámica.

Este campo contiene `D=` de forma predeterminada. Puede cambiar el valor si desea utilizar un prefijo de variable dinámica diferente. Puede utilizar cualquier valor que desee, siempre que coincida con la codificación de caracteres del sitio.

## s.dynamicVariablePrefix en el editor de código personalizado AppMeasurement e Launch

La `s.dynamicVariablePrefix` variable es una cadena que puede contener cualquier secuencia de caracteres. Si esta variable no está definida, AppMeasurement utiliza la cadena de forma `D=` predeterminada.

```js
// An example that changes the dynamic variable prefix
s.dynamicVariablePrefix="..";

// This eVar uses the above customized dynamic variable prefix to set eVar to page URL
s.eVar1="..g";
```

---
title: dynamicVariablePrefix
description: Permite personalizar la cadena que identifica las variables dinámicas.
exl-id: fe208723-0cf2-4899-be7a-8f23c6501c11
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '207'
ht-degree: 100%

---

# dynamicVariablePrefix

Las variables dinámicas son un concepto abreviado que permite copiar valores de una variable a otra. Son útiles para valores de variables largos, ya que ayudan a reducir la longitud de la dirección URL de una solicitud de imagen. Consulte [Variables dinámicas](../page-vars/dynamic-variables.md) para obtener más información sobre este concepto.

De forma predeterminada, las variables dinámicas utilizan el prefijo `D=`. La variable `dynamicVariablePrefix` permite personalizar la cadena que identifica las variables dinámicas. Distingue entre mayúsculas y minúsculas.

## Prefijo de variable dinámica en Adobe Experience Platform Launch

El prefijo de variable dinámica es un campo situado en el acordeón de [!UICONTROL Variables globales] al configurar la extensión de Adobe Analytics.

1. Inicie sesión en [launch.adobe.com](https://launch.adobe.com) con sus credenciales de Adobe ID.
2. Haga clic en la propiedad deseada.
3. Vaya a la pestaña [!UICONTROL Extensiones] y, a continuación, haga clic en el botón [!UICONTROL Configurar] en Adobe Analytics.
4. Expanda el acordeón de [!UICONTROL Variables globales], que muestra el campo [!UICONTROL Prefijo de variable dinámica].

Este campo contiene `D=` de forma predeterminada. Puede cambiar el valor si desea utilizar un prefijo de variable dinámica diferente. Puede utilizar cualquier valor que desee, siempre que coincida con la codificación de caracteres del sitio.

## s.dynamicVariablePrefix en el editor de código personalizado de AppMeasurement y Launch

La variable `s.dynamicVariablePrefix` es una cadena que puede contener cualquier secuencia de caracteres. Si esta variable no está definida, AppMeasurement utiliza la cadena `D=` de forma predeterminada.

```js
// An example that changes the dynamic variable prefix
s.dynamicVariablePrefix="..";

// This eVar uses the above customized dynamic variable prefix to set eVar to page URL
s.eVar1="..g";
```

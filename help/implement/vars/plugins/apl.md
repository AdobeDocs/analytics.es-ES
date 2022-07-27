---
title: apl (appendToList)
description: Anexe valores a variables que admitan varios valores.
feature: Variables
exl-id: 08ca43f4-f2cc-43fb-a8eb-7c9dd237dfba
source-git-commit: 7c7a7d8add9edb1538df12b440bc0a15f09efe5e
workflow-type: tm+mt
source-wordcount: '586'
ht-degree: 97%

---

# Complemento de Adobe: apl (appendToList)

>[!IMPORTANT]
>
>Adobe Consulting proporciona este complemento por cortesía para ayudarle a sacar el máximo partido a Adobe Analytics. El Servicio de atención al cliente de Adobe no ofrece asistencia técnica con este complemento, incluida la instalación o solución de problemas. Si necesita ayuda con este complemento, póngase en contacto con el administrador de cuentas de su organización. Ellos podrán organizar una reunión con un consultor para ayudarle.

El complemento `apl` le permite agregar de forma segura nuevos valores a variables delimitadas por listas, como [`events`](../page-vars/events/events-overview.md), [`linkTrackVars`](../config-vars/linktrackvars.md), [`list`](../page-vars/list.md) y otras.

* Si el valor que desea agregar no aparece en la variable, el código agrega el valor al final de la cadena.
* Si el valor que desea agregar ya aparece en la variable, este complemento no cambia el valor. Esta función permite que la implementación no incluya valores duplicados.
* Si la variable que desea agregar está vacía, el complemento establece la variable en el nuevo valor.

Adobe recomienda utilizar este complemento si desea añadir valores nuevos a variables existentes que contengan una cadena de valores delimitados. Este complemento no es necesario si prefiere concatenar cadenas para variables que contengan valores delimitados.

<!--## Install the plug-in using the Web SDK or the Adobe Analytics extension

Adobe offers an extension that allows you to use most commonly-used plug-ins.

1. Log in to [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) using your AdobeID credentials.
1. Click the desired tag property.
1. Go to the [!UICONTROL Extensions] tab, then click on the [!UICONTROL Catalog] button
1. Install and publish the [!UICONTROL Common Analytics Plugins] extension
1. If you haven't already, create a rule labeled "Initialize Plug-ins" with the following configuration:
    * Condition: None
    * Event: Core – Library Loaded (Page Top)
1. Add an action to the above rule with the following configuration:
    * Extension: Common Analytics Plugins
    * Action Type: Initialize APL (Append To List)
1. Save and publish the changes to the rule.-->

## Instalación del complemento con el editor de código personalizado de 

Si no desea utilizar la extensión del complemento, puede utilizar el editor de código personalizado.

1. Iniciar sesión en [Recopilación de datos de Adobe Experience Platform](https://experience.adobe.com/data-collection) uso de sus credenciales de Adobe ID.
1. Haga clic en la propiedad deseada.
1. Vaya a la pestaña [!UICONTROL Extensiones] y, a continuación, haga clic en el botón **[!UICONTROL Configurar]** en la extensión de Adobe Analytics.
1. Expanda [!UICONTROL Configurar seguimiento con el código personalizado], que muestra el botón [!UICONTROL Abrir editor].
1. Abra el editor de código personalizado y pegue el código del complemento que se proporciona a continuación en la ventana de edición.
1. Guarde y publique los cambios en la extensión de Analytics.

## Instalación del complemento con AppMeasurement

Copie y pegue el siguiente código en cualquier parte del archivo AppMeasurement después de crear una instancia del objeto de seguimiento de Analytics (con [`s_gi`](../functions/s-gi.md)). Conservar los comentarios y los números de versión del código en la implementación ayuda a Adobe a solucionar cualquier posible problema.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: apl (appendToList) v4.0 */
function apl(lv,va,d1,d2,cc){var b=lv,d=va,e=d1,c=d2,g=cc;if("-v"===b)return{plugin:"apl",version:"4.0"};var h=function(){if("undefined"!==typeof window.s_c_il)for(var k=0,b;k<window.s_c_il.length;k++)if(b=window.s_c_il[k],b._c&&"s_c"===b._c)return b}();"undefined"!==typeof h&&(h.contextData.apl="4.0");window.inList=window.inList||function(b,d,c,e){if("string"!==typeof d)return!1;if("string"===typeof b)b=b.split(c||",");else if("object"!==typeof b)return!1;c=0;for(a=b.length;c<a;c++)if(1==e&&d===b[c]||d.toLowerCase()===b[c].toLowerCase())return!0;return!1};if(!b||"string"===typeof b){if("string"!==typeof d||""===d)return b;e=e||",";c=c||e;1==c&&(c=e,g||(g=1));2==c&&1!=g&&(c=e);d=d.split(",");h=d.length;for(var f=0;f<h;f++)window.inList(b,d[f],e,g)||(b=b?b+c+d[f]:d[f])}return b};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Uso del complemento

La función `apl` utiliza los siguientes argumentos:

* **`lv`** (obligatorio, cadena): La variable que contiene una lista delimitada de elementos para agregar un nuevo valor a
* **`vta`** (obligatorio, cadena): Una lista delimitada por comas de los nuevos valores que se agregan al valor del argumento `lv`.
* **`d1`** (opcional, cadena): El delimitador utilizado para separar los valores individuales ya contenidos en el argumento `lv`.  Si no se configura de forma distinta, el valor predeterminado es una coma (`,`).
* **`d2`** (opcional, cadena): El delimitador de salida. Si no se especifica lo contrario, el valor predeterminado es el mismo que `d1`.
* **`cc`** (opcional, booleano): Indica si se utiliza una comprobación que distingue entre mayúsculas y minúsculas. Con `true`, la comprobación de duplicaciones distingue entre mayúsculas y minúsculas. Si se selecciona `false` o no, la comprobación de duplicaciones no distingue entre mayúsculas y minúsculas. El valor predeterminado es `false`.

La función `apl` devuelve el valor del argumento `lv` más cualquier valor no duplicado del argumento `vta`.

## Ejemplos

```js
// Set the events variable to "event22,event24,event23".
s.events = "event22,event24";
s.events = apl(s.events,"event23");

// The events variable remains unchanged because the apl function does not add duplicate values
s.events = "event22,event23";
s.events = apl(s.events,"event23");

// Set the events variable to "event23" if the events variable is blank
s.events = "";
s.events = apl(s.events,"event23");

// Append a value to eVar5. The value of prop4 remains unchanged.
// The value of eVar5 is "hello|people|today".
s.prop4 = "hello|people";
s.eVar5 = apl(s.prop4, "today", "|");

// Sets prop4 to "hello|people,today". Be mindful of correct delimiters!
s.prop4 = "hello|people";
s.prop4 = apl(s.prop4, "today");

// Sets the events variable to "event22,event23,EVentT23". Be mindful of capitalization when using the cc argument!
s.events = "event22,event23";
s.events = apl(s.events,"EVenT23", ",", ",", true);

// Sets the events variable to "event22,event23,event24,event25".
s.events = "event22,event23";
s.events = apl(s.events, "event23,event24,event25");

// Sets linkTrackVars to "events,eVar1,campaign".
// The last three arguments at the end of this apl call are not necessary because they match the default argument values.
s.linkTrackVars = "events,eVar1";
s.linkTrackVars = apl(s.linkTrackVars, "campaign", ",", ",", false);

// This apl call does not do anything because the code does not assign the returned value to a variable.
s.events = "event22,event24";
apl(s.events, "event23");

// Sets the list2 variable to "apple-APPLE-Apple".
// Since the two delimiter arguments are different, the value passed in is delimited by "|", then joined together by "-".
s.list2 = "apple|APPLE";
s.list2 = apl(s.list2, "Apple", "|", "-", true);

// Sets the list3 variable to "value1,value1,value1" (unchanged).
// Only new values are deduplicated. Existing duplicate values remain.
s.list3 = "value1,value1,value1";
s.list3 = apl(s.list3,"value1");
```

## Historial de versiones

### 4.0 (19 de marzo de 2021)

* Se ha añadido el número de versión como datos de contexto.

### 3.2 (25 de septiembre de 2019)

* Se han corregido problemas de compatibilidad con llamadas `apl` que usaban versiones anteriores del complemento.
* Se han eliminado las advertencias de la consola para reducir el tamaño.
* Se ha añadido `inList 2.1`.

### 3.1 (22 de abril de 2018)

* El argumento `d2` ahora se establece de forma predeterminada en el valor del argumento `d1` cuando, si no se especifica lo contrario.

### 3.0 (16 de abril de 2018)

* Reanálisis y reescritura completos del complemento
* Se ha agregado la comprobación avanzada de errores.
* El argumento `vta` ahora acepta varios valores al mismo tiempo.
* Se ha agregado el argumento `d2` para dar formato al valor devuelto.
* Se ha cambiado el argumento `cc`, ahora es booleano.

### 2.5 (18 de febrero de 2016)

* Ahora se utiliza la función `inList` para el procesamiento de comparación.

### 2.0 (26 de enero de 2016)

* El argumento `d` (delimitador) ahora es opcional (el valor predeterminado es una coma).
* El argumento `u` (indicador de distinción entre mayúsculas y minúsculas) ahora es opcional (de forma predeterminada distingue entre mayúsculas y minúsculas).
* Independientemente del argumento `u` (indicador de distinción entre mayúsculas y minúsculas), el complemento ya no añade un valor a una lista si este ya existe en dicha lista.

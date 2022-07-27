---
title: pt
description: Ejecute una función en una lista de variables.
feature: Variables
exl-id: 2ab24a8e-ced3-43ea-bdb5-7c39810e4102
source-git-commit: 7c7a7d8add9edb1538df12b440bc0a15f09efe5e
workflow-type: tm+mt
source-wordcount: '502'
ht-degree: 97%

---

# Complemento de Adobe: pt

>[!IMPORTANT]
>
>Adobe Consulting proporciona este complemento por cortesía para ayudarle a sacar el máximo partido a Adobe Analytics. El Servicio de atención al cliente de Adobe no ofrece asistencia técnica con este complemento, incluida la instalación o solución de problemas. Si necesita ayuda con este complemento, póngase en contacto con el administrador de cuentas de su organización. Ellos podrán organizar una reunión con un consultor para ayudarle.

El complemento `pt` ejecuta una función o un método en una lista de variables de Analytics. Por ejemplo, puede ejecutar la función [`clearVars`](../functions/clearvars.md) de forma selectiva en varias variables sin llamar manualmente a la función cada vez. Otros complementos dependen de este código para ejecutarse correctamente. Este complemento no es necesario si no necesita ejecutar una función específica en más de una variable de Analytics a la vez o si no utiliza ningún complemento dependiente.

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
    * Action Type: Initialize pt
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
/* Adobe Consulting Plugin: pt v3.0 */
function pt(l,de,cf,fa){var b=l,d=de,f=cf,g=fa;if("-v"===b)return{plugin:"pt",version:"3.0"};a:{if("undefined"!==typeof window.s_c_il){var a=0;for(var c;a<window.s_c_il.length;a++)if(c=window.s_c_il[a],c._c&&"s_c"===c._c){a=c;break a}}a=void 0}if("undefined"!==typeof a&&(a.contextData.pt="3.0",b&&a[f])){b=b.split(d||",");d=b.length;for(var e=0;e<d;e++)if(c=a[f](b[e],g))return c}};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Uso del complemento

La función `pt` utiliza los siguientes argumentos:

* **`l`** (obligatorio, cadena): Una lista de variables con las que se puede ejecutar la función contenida en el argumento `cf`.
* **`de`** (opcional, cadena): El delimitador que separa la lista de variables del argumento `l`. El valor predeterminado es una coma (`,`).
* **`cf`** (obligatorio, cadena): El nombre de la función de llamada de retorno contenida en el objeto AppMeasurement al que se va a llamar en relación con cada una de las variables contenidas en el argumento `l`.
* **`fa`** (opcional, cadena): Si la función del argumento `cf` necesita argumentos adicionales cuando se ejecute, inclúyalos aquí. El valor predeterminado es `undefined`.

La llamada a esta función hace que se devuelva un valor si la función de llamada de retorno (en el argumento `cf`) devuelve un valor.

## Llamadas de ejemplo

### Ejemplo 1

El código siguiente forma parte del complemento getQueryParam.  Ejecuta la función de ayuda getParameterValue con cada uno de los pares clave-valor que se encuentran en la cadena de consulta de la dirección URL (fullQueryString).  Para extraer cada par clave-valor, fullQueryString debe estar delimitado y dividido por un carácter ampersand “&amp;”. El parámetro parameterKey hace referencia al parámetro de cadena de consulta que el complemento intenta extraer específicamente de la cadena de consulta.

```js
returnValue = pt(fullQueryString, "&", "getParameterValue", parameterKey)
```

La línea anterior es un método abreviado para ejecutar código similar a esto:

```js
var returnValue = "",
  parameters = fullQueryString.split("&"),
  parametersLength = parameters.length;
for(var i = 0; i < parametersLength; i++)
{
  returnValue = getParameterValue(parameters[i], parameterKey);
  if(returnValue !== "") break;
}
```

## Historial de versiones

### 3.0 (19 de marzo de 2021)

* Se ha añadido el número de versión como datos de contexto.

### 2.01 (24 de septiembre de 2019)

* Cambios menores en el código para reducir el tamaño total.

### 2.0 (17 de abril de 2018)

* Versión puntual (compilada de nuevo, con un tamaño de código más pequeño).
* Se ha agregado soporte para el código H y con AppMeasurement.

### 1.0 (23 de septiembre de 2013)

* Versión inicial.

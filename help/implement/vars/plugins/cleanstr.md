---
title: cleanStr
description: Eliminación o sustitución de todos los caracteres innecesarios de una cadena.
feature: Appmeasurement Implementation
exl-id: d699dcd4-5e0a-40d3-b345-e5b1a077d393
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '434'
ht-degree: 68%

---

# Complemento de Adobe: cleanStr

{{plug-in}}

El complemento `cleanStr` elimina o reemplaza todos los caracteres innecesarios de una cadena, incluidos los caracteres de etiqueta HTML, espacios en blanco adicionales, pestañas y retornos de línea/carro nuevos. También reemplaza las comillas simples izquierda/derecha con las rectas (`'`). Adobe recomienda utilizar este complemento si desea eliminar caracteres innecesarios de los valores de las variables y la función Limpiar texto de la recopilación de datos de Adobe Experience Platform no satisface sus necesidades de implementación. Este complemento no es necesario si los datos recopilados no contienen caracteres innecesarios o si la función Limpiar texto de la recopilación de datos de Adobe Experience Platform es suficiente.

## Instalación del complemento con la extensión Web SDK o Web SDK

Este complemento aún no es compatible con el uso en Web SDK.

## Instalación del complemento con la extensión de Adobe Analytics

Adobe ofrece una extensión que le permite utilizar los complementos más utilizados con Adobe Analytics.

1. Inicie sesión en la [Recopilación de datos de Adobe Experience Platform](https://experience.adobe.com/data-collection) con sus credenciales de Adobe ID.
1. Haga clic en la propiedad de etiquetas deseada.
1. Vaya a la pestaña [!UICONTROL Extensiones] y, a continuación, haga clic en el botón [!UICONTROL Catálogo].
1. Instalación y publicación de la extensión [!UICONTROL Common Analytics Plugins].
1. Si aún no lo ha hecho, cree una regla con la etiqueta “Inicializar complementos” con la siguiente configuración:
   * Condición: Ninguna
   * Evento: Core – Biblioteca cargada (Principio de página)
1. Añada una acción a la regla anterior con la siguiente configuración:
   * Extensión: Common Analytics Plugins
   * Tipo de acción: Inicializar cleanStr
1. Guarde y publique los cambios en la regla.

## Instalación del complemento con el editor de código personalizado de 

Si no desea utilizar la extensión de complemento Common Analytics Plugins, puede utilizar el editor de código personalizado.

1. Inicie sesión en la [Recopilación de datos de Adobe Experience Platform](https://experience.adobe.com/data-collection) con sus credenciales de Adobe ID.
1. Haga clic en la propiedad deseada.
1. Vaya a la pestaña [!UICONTROL Extensiones] y, a continuación, haga clic en el botón **[!UICONTROL Configurar]** en la extensión de Adobe Analytics.
1. Expanda [!UICONTROL Configurar seguimiento con el código personalizado], que muestra el botón [!UICONTROL Abrir editor].
1. Abra el editor de código personalizado y pegue el código del complemento que se proporciona a continuación en la ventana de edición.
1. Guarde y publique los cambios en la extensión de Analytics.

## Instalación del complemento con AppMeasurement

Copie y pegue el siguiente código en cualquier parte del archivo AppMeasurement después de crear una instancia del objeto de seguimiento de Analytics (con [`s_gi`](../functions/s-gi.md)). Conservar los comentarios y los números de versión del código en la implementación ayuda a Adobe a solucionar cualquier posible problema.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: cleanStr v2.0 (No Prerequisites Required) */
function cleanStr(str){var a=str;if("-v"===a)return{plugin:"cleanStr",version:"2.0"};a:{if("undefined"!==typeof window.s_c_il){var b=0;for(var c;b<window.s_c_il.length;b++)if(c=window.s_c_il[b],c._c&&"s_c"===c._c){b=c;break a}}b=void 0}"undefined"!==typeof b&&(b.contextData.cleanStr="2.0");if("string"===typeof a){a=a.replace(/<\/?[^>]+(>|$)/g,"");a=a.trim();a=a.replace(/[\u2018\u2019\u201A]/g,"'");a=a.replace(/\t+/g,"");for(a=a.replace(/[\n\r]/g," ");-1<a.indexOf("  ");)a=a.replace(/\s\s/g," ");return a}return""}
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Uso del complemento

El complemento `cleanStr` utiliza los siguientes argumentos:

* **`str`** (obligatorio, cadena): El valor que desea para limpiar la codificación HTML, los espacios en blanco adicionales, las pestañas u otros caracteres innecesarios.

La función recupera el valor del argumento `str` con todos los caracteres innecesarios eliminados.

## Ejemplos

```js
// Returns the value "this is a messystring". Note that both tabs and extra spaces are present in the original string.
// Multiple spaces are reduced to one, while tabs are omitted entirely.
s.eVar1 = "  this  is a      messy  string    ";
s.eVar1 = cleanStr(s.eVar1)

// This function call does not do anything because the code does not assign the returned value to a variable.
s.eVar1 = "  this  is a      messy  string    ";
cleanStr(s.eVar1);
```

## Historial de versiones

### 2.0 (19 de marzo de 2021)

* Se ha añadido el número de versión como datos de contexto.

### 1.0 (15 de abril de 2018)

* Versión inicial.

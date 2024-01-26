---
title: inList
description: Compruebe si un valor está contenido en otro valor delimitado por caracteres.
feature: Variables
exl-id: 7eedfd01-2b9a-4fae-a35b-433ca6900f27
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '530'
ht-degree: 87%

---

# Complemento de Adobe: inList

{{plug-in}}

El complemento `inList` le permite comprobar si ya existe un valor en una cadena delimitada o en un objeto de matriz JavaScript. Otros complementos dependen del complemento `inList` para funcionar. Este complemento proporciona una clara ventaja sobre el método `indexOf()` de JavaScript, que no comprueba si coincide con cadenas parciales. Por ejemplo, si utilizó este complemento para buscar `"event2"`, no coincidirá con una cadena que contenga `"event25"`. Este complemento no es necesario si no necesita comprobar los valores de cadenas o matrices delimitadas o si desea utilizar su propia lógica `indexOf()`.

## Instalación del complemento con el SDK web o la extensión del SDK web

Este complemento aún no es compatible con el SDK web.

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
   * Tipo de acción: Inicializar inList
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
/* Adobe Consulting Plugin: inList v3.0 */
function inList(lv,vtc,d,cc){var b=lv,e=vtc,c=d,f=cc;if("-v"===b)return{plugin:"inList",version:"3.0"};a:{if("undefined"!==typeof window.s_c_il){var a=0;for(var d;a<window.s_c_il.length;a++)if(d=window.s_c_il[a],d._c&&"s_c"===d._c){a=d;break a}}a=void 0}"undefined"!==typeof a&&(a.contextData.inList="3.0");if("string"!==typeof e)return!1;if("string"===typeof b)b=b.split(c||",");else if("object"!==typeof b)return!1;c=0;for(a=b.length;c<a;c++)if(1==f&&e===b[c]||e.toLowerCase()===b[c].toLowerCase())return!0;return!1};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Uso del complemento

La función `inList` devuelve un valor booleano según sus entradas. Utiliza los siguientes argumentos:

* **`lv`** (obligatorio, cadena o matriz): Una lista delimitada de valores o un objeto de matriz JavaScript que buscar
* **`vtc`** (obligatorio, cadena): El valor que se va a buscar
* **`d`** (opcional, cadena): El delimitador utilizado para separar valores individuales en el argumento `lv`. Si no se configura de forma distinta, el valor predeterminado es una coma (`,`).
* **`cc`** (opcional, booleano): si se establece en`true` o `1`, se realiza una comprobación que distingue entre mayúsculas y minúsculas. Si se define como `false` o se omite, se realiza una comprobación que no distingue entre mayúsculas y minúsculas. El valor predeterminado es `false`.

La llamada a esta función hace que se devuelva `true` si encuentra una coincidencia, y `false` si no encuentra ninguna coincidencia.

## Ejemplos

```js
// Returns true
s.events = "event22,event24";
if(inList(s.events,"event22")) {
    // Code will execute
}

// Returns false because event2 is not an exact match in the string
s.events = "event22,event24";
if(inList(s.events,"event2")) {
    // Code will not execute
}

// Returns true because of the NOT operator
s.events = "event22,event24";
if(!inList(s.events,"event23")) {
    // Code will execute
}

// Returns false because of the case-sensitive check
s.events = "event22,event23";
if(inList(s.events,"EVenT23","",true)) {
    // Code will not execute
}

// Returns false because of a mismatched delimiter, treating "events,eVar1" as a single value
s.linkTrackVars = "events,eVar1";
if(inList(s.linkTrackVars,"eVar1","|")) {
    // Code will not execute
}
```

## Historial de versiones

### 3.0 (19 de marzo de 2021)

* Se ha añadido el número de versión como datos de contexto.

### v2.1 (26 de septiembre de 2019)

* Se ha agregado la opción para que el argumento `cc` no sea booleano. Por ejemplo, `1` es un valor válido para la comprobación de mayúsculas y minúsculas.

### v2.0 (17 de abril de 2018)

* Versión puntual (compilada de nuevo, con un tamaño de código más pequeño).

### v1.01 (27 de septiembre de 2017)

* Código optimizado para reducir el tamaño

### v1.0 (2009)

* Versión inicial.

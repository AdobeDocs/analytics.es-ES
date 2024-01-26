---
title: getResponsiveLayout
description: Determine qué diseño de un sitio web se está viendo en ese momento.
feature: Variables
exl-id: 5b192d02-fc3c-4b82-acb4-42902202ab5f
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '501'
ht-degree: 86%

---

# Complemento de Adobe: getResponsiveLayout

{{plug-in}}

El complemento `getResponsiveLayout` le permite rastrear qué versión de su sitio web con diseño interactivo está viendo un visitante en ese momento. Adobe recomienda utilizar este complemento si su sitio utiliza un diseño interactivo y si desea rastrear la versión del sitio que vio un visitante. Este complemento no es necesario si su sitio no utiliza un diseño interactivo.

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
   * Tipo de acción: Inicializar getResponsiveLayout
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
/* Adobe Consulting Plugin: getResponsiveLayout v1.1 (Requires AppMeasurement) */
var getResponsiveLayout=function(ppw,plw,tw){var c=ppw,b=plw,e=tw;if("-v"===c)return{plugin:"getResponsiveLayout",version:"1.1"};a:{if("undefined"!==typeof window.s_c_il){var a=0;for(var d;a<window.s_c_il.length;a++)if(d=window.s_c_il[a],d._c&&"s_c"===d._c){a=d;break a}}a=void 0}"undefined"!==typeof a&&(a.contextData.getResponsiveLayout="1.1");if(!(isNaN(c)||isNaN(b)||isNaN(e)||b<c||e<b))return a=window.innerWidth||document.documentElement.clientWidth||document.body.clientWidth,(c<b&&a<=b?a<=c?"phone portrait layout":"phone landscape layout":a<=b?"phone layout":a<=e?"tablet layout":"desktop layout")+":"+a+"x"+(window.innerHeight||document.documentElement.clientHeight||document.body.clientHeight)};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Uso del complemento

La función `getResponsiveLayout` utiliza los argumentos siguientes:

* **`ppw`** (obligatorio, entero): El ancho de píxeles máximo que puede tener una ventana del explorador antes de que la página cambie de un diseño vertical para teléfonos a un diseño horizontal para teléfonos
* **`plw`** (obligatorio, entero): El ancho de píxeles máximo que puede tener una ventana del explorador antes de que la página cambie de un diseño horizontal para teléfonos a un diseño para tableta
* **`tw`** (obligatorio, entero): La anchura máxima de píxeles que puede tener una ventana del explorador antes de que la página cambie de un diseño para tableta a un diseño para escritorio

La llamada a esta función hace que se devuelva una cadena que contiene dos partes delimitadas por dos puntos (`:`). La primera parte de la cadena contiene uno de los siguientes valores, según la anchura y los argumentos mencionados del explorador:

* `"phone portrait layout"`
* `"phone landscape layout"`
* `"phone layout"` (para sitios que no tienen diseños verticales y horizontales)
* `"tablet layout"`
* `"desktop layout"`

La segunda parte de la cadena devuelta son las dimensiones de ancho y alto del explorador. Por ejemplo: `"desktop layout:1243x700"`.

## Ejemplos

```js
// A visitor accesses your site on their laptop. The browser window is maximized.
// * Your site switches from phone portrait mode to phone landscape mode when the browser width is greater than 500 pixels
// * Your site switches from phone landscape mode to tablet mode when the browser width is greater than 700 pixels
// * Your site switches from tablet mode to desktop mode when the browser width is greater than 1000 pixels
// Sets eVar10 to "desktop layout:1920x937".
s.eVar10 = getResponsiveLayout(500, 700, 1000);

// A visitor accesses your site on their phone.
// * Your site has only a phone mode, a tablet mode, and a desktop mode
// * Your site switches from phone mode to tablet mode when the browser width is greater than 800 pixels
// * Your site switches from tablet mode to desktop mode when the browser width is greater than 1,100 pixels
// Sets eVar10 to "phone portrait layout:720x1280"
s.eVar10 = getResponsiveLayout(800, 800, 1100);
```

## Historial de versiones

### 1.1 (19 de marzo de 2021)

* Se ha añadido el número de versión como datos de contexto.

### 1.0 (2 de mayo de 2018)

* Versión inicial.

---
title: getResponsiveLayout
description: Determine qué diseño de un sitio web se está viendo en ese momento.
exl-id: 5b192d02-fc3c-4b82-acb4-42902202ab5f
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '674'
ht-degree: 100%

---

# Complemento de Adobe: getResponsiveLayout

>[!IMPORTANT]
>
>Adobe Consulting proporciona este complemento por cortesía para ayudarle a sacar el máximo partido a Adobe Analytics. El Servicio de atención al cliente de Adobe no ofrece asistencia técnica con este complemento, incluida la instalación o solución de problemas. Si necesita ayuda con este complemento, póngase en contacto con el administrador de cuentas de su organización. Ellos podrán organizar una reunión con un consultor para ayudarle.

El complemento `getResponsiveLayout` le permite rastrear qué versión de su sitio web con diseño interactivo está viendo un visitante en ese momento. Adobe recomienda utilizar este complemento si su sitio utiliza un diseño interactivo y si desea rastrear la versión del sitio que vio un visitante. Este complemento no es necesario si su sitio no utiliza un diseño interactivo.

## Instalación del complemento con la extensión de Adobe Experience Platform Launch

Adobe ofrece una extensión que le permite disfrutar de los complementos más utilizados.

1. Inicie sesión en [launch.adobe.com](https://launch.adobe.com) con sus credenciales de Adobe ID.
1. Haga clic en la propiedad deseada.
1. Vaya a la pestaña [!UICONTROL Extensiones] y, a continuación, haga clic en el botón [!UICONTROL Catálogo].
1. Instalación y publicación de la extensión [!UICONTROL Common Analytics Plugins].
1. Si aún no lo ha hecho, cree una regla con la etiqueta “Inicializar complementos” con la siguiente configuración:
   * Condición: Ninguna
   * Evento: Core – Biblioteca cargada (Principio de página)
1. Añada una acción a la regla anterior con la siguiente configuración:
   * Extensión: Common Analytics Plugins
   * Tipo de acción: Inicializar getResponsiveLayout
1. Guarde y publique los cambios en la regla.

## Instalación del complemento con el editor de código personalizado de Launch

Si no desea utilizar la extensión del complemento, puede utilizar el editor de código personalizado.

1. Inicie sesión en [launch.adobe.com](https://launch.adobe.com) con sus credenciales de Adobe ID.
1. Haga clic en la propiedad deseada.
1. Vaya a la pestaña [!UICONTROL Extensiones] y, a continuación, haga clic en el botón [!UICONTROL Configurar] en la extensión de Adobe Analytics.
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

El método `getResponsiveLayout` utiliza los siguientes argumentos:

* **`ppw`** (obligatorio, entero): El ancho de píxeles máximo que puede tener una ventana del explorador antes de que la página cambie de un diseño vertical para teléfonos a un diseño horizontal para teléfonos
* **`plw`** (obligatorio, entero): El ancho de píxeles máximo que puede tener una ventana del explorador antes de que la página cambie de un diseño horizontal para teléfonos a un diseño para tableta
* **`tw`** (obligatorio, booleano): El ancho de píxeles máximo que puede tener una ventana del explorador antes de que la página cambie de un diseño para tableta a un diseño para escritorio

Llamar a este método devuelve una cadena de dos partes. La primera parte utiliza los siguientes valores, según el ancho del explorador y los argumentos anteriores:

* `"phone portrait layout"`
* `"phone landscape layout"`
* `"phone layout"` (para sitios que no tienen diseños verticales y horizontales)
* `"tablet layout"`
* `"desktop layout"`

La segunda parte de la cadena devuelta son las dimensiones de ancho y alto del explorador. Por ejemplo: `"desktop layout:1243x700"`.

## Llamadas de ejemplo

### Ejemplo 1

Si...

* Su sitio cambia del modo vertical para teléfono al modo horizontal para teléfono cuando el ancho del explorador es mayor de 500 píxeles
* Su sitio cambia del modo horizontal para teléfono al modo tableta cuando el ancho del explorador es mayor de 700 píxeles
* Su sitio cambia del modo tableta al modo escritorio cuando el ancho del explorador es mayor de 1000 píxeles

... el siguiente código establecerá eVar10 en el diseño interactivo actual que experimente el visitante, así como las dimensiones y el ancho del explorador

```js
s.eVar10 = getResponsiveLayout(500, 700, 1000);
```

### Ejemplo 2

Si...

* Su sitio solo tiene un modo de teléfono, un modo de tableta y un modo de escritorio
* Su sitio cambia del modo de teléfono al modo de tableta cuando el ancho del explorador es mayor de 500 píxeles
* Su sitio cambia del modo tableta al modo escritorio cuando el ancho del explorador es mayor de 1.100 píxeles

... el siguiente código establecerá eVar10 en el diseño interactivo actual que experimente el visitante, así como las dimensiones y el ancho del explorador

```js
s.eVar10 = getResponsiveLayout(500, 500, 1100);
```

## Historial de versiones

### 1.1 (19 de marzo de 2021)

* Se ha añadido el número de versión como datos de contexto.

### 1.0 (2 de mayo de 2018)

* Versión inicial.

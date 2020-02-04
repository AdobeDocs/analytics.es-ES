---
title: ' getResponsiveLayout'
description: Determinar qué diseño de un sitio web se está viendo en ese momento.
translation-type: tm+mt
source-git-commit: 180ad544541f25d02b3a257559bc045abed7387b

---


# Complemento de Adobe: getResponsiveLayout

> [!IMPORTANT] Este complemento lo proporciona Adobe Consulting por cortesía para ayudarle a obtener más valor de Adobe Analytics. El Servicio de atención al cliente de Adobe no ofrece asistencia técnica con este complemento, incluida la instalación o solución de problemas. Si necesita ayuda con este complemento, póngase en contacto con el administrador de cuentas de su organización. Pueden organizar una reunión con un consultor para obtener ayuda.

El `getResponsiveLayout` complemento le permite rastrear qué versión del sitio web adaptable basado en diseño está viendo un visitante en este momento. Adobe recomienda utilizar este complemento si su sitio utiliza un diseño interactivo y desea rastrear la versión del sitio que vio un visitante. Este complemento no es necesario si su sitio no utiliza un diseño interactivo.

## Instalación del complemento con la extensión Adobe Experience Platform Launch

Adobe ofrece una extensión que le permite utilizar los complementos más utilizados.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
1. Haga clic en la propiedad que desee.
1. Vaya a la ficha [!UICONTROL Extensiones] y, a continuación, haga clic en el botón [!UICONTROL Catálogo]
1. Instalación y publicación de la extensión [!UICONTROL Common Analytics Plugins]
1. Si aún no lo ha hecho, cree una regla con la etiqueta &quot;Inicializar complementos&quot; con la siguiente configuración:
   * Condición: Ninguno
   * Evento: Core - Biblioteca cargada (Principio de página)
1. Agregue una acción a la regla anterior con la siguiente configuración:
   * Extensión: Complementos comunes de Analytics
   * Tipo de acción: Inicializar getResponsiveLayout
1. Guarde y publique los cambios en la regla.

## Instalación del complemento con el editor de código personalizado Iniciar

Si no desea utilizar la extensión del complemento, puede utilizar el editor de código personalizado.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
1. Haga clic en la propiedad deseada.
1. Vaya a la ficha [!UICONTROL Extensiones] y, a continuación, haga clic en el botón [!UICONTROL Configurar] en la extensión de Adobe Analytics.
1. Expanda el seguimiento [!UICONTROL Configurar mediante el acordeón de código] personalizado, que muestra el botón [!UICONTROL Abrir editor] .
1. Abra el editor de código personalizado y pegue el código del complemento que se proporciona a continuación en la ventana de edición.
1. Guarde y publique los cambios en la extensión de Analytics.

## Instalación del complemento mediante AppMeasurement

Copie y pegue el siguiente código en cualquier parte del archivo AppMeasurement después de crear una instancia del objeto de seguimiento de Analytics (mediante `s_gi`). La conservación de los comentarios y los números de versión del código en la implementación ayuda a Adobe a solucionar cualquier problema potencial.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getResponsiveLayout v1.0 */
var getResponsiveLayout=function(ppw,plw,tw){if(!(isNaN(ppw)||isNaN(plw)||isNaN(tw)||plw<ppw||tw<plw)){var b=window.innerWidth|| document.documentElement.clientWidth||document.body.clientWidth;return(ppw<plw&&b<=plw?b<=ppw?"phone portrait layout":"phone landscape layout":b<=plw?"phone layout":b<=tw?"tablet layout":"desktop layout")+":"+b+"x"+(window.innerHeight|| document.documentElement.clientHeight||document.body.clientHeight)}};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Utilizar el complemento

El `getResponsiveLayout` método utiliza los siguientes argumentos:

* **`ppw`**(requerido, entero): El ancho máximo de píxeles que puede tener una ventana del explorador antes de que la página cambie de un diseño vertical para teléfonos a un diseño basado en horizontes para teléfonos
* **`plw`**(requerido, entero): El ancho máximo de píxeles que puede tener una ventana del explorador antes de que la página cambie de un diseño horizontal para teléfonos a un diseño basado en tabletas
* **`tw`**(requerido, booleano): El ancho máximo de píxeles que puede tener una ventana del explorador antes de que la página cambie de una presentación para tablet a una presentación basada en escritorio

Al llamar a este método se devuelve una cadena que contiene dos partes. La primera parte utiliza los siguientes valores, según el ancho del explorador y los argumentos anteriores:

* `"phone portrait layout"`
* `"phone landscape layout"`
* `"phone layout"` (para sitios que no tienen maquetaciones verticales y horizontales)
* `"tablet layout"`
* `"desktop layout"`

La segunda parte de la cadena devuelta son las dimensiones de anchura y altura del explorador. Por ejemplo: `"desktop layout:1243x700"`.

## Llamadas de ejemplo

### Ejemplo n.º 1

Si...

* El sitio cambia del modo vertical del teléfono al modo horizontal del teléfono cuando el ancho del explorador es mayor que 500 píxeles
* El sitio cambia del modo horizontal del teléfono al modo tablet cuando el ancho del explorador es mayor que 700 píxeles
* El sitio cambia del modo tablet al modo escritorio cuando la anchura del explorador es mayor que 1000 píxeles

...el siguiente código establecerá eVar10 igual al diseño interactivo actual como experiencia del visitante, así como el ancho y las dimensiones del explorador

```js
s.eVar10 = getResponsiveLayout(500, 700, 1000);
```

### Ejemplo n.º 2

Si...

* El sitio solo tiene un modo de teléfono, un modo de tablet y un modo de escritorio
* El sitio cambia del modo de teléfono al modo de tablet cuando el ancho del explorador es mayor que 500 píxeles
* El sitio cambia del modo tablet al modo escritorio cuando la anchura del explorador es mayor que 1.100 píxeles

...el siguiente código establecerá eVar10 igual al diseño interactivo actual como experiencia del visitante, así como el ancho y las dimensiones del explorador

```js
s.eVar10 = getResponsiveLayout(500, 500, 1100);
```

## Historial de versiones

### 1.0 (2 de mayo de 2018)

* Versión inicial.

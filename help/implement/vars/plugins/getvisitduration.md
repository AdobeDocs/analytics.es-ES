---
title: getVisitDuration
description: Rastree cuánto tiempo ha pasado un visitante en el sitio hasta el momento.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '578'
ht-degree: 100%

---


# Complemento de Adobe: getVisitDuration

>[!IMPORTANT]
>
>Adobe Consulting proporciona este complemento por cortesía para ayudarle a sacar el máximo partido a Adobe Analytics. El Servicio de atención al cliente de Adobe no ofrece asistencia técnica con este complemento, incluida la instalación o solución de problemas. Si necesita ayuda con este complemento, póngase en contacto con el administrador de cuentas de su organización. Ellos podrán organizar una reunión con un consultor para ayudarle.

El complemento `getVisitDuration` rastrea el tiempo en minutos que el visitante ha pasado en el sitio hasta ese momento. Adobe recomienda utilizar este complemento si desea rastrear el tiempo acumulado en el sitio hasta ese momento o para rastrear el tiempo que tarda en realizar una actividad. Este complemento no rastrea el tiempo entre eventos; si desea esta funcionalidad, utilice el complemento [`getTimeBetweenEvents`](gettimebetweenevents.md).

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
   * Tipo de acción: Inicializar getVisitDuration
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
/* Adobe Consulting Plugin: getVisitDuration v2.0 */
s.getVisitDuration=function(){var d=new Date,c=d.getTime(),b=this.c_r("s_dur");if(isNaN(b)||18E5<c-b)b=c;var a=c-b;d.setTime(c+18E5); this.c_w("s_dur",b+"",d);if(0===a)return"first hit of visit";a=Math.floor(a/6E4);return 0===a?"less than a minute":1===a?"1 minute": a+" minutes"};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Uso del complemento

El método `getVisitDuration` no utiliza ningún argumento. Devuelve uno de los siguientes valores:

* `"first hit of visit"`
* `"less than a minute"`
* `"1 minute"`
* `"[x] minutes"` (donde `[x]` es el número de minutos transcurridos desde que el visitante accedió al sitio)

Este complemento crea una cookie de origen llamada `"s_dur"`, que es el número de milisegundos transcurridos desde que el visitante accedió al sitio. La cookie caduca tras 30 minutos de inactividad.

## Llamadas de ejemplo

### Ejemplo 1

El siguiente código...

```js
s.eVar10 = s.getVisitDuration();
```

...siempre establecerá eVar10 en el número de minutos transcurridos desde que el visitante accedió al sitio.

### Ejemplo 2

El siguiente código...

```js
if(s.inList(s.events, "purchase")) s.eVar10 = s.getVisitDuration();
```

...utiliza el complemento inList para comprobar si la variable de eventos contiene el evento de compra.  Si es así, eVar10 se establece en el número de minutos entre el inicio de la visita y la hora de compra.

### Ejemplo 3

El siguiente código...

```js
s.prop10 = s.getVisitDuration();
```

...siempre establecerá prop10 en el número de minutos transcurridos desde que el visitante accedió al sitio.  Será útil si prop10 tiene las rutas habilitadas.  Si agrega la métrica “salidas” al informe prop10, se mostrará un informe “de diagrama de dispersión” granular de cuántos minutos duró una visita antes de que abandonara el sitio.

## Historial de versiones

### 2.0 (2 de mayo de 2018)

* Versión puntual (reanálisis/reescritura completa del complemento).

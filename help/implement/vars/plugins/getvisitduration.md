---
title: ' getVisitDuration'
description: Rastrear cuánto tiempo ha estado un visitante en el sitio hasta ahora.
translation-type: tm+mt
source-git-commit: 26f06adbef1608a6e01df3ab1d3ad4ba78abc28f

---


# Complemento de Adobe: getVisitDuration

> [!IMPORTANT] Este complemento lo proporciona Adobe Consulting por cortesía para ayudarle a obtener más valor con el uso de Adobe Analytics. El Servicio de atención al cliente de Adobe no ofrece asistencia técnica con este complemento, incluida la instalación o solución de problemas. Si necesita ayuda con este complemento, póngase en contacto con el administrador de cuentas de su organización. Pueden organizar una reunión con un consultor para obtener ayuda.

El `getVisitDuration` complemento rastrea la cantidad de tiempo en minutos que el visitante ha estado en el sitio hasta ese momento. Adobe recomienda utilizar este complemento si desea rastrear el tiempo acumulado en el sitio hasta ese momento o para rastrear el tiempo que tarda en realizar una actividad. Este complemento no rastrea la cantidad de tiempo entre eventos; si desea utilizar esta funcionalidad, utilice el `getTimeBetweenEvents` complemento.

## Instalación del complemento con la extensión Adobe Experience Platform Launch

Adobe ofrece una extensión que le permite utilizar los complementos más utilizados.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
1. Haga clic en la propiedad que desee.
1. Vaya a la ficha [!UICONTROL Extensiones] y, a continuación, haga clic en el botón [!UICONTROL Catálogo]
1. Instalación y publicación de la extensión [!UICONTROL Common Analytics Plugins]
1. Para cualquier regla de inicio en la que desee utilizar el complemento, agregue una acción con la siguiente configuración:
   * Extensión: Complementos comunes de Analytics
   * Tipo de acción: Inicializar addProductEvar
1. Guardar y publicar los cambios en la regla

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
/* Adobe Consulting Plugin: getVisitDuration v2.0 */
s.getVisitDuration=function(){var d=new Date,c=d.getTime(),b=this.c_r("s_dur");if(isNaN(b)||18E5<c-b)b=c;var a=c-b;d.setTime(c+18E5); this.c_w("s_dur",b+"",d);if(0===a)return"first hit of visit";a=Math.floor(a/6E4);return 0===a?"less than a minute":1===a?"1 minute": a+" minutes"};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Utilizar el complemento

El `getVisitDuration` método no utiliza ningún argumento. Devuelve uno de los siguientes valores:

* `"first hit of visit"`
* `"less than a minute"`
* `"1 minute"`
* `"[x] minutes"` (donde `[x]` es el número de minutos transcurridos desde que el visitante aterrizó en el sitio)

Este complemento crea una cookie de origen llamada `"s_dur"`, que es el número de milisegundos transcurridos desde que el visitante aterrizó en el sitio. La cookie caduca tras 30 minutos de inactividad.

## Llamadas de ejemplo

### Ejemplo n.º 1

El siguiente código...

```js
s.eVar10 = s.getVisitDuration();
```

...siempre configurará eVar10 igual al número de minutos transcurridos desde que el visitante aterrizó en el sitio

### Ejemplo n.º 2

El siguiente código...

```js
if(s.inList(s.events, "purchase")) s.eVar10 = s.getVisitDuration();
```

...utiliza el complemento inList para comprobar si la variable events contiene el evento purchase.  Si es así, eVar10 se configurará igual al número de minutos entre el inicio de la visita y la hora de compra del visitante.

### Ejemplo n.º 3

El siguiente código...

```js
s.prop10 = s.getVisitDuration();
```

...siempre configurará prop10 igual al número de minutos transcurridos desde que el visitante aterrizó en el sitio.  Esto será útil si prop10 tiene las rutas habilitadas.  Si agrega la métrica &quot;salidas&quot; al informe prop10, se mostrará un informe &quot;de diagrama de dispersión&quot; granular de cuánto tiempo tardó una visita en minutos antes de que un visitante abandonara el sitio.

## Historial de versiones

### 2.0 (2 de mayo de 2018)

* Versión puntual (reanálisis/reescritura completa del complemento).

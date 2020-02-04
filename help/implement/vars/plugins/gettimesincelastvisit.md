---
title: getTimeSinceLastVisit
description: Mida la cantidad de tiempo transcurrido entre dos visitas.
translation-type: tm+mt
source-git-commit: 26f06adbef1608a6e01df3ab1d3ad4ba78abc28f

---


# Complemento de Adobe:getTimeSinceLastVisit

> [!IMPORTANT] Este complemento lo proporciona Adobe Consulting por cortesía para ayudarle a obtener más valor con el uso de Adobe Analytics. El Servicio de atención al cliente de Adobe no ofrece asistencia técnica con este complemento, incluida la instalación o solución de problemas. Si necesita ayuda con este complemento, póngase en contacto con el administrador de cuentas de su organización. Pueden organizar una reunión con un consultor para obtener ayuda.

El `getTimeSinceLastVisit` complemento le permite rastrear cuánto tiempo ha tardado un visitante en regresar a su sitio después de su última visita.

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
/* Adobe Consulting Plugin: getTimeSinceLastVisit v1.0 (Requires formatTime and inList plug-ins) */
s.getTimeSinceLastVisit=function(){var s=this,a=new Date,b=a.getTime(),c=s.c_r("s_tslv")||0,d=Math.round((b-c)/1E3);a.setTime(b+63072E6);s.c_w("s_tslv",b,a);return c?1800<d&&s.formatTime?s.formatTime(d):"":"New Visitor"};

/* Adobe Consulting Plugin: formatTime v1.1 (Requires inList plug-in) */
s.formatTime=function(ns,tf,bml){var s=this;if(!("undefined"===typeof ns||isNaN(ns)||0>Number(ns))){if("string"===typeof tf&&"d"===tf||("string"!==typeof tf||!s.inList("h,m,s",tf))&&86400<=ns){tf=86400;var d="days";bml=isNaN(bml)?1:tf/(bml*tf)} else"string"===typeof tf&&"h"===tf||("string"!==typeof tf||!s.inList("m,s",tf))&&3600<=ns?(tf=3600,d="hours", bml=isNaN(bml)?4: tf/(bml*tf)):"string"===typeof tf&&"m"===tf||("string"!==typeof tf||!s.inList("s",tf))&&60<=ns?(tf=60,d="minutes",bml=isNaN(bml)?2: tf/(bml*tf)):(tf=1,d="seconds",bml=isNaN(bml)?.2:tf/bml);ns=Math.round(ns*bml/tf)/bml+" "+d;0===ns.indexOf("1 ")&&(ns=ns.substring(0, ns.length-1));return ns}};

/* Adobe Consulting Plugin: inList v2.1 */
s.inList=function(lv,vtc,d,cc){if("string"!==typeof vtc)return!1;if("string"===typeof lv)lv=lv.split(d||",");else if("object"!== typeof lv)return!1;d=0;for(var e=lv.length;d<e;d++)if(1==cc&&vtc===lv[d]||vtc.toLowerCase()===lv[d].toLowerCase())return!0;return!1};
 /******************************************** END CODE TO DEPLOY ********************************************/
```

## Utilizar el complemento

El `getTimeSinceLastVisit` método no utiliza ningún argumento. Devuelve la cantidad de tiempo transcurrido desde la última vez que el visitante ingresó al sitio, agrupado en el siguiente formato:

* El tiempo transcurrido entre 30 minutos y una hora desde la última visita se establece en el valor de referencia de medio minuto más cercano. Por ejemplo, `"30.5 minutes"`, `"53 minutes"`
* El tiempo entre una hora y un día se redondea al valor de referencia de cuarto de hora más cercano. Por ejemplo, `"2.25 hours"`, `"7.5 hours"`
* El tiempo mayor que un día se redondea al valor de referencia del día más próximo. Por ejemplo, `"1 day"`, `"3 days"`, `"9 days"`, `"372 days"`
* Si un visitante no ha visitado antes o el tiempo transcurrido es mayor que dos años, el valor se establece en `"New Visitor"`.

> [!NOTE] Este complemento solo devuelve un valor en la primera visita individual de una visita.

Este complemento crea una cookie de origen denominada `"s_tslv"` establecida en una marca de tiempo Unix de la hora actual. La cookie caduca tras dos años de inactividad.

## Llamadas de ejemplo

### Ejemplo n.º 1

Si un visitante nuevo llega al sitio y el siguiente código se ejecuta en la primera página de la visita...

```javascript
s.prop1 = s.getTimeSinceLastVisit();
s.linkTrackVars = s.apl(s.linkTrackVars, "prop1") //ensures that prop1 will be included on the first hit of the visit
```

...el valor de s.prop1 se establecerá igual a &quot;Nuevo visitante&quot;.

Si el mismo código se ejecuta en el mismo dominio después de 35 minutos de inactividad, el valor de s.prop1 se establecerá en &quot;35 minutos&quot;.

Si el mismo código se ejecuta en el mismo dominio después de 4 días de inactividad adicional, el valor de s.prop1 se establecerá en &quot;4 días&quot;.

## Historial de versiones

### 1.0 (16 de abril de 2018)

* Versión puntual (código recompilado y tamaño más pequeño).
* Código derivado del `getDaysSinceLastVisit` complemento (ahora obsoleto y con el nombre cambiado).
* Ahora utiliza `formatTime` y `inList` complementos para el valor devuelto.

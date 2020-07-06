---
title: getTimeSinceLastVisit
description: Mida el tiempo transcurrido entre dos visitas.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '575'
ht-degree: 100%

---


# Complemento de Adobe: getTimeSinceLastVisit

>[!IMPORTANT]
>
>Adobe Consulting proporciona este complemento por cortesía para ayudarle a sacar el máximo partido a Adobe Analytics. El Servicio de atención al cliente de Adobe no ofrece asistencia técnica con este complemento, incluida la instalación o solución de problemas. Si necesita ayuda con este complemento, póngase en contacto con el administrador de cuentas de su organización. Ellos podrán organizar una reunión con un consultor para ayudarle.

El complemento `getTimeSinceLastVisit` le permite rastrear cuánto tiempo ha tardado un visitante en regresar a su sitio después de su última visita.

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
   * Tipo de acción: Inicializar getTimeSinceLastVisit
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
/* Adobe Consulting Plugin: getTimeSinceLastVisit v1.0 (Requires formatTime and inList plug-ins) */
s.getTimeSinceLastVisit=function(){var s=this,a=new Date,b=a.getTime(),c=s.c_r("s_tslv")||0,d=Math.round((b-c)/1E3);a.setTime(b+63072E6);s.c_w("s_tslv",b,a);return c?1800<d&&s.formatTime?s.formatTime(d):"":"New Visitor"};

/* Adobe Consulting Plugin: formatTime v1.1 (Requires inList plug-in) */
s.formatTime=function(ns,tf,bml){var s=this;if(!("undefined"===typeof ns||isNaN(ns)||0>Number(ns))){if("string"===typeof tf&&"d"===tf||("string"!==typeof tf||!s.inList("h,m,s",tf))&&86400<=ns){tf=86400;var d="days";bml=isNaN(bml)?1:tf/(bml*tf)} else"string"===typeof tf&&"h"===tf||("string"!==typeof tf||!s.inList("m,s",tf))&&3600<=ns?(tf=3600,d="hours", bml=isNaN(bml)?4: tf/(bml*tf)):"string"===typeof tf&&"m"===tf||("string"!==typeof tf||!s.inList("s",tf))&&60<=ns?(tf=60,d="minutes",bml=isNaN(bml)?2: tf/(bml*tf)):(tf=1,d="seconds",bml=isNaN(bml)?.2:tf/bml);ns=Math.round(ns*bml/tf)/bml+" "+d;0===ns.indexOf("1 ")&&(ns=ns.substring(0, ns.length-1));return ns}};

/* Adobe Consulting Plugin: inList v2.1 */
s.inList=function(lv,vtc,d,cc){if("string"!==typeof vtc)return!1;if("string"===typeof lv)lv=lv.split(d||",");else if("object"!== typeof lv)return!1;d=0;for(var e=lv.length;d<e;d++)if(1==cc&&vtc===lv[d]||vtc.toLowerCase()===lv[d].toLowerCase())return!0;return!1};
 /******************************************** END CODE TO DEPLOY ********************************************/
```

## Uso del complemento

El método `getTimeSinceLastVisit` no utiliza ningún argumento. Devuelve el tiempo transcurrido desde la última vez que el visitante accedió al sitio, agrupado en el siguiente formato:

* Un valor entre 30 minutos y una hora desde la última visita se establece en la referencia de medio minuto más cercana. Por ejemplo, `"30.5 minutes"`, `"53 minutes"`.
* Un valor entre una hora y un día se redondea a la referencia de cuarto de hora más cercana. Por ejemplo, `"2.25 hours"`, `"7.5 hours"`.
* Un valor mayor que un día se redondea a la referencia del día más próximo. Por ejemplo, `"1 day"`, `"3 days"`, `"9 days"`, `"372 days"`.
* Si es la primera visita de un visitante o si el tiempo transcurrido supera los dos años, el valor se establece en `"New Visitor"`.

>[!NOTE]
>
>Este complemento solo devuelve un valor en la primera visita.

Este complemento crea una cookie de origen denominada `"s_tslv"` establecida en una marca de tiempo Unix de la hora actual. La cookie caduca tras dos años de inactividad.

## Llamadas de ejemplo

### Ejemplo 1

Si un visitante nuevo llega al sitio y el siguiente código se ejecuta en la primera página de la visita...

```javascript
s.prop1 = s.getTimeSinceLastVisit();
s.linkTrackVars = s.apl(s.linkTrackVars, "prop1") //ensures that prop1 will be included on the first hit of the visit
```

...el valor de s.prop1 se establecerá en “Nuevo visitante”.

Si el mismo código se ejecuta en el mismo dominio después de 35 minutos de inactividad, el valor de s.prop1 se establecerá en “35 minutos”.

Si el mismo código se ejecuta en el mismo dominio después de 4 días de inactividad adicional, el valor de s.prop1 se establecerá en “4 días”.

## Historial de versiones

### 1.0 (16 de abril de 2018)

* Versión puntual (código compilado de nuevo y tamaño más pequeño).
* Código derivado del complemento `getDaysSinceLastVisit` (ahora obsoleto y con un nuevo nombre).
* Ahora utiliza los complementos `formatTime` y `inList` para el valor devuelto.

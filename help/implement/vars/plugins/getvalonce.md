---
title: getValOnce
description: Impedir que una variable de Analytics se establezca en el mismo valor dos veces seguidas.
translation-type: tm+mt
source-git-commit: 180ad544541f25d02b3a257559bc045abed7387b

---


# Complemento de Adobe: getValOnce

> [!IMPORTANT] Este complemento lo proporciona Adobe Consulting por cortesía para ayudarle a obtener más valor de Adobe Analytics. El Servicio de atención al cliente de Adobe no ofrece asistencia técnica con este complemento, incluida la instalación o solución de problemas. Si necesita ayuda con este complemento, póngase en contacto con el administrador de cuentas de su organización. Pueden organizar una reunión con un consultor para obtener ayuda.

El complemento evita que se establezca una variable igual al mismo valor más de una vez. `getValOnce` Adobe recomienda utilizar este complemento cuando desee anular la duplicación de incidencias en las que un visitante actualiza una página o visita una página determinada varias veces. Este complemento no es necesario si no le preocupa la métrica &quot;Ocurrencias&quot; en Analysis Workspace.

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
   * Tipo de acción: Inicializar getValOnce
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
/* Adobe Consulting Plugin: getValOnce v2.0 */
s.getValOnce=function(vtc,cn,et,ep){if(vtc&&(cn=cn||"s_gvo",et=et||0,ep="m"===ep?6E4:864E5,vtc!==this.c_r(cn))){var e=new Date;e.setTime(e.getTime()+et*ep);this.c_w(cn,vtc,0===et?0:ep);return vtc}return""};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Utilizar el complemento

El `getValOnce` método utiliza los siguientes argumentos:

* **`vtc`**(requerido, cadena): La variable que se va a comprobar y ver si se ha definido anteriormente en un valor idéntico
* **`cn`**(opcional, cadena): Nombre de la cookie que contiene el valor que se va a comprobar. El valor predeterminado es`"s_gvo"`
* **`et`**(opcional, entero): Caducidad de la cookie en días (o minutos, según el`ep`argumento). Predeterminado en`0`, que caduca al final de la sesión del explorador
* **`ep`**(opcional, cadena): Sólo configure este argumento si también se establece el`et`argumento. Establezca este argumento en`"m"`si desea que el`et`argumento caduque en minutos en lugar de días. El valor predeterminado es`"d"`, que establece el`et`argumento en días.

Si el argumento `vtc` y el valor de la cookie coinciden, este método devuelve una cadena vacía. Si el argumento `vtc` y el valor de la cookie no coinciden, el método devuelve el `vtc` argumento como una cadena.

## Llamadas de ejemplo

### Ejemplo #1

Utilice esta llamada para evitar que el mismo valor se pase a s.campaign más de una vez seguidas durante los próximos 30 días:

```js
s.campaign=s.getValOnce(s.campaign,"s_campaign",30);
```

En la llamada anterior, el complemento comparará primero el valor ya contenido en la cookie s_campaign con el valor proveniente de la variable s.campaign actual.   Si no se realiza una coincidencia, el complemento establecerá la cookie s_campaign igual al nuevo valor que se obtiene de s.campaign y, a continuación, devolverá el nuevo valor.   Esta comparación se realizará durante los próximos treinta días

### Ejemplo #2

Utilice esta llamada para evitar que se establezca el mismo valor durante toda la sesión:

```js
s.eVar2=s.getValOnce(s.eVar2,"s_ev2",0,"m");
```

Este código evita que el mismo valor se pase a s.eVar2 más de una vez seguidas durante toda la sesión del usuario.  También ignora el valor &quot;m&quot; del parámetro (al final de la llamada), ya que la hora de caducidad es igual a 0.   El código también almacena el valor de comparación en la cookie s_ev2.

## Historial de versiones

### 2.0

* Versión puntual (recompilada, tamaño de código más pequeño).

### 1.1

* Se ha agregado la opción de elegir minutos o días para la caducidad mediante el `t` parámetro .
* Se corrigió el ámbito de la `k` variable utilizada para restringirla únicamente al complemento. Este cambio evita posibles interferencias con otro código de la página.

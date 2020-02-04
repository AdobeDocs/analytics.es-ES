---
title: ' p_fo (Página sólo la primera)'
description: Asegúrese de que determinadas rutinas se activen solo una vez por página.
translation-type: tm+mt
source-git-commit: 180ad544541f25d02b3a257559bc045abed7387b

---


# Complemento de Adobe: p_fo (Página sólo la primera)

> [!IMPORTANT] Este complemento lo proporciona Adobe Consulting por cortesía para ayudarle a obtener más valor de Adobe Analytics. El Servicio de atención al cliente de Adobe no ofrece asistencia técnica con este complemento, incluida la instalación o solución de problemas. Si necesita ayuda con este complemento, póngase en contacto con el administrador de cuentas de su organización. Pueden organizar una reunión con un consultor para obtener ayuda.

El `p_fo` complemento es una utilidad que comprueba la existencia de un objeto JavaScript específico. Si el objeto no existe, el complemento crea el objeto y lo devuelve `true`. Si el objeto JavaScript ya existe en la página, devuelve `false`. Este complemento es útil para ejecutar código exactamente una vez en una página. Otros complementos dependen de este código para funcionar. Este complemento no es necesario si no le preocupa la cantidad de veces que se ejecuta el código en una página o si no utiliza ningún complemento dependiente.

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
   * Tipo de acción: Inicializar p_fo
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
/* Adobe Consulting Plugin: p_fo (pageFirstOnly) v2.0 */
s.p_fo=function(on){var s=this;s.__fo||(s.__fo={});if(s.__fo[on])return!1;s.__fo[on]={};return!0};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Utilizar el complemento

El `p_fo` método utiliza los siguientes argumentos:

* **on** (requerido, cadena): Nombre del objeto JavaScript que crea el complemento si el objeto no existe aún en la página.

Si el objeto aún no existe, este método devuelve `true` y crea el objeto. Si el objeto ya existe, este método devuelve `false`.

## Llamadas de ejemplo

### Ejemplo n.º 1

El siguiente código comprobará la existencia del objeto &quot;myobject&quot; dentro de la página.  Si el objeto &quot;myobject&quot; no existe, el código creará el objeto &quot;myobject&quot; y devolverá el valor true.  Como resultado, se ejecutará el código dentro de la afirmación condicional (por ejemplo, Console.log(&#39;hello&#39;);).

Por otro lado, si el objeto &quot;myobject&quot; ya existe cuando se realiza la llamada p_fo, la función p_fo devolverá el valor de false y, por lo tanto, la afirmación condicional se considerará falsa.  En este caso, el código dentro de la afirmación condicional no se ejecutará.

```javascript
if(s.p_fo("myobject"))
{
  console.log("hello");
}
```

**** NOTA: Cada vez que se carga un nuevo objeto de página/DOM (o que la página actual se recarga), el objeto especificado en el argumento on dejará de existir y, por lo tanto, el complemento p_fo volverá a ser true la primera vez que se ejecute después de que la página termine de cargarse.

## Historial de versiones

### 2.0

* Versión puntual (recompilada, tamaño de código más pequeño).
* Se cambió el tipo de valor devuelto de entero a booleano

### 1.0

* Versión inicial.

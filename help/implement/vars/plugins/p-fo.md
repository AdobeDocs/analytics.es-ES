---
title: p_fo (Page First Only)
description: Asegure que determinadas rutinas se activen solo una vez por página.
translation-type: ht
source-git-commit: 3c9e656d2f5bb9393826f31803d7b6f11a26ce0e
workflow-type: ht
source-wordcount: '628'
ht-degree: 100%

---


# Complemento de Adobe: p_fo (Page First Only)

>[!IMPORTANT]
>
>Adobe Consulting proporciona este complemento por cortesía para ayudarle a sacar el máximo partido a Adobe Analytics. El Servicio de atención al cliente de Adobe no ofrece asistencia técnica con este complemento, incluida la instalación o solución de problemas. Si necesita ayuda con este complemento, póngase en contacto con el administrador de cuentas de su organización. Ellos podrán organizar una reunión con un consultor para ayudarle.

El complemento `p_fo` es una utilidad que comprueba la existencia de un objeto JavaScript específico. Si el objeto no existe, el complemento crea el objeto y lo devuelve `true`. Si el objeto JavaScript ya existe en la página, devuelve `false`. Este complemento es útil para ejecutar código solo una vez en una página. Otros complementos dependen de este código para funcionar. Este complemento no es necesario si no le preocupa la cantidad de veces que se ejecuta el código en una página o si no utiliza ningún complemento dependiente.

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
   * Tipo de acción: Inicializar p_fo
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
/* Adobe Consulting Plugin: p_fo (pageFirstOnly) v3.0 (Requires AppMeasurement) */
function p_fo(c){if("-v"===c)return{plugin:"p_fo",version:"3.0"};a:{if("undefined"!==typeof window.s_c_il){var a=0;for(var b;a<window.s_c_il.length;a++)if(b=window.s_c_il[a],b._c&&"s_c"===b._c){a=b;break a}}a=void 0}"undefined"!==typeof a&&(a.contextData.p_fo="3.0");window.__fo||(window.__fo={});if(window.__fo[c])return!1;window.__fo[c]={};return!0};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Uso del complemento

El método `p_fo` utiliza los siguientes argumentos:

* **on** (obligatorio, cadena): El nombre del objeto JavaScript que crea el complemento si el objeto no existe aún en la página.

Si el objeto aún no existe, este método devuelve `true` y crea el objeto. Si el objeto ya existe, este método devuelve `false`.

## Llamadas de ejemplo

### Ejemplo 1

El siguiente código comprobará la existencia del objeto “myobject” dentro de la página.  Si el objeto “myobject” no existe, el código creará el objeto “myobject” y devolverá el valor true.  Como resultado, se ejecutará el código dentro del enunciado condicional (es decir, Console.log(&#39;hello&#39;);).

Por otro lado, si el objeto “myobject” ya existe cuando se realiza la llamada p_fo, la función p_fo devolverá el valor false y, por lo tanto, el enunciado condicional se considerará false.  En este caso, el código dentro de la afirmación condicional no se ejecutará.

```javascript
if(s.p_fo("myobject"))
{
  console.log("hello");
}
```

**NOTA**: Cada vez que se carga un nuevo objeto de página/DOM (o que la página actual se recarga), el objeto especificado en el argumento on dejará de existir y, por lo tanto, el complemento p_fo volverá a ser true la primera vez que se ejecute después de que la página termine de cargarse.

## Historial de versiones

### 3.0 (19 de marzo de 2021)

* Se ha añadido el número de versión como datos de contexto.

### 2,0

* Versión puntual (compilada de nuevo, con un tamaño de código más pequeño).
* Se ha cambiado el tipo de valor devuelto de entero a booleano.

### 1.0

* Versión inicial.

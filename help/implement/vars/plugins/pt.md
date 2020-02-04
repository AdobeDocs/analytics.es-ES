---
title: pt
description: Ejecuta una función en una lista de variables.
translation-type: tm+mt
source-git-commit: 180ad544541f25d02b3a257559bc045abed7387b

---


# Complemento de Adobe: pt

> [!IMPORTANT] Este complemento lo proporciona Adobe Consulting por cortesía para ayudarle a obtener más valor de Adobe Analytics. El Servicio de atención al cliente de Adobe no ofrece asistencia técnica con este complemento, incluida la instalación o solución de problemas. Si necesita ayuda con este complemento, póngase en contacto con el administrador de cuentas de su organización. Pueden organizar una reunión con un consultor para obtener ayuda.

El `pt` complemento ejecuta una función o un método en una lista de variables de Analytics. Por ejemplo, puede ejecutar el `clearVars` método de forma selectiva en varias variables sin llamar manualmente al método cada vez. Otros complementos dependen de este código para ejecutarse correctamente. Este complemento no es necesario si no necesita ejecutar una función específica en más de una variable de Analytics a la vez o si no utiliza ningún complemento dependiente.

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
   * Tipo de acción: Inicializar pt
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
/* Adobe Consulting Plugin: pt v2.01 */
 s.pt=function(l,de,cf,fa){if(l&&this[cf]){l=l.split(de||",");de=l.length;for(var e,c=0;c<de;c++)if(e=this[cf](l[c],fa))return e}};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Utilizar el complemento

El `pt` método utiliza los siguientes argumentos:

* **`l`**(requerido, cadena): Una lista de variables con las que se puede ejecutar la función contenida en el`cf`argumento.
* **`de`**(opcional, cadena): El delimitador que separa la lista de variables del`l`argumento. Valores predeterminados en una coma (`,`).
* **`cf`**(requerido, cadena): Nombre de la función de llamada de retorno contenida en el objeto AppMeasurement que se va a llamar en relación con cada una de las variables contenidas en el`l`argumento.
* **`fa`**(opcional, cadena): Si la función del`cf`argumento necesita argumentos adicionales cuando se ejecute, inclúyalos aquí. El valor predeterminado es`undefined`.

Al llamar a este método se devuelve un valor si la función de llamada de retorno (en el `cf` argumento) devuelve un valor.

## Llamadas de ejemplo

### Ejemplo n.º 1

El código siguiente forma parte del complemento getQueryParam.  Ejecuta la función de ayuda getParameterValue con cada uno de los pares de clave-valor que se encuentran en la cadena de consulta de la dirección URL (fullQueryString).  En otras, para extraer cada par clave-valor, fullQueryString debe estar delimitado y dividido por un carácter &quot;&amp;&quot; de símbolo &amp;. El parámetro parameterKey hace referencia al parámetro de cadena de consulta que el complemento intenta extraer específicamente de la cadena de consulta

```javascript
returnValue = s.pt(fullQueryString, "&", "getParameterValue", parameterKey)
```

La línea anterior es un método abreviado para ejecutar código similar a lo siguiente:

```js
var returnValue = "",
  parameters = fullQueryString.split("&"),
  parametersLength = parameters.length;
for(var i = 0; i < parametersLength; i++)
{
  returnValue = s.getParameterValue(parameters[i], parameterKey);
  if(returnValue !== "") break;
}
```

## Historial de versiones

### 2.01 (24 de septiembre de 2019)

* Cambios menores en el código para reducir el tamaño total

### 2.0 (17 de abril de 2018)

* Versión puntual (recompilada, tamaño de código más pequeño).
* Se agregó compatibilidad con el código H y AppMeasurement.

### 1.0 (23 de septiembre de 2013)

* Versión inicial.

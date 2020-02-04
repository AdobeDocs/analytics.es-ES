---
title: cleanStr
description: Quitar o reemplazar todos los caracteres innecesarios de una cadena.
translation-type: tm+mt
source-git-commit: 180ad544541f25d02b3a257559bc045abed7387b

---


# Complemento de Adobe:cleanStr

> [!IMPORTANT] Este complemento lo proporciona Adobe Consulting por cortesía para ayudarle a obtener más valor de Adobe Analytics. El Servicio de atención al cliente de Adobe no ofrece asistencia técnica con este complemento, incluida la instalación o solución de problemas. Si necesita ayuda con este complemento, póngase en contacto con el administrador de cuentas de su organización. Pueden organizar una reunión con un consultor para obtener ayuda.

El complemento elimina o reemplaza todos los caracteres innecesarios de una cadena, incluidos los caracteres de etiqueta HTML, espacios en blanco adicionales, fichas y retornos de línea/carro nuevos. `cleanStr` También reemplaza las comillas simples (`‘` y `’`) rectas (`'`). Adobe recomienda utilizar este complemento si desea eliminar caracteres innecesarios de los valores de las variables y la función &quot;Limpiar texto&quot; de Launch no satisface sus necesidades de implementación. Este complemento no es necesario si los datos recopilados no contienen caracteres innecesarios o si la función &quot;Limpiar texto&quot; de Launch es suficiente.

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
   * Tipo de acción: Inicializar cleanStr
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
/* Adobe Consulting Plugin: cleanStr v1.0 */
function cleanStr(str){if("string"===typeof str){str=str.replace(/<\/?[^>]+(>|$)/g,"");str=str.trim(); str=str.replace(/[\u2018\u2019\u201A]/g,"'");str=str.replace(/\t+/g,"");for(str=str.replace(/[\n\r]/g," ");-1<str.indexOf("  ");)str=str.replace(/\s\s/g," ");return str}return""};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Utilizar el complemento

El `cleanStr` método utiliza los siguientes argumentos:

* **`str`**(requerido, cadena): El valor que desea limpiar la codificación HTML, los espacios en blanco adicionales, las fichas u otros caracteres innecesarios.

El método devuelve el valor del `str` argumento con todos los caracteres innecesarios eliminados.

## Ejemplos

### Ejemplo n.º 1

Suponga lo siguiente (donde los puntos representan espacios y las flechas representan caracteres de tabulación)

```js
s.eVar1 = "»∙∙this∙∙is∙a∙∙»∙messy»string∙∙∙∙"
```

Al ejecutar el siguiente código...

```js
s.eVar1 = cleanStr(s.eVar1)
```

...eVar1 se configurará igual a &quot;esto es una cadena de mensajes&quot; (con todos los espacios adicionales y todos los caracteres de tabulación eliminados)

### Ejemplo n.º 2

Si...

```js
s.eVar1 = "»∙∙this∙∙is∙a∙∙»∙messy»string∙∙∙∙"
```

...y se ejecuta el siguiente código...

```js
cleanStr(s.eVar1)
```

...el valor final de s.eVar1 seguirá siendo:

```js
"»∙∙this∙∙is∙a∙∙»∙messy»string∙∙∙∙"
```

La ejecución del complemento por sí sola (sin asignar el valor devuelto a una variable) no &quot;restablece&quot; realmente la variable pasada a través del argumento str.

## Historial de versiones

### 1.0 (15 de abril de 2018)

* Versión inicial.

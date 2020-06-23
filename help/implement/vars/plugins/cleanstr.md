---
title: cleanStr
description: Eliminación o sustitución de todos los caracteres innecesarios de una cadena.
translation-type: ht
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Complemento de Adobe: cleanStr

>[!IMPORTANT] Adobe Consulting proporciona este complemento por cortesía para ayudarle a sacar el máximo partido a Adobe Analytics. El Servicio de atención al cliente de Adobe no ofrece asistencia técnica con este complemento, incluida la instalación o solución de problemas. Si necesita ayuda con este complemento, póngase en contacto con el administrador de cuentas de su organización. Ellos podrán organizar una reunión con un consultor para ayudarle.

El complemento `cleanStr` elimina o reemplaza todos los caracteres innecesarios de una cadena, incluidos los caracteres de etiqueta HTML, espacios en blanco adicionales, pestañas y retornos de línea/carro nuevos. También reemplaza las comillas simples (`‘` y `’`) con las rectas (`'`). Adobe recomienda utilizar este complemento si desea eliminar caracteres innecesarios de los valores de las variables y la función “Limpiar texto” de Launch no satisface sus necesidades de implementación. Este complemento no es necesario si los datos recopilados no contienen caracteres innecesarios o si la función “Limpiar texto” de Launch es suficiente.

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
   * Tipo de acción: Inicializar cleanStr
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
/* Adobe Consulting Plugin: cleanStr v1.0 */
function cleanStr(str){if("string"===typeof str){str=str.replace(/<\/?[^>]+(>|$)/g,"");str=str.trim(); str=str.replace(/[\u2018\u2019\u201A]/g,"'");str=str.replace(/\t+/g,"");for(str=str.replace(/[\n\r]/g," ");-1<str.indexOf("  ");)str=str.replace(/\s\s/g," ");return str}return""};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Uso del complemento

El método `cleanStr` utiliza los siguientes argumentos:

* **`str`** (obligatorio, cadena): El valor que desea para limpiar la codificación HTML, los espacios en blanco adicionales, las pestañas u otros caracteres innecesarios.

El método recupera el valor del argumento `str` con todos los caracteres innecesarios eliminados.

## Ejemplos

### Ejemplo 1

Supongamos lo siguiente (donde los puntos representan espacios y las flechas representan caracteres de tabulación)

```js
s.eVar1 = "»∙∙this∙∙is∙a∙∙»∙messy»string∙∙∙∙"
```

Al ejecutar el siguiente código...

```js
s.eVar1 = cleanStr(s.eVar1)
```

... eVar1 se configura igual a “esto es una cadena de mensajes” (con todos los espacios adicionales y todos los caracteres de tabulación eliminados).

### Ejemplo 2

Si...

```js
s.eVar1 = "»∙∙this∙∙is∙a∙∙»∙messy»string∙∙∙∙"
```

... y se ejecuta el siguiente código...

```js
cleanStr(s.eVar1)
```

... el valor final de s.eVar1 sigue siendo:

```js
"»∙∙this∙∙is∙a∙∙»∙messy»string∙∙∙∙"
```

La ejecución del complemento por sí sola (sin asignar el valor devuelto a una variable) no “restablece” realmente la variable pasada a través del argumento str.

## Historial de versiones

### 1.0 (15 de abril de 2018)

* Versión inicial.

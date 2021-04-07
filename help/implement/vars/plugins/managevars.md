---
title: manageVars
description: Modifique los valores de más de una variable de Analytics a la vez.
translation-type: ht
source-git-commit: 93a2dc1b265c92468722ebc2e3656db55d63547c
workflow-type: ht
source-wordcount: '697'
ht-degree: 100%

---


# Complemento de Adobe: manageVars

>[!IMPORTANT]
>
>Adobe Consulting proporciona este complemento por cortesía para ayudarle a sacar el máximo partido a Adobe Analytics. El Servicio de atención al cliente de Adobe no ofrece asistencia técnica con este complemento, incluida la instalación o solución de problemas. Si necesita ayuda con este complemento, póngase en contacto con el administrador de cuentas de su organización. Ellos podrán organizar una reunión con un consultor para ayudarle.

El complemento `manageVars` le permite manipular los valores de varias variables de Analytics a la vez. También puede definir valores en minúsculas o eliminar caracteres innecesarios de varios valores de variables al mismo tiempo. Adobe recomienda utilizar este complemento si desea limpiar el valor de diferentes variables a la vez.

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
   * Tipo de acción: Inicializar manageVars
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
/* Adobe Consulting Plugin: manageVars v3.0 (Requires AppMeasurement) */
function manageVars(cb,l,il){var g=cb,c=l,d=il;if("-v"===g)return{plugin:"manageVars",version:"3.0"};var f=function(){if("undefined"!==typeof window.s_c_il)for(var a=0,b;a<window.s_c_il.length;a++)if(b=window.s_c_il[a],b._c&&"s_c"===b._c)return b}();if("undefined"!==typeof f){f.contextData.manageVars="3.0";f.blankVars=function(a){this[a]&&(0>a.indexOf("contextData")?this[a]="":(a=a.substring(a.indexOf(".")+1),this.contextData[a]&&(this.contextData[a]="")))};f.lowerCaseVars=function(a){this[a]&&("events"!==a&&-1===a.indexOf("contextData")?(this[a]=this[a].toString(),0!==this[a].indexOf("D=")&&(this[a]=this[a].toLowerCase())):-1<a.indexOf("contextData")&&(a=a.substring(a.indexOf(".")+1),this.contextData[a]&&(this.contextData[a]=this.contextData[a].toString().toLowerCase())))};f.cleanStr=function(a){function b(a){if("string"===typeof a){for(a=a.replace(/<\/?[^>]+(>|$)/g,"").trim().replace(/[\u2018\u2019\u201A]/g,"'").replace(/\t+/g,"").replace(/[\n\r]/g," ");-1<a.indexOf("  ");)a=a.replace(/\s\s/g," ");return a}return""}this[a]&&"function"===typeof b&&(0>a.indexOf("contextData")?this[a]=b(this[a]):(a=a.substring(a.indexOf(".")+1),this.contextData[a]&&(this.contextData[a]=b(this.contextData[a].toString()))))};f.pt=function(a,b,c,d){if(a&&this[c]){a=a.split(b||",");b=a.length;for(var e,f=0;f<b;f++)if(e=this[c](a[f],d))return e}};if(!f[g])return!1;c=c||"";d=d||!0;var b,e="pageName,purchaseID,channel,server,pageType,campaign,state,zip,events,products,transactionID";for(b=1;76>b;b++)e+=",prop"+b;for(b=1;251>b;b++)e+=",eVar"+b;for(b=1;6>b;b++)e+=",hier"+b;for(b=1;4>b;b++)e+=",list"+b;for(b in f.contextData)e+=",contextData."+b;if(c){if(1==d)e=c.replace("['",".").replace("']","");else if(0==d){c=c.split(",");d=e.split(",");e="";for(x in c)for(y in-1<c[x].indexOf("contextData")&&(c[x]="contextData."+c[x].split("'")[1]),d)c[x]===d[y]&&(d[y]="");for(y in d)e+=d[y]?","+d[y]:""}f.pt(e,",",g,0);return!0}return""===c&&d?(f.pt(e,",",g,0),!0):!1}};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Uso del complemento

El método `manageVars` utiliza los siguientes argumentos:

* **`cb`** (obligatorio, cadena): El nombre de una función de llamada de retorno que el complemento utiliza para manipular las variables de Analytics. Puede utilizar una función de Adobe como `cleanStr` o su propia función personalizada.
* **`l`** (opcional, cadena): Una lista delimitada por comas de las variables de Analytics que desea manipular. Si no se establece, el valor predeterminado son TODAS las variables de Adobe Analytics, lo que incluye:
   * `pageName`
   * `purchaseID`
   * `channel`
   * `server`
   * `pageType`
   * `campaign`
   * `state`
   * `zip`
   * `events`
   * `products`
   * `transactionID`
   * Todas las props
   * Todas las eVars
   * Todas las variables de jerarquía
   * Todas las variables de lista
   * Todas las variables de datos de contexto
* **`Il`** (opcional, booleano): Se configura como `false` si desea *excluir* la lista de variables declaradas en el argumento `l` en lugar de incluirlas. El valor predeterminado es `true`.

Llamar a este método no devuelve nada. En su lugar, cambia los valores de las variables de Analytics según la función de llamada de retorno deseada.

## Llamadas de ejemplo

### Ejemplo 1

El siguiente código...

```js
s.manageVars("lowerCaseVars");
```

...cambia los valores de todas las variables descritas anteriormente a versiones en minúsculas.  La única excepción es la variable de eventos, ya que algunos eventos (por ejemplo: scAdd, scCheckout, etc.) distinguen entre mayúsculas y minúsculas y no deben cambiarse a minúsculas.

### Ejemplo 2

El siguiente código...

```js
s.manageVars("lowerCaseVars", "events", false);
```

... produce casi el mismo resultado que el primer ejemplo, ya que la variable de eventos no se convierte en minúsculas de forma predeterminada.

### Ejemplo 3

El siguiente código...

```js
s.manageVars("lowerCaseVars", "eVar1,eVar2,eVar3,list2");
```

... solo cambiará (por ejemplo, a minúsculas) los valores de eVar1, eVar2, eVar3 y list2.

### Ejemplo 4

El siguiente código...

```js
s.manageVars("lowerCaseVars", "eVar1,eVar2,eVar3,list2", false);
```

... cambiará (por ejemplo, a minúsculas) los valores de todas las variables descritas anteriormente EXCEPTO eVar1, eVar2, eVar3 y list2.

### Ejemplo 5

El siguiente código...

```js
s.manageVars("cleanStr");
```

... cambia los valores de todas las variables descritas anteriormente, incluidas las variables de eventos.  En concreto, la función de llamada de retorno cleanStr hace lo siguiente al valor de cada variable:

* Elimina la codificación HTML
* Elimina los espacios en blanco que se encuentran al principio y al final del valor
* Reemplaza las comillas simples izquierda/derecha (por ejemplo ’) con una comilla simple recta (&#39;)
* Reemplaza caracteres de tabulación, caracteres de nueva línea y caracteres de retorno de carro por espacios
* Reemplaza todos los espacios dobles (o triples, etc.) con espacios únicos

## Historial de versiones

### 3.0 (19 de marzo de 2021)

* Se ha añadido el número de versión como datos de contexto.

### 2.1 (14 de enero de 2019)

* Se han corregido los errores en los navegadores Internet Explorer 11.
* Se han hecho cambios en `s.cleanStr`, que ahora utiliza la función regular `cleanStr`.

### 2.0 (7 de mayo de 2018)

* Versión puntual (incluido el reanálisis/reescritura completo del complemento)
* Se ha agregado la función `cleanStr` de llamada de retorno

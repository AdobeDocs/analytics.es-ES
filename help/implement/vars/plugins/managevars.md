---
title: manageVars
description: Modifique los valores de más de una variable de Analytics a la vez.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '690'
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
/* Adobe Consulting Plugin: manageVars v2.1 (Requires pt plug-in and other necessary callback plug-ins) */
s.manageVars=function(cb,l,il){var s=this;if(!s[cb])return!1;l=l||"";il=il||!0;var a,d="pageName,purchaseID,channel,server, pageType,campaign,state,zip,events,products,transactionID";for(a=1;76>a;a++)d+=",prop"+a;for(a=1;251>a;a++)d+=",eVar"+a;for(a=1;6>a;a++)d+=",hier"+a;for(a=1;4>a;a++)d+=",list"+a;for(a in s.contextData)d+=",contextData."+a;if(l){if(1==il)d=l.replace("['", ".").replace("']","");else if(0==il){l=l.split(",");il=d.split(",");d="";for(x in l)for(y in-1<l[x].indexOf("contextData")&& (l[x]="contextData."+l[x].split("'")[1]),il)l[x]===il[y]&&(il[y]="");for(y in il)d+=il[y]?","+il[y]:""}s.pt(d,",",cb,0);return!0} return""===l&&il?(s.pt(d,",",cb,0),!0):!1};

/* Adobe Consulting Plugin: lowerCaseVars for manageVars (Requires manageVars plug-in) */
s.lowerCaseVars=function(v){var s=this;s[v]&&("events"!==v&&-1===v.indexOf("contextData")?(s[v]=s[v].toString(),0!== s[v].indexOf("D=")&&(s[v]=s[v].toLowerCase())):-1<v.indexOf("contextData")&&(v=v.substring(v.indexOf(".")+1),s.contextData[v]&& (s.contextData[v]=s.contextData[v].toString().toLowerCase())))};

/* Adobe Consulting Plugin: cleanStr for manageVars (Requires manageVars and cleanStr plug-ins) */
s.cleanStr=function(v){var s=this;s[v]&&"function"!==typeof cleanStr&&(0>v.indexOf("contextData")?s[v]=cleanStr(s[v]): (v=v.substring(v.indexOf(".")+1),s.contextData[v]&&(s.contextData[v]=cleanStr(s.contextData[v].toString()))))};

/* Adobe Consulting Plugin: cleanStr v1.0 */
function cleanStr(str){if("string"===typeof str){str=str.replace(/<\/?[^>]+(>|$)/g,"").trim().replace(/[\u2018\u2019\u201A]/g, "'").replace(/\t+/g,"").replace(/[\n\r]/g," ");for(;-1<str.indexOf("  ");)str=str.replace(/\s\s/g," ");return str}return""};

/* Adobe Consulting Plugin: pt v2.01 */
s.pt=function(l,de,cf,fa){if(l&&this[cf]){l=l.split(de||",");de=l.length;for(var e,c=0;c<de;c++)if(e=this[cf](l[c],fa))return e}};
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

### 2.1 (14 de enero de 2019)

* Se han corregido los errores en los navegadores Internet Explorer 11.
* Se han hecho cambios en `s.cleanStr`, que ahora utiliza la función regular `cleanStr`.

### 2.0 (7 de mayo de 2018)

* Versión puntual (incluido el reanálisis/reescritura completo del complemento)
* Se ha agregado la función `cleanStr` de llamada de retorno

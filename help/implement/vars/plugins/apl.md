---
title: apl (appendToList)
description: Anexe valores a variables que admitan varios valores.
translation-type: ht
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: ht
source-wordcount: '1029'
ht-degree: 100%

---


# Complemento de Adobe: apl (appendToList)

>[!IMPORTANT]
>
>Adobe Consulting proporciona este complemento por cortesía para ayudarle a sacar el máximo partido a Adobe Analytics. El Servicio de atención al cliente de Adobe no ofrece asistencia técnica con este complemento, incluida la instalación o solución de problemas. Si necesita ayuda con este complemento, póngase en contacto con el administrador de cuentas de su organización. Ellos podrán organizar una reunión con un consultor para ayudarle.

El complemento `apl` le permite agregar de forma segura nuevos valores a variables delimitadas por listas, como [`events`](../page-vars/events/events-overview.md), [`linkTrackVars`](../config-vars/linktrackvars.md), [`list`](../page-vars/list.md) y otras.

* Si el valor que desea agregar no aparece en la variable, el código agrega el valor al final de la cadena.
* Si el valor que desea agregar ya aparece en la variable, este complemento no cambia el valor. Esta función permite que la implementación no incluya valores duplicados.
* Si la variable que desea agregar está vacía, el complemento establece la variable en el nuevo valor.

Adobe recomienda utilizar este complemento si desea añadir valores nuevos a variables existentes que contengan una cadena de valores delimitados. Este complemento no es necesario si prefiere concatenar cadenas para variables que contengan valores delimitados.

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
   * Tipo de acción: Inicializar APL (Anexar a lista)
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
/* Adobe Consulting Plugin: apl (appendToList) v3.2 (Requires inList v2.0 or higher) */
s.apl=function(lv,vta,d1,d2,cc){if(!lv||"string"===typeof lv){if("undefined"===typeof this.inList||"string"!==typeof vta||""===vta)return lv;d1=d1||",";d2=d2||d1;1==d2&&(d2=d1,cc||(cc=1));2==d2&&1!=cc&&(d2=d1);vta=vta.split(",");for(var g=vta.length,e=0;e<g;e++)this.inList(lv,vta[e],d1,cc)||(lv=lv?lv+d2+vta[e]:vta[e])}return lv};

/* Adobe Consulting Plugin: inList v2.1 */
s.inList=function(lv,vtc,d,cc){if("string"!==typeof vtc)return!1;if("string"===typeof lv)lv=lv.split(d||",");else if("object"!== typeof lv)return!1;d=0;for(var e=lv.length;d<e;d++)if(1==cc&&vtc===lv[d]||vtc.toLowerCase()===lv[d].toLowerCase())return!0;return!1};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Uso del complemento

El método `apl` utiliza los siguientes argumentos:

* **`lv`** (obligatorio, cadena): La variable que contiene una lista delimitada de elementos para agregar un nuevo valor a
* **`vta`** (obligatorio, cadena): Una lista delimitada por comas de los nuevos valores que se agregan al valor del argumento `lv`.
* **`d1`** (opcional, cadena): El delimitador utilizado para separar los valores individuales ya contenidos en el argumento `lv`.  Si no se configura de forma distinta, el valor predeterminado es una coma (`,`).
* **`d2`** (opcional, cadena): El delimitador de salida. Si no se especifica lo contrario, el valor predeterminado es el mismo que `d1`.
* **`cc`** (opcional, booleano): Indica si se utiliza una comprobación que distingue entre mayúsculas y minúsculas. Con `true`, la comprobación de duplicaciones distingue entre mayúsculas y minúsculas. Si se selecciona `false` o no, la comprobación de duplicaciones no distingue entre mayúsculas y minúsculas. El valor predeterminado es `false`.

El método `apl` devuelve el valor del argumento `lv` más cualquier valor no duplicado del argumento `vta`.

## Llamadas de ejemplo

### Ejemplo 1

Si...

```js
s.events = "event22,event24";
```

... y se ejecuta el siguiente código...

```js
s.events = s.apl(s.events, "event23");
```

... el valor final de s.events es:

```js
s.events = "event22,event24,event23";
```

### Ejemplo 2

Si...

```js
s.events = "event22,event23";
```

... y se ejecuta el siguiente código...

```js
s.events = s.apl(s.events, "event23");
```

... el valor final de s.events sigue siendo:

```js
s.events = "event22,event23";
```

En este ejemplo, la llamada de apl no realiza cambios en s.events porque s.events ya contiene “event23”.

### Ejemplo 3

Si...

```js
s.events = ""; //blank value
```

... y se ejecuta el siguiente código...

```js
s.events = s.apl(s.events, "event23");
```

... el valor final de s.events es...

```js
s.events = "event23";
```

### Ejemplo 4

Si...

```js
s.prop4 = "hello|people";
```

... y se ejecuta el siguiente código...

```js
s.eVar5 = s.apl(s.prop4, "today", "|");
```

... el valor final de s.prop4 sigue siendo...

```js
s.prop4 = "hello|people";
```

... pero el valor final de s.eVar5 es

```js
s.eVar5 = "hello|people|today";
```

Tenga en cuenta que el complemento solo devuelve un valor; no necesariamente “restablece” la variable pasada a través del argumento lv.

### Ejemplo 5

Si...

```js
s.prop4 = "hello|people";
```

... y se ejecuta el siguiente código...

```js
s.prop4 = s.apl(s.prop4, "today");
```

... el valor final de s.prop4 es...

```js
s.prop4 = "hello|people,today";
```

Asegúrese de mantener el mismo delimitador entre lo que hay en el valor del argumento lv y lo que hay en los argumentos d1/d2.

### Ejemplo 6

Si...

```js
s.events = "event22,event23";
```

... y se ejecuta el siguiente código...

```js
s.events = s.apl(s.events,"EVenT23", ",", ",", true);
```

... el valor final de s.events es:

```js
s.events = "event22,event23,EVentT23";
```

Aunque este ejemplo no es práctico, demuestra la necesidad de tener cuidado al utilizar el indicador que distingue entre mayúsculas y minúsculas.

### Ejemplo 7

Si...

```js
s.events = "event22,event23";
```

... y se ejecuta el siguiente código...

```js
s.events = s.apl(s.events, "event23,event24,event25");
```

... el valor final de s.events es:

```js
s.events = "event22,event23,event24,event25");
```

El complemento no añade “event23” a s.events porque ya existe en s.events.  Sin embargo, sí añade event24 y event25 a s.events porque no se incluyeron en s.events anteriormente.

### Ejemplo 8

Si...

```js
s.linkTrackVars = "events,eVar1";
```

... y se ejecuta el siguiente código...

```js
s.linkTrackVars = s.apl(s.linkTrackVars, "campaign", ",", ",", false);
```

... el valor final de s.linkTrackVars es:

```js
s.linkTrackVars = "events,eVar1,campaign";
```

Los tres últimos argumentos (p. ej. “,”, “,”, false) al final de esta llamada de API no son necesarios pero tampoco “dañan nada” al configurarse, ya que coinciden con los valores de argumento predeterminados.

### Ejemplo 9

Si...

```js
s.events = "event22,event24";
```

... y se ejecuta el siguiente código...

```js
s.apl(s.events, "event23");
```

... el valor final de s.events sigue siendo:

```js
s.events = "event22,event24";
```

La ejecución del complemento por sí sola (sin asignar el valor devuelto a una variable) no “restablece” realmente la variable pasada a través del argumento lv.

### Ejemplo 10

Si...

```js
s.list2 = "casesensitivevalue|casesensitiveValue"
```

... y se ejecuta el siguiente código...

```js
s.list2 = s.apl(s.list2, "CasESensiTiveValuE", "|", "-", true);
```

... el valor final de s.list2 es:

```js
s.list2 = "casesensitivevalue-casesensitiveValue-CasESensiTiveValuE"
```

Dado que los dos argumentos delimitadores son diferentes, el valor pasado se delimita por el primer argumento delimitador (“|”) y luego se une por el segundo argumento delimitador (“-”).

## Historial de versiones

### 3.2 (25 de septiembre de 2019)

* Se han corregido problemas de compatibilidad con llamadas `apl` que usaban versiones anteriores del complemento.
* Se han eliminado las advertencias de la consola para reducir el tamaño.
* Se ha añadido `inList 2.1`.

### 3.1 (22 de abril de 2018)

* El argumento `d2` ahora se establece de forma predeterminada en el valor del argumento `d1` cuando, si no se especifica lo contrario.

### 3.0 (16 de abril de 2018)

* Reanálisis y reescritura completos del complemento
* Se ha agregado la comprobación avanzada de errores.
* El argumento `vta` ahora acepta varios valores al mismo tiempo.
* Se ha agregado el argumento `d2` para dar formato al valor devuelto.
* Se ha cambiado el argumento `cc`, ahora es booleano.

### 2.5 (18 de febrero de 2016)

* Ahora se utiliza el método `inList` para el procesamiento de comparación.

### 2.0 (26 de enero de 2016)

* El argumento `d` (delimitador) ahora es opcional (el valor predeterminado es una coma).
* El argumento `u` (indicador de distinción entre mayúsculas y minúsculas) ahora es opcional (de forma predeterminada distingue entre mayúsculas y minúsculas).
* Independientemente del argumento `u` (indicador de distinción entre mayúsculas y minúsculas), el complemento ya no añade un valor a una lista si este ya existe en dicha lista.
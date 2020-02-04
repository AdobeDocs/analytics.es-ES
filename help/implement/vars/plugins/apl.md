---
title: ' apl (appendToList)'
description: Anexe valores a variables que admitan varios valores.
translation-type: tm+mt
source-git-commit: 180ad544541f25d02b3a257559bc045abed7387b

---


# Complemento de Adobe: apl (appendToList)

> [!IMPORTANT] Este complemento lo proporciona Adobe Consulting por cortesía para ayudarle a obtener más valor de Adobe Analytics. El Servicio de atención al cliente de Adobe no ofrece asistencia técnica con este complemento, incluida la instalación o solución de problemas. Si necesita ayuda con este complemento, póngase en contacto con el administrador de cuentas de su organización. Pueden organizar una reunión con un consultor para obtener ayuda.

El `apl` complemento le permite agregar de forma segura nuevos valores a variables delimitadas por listas, como `events`, `linkTrackVars`, variables de lista y otras.

* Si el valor que desea agregar no existe en la variable, el código agrega el valor al final de la cadena.
* Si el valor que desea agregar ya existe en la variable, este complemento no cambia el valor. Esta función permite que la implementación evite valores duplicados.
* Si la variable que desea agregar está vacía, el complemento establece la variable en el nuevo valor.

Adobe recomienda utilizar este complemento si desea agregar nuevos valores a variables existentes que contengan una cadena de valores delimitados. Este complemento no es necesario si prefiere concatenar cadenas para variables que contengan valores delimitados.

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
   * Tipo de acción: Inicializar APL (Anexar a lista)
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
/* Adobe Consulting Plugin: apl (appendToList) v3.2 (Requires inList v2.0 or higher) */
s.apl=function(lv,vta,d1,d2,cc){if(!lv||"string"===typeof lv){if("undefined"===typeof this.inList||"string"!==typeof vta||""===vta)return lv;d1=d1||",";d2=d2||d1;1==d2&&(d2=d1,cc||(cc=1));2==d2&&1!=cc&&(d2=d1);vta=vta.split(",");for(var g=vta.length,e=0;e<g;e++)this.inList(lv,vta[e],d1,cc)||(lv=lv?lv+d2+vta[e]:vta[e])}return lv};

/* Adobe Consulting Plugin: inList v2.1 */
s.inList=function(lv,vtc,d,cc){if("string"!==typeof vtc)return!1;if("string"===typeof lv)lv=lv.split(d||",");else if("object"!== typeof lv)return!1;d=0;for(var e=lv.length;d<e;d++)if(1==cc&&vtc===lv[d]||vtc.toLowerCase()===lv[d].toLowerCase())return!0;return!1};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Utilizar el complemento

El `apl` método utiliza los siguientes argumentos:

* **`lv`**(requerido, cadena): La variable que contiene una lista delimitada de elementos para agregar un nuevo valor a
* **`vta`**(requerido, cadena): Una lista delimitada por comas de los nuevos valores que se agregarán al valor del`lv`argumento.
* **`d1`**(opcional, cadena): El delimitador utilizado para separar los valores individuales ya contenidos en el`lv`argumento.  El valor predeterminado es una coma (`,`) cuando no se establece.
* **`d2`**(opcional, cadena): El delimitador de salida. El valor predeterminado es el mismo que`d1`cuando no se establece.
* **`cc`**(opcional, booleano): Un indicador que indica si se utiliza una comprobación que distingue entre mayúsculas y minúsculas. Si`true`la comprobación de la duplicación distingue entre mayúsculas y minúsculas. Si`false`se establece o no, la comprobación de la duplicación no distingue entre mayúsculas y minúsculas. El valor predeterminado es`false`.

El `apl` método devuelve el valor del `lv` argumento más cualquier valor no duplicado del `vta` argumento.

## Llamadas de ejemplo

### Ejemplo n.º 1

Si...

```js
s.events = "event22,event24";
```

...y se ejecuta el siguiente código...

```js
s.events = s.apl(s.events, "event23");
```

...el valor final de s.events será:

```js
s.events = "event22,event24,event23";
```

### Ejemplo n.º 2

Si...

```js
s.events = "event22,event23";
```

...y se ejecuta el siguiente código...

```js
s.events = s.apl(s.events, "event23");
```

...el valor final de s.events seguirá siendo:

```js
s.events = "event22,event23";
```

En este ejemplo, la llamada de apl no realizó cambios en s.events porque s.events ya contenía &quot;event23&quot;

### Ejemplo n.º 3

Si...

```js
s.events = ""; //blank value
```

...y se ejecuta el siguiente código...

```js
s.events = s.apl(s.events, "event23");
```

... el valor final de s.events será...

```js
s.events = "event23";
```

### Ejemplo n.º 4

Si...

```js
s.prop4 = "hello|people";
```

...y se ejecuta el siguiente código...

```js
s.eVar5 = s.apl(s.prop4, "today", "|");
```

...el valor final de s.prop4 seguirá siendo...

```js
s.prop4 = "hello|people";
```

...pero el valor final de s.eVar5 será

```js
s.eVar5 = "hello|people|today";
```

Tenga en cuenta que el complemento solo devuelve un valor; no necesariamente &quot;restablece&quot; la variable pasada a través del argumento lv.

### Ejemplo n.º 5

Si...

```js
s.prop4 = "hello|people";
```

...y se ejecuta el siguiente código...

```js
s.prop4 = s.apl(s.prop4, "today");
```

... el valor final de s.prop4 será...

```js
s.prop4 = "hello|people,today";
```

Asegúrese de mantener el delimitador coherente entre lo que hay en el valor del argumento lv y lo que hay en los argumentos d1/d2

### Ejemplo n.º 6

Si...

```js
s.events = "event22,event23";
```

...y se ejecuta el siguiente código...

```js
s.events = s.apl(s.events,"EVenT23", ",", ",", true);
```

...el valor final de s.events será:

```js
s.events = "event22,event23,EVentT23";
```

Aunque este ejemplo no es práctico, demuestra la necesidad de tener cuidado al utilizar el indicador que distingue entre mayúsculas y minúsculas.

### Ejemplo n.º 7

Si...

```js
s.events = "event22,event23";
```

...y se ejecuta el siguiente código...

```js
s.events = s.apl(s.events, "event23,event24,event25");
```

...el valor final de s.events será:

```js
s.events = "event22,event23,event24,event25");
```

El complemento no agregará &quot;event23&quot; a s.events porque ya existe en s.events.  Sin embargo, agregará event24 y event25 a s.events porque no se incluyeron en s.events anteriormente.

### Ejemplo n.º 8

Si...

```js
s.linkTrackVars = "events,eVar1";
```

...y se ejecuta el siguiente código...

```js
s.linkTrackVars = s.apl(s.linkTrackVars, "campaign", ",", ",", false);
```

...el valor final de s.linkTrackVars será:

```js
s.linkTrackVars = "events,eVar1,campaign";
```

Los tres últimos argumentos (p. ej. &quot;,&quot;, &quot;,&quot;, false) al final de esta llamada de API no son necesarios pero tampoco &quot;dañan nada&quot; al configurarse, ya que coinciden con los valores de argumento predeterminados.

### Ejemplo n.º 9

Si...

```js
s.events = "event22,event24";
```

...y se ejecuta el siguiente código...

```js
s.apl(s.events, "event23");
```

...el valor final de s.events seguirá siendo:

```js
s.events = "event22,event24";
```

La ejecución del complemento por sí sola (sin asignar el valor devuelto a una variable) no &quot;restablece&quot; realmente la variable pasada a través del argumento lv.

### Ejemplo 10

Si...

```js
s.list2 = "casesensitivevalue|casesensitiveValue"
```

...y se ejecuta el siguiente código...

```js
s.list2 = s.apl(s.list2, "CasESensiTiveValuE", "|", "-", true);
```

... el valor final de s.list2 será:

```js
s.list2 = "casesensitivevalue-casesensitiveValue-CasESensiTiveValuE"
```

Dado que los dos argumentos delimitadores son diferentes, el valor pasado se delimita por el primer argumento delimitador (&quot;|&quot;) y luego se une por el segundo argumento delimitador (&quot;-&quot;)

## Historial de versiones

### 3.2 (25 de septiembre de 2019)

* Se han corregido problemas de compatibilidad con `apl` llamadas que usaban versiones anteriores del complemento
* Se han eliminado las advertencias de la consola para reducir el tamaño
* Se ha añadido `inList 2.1`

### 3.1 (22 de abril de 2018)

* `d2` ahora se establece de forma predeterminada en el valor del `d1` argumento cuando no se establece

### 3.0 (16 de abril de 2018)

* Reanálisis y reescritura completos del complemento
* Se agregó la comprobación avanzada de errores
* El `vta` argumento ahora acepta varios valores al mismo tiempo
* Se agregó el `d2` argumento para dar formato al valor devuelto
* Se cambió el argumento `cc` a booleano

### 2.5 (18 de febrero de 2016)

* Ahora utiliza el `inList` método para el procesamiento de comparación

### 2.0 (26 de enero de 2016)

* `d` (Delimitador) ahora es opcional (el valor predeterminado es una coma)
* `u` (Indicador de distinción entre mayúsculas y minúsculas) ahora es opcional (se utiliza de forma predeterminada para distinguir entre mayúsculas y minúsculas)
* Independientemente del argumento `u` (indicador de distinción entre mayúsculas y minúsculas), el complemento ya no anexa un valor a una lista si el valor ya existe en la lista
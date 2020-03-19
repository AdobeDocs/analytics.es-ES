---
title: rfl
description: Elimine un valor específico de una cadena delimitada por caracteres.
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# Complemento de Adobe: rfl (Quitar de la lista)

> [!IMPORTANT] Este complemento lo proporciona Adobe Consulting por cortesía para ayudarle a obtener más valor de Adobe Analytics. El Servicio de atención al cliente de Adobe no ofrece asistencia técnica con este complemento, incluida la instalación o solución de problemas. Si necesita ayuda con este complemento, póngase en contacto con el administrador de cuentas de su organización. Pueden organizar una reunión con un consultor para obtener ayuda.

El `rfl` complemento le permite eliminar &quot;con seguridad&quot; los valores de las cadenas delimitadas, como [`events`](../page-vars/events/events-overview.md), [`products`](../page-vars/products.md), [`list`](../page-vars/list.md), etc. Este complemento es útil si desea eliminar valores específicos de una cadena delimitada sin preocuparse por los delimitadores. Otros complementos dependen de este código para ejecutarse correctamente. Este complemento no es necesario si no necesita ejecutar una función específica en más de una variable de Analytics a la vez o si no utiliza ningún complemento dependiente.

El complemento utiliza la lógica siguiente:

* Si el valor que desea eliminar existe, el complemento lo guarda todo en la variable excepto el valor que se va a eliminar.
* Si el valor que desea eliminar no existe, el complemento mantiene la cadena original tal cual.

## Instalación del complemento con la extensión Adobe Experience Platform Launch

Adobe ofrece una extensión que le permite utilizar los complementos más utilizados.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
1. Haga clic en la propiedad que desee.
1. Vaya a la ficha [!UICONTROL Extensions] y haga clic en el [!UICONTROL Catalog]
1. Instalación y publicación de la [!UICONTROL Common Analytics Plugins] extensión
1. Si aún no lo ha hecho, cree una regla con la etiqueta &quot;Inicializar complementos&quot; con la siguiente configuración:
   * Condición: Ninguno
   * Evento: Core - Biblioteca cargada (Principio de página)
1. Agregue una acción a la regla anterior con la siguiente configuración:
   * Extensión: Complementos comunes de Analytics
   * Tipo de acción: Inicializar RFP (Quitar de la lista)
1. Guarde y publique los cambios en la regla.

## Instalación del complemento con el editor de código personalizado Iniciar

Si no desea utilizar la extensión del complemento, puede utilizar el editor de código personalizado.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
1. Haga clic en la propiedad deseada.
1. Vaya a la [!UICONTROL Extensions] ficha y, a continuación, haga clic en el [!UICONTROL Configure] botón situado debajo de la extensión de Adobe Analytics.
1. Expanda el [!UICONTROL Configure tracking using custom code] acordeón, que muestra el [!UICONTROL Open Editor] botón.
1. Abra el editor de código personalizado y pegue el código del complemento que se proporciona a continuación en la ventana de edición.
1. Guarde y publique los cambios en la extensión de Analytics.

## Instalación del complemento mediante AppMeasurement

Copie y pegue el siguiente código en cualquier parte del archivo AppMeasurement después de crear una instancia del objeto de seguimiento de Analytics (mediante [`s_gi`](../functions/s-gi.md)). La conservación de los comentarios y los números de versión del código en la implementación ayuda a Adobe a solucionar cualquier problema potencial.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: rfl (removeFromList) v2.01 */
s.rfl=function(lv,vr,d1,d2,df){if(!lv||!vr)return"";var d=[],b="";d2=d2?d2:d1;df=df?!0:!1;lv=lv.split(d1?d1:",");d1=lv.length;for(var c=0;c<d1;c++)-1<lv[c].indexOf(":")&&(b=lv[c].split(":"),b[1]=b[0]+":"+b[1],lv[c]=b[0]),-1<lv[c].indexOf("=")&&(b=lv[c].split("="), b[1]=b[0]+"="+b[1],lv[c]=b[0]),lv[c]!==vr&&b?d.push(b[1]):lv[c]!==vr?d.push(lv[c]):lv[c]===vr&&df&&(b?d.push(b[1]):d.push(lv[c]),df=!1),b="";return d.join(d2)};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Utilizar el complemento

El `rfl` método utiliza los siguientes argumentos:

* **`lv`** (requerido, cadena): Variable (o cadena) que contiene una lista de valores delimitados
* **`vr`** (requerido, cadena): El valor que desea eliminar del `lv` argumento. Adobe recomienda no eliminar varios valores durante una sola `rfl` llamada.
* **`d1`** (opcional, cadena): El delimitador que utiliza el `lv` argumento. Valores predeterminados en una coma (`,`).
* **`d2`** (opcional, cadena): El delimitador que desea que utilice la cadena de retorno. El valor predeterminado es el mismo que el `d1` argumento.
* **`df`** (opcional, booleano): Si `true`, fuerza sólo las instancias duplicadas del `vr` argumento desde el `lv` argumento en lugar de todas las instancias. El valor predeterminado es `false` cuando no se establece.

Al llamar a este método se devuelve una cadena modificada que contiene el `lv` argumento, pero sin instancias (o instancias duplicadas) del valor especificado en el `vr` argumento.

## Llamadas de ejemplo

### Ejemplo n.º 1

Si...

```js
s.events = "event22,event24,event25";
```

...y se ejecuta el siguiente código...

```js
s.events = s.rfl(s.events,"event24");
```

...el valor final de s.events será:

```js
s.events = "event22,event25";
```

### Ejemplo n.º 2

Si...

```js
s.events = "event22,event24,event25";
```

...y se ejecuta el siguiente código...

```js
s.events = s.rfl(s.events,"event26");
```

...el valor final de s.events será:

```js
s.events = "event22,event24,event25";
```

En este ejemplo, la llamada rfl no realizó cambios en s.events porque s.events no contenía &quot;event26&quot;

### Ejemplo n.º 3

Si...

```js
s.events = "event22,event24,event25";
```

...y se ejecuta el siguiente código...

```js
s.events = s.rfl(s.events);
```

...el valor final de s.events será:

```js
s.events = "";
```

Si el argumento lv o el argumento vr están en blanco en una llamada s.rfl, el complemento no devolverá nada

### Ejemplo n.º 4

Si...

```js
s.prop4 = "hello|people|today";
```

...y se ejecuta el siguiente código...

```js
s.eVar5 = s.rfl(s.prop4,"people","|");
```

...el valor final de s.prop4 seguirá siendo...

```js
s.prop4 = "hello|people|today";
```

...pero el valor final de s.eVar5 será:

```js
s.eVar5 = "hello|today";
```

Tenga en cuenta que el complemento solo devuelve un valor; no &quot;restablece&quot; realmente la variable pasada a través del argumento lv.

### Ejemplo n.º 5

Si...

```js
s.prop4 = "hello|people|today";
```

...y se ejecuta el siguiente código...

```js
s.prop4 = s.rfl(s.prop4,"people");
```

...el valor final de s.prop4 seguirá siendo...

```js
s.prop4 = "hello|people|today";
```

Asegúrese de establecer el argumento d1 en casos en los que el valor del argumento lv contenga un delimitador diferente del valor predeterminado (es decir, coma).

### Ejemplo n.º 6

Si...

```js
s.events = "event22,event23,event25";
```

...y se ejecuta el siguiente código...

```js
s.events = s.rfl(s.events,"EVenT23");
```

...el valor final de s.events será:

```js
s.events = "event22,event23,event25";
```

Aunque este ejemplo no es práctico, demuestra la necesidad de pasar valores que distinguen entre mayúsculas y minúsculas.

### Ejemplo n.º 7

Si...

```js
s.events = "event22,event23:12345,event25";
```

...y se ejecuta el siguiente código...

```js
s.events = s.rfl(s.events,"event23");
```

...el valor final de s.events será:

```js
s.events = "event22,event25";
```

### Ejemplo n.º 8

Si...

```js
s.events = "event22,event23:12345,event25";
```

...y se ejecuta el siguiente código...

```js
s.events = s.rfl(s.events,"event23:12345");
```

...el valor final de s.events será:

```js
s.events = "event22,event23:12345,event25";
```

Cuando necesite eliminar un evento que utilice una sintaxis de serialización o numérica/monetaria, debe especificar solo el evento en sí (es decir, sin los valores de serialización/numéricos/monetarios) en la llamada s.rfl.

### Ejemplo n.º 9

Si...

```js
s.events = "event22,event23,event23,event23,event24,event25";
```

...y se ejecuta el siguiente código...

```js
s.events = s.rfl(s.events,"event23");
```

...el valor final de s.events será:

```js
s.events = "event22,event24,event25");
```

### Ejemplo 10

Si...

```js
s.events = "event22,event23,event23,event23,event24,event25";
```

...y se ejecuta el siguiente código...

```js
s.events = s.rfl(s.events,"event23", "", "",true);
```

...el valor final de s.events será:

```js
s.events = "event22,event23,event24,event25");
```

### Ejemplo 11

Si...

```js
s.events = "event22,event23,event23,event23,event24,event25";
```

...y se ejecuta el siguiente código...

```js
s.events = s.rfl(s.events,"event23", "", "|",true);
```

...el valor final de s.events será:

```js
s.events = "event22|event23|event24|event25");
```

### Ejemplo 12

Si...

```js
s.events = "event22,event23,event24,event25";
```

...y se ejecuta el siguiente código...

```js
s.events = s.rfl(s.events,"event23,event24");
```

...el valor final de s.events será:

```js
s.events = "event22,event23,event24,event25";
```

No se admite la configuración de varios valores en el argumento vr. La lógica rfl del ejemplo anterior primero dividiría los valores del argumento lv (es decir, s.events) y luego trataría de hacer coincidir cada valor delimitado con el valor del argumento vr completo (es decir, &quot;event23,event24&quot;).

### Ejemplo 13

Si...

```js
s.events = "event22,event23,event24,event25";
```

...y se ejecuta el siguiente código...

```js
s.events = s.rfl(s.events,"event23");
s.events = s.rfl(s.events,"event24");
```

...el valor final de s.events será:

```js
s.events = "event22,event25");
```

Cada valor que se va a eliminar de la lista debe estar contenido dentro de su propia llamada s.rfl.

### Ejemplo 14

Si...

```js
s.linkTrackVars = "events,eVar1,eVar2,eVar3";
```

...y se ejecuta el siguiente código...

```js
s.linkTrackVars = s.rfl(s.linkTrackVars,"eVar2", ",", ",", false);
```

...el valor final de s.linkTrackVars será:

```js
s.linkTrackVars = "events,eVar1,eVar3";
```

Los tres últimos argumentos (p. ej. &quot;,&quot;,&quot;,&quot;,false) al final de esta llamada s.rfl no son necesarios, pero tampoco &quot;dañan nada&quot; al estar allí porque coinciden con la configuración predeterminada.

### Ejemplo 15

Si...

```js
s.events = "event22,event23,event24";
```

...y se ejecuta el siguiente código...

```js
s.rfl(s.events,"event23");
```

...el valor final de s.events seguirá siendo:

```js
s.events = "event22,event23,event24";
```

Nuevamente, tenga en cuenta que el complemento solo devuelve un valor; no &quot;restablece&quot; realmente la variable pasada a través del argumento lv.

## Historial de versiones

### 2.01 (17 de septiembre de 2019)

* Corrección de errores menor para el valor de delimitador predeterminado

### 2.0 (16 de abril de 2018)

* Versión puntual (recompilada, tamaño de código más pequeño).
* Se ha eliminado la necesidad del `join` complemento.

### 1.0 (18 de julio de 2016)

* Versión inicial.

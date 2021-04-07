---
title: rfl
description: Elimine un valor específico de una cadena delimitada por caracteres.
translation-type: ht
source-git-commit: 4c23f3cf764834636c1cdcefb2903efc9c90be7a
workflow-type: ht
source-wordcount: '1054'
ht-degree: 100%

---


# Complemento de Adobe: rfl (Remove From List)

>[!IMPORTANT]
>
>Adobe Consulting proporciona este complemento por cortesía para ayudarle a sacar el máximo partido a Adobe Analytics. El Servicio de atención al cliente de Adobe no ofrece asistencia técnica con este complemento, incluida la instalación o solución de problemas. Si necesita ayuda con este complemento, póngase en contacto con el administrador de cuentas de su organización. Ellos podrán organizar una reunión con un consultor para ayudarle.

El complemento `rfl` le permite eliminar “con seguridad” valores de cadenas delimitadas, como [`events`](../page-vars/events/events-overview.md), [`products`](../page-vars/products.md), [`list`](../page-vars/list.md) y otros. Este complemento es útil si desea eliminar valores específicos de una cadena delimitada sin preocuparse por los delimitadores. Otros complementos dependen de este código para ejecutarse correctamente. Este complemento no es necesario si no necesita ejecutar una función específica en más de una variable de Analytics a la vez o si no utiliza ningún complemento dependiente.

El complemento utiliza la lógica siguiente:

* Si el valor que desea eliminar existe, el complemento guarda todo en la variable excepto el valor que se va a eliminar.
* Si el valor que desea eliminar no existe, el complemento mantiene la cadena original tal cual.

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
   * Tipo de acción: Inicializar RFP (Remove From List)
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
/* Adobe Consulting Plugin: rfl (removeFromList) v2.1  */
function rfl(lv,vr,d1,d2,df){var b=lv,f=vr,e=d1,h=d2,g=df;if("-v"===b)return{plugin:"rfl",version:"2.1"};a:{if("undefined"!==typeof window.s_c_il){var c=0;for(var a;c<window.s_c_il.length;c++)if(a=window.s_c_il[c],a._c&&"s_c"===a._c){c=a;break a}}c=void 0}"undefined"!==typeof c&&(c.contextData.rfl="2.1");if(!b||!f)return"";c=[];a="";e=e||",";h=h||e;g=g||!1;b=b.split(e);e=b.length;for(var d=0;d<e;d++)-1<b[d].indexOf(":")&&(a=b[d].split(":"),a[1]=a[0]+":"+a[1],b[d]=a[0]),-1<b[d].indexOf("=")&&(a=b[d].split("="),a[1]=a[0]+"="+a[1],b[d]=a[0]),b[d]!==f&&a?c.push(a[1]):b[d]!==f?c.push(b[d]):b[d]===f&&g&&(a?c.push(a[1]):c.push(b[d]),g=!1),a="";return c.join(h)};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Uso del complemento

El método `rfl` utiliza los siguientes argumentos:

* **`lv`** (obligatorio, cadena): Una variable (o cadena) que contiene una lista de valores delimitados.
* **`vr`** (obligatorio, cadena): El valor que desea eliminar del argumento `lv`. Adobe recomienda no eliminar varios valores durante una sola llamada `rfl`.
* **`d1`** (opcional, cadena): El delimitador que utiliza el argumento `lv`. El valor predeterminado es una coma (`,`).
* **`d2`** (opcional, cadena): El delimitador que desea que utilice la cadena de retorno. El valor predeterminado es el mismo que el argumento `d1`.
* **`df`** (opcional, booleano): Si `true`, fuerza solo las instancias duplicadas del argumento `vr` desde el argumento `lv` en lugar de todas las instancias. Si no se configura de forma distinta, el valor predeterminado es `false`.

Llamar a este método devuelve una cadena modificada que contiene el argumento `lv`, pero sin instancias (o instancias duplicadas) del valor especificado en el argumento `vr`.

## Llamadas de ejemplo

### Ejemplo 1

Si...

```js
s.events = "event22,event24,event25";
```

... y se ejecuta el siguiente código...

```js
s.events = s.rfl(s.events,"event24");
```

... el valor final de s.events será:

```js
s.events = "event22,event25";
```

### Ejemplo 2

Si...

```js
s.events = "event22,event24,event25";
```

... y se ejecuta el siguiente código...

```js
s.events = s.rfl(s.events,"event26");
```

... el valor final de s.events será:

```js
s.events = "event22,event24,event25";
```

En este ejemplo, la llamada rfl no realizó cambios en s.events porque s.events no contenía “event26”.

### Ejemplo 3

Si...

```js
s.events = "event22,event24,event25";
```

... y se ejecuta el siguiente código...

```js
s.events = s.rfl(s.events);
```

... el valor final de s.events será:

```js
s.events = "";
```

Si el argumento lv o el argumento vr están en blanco en una llamada s.rfl, el complemento no devolverá nada.

### Ejemplo 4

Si...

```js
s.prop4 = "hello|people|today";
```

... y se ejecuta el siguiente código...

```js
s.eVar5 = s.rfl(s.prop4,"people","|");
```

... el valor final de s.prop4 seguirá siendo...

```js
s.prop4 = "hello|people|today";
```

... pero el valor final de s.eVar5 será:

```js
s.eVar5 = "hello|today";
```

Tenga en cuenta que el complemento solo devuelve un valor; realmente no “restablece” la variable pasada a través del argumento lv.

### Ejemplo 5

Si...

```js
s.prop4 = "hello|people|today";
```

... y se ejecuta el siguiente código...

```js
s.prop4 = s.rfl(s.prop4,"people");
```

... el valor final de s.prop4 seguirá siendo...

```js
s.prop4 = "hello|people|today";
```

Asegúrese de establecer el argumento d1 en casos en los que el valor del argumento lv contenga un delimitador diferente al valor predeterminado (es decir, una coma).

### Ejemplo 6

Si...

```js
s.events = "event22,event23,event25";
```

... y se ejecuta el siguiente código...

```js
s.events = s.rfl(s.events,"EVenT23");
```

... el valor final de s.events será:

```js
s.events = "event22,event23,event25";
```

Aunque este ejemplo no es práctico, demuestra la necesidad de pasar valores que distinguen entre mayúsculas y minúsculas.

### Ejemplo 7

Si...

```js
s.events = "event22,event23:12345,event25";
```

... y se ejecuta el siguiente código...

```js
s.events = s.rfl(s.events,"event23");
```

... el valor final de s.events será:

```js
s.events = "event22,event25";
```

### Ejemplo 8

Si...

```js
s.events = "event22,event23:12345,event25";
```

... y se ejecuta el siguiente código...

```js
s.events = s.rfl(s.events,"event23:12345");
```

... el valor final de s.events será:

```js
s.events = "event22,event23:12345,event25";
```

Cuando necesite eliminar un evento que utilice una sintaxis de serialización o numérica/monetaria, debe especificar solo el evento en sí (es decir, sin los valores de serialización/numéricos/monetarios) en la llamada s.rfl.

### Ejemplo 9

Si...

```js
s.events = "event22,event23,event23,event23,event24,event25";
```

... y se ejecuta el siguiente código...

```js
s.events = s.rfl(s.events,"event23");
```

... el valor final de s.events será:

```js
s.events = "event22,event24,event25");
```

### Ejemplo 10

Si...

```js
s.events = "event22,event23,event23,event23,event24,event25";
```

... y se ejecuta el siguiente código...

```js
s.events = s.rfl(s.events,"event23", "", "",true);
```

... el valor final de s.events será:

```js
s.events = "event22,event23,event24,event25");
```

### Ejemplo 11

Si...

```js
s.events = "event22,event23,event23,event23,event24,event25";
```

... y se ejecuta el siguiente código...

```js
s.events = s.rfl(s.events,"event23", "", "|",true);
```

... el valor final de s.events será:

```js
s.events = "event22|event23|event24|event25");
```

### Ejemplo 12

Si...

```js
s.events = "event22,event23,event24,event25";
```

... y se ejecuta el siguiente código...

```js
s.events = s.rfl(s.events,"event23,event24");
```

... el valor final de s.events será:

```js
s.events = "event22,event23,event24,event25";
```

No se admite la configuración de varios valores en el argumento vr. La lógica rfl del ejemplo anterior primero dividiría los valores del argumento lv (es decir, s.events) y luego trataría de hacer coincidir cada valor delimitado con el valor del argumento vr completo (es decir, “event23,event24”).

### Ejemplo 13

Si...

```js
s.events = "event22,event23,event24,event25";
```

... y se ejecuta el siguiente código...

```js
s.events = s.rfl(s.events,"event23");
s.events = s.rfl(s.events,"event24");
```

... el valor final de s.events será:

```js
s.events = "event22,event25");
```

Cada valor que se va a eliminar de la lista debe estar contenido en su propia llamada s.rfl.

### Ejemplo 14

Si...

```js
s.linkTrackVars = "events,eVar1,eVar2,eVar3";
```

... y se ejecuta el siguiente código...

```js
s.linkTrackVars = s.rfl(s.linkTrackVars,"eVar2", ",", ",", false);
```

... el valor final de s.linkTrackVars será:

```js
s.linkTrackVars = "events,eVar1,eVar3";
```

Los tres últimos argumentos (por ejemplo &quot;,&quot;,&quot;,&quot;,false) al final de esta llamada s.rfl no son necesarios, pero tampoco pasa nada porque estén ahí ya que coinciden con la configuración predeterminada.

### Ejemplo 15

Si...

```js
s.events = "event22,event23,event24";
```

... y se ejecuta el siguiente código...

```js
s.rfl(s.events,"event23");
```

... el valor final de s.events seguirá siendo:

```js
s.events = "event22,event23,event24";
```

De nuevo, tenga en cuenta que el complemento solo devuelve un valor; realmente no “restablece” la variable pasada a través del argumento lv.

## Historial de versiones

### 2.1 (19 de marzo de 2021)

* Se ha añadido el número de versión como datos de contexto.

### 2.01 (17 de septiembre de 2019)

* Corrección de errores menores para el valor de delimitador predeterminado.

### 2.0 (16 de abril de 2018)

* Versión puntual (compilada de nuevo, con un tamaño de código más pequeño).
* Se ha eliminado la necesidad del complemento `join`.

### 1.0 (18 de julio de 2016)

* Versión inicial.

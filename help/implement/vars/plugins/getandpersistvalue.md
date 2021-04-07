---
title: getAndPersistValue
description: Almacene un valor que pueda utilizarse posteriormente en cualquier momento.
translation-type: ht
source-git-commit: a2970e05abf0d1f963175db6e3554aa0e3034a70
workflow-type: ht
source-wordcount: '934'
ht-degree: 100%

---


# Complemento de Adobe: getAndPersistValue

>[!IMPORTANT]
>
>Adobe Consulting proporciona este complemento por cortesía para ayudarle a sacar el máximo partido a Adobe Analytics. El Servicio de atención al cliente de Adobe no ofrece asistencia técnica con este complemento, incluida la instalación o solución de problemas. Si necesita ayuda con este complemento, póngase en contacto con el administrador de cuentas de su organización. Ellos podrán organizar una reunión con un consultor para ayudarle.

El complemento `getAndPersistValue` le permite almacenar un valor en una cookie que se puede utilizar más adelante durante una visita. Cumple una función similar a la de [!UICONTROL duración del almacenamiento] en Adobe Experience Platform Launch. Adobe recomienda utilizar este complemento si desea mantener automáticamente una variable de Analytics con el mismo valor en las visitas posteriores después de configurar la variable. Este complemento no es necesario si la función de [!UICONTROL duración del almacenamiento] de Launch es suficiente o si no es necesario establecer y mantener variables con el mismo valor en las visitas posteriores. La persistencia integrada de eVars no requiere el uso de este complemento, ya que Adobe mantiene estas variables en el lado del servidor.

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
   * Tipo de acción: Inicializar getAndPersistValue
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
/* Adobe Consulting Plugin: getAndPersistValue v3.0 (Requires AppMeasurement) */
function getAndPersistValue(vtp,cn,ex){var d=vtp,k=cn,l=ex;if("undefined"!==typeof d&&"-v"===d)return{plugin:"getAndPersistValue",version:"3.0"};var a=function(){if("undefined"!==typeof window.s_c_il)for(var c=0,b;c<window.s_c_il.length;c++)if(b=window.s_c_il[c],b._c&&"s_c"===b._c)return b}();"undefined"!==typeof a&&(a.contextData.getAndPersistValue="3.0");window.cookieWrite=window.cookieWrite||function(c,b,f){if("string"===typeof c){var h=window.location.hostname,a=window.location.hostname.split(".").length-1;if(h&&!/^[0-9.]+$/.test(h)){a=2<a?a:2;var e=h.lastIndexOf(".");if(0<=e){for(;0<=e&&1<a;)e=h.lastIndexOf(".",e-1),a--;e=0<e?h.substring(e):h}}g=e;b="undefined"!==typeof b?""+b:"";if(f||""===b)if(""===b&&(f=-60),"number"===typeof f){var d=new Date;d.setTime(d.getTime()+6E4*f)}else d=f;return c&&(document.cookie=encodeURIComponent(c)+"="+encodeURIComponent(b)+"; path=/;"+(f?" expires="+d.toUTCString()+";":"")+(g?" domain="+g+";":""),"undefined"!==typeof cookieRead)?cookieRead(c)===b:!1}};window.cookieRead=window.cookieRead||function(c){if("string"===typeof c)c=encodeURIComponent(c);else return"";var b=" "+document.cookie,a=b.indexOf(" "+c+"="),d=0>a?a:b.indexOf(";",a);return(c=0>a?"":decodeURIComponent(b.substring(a+2+c.length,0>d?b.length:d)))?c:""};a=new Date;k=k?k:"s_gapv";(l=l?l:0)?a.setTime(a.getTime()+864E5*l):a.setTime(a.getTime()+18E5);"undefined"!==typeof d&&d||(d=cookieRead(k));cookieWrite(k,d,a);return d};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Uso del complemento

El método `getAndPersist` utiliza los siguientes argumentos:

* **`vtp`** (obligatorio): El valor que se va a mantener de página en página.
* **`cn`** (opcional): El nombre de la cookie para almacenar el valor. Si no se establece este argumento, se llamará a la cookie `"s_gapv"`.
* **`ex`** (opcional): Número de días antes de que caduque la cookie. Si este argumento está establecido en `0` o no, la cookie caduca al final de la visita (a los 30 minutos de inactividad).

Si se establece la variable en el argumento `vtp`, el complemento establece la cookie y recupera el valor de la cookie. Si no se establece la variable en el argumento `vtp`, el complemento solo recupera el valor de la cookie.

## Ejemplos

### Ejemplo 1

El siguiente código configura eVar21 igual al valor de “hello”.  El código establece entonces la cookie ev21gapv, que caduca en 28 días, igual al valor de eVar21 (es decir, “hello”).  El código entonces (re)configura eVar21 igual al valor de la cookie ev21gapv.

```js
s.eVar21 = "hello";
s.eVar21 = s.getAndPersistValue(s.eVar21,"ev21gapv",28);
```

### Ejemplo 2

Supongamos que la eVar21 no se ha establecido aún en la página actual pero se ha configurado igual a “hello” en una página anterior en los últimos 28 días.   El siguiente código solo configura eVar21 igual al valor de la cookie ev21gapv (por ejemplo: “hello”).  No restablece la cookie ev21gapv porque no se ha configurado eVar21 en la página actual antes de llamar a la función.

```js
s.eVar21 = s.getAndPersistValue(s.eVar21,"ev21gapv",28);
```

### Ejemplo 3

Supongamos que la eVar21 no se ha establecido aún en la página actual pero se ha configurado igual a “hello” en una página anterior en los últimos 28 días.  El siguiente código establece solamente prop35 igual al valor de la cookie ev21gapv (por ejemplo: “hello”).  No se configura eVar21.

```js
s.prop35 = s.getAndPersistValue(s.eVar21,"ev21gapv",28);
```

### Ejemplo 4

El siguiente código configura eVar21 igual al valor de “howdy”.  A continuación, el código establece (o restablece) la cookie ev21gapv, que caduca en 28 días, igual al valor de eVar21 (es decir, “howdy”).  A continuación, el código establece prop35 igual al valor de la cookie ev21gapv (por ejemplo: “howdy”).

```js
s.eVar21 = "howdy";
s.prop35 = s.getAndPersistValue(s.eVar21,"ev21gapv",28);
```

### Ejemplo 5

Supongamos que s.eVar21 no se ha configurado en ninguna página en los últimos 28 días.  El siguiente código establece s.eVar21 como cero, ya que la cookie ev21gapv habría caducado 28 días después de la última vez que se configuró.

```js
s.eVar21 = s.getAndPersistValue(s.eVar21,"ev21gapv",28);
```

### Ejemplo 6

El siguiente código establece eVar30 en igual que “shopping”.  Luego establece la cookie s_gapv, que caduca al final de la sesión del explorador, igual al valor de s.eVar30 (es decir, “shopping”).  Luego establece s.eVar30 igual al valor de la cookie s_gapv (es decir, la llamada getAndPersistValue devuelve el valor de la cookie s_gapv, que en este caso es “shopping”).

```js
s.eVar30 = "shopping";
s.eVar30 = s.getAndPersistValue(s.eVar30);
```

Si s.eVar30 no se establece en un valor explícito en ninguna página adicional que se vea durante la sesión, pero se establece (en doPlugins) mediante el siguiente código...

```js
s.eVar30 = s.getAndPersistValue(s.eVar30);
```

... s.eVar30 se configura igual a “shopping” (es decir, el valor persistente de la cookie s_gapv).

## Historial de versiones

### 3.0 (19 de marzo de 2021)

* Se ha añadido el número de versión como datos de contexto.

### 2.0 (16 de abril de 2018)

* Versión puntual (tamaño de código más pequeño)
* Pasar 0 al argumento `ex` ahora fuerza la caducidad después de 30 minutos de inactividad en lugar de al final de la sesión en el explorador.

### 1.0 (18 de enero de 2016)

* Versión inicial.

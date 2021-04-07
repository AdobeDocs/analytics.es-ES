---
title: getNewRepeat
description: Rastree la actividad de visitantes nuevos frente a los que repiten.
translation-type: ht
source-git-commit: 9d44226202cd690d069f9c0c85c8af2ef8fd0106
workflow-type: ht
source-wordcount: '826'
ht-degree: 100%

---


# Complemento de Adobe: getNewRepeat

>[!IMPORTANT]
>
>Adobe Consulting proporciona este complemento por cortesía para ayudarle a sacar el máximo partido a Adobe Analytics. El Servicio de atención al cliente de Adobe no ofrece asistencia técnica con este complemento, incluida la instalación o solución de problemas. Si necesita ayuda con este complemento, póngase en contacto con el administrador de cuentas de su organización. Ellos podrán organizar una reunión con un consultor para ayudarle.

El complemento `getNewRepeat` le permite determinar si un visitante del sitio accede por primera vez o si repite dentro de un número determinado de días. Adobe recomienda utilizar este complemento si desea identificar a los visitantes como “nuevos” con un número personalizado de días. Este complemento no es necesario si las dimensiones de visitante Nuevo/Repetición de Analysis Workspace satisfacen las necesidades de su organización.

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
   * Tipo de acción: Inicializar getNewRepeat
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
/* Adobe Consulting Plugin: getNewRepeat v3.0 (Requires AppMeasurement) */
function getNewRepeat(d){var a=d;if("-v"===a)return{plugin:"getNewRepeat",version:"3.0"};var d=function(){if("undefined"!==typeof window.s_c_il)for(var c=0,b;c<window.s_c_il.length;c++)if(b=window.s_c_il[c],b._c&&"s_c"===b._c)return b}();"undefined"!==typeof d&&(d.contextData.getNewRepeat="3.0");window.cookieWrite=window.cookieWrite||function(c,b,f){if("string"===typeof c){var h=window.location.hostname,a=window.location.hostname.split(".").length-1;if(h&&!/^[0-9.]+$/.test(h)){a=2<a?a:2;var e=h.lastIndexOf(".");if(0<=e){for(;0<=e&&1<a;)e=h.lastIndexOf(".",e-1),a--;e=0<e?h.substring(e):h}}g=e;b="undefined"!==typeof b?""+b:"";if(f||""===b)if(""===b&&(f=-60),"number"===typeof f){var d=new Date;d.setTime(d.getTime()+6E4*f)}else d=f;return c&&(document.cookie=encodeURIComponent(c)+"="+encodeURIComponent(b)+"; path=/;"+(f?" expires="+d.toUTCString()+";":"")+(g?" domain="+g+";":""),"undefined"!==typeof cookieRead)?cookieRead(c)===b:!1}};window.cookieRead=window.cookieRead||function(c){if("string"===typeof c)c=encodeURIComponent(c);else return"";var b=" "+document.cookie,a=b.indexOf(" "+c+"="),d=0>a?a:b.indexOf(";",a);return(c=0>a?"":decodeURIComponent(b.substring(a+2+c.length,0>d?b.length:d)))?c:""};a=a?a:30;d="s_nr"+a;var k=new Date,m=cookieRead(d),n=m.split("-"),l=k.getTime();k.setTime(l+864E5*a);if(""===m||18E5>l-n[0]&&"New"===n[1])return cookieWrite(d,l+"-New",k),"New";cookieWrite(d,l+"-Repeat",k);return"Repeat"};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Uso del complemento

El método `getNewRepeat` utiliza los siguientes argumentos:

* **`d`** (entero, opcional): el número mínimo de días entre visitas que restablece a los visitantes de nuevo como `"New"`. Si no se establece este argumento, el valor predeterminado es de 30 días.

Este método devuelve el valor de `"New"` si la cookie configurada por el complemento no existe o ha caducado. Devuelve el valor de `"Repeat"` si la cookie configurada por el complemento existe y el tiempo desde la visita actual y el tiempo establecido en la cookie supera los 30 minutos. Este método devuelve el mismo valor para una visita completa.

Este complemento utiliza una cookie denominada `"s_nr[LENGTH]"` donde `[LENGTH]` es igual al argumento `d`. La cookie contiene una marca de tiempo Unix que representa la hora actual y el estado actual del visitante (`"New"` o `"Repeat"`).

## Llamadas de ejemplo

### Ejemplo 1

El siguiente código establecerá s.eVar1 en el valor de “Nuevo” para los nuevos visitantes y seguirá estableciendo s.eVar1 en el valor de “Nuevo” (con cada nueva llamada) durante el resto de la visita del visitante al sitio.

```js
s.eVar1=s.getNewRepeat();
```

### Ejemplo 2

Si el visitante regresa al sitio en cualquier momento pasados 31 minutos hasta 30 días desde la última vez que se llamó a s.getNewRepeat(), el siguiente código establecerá s.eVar1 en al valor de “Repetición” y seguirá configurando s.eVar1 igual al valor de “Repetición” (con cada nueva llamada) durante el resto de la visita del visitante al sitio.

```js
s.eVar1=s.getNewRepeat();
```

### Ejemplo 3

Si el visitante no ha estado en el sitio durante al menos 30 días desde la última vez que se llamó a s.getNewRepeat(), el siguiente código establecerá s.eVar1 en el valor de “Nuevo” y seguirá configurando s.eVar1 en el valor de “Nuevo” (con cada nueva llamada) durante el resto de la visita del visitante al sitio.

```js
s.eVar1=s.getNewRepeat();
```

### Ejemplo 4

Si el visitante regresa al sitio en cualquier momento pasados 31 minutos hasta 365 días (es decir un año) desde la última vez que se llamó a s.getNewRepeat(), el siguiente código establecerá s.eVar1 en al valor de “Repetición” y seguirá configurando s.eVar1 igual al valor de “Repetición” (con cada nueva llamada) durante el resto de la visita del visitante al sitio.

```js
s.eVar1=s.getNewRepeat(365);
```

### Ejemplo 5

Si el visitante no ha estado en el sitio durante al menos 365 días (es decir, un año) desde la última vez que se llamó a s.getNewRepeat(), el siguiente código establecerá s.eVar1 en el valor de “Nuevo” y seguirá configurando s.eVar1 en el valor de “Nuevo” (con cada nueva llamada) durante el resto de la visita del visitante al sitio.

```js
s.eVar1=s.getNewRepeat(365);
```

## Historial de versiones

### 3.0 (19 de marzo de 2021)

* Se ha añadido el número de versión como datos de contexto.

### 2.1 (30 de septiembre de 2019)

* Reorganización de la lógica de JavaScript para reducir el tamaño de los complementos

### 2.0 (16 de abril de 2018)

* Recompilado con un tamaño de código más pequeño
* Se ha eliminado la posibilidad de asignar un nombre a la cookie para almacenar la información de la visita. El complemento ahora asigna un nombre dinámico a la cookie en función del valor pasado al argumento `d`.

---
title: getNewRepeat
description: Rastree la actividad de los visitantes nuevos frente a los que repiten.
translation-type: tm+mt
source-git-commit: 365944140bb1dfc9bc8669ae530c631e8ff1629b

---


# Complemento de Adobe: getNewRepeat

> [!IMPORTANT] Este complemento lo proporciona Adobe Consulting por cortesía para ayudarle a obtener más valor de Adobe Analytics. El Servicio de atención al cliente de Adobe no ofrece asistencia técnica con este complemento, incluida la instalación o solución de problemas. Si necesita ayuda con este complemento, póngase en contacto con el administrador de cuentas de su organización. Pueden organizar una reunión con un consultor para obtener ayuda.

El `getNewRepeat` complemento le permite determinar si un visitante del sitio es un visitante nuevo o un visitante de retorno en un número deseado de días. Adobe recomienda utilizar este complemento si desea identificar a los visitantes como &quot;nuevos&quot; con un número personalizado de días. Este complemento no es necesario si las dimensiones de visitante Nuevo/Repetir en Analysis Workspace satisfacen las necesidades de su organización.

## Instalación del complemento con la extensión Adobe Experience Platform Launch

Adobe ofrece una extensión que le permite utilizar los complementos más utilizados.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
1. Haga clic en la propiedad que desee.
1. Vaya a la ficha [!UICONTROL Extensiones] y, a continuación, haga clic en el botón [!UICONTROL Catálogo]
1. Instalación y publicación de la extensión [!UICONTROL Common Analytics Plugins]
1. Para cualquier regla de inicio en la que desee utilizar el complemento, agregue una acción con la siguiente configuración:
   * Extensión: Complementos comunes de Analytics
   * Tipo de acción: Inicializar addProductEvar
1. Guardar y publicar los cambios en la regla

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
/* Adobe Consulting Plugin: getNewRepeat v2.1 */
s.getNewRepeat=function(d){d=d?d:30;var s=this,p="s_nr"+d,b=new Date,e=s.c_r(p),f=e.split("-"),c=b.getTime();b.setTime(c+864E5*d); if(""===e||18E4>c-f[0]&&"New"===f[1])return s.c_w(p,c+"-New",b),"New";s.c_w(p,c+"-Repeat",b);return"Repeat"};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Utilizar el complemento

El `getNewRepeat` método utiliza los siguientes argumentos:

* **`d`**(entero, opcional): El número mínimo de días necesario entre visitas que restablece a los visitantes de nuevo`"New"`. Si no se establece este argumento, el valor predeterminado es de 30 días.

Este método devuelve el valor de `"New"` si la cookie configurada por el complemento no existe o ha caducado. Devuelve el valor de `"Repeat"` si la cookie configurada por el complemento existe y la cantidad de tiempo desde la visita actual y el tiempo establecido en la cookie es mayor que 30 minutos. Este método devuelve el mismo valor para una visita completa.

Este complemento utiliza una cookie denominada `"s_nr[LENGTH]"` donde `[LENGTH]` es igual al `d` argumento. La cookie contiene una marca de tiempo Unix que representa la hora actual y el estado actual del visitante (`"New"` o `"Repeat"`).

## Llamadas de ejemplo

### Ejemplo n.º 1

El siguiente código establecerá s.eVar1 en el valor de &quot;Nuevo&quot; para los nuevos visitantes y seguirá configurando s.eVar1 en el valor de &quot;Nuevo&quot; (con cada nueva llamada) durante el resto de la visita del visitante al sitio.

```js
s.eVar1=s.getNewRepeat();
```

### Ejemplo n.º 2

Si el visitante regresa al sitio en cualquier momento desde 31 minutos hasta 30 días desde la última vez que se llamó a s.getNewRepeat(), el siguiente código establecerá s.eVar1 igual al valor de &quot;Repetir&quot; y seguirá configurando s.eVar1 igual al valor de &quot;Repetir&quot; (con cada nueva llamada) durante el resto de la visita del visitante al sitio.

```js
s.eVar1=s.getNewRepeat();
```

### Ejemplo n.º 3

Si el visitante no ha estado en el sitio durante al menos 30 días desde la última vez que se llamó a s.getNewRepeat(), el siguiente código establecerá s.eVar1 en el valor de &quot;New&quot; y seguirá configurando s.eVar1 en el valor de &quot;New&quot; (con cada nueva llamada) durante el resto de la visita del visitante al sitio.

```js
s.eVar1=s.getNewRepeat();
```

### Ejemplo n.º 4

Si el visitante regresa al sitio en cualquier momento, de 31 minutos a 365 días (es decir, 1 año) desde la última vez que se llamó a s.getNewRepeat(), el siguiente código establecerá s.eVar1 igual al valor de &quot;Repetir&quot; y seguirá configurando s.eVar1 igual al valor de &quot;Repetir&quot; (con cada nueva llamada) durante el resto del visitante Visita al sitio.

```js
s.eVar1=s.getNewRepeat(365);
```

### Ejemplo n.º 5

Si el visitante no ha estado en el sitio durante al menos 365 días (es decir, un año) desde la última vez que se llamó a s.getNewRepeat(), el siguiente código establecerá s.eVar1 igual al valor de &quot;New&quot; y seguirá configurando s.eVar1 igual al valor de &quot;New&quot; (con cada nueva llamada) durante el resto de la visita del visitante al sitio.

```js
s.eVar1=s.getNewRepeat(365);
```

## Historial de versiones

### 2.1 (30 de septiembre de 2019)

* Reorganización de la lógica de JavaScript para reducir el tamaño de los complementos

### 2.0 (16 de abril de 2018)

* Recompilado con un tamaño de código más pequeño
* Se ha eliminado la posibilidad de asignar un nombre a la cookie para almacenar la información de la visita. El complemento ahora asigna un nombre dinámico a la cookie en función del valor pasado al `d` argumento.

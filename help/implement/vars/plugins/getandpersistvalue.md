---
title: getAndPersistValue
description: Almacene un valor que pueda recuperarse posteriormente en cualquier momento.
translation-type: tm+mt
source-git-commit: 180ad544541f25d02b3a257559bc045abed7387b

---


# Complemento de Adobe: getAndPersistValue

> [!IMPORTANT] Este complemento lo proporciona Adobe Consulting por cortesía para ayudarle a obtener más valor de Adobe Analytics. El Servicio de atención al cliente de Adobe no ofrece asistencia técnica con este complemento, incluida la instalación o solución de problemas. Si necesita ayuda con este complemento, póngase en contacto con el administrador de cuentas de su organización. Pueden organizar una reunión con un consultor para obtener ayuda.

El `getAndPersistValue` complemento le permite almacenar un valor en una cookie que se puede recuperar más adelante durante una visita. Cumple una función similar a la función de duración [!UICONTROL del] almacenamiento en Adobe Experience Platform Launch. Adobe recomienda utilizar este complemento si desea mantener automáticamente una variable de Analytics con el mismo valor en las visitas posteriores después de configurar la variable. Este complemento no es necesario si la función de duración [!UICONTROL del] almacenamiento de Launch es suficiente o si no es necesario establecer y mantener variables con el mismo valor en las visitas posteriores. La persistencia integrada de eVars no requiere el uso de este complemento, ya que Adobe mantiene estas variables en el servidor.

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
   * Tipo de acción: Inicializar getAndPersistValue
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
/* Adobe Consulting Plugin: getAndPersistValue v2.0 */
s.getAndPersistValue=function(vtp,cn,ex){var b=new Date;cn=cn?cn:"s_gapv";(ex=ex?ex:0)?b.setTime(b.getTime()+864E5*ex): b.setTime(b.getTime()+18E5);vtp||(vtp=this.c_r(cn));this.c_w(cn,vtp,b);return vtp};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Utilizar el complemento

El `getAndPersist` método utiliza los siguientes argumentos:

* **`vtp`**(obligatorio): El valor que se va a mantener de página en página
* **`cn`**(opcional): El nombre de la cookie para almacenar el valor. Si no se establece este argumento, se llamará a la cookie`"s_gapv"`
* **`ex`**(opcional): Número de días antes de que caduque la cookie. Si este argumento está establecido`0`o no, la cookie caduca al final de la visita (30 minutos de inactividad).

Si se establece la variable en el `vtp` argumento, el complemento establece la cookie y devuelve el valor de la cookie. Si no se establece la variable en el `vtp` argumento, el complemento solo devuelve el valor de la cookie.

## Ejemplos

### Ejemplo n.º 1

El siguiente código configurará eVar21 igual al valor de &quot;hello&quot;.  El código establecerá entonces la cookie ev21gapv, que caducará en 28 días, igual al valor de eVar21 (es decir, &quot;hola&quot;).  El código entonces (re)configurará eVar21 igual al valor de la cookie ev21gapv.

```js
s.eVar21 = "hello";
s.eVar21 = s.getAndPersistValue(s.eVar21,"ev21gapv",28);
```

### Ejemplo n.º 2

Supongamos que la eVar21 no se ha establecido aún en la página actual pero se ha configurado igual a &quot;hola&quot; en una página anterior en los últimos 28 días.   El siguiente código sólo configurará eVar21 igual al valor de la cookie ev21gapv (por ejemplo: &quot;hola&quot;).  No restablece la cookie ev21gapv porque no se configuró eVar21 en la página actual antes de llamar a la función.

```js
s.eVar21 = s.getAndPersistValue(s.eVar21,"ev21gapv",28);
```

### Ejemplo n.º 3

Supongamos que la eVar21 no se ha establecido aún en la página actual pero se ha configurado igual a &quot;hola&quot; en una página anterior en los últimos 28 días.  El siguiente código establecerá solamente prop35 igual al valor de la cookie ev21gapv (por ejemplo: &quot;hola&quot;).  No se configurará eVar21.

```js
s.prop35 = s.getAndPersistValue(s.eVar21,"ev21gapv",28);
```

### Ejemplo n.º 4

El siguiente código establecerá eVar21 igual al valor de &quot;howdy&quot;.  A continuación, el código establecerá (o restablecerá) la cookie ev21gapv, que caducará en 28 días, igual al valor de eVar21 (es decir, &quot;caramba&quot;).  A continuación, el código establecerá prop35 igual al valor de la cookie ev21gapv (por ejemplo: &quot;caramba&quot;).

```js
s.eVar21 = "howdy";
s.prop35 = s.getAndPersistValue(s.eVar21,"ev21gapv",28);
```

### Ejemplo n.º 5

Supongamos que s.eVar21 no se ha configurado en ninguna página en los últimos 28 días.  El siguiente código establecerá s.eVar21 como cero, ya que la cookie ev21gapv habría caducado 28 días después de la última vez que se configuró.

```js
s.eVar21 = s.getAndPersistValue(s.eVar21,"ev21gapv",28);
```

### Ejemplo n.º 6

El siguiente código establecerá eVar30 en igual que &quot;compra&quot;.  Luego establecerá la cookie s_gapv, que caducará al final de la sesión del explorador, igual al valor de s.eVar30 (es decir, &quot;compras&quot;).  Luego establecerá s.eVar30 igual al valor de la cookie s_gapv (es decir, la llamada getAndPersistValue devuelve el valor de la cookie s_gapv, que en este caso es &quot;compra&quot;).

```js
s.eVar30 = "shopping";
s.eVar30 = s.getAndPersistValue(s.eVar30);
```

Si s.eVar30 no se establece en un valor explícito en ninguna página adicional que se vea durante la sesión pero se establece (en doPlugins) mediante el siguiente código...

```js
s.eVar30 = s.getAndPersistValue(s.eVar30);
```

...s.eVar30 se configurará igual a &quot;shopping&quot; (es decir, el valor persistente de la cookie s_gapv)

## Historial de versiones

### 2.0 (16 de abril de 2018)

* Versión puntual (tamaño de código más pequeño)
* Pasar 0 al `ex` argumento ahora fuerza la caducidad después de 30 minutos de inactividad en lugar de la caducidad al final de la sesión del explorador.

### 1.0 (18 de enero de 2016)

* Versión inicial.

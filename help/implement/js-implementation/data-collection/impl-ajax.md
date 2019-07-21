---
description: Implementar con AJAX es exactamente igual que implementar código en una página HTML estándar.
keywords: Implementación de Analytics
seo-description: Implementar con AJAX es exactamente igual que implementar código en una página HTML estándar.
seo-title: Implementación con AJAX
solution: Analytics
title: Implementación con AJAX
topic: Desarrollador e implementación
uuid: 9 e 3477 ef -7 dea -4 c 76-ab 61-36 a 188222 be 7 7
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Implementación con AJAX

Implementar con AJAX es exactamente igual que implementar código en una página HTML estándar.

La empresa tiene preguntas que necesitan respuesta, se evalúan las necesidades y se asignan las variables. Después, se aplica y se implementa el diseño. Estos conceptos le resultarán familiares si ya ha pasado por las fases iniciales de la implementación.

## Diseño de la solución {#section_78F1C7AFBB4E4175A6FE04A962C9C9D0}

La diferencia respecto a incluir [!UICONTROL AJAX] en la combinación es que hay que comprender primero el nivel de detalle que debe recopilarse. El potencial de cambio del contenido de la página (macronivel) o del seguimiento de atributos de la aplicación (micronivel) determina qué variables deben configurarse y qué método de envío de datos a Adobe funciona mejor.

## Implementación del código {#section_F3FC6F07A3E148D89A4C9ABC442920C3}

Hay dos funciones en el código de JavaScript que permite enviar datos. Hay algunas directrices diferentes que deben seguirse para saber qué método se debe utilizar para enviar datos.
Si ya se ha realizado una solicitud de imagen en la página, debe borrar los valores de las variables establecidas con anterioridad. Use the `clearVars()` funtion in [!DNL AppMeasurement] for JavaScript, or write a simple JavaScript function to clear the variables if you are using H code. Set the values appropriate for the changed content, namely the *`pageName`* variable. After the variables are set call the *`t()`* function.

>[!NOTE]
>
>Before you call `s.t()`, you must clear any values on the s object that you do not want to persist. if you are using [!DNL AppMeasurement] for JavaScript, you can call `s.clearVars()`. Si usa código H, establezca las variables para una cadena vacía escribiendo una rutina simple.

```js
s.clearVars(); 
s.pageName="New Page" 
s.prop1="some value" 
void(s.t());
```

The following example shows a tracking call in the `done` callback of the JQuery `.ajax` function:

```
$.ajax({ 
  url: "test.html", 
  dataType: "html" 
}) 
  .done(function( response ) { 
    $( "#content" ).html( response ); 
  s.clearVars(); 
  s.pageName = $( "h1:first" ).text(); 
  s.t(); 
  }); 
```

Si anteriormente se realizó una solicitud de imagen en la misma página, borre los valores de las variables previamente configuradas. Para ello:

* Escriba una función de JavaScript simple para borrar las variables de Adobe.
* Configure las variables  *`linkTrackVars`* y *`linkTrackEvents`* variables si aún no lo ha hecho en [!DNL s_code.js] el archivo.

* Set the values appropriate for the changed content, namely the *`pageName`* variable.
* After the variables are set, call the *`tl()`* function.

```js
//set linkTrackVars and linkTrackEvents> (if applicable) 
//set new variables 
s.tl(this,'o','Link Name');
```

```js
s.linkTrackVars="prop1,eVar1,events"; s.linkTrackEvents="event1"; 
s.prop1="some value"; s.eVar1="another value"; s.events="event1"; 
s.tl(this,'o','My Link Name');
```


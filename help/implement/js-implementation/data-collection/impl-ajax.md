---
description: Implementar con AJAX es exactamente igual que implementar código en una página HTML estándar.
keywords: Analytics Implementation
title: Implementación con AJAX
topic: Developer and implementation
uuid: 9e3477ef-7dea-4c76-ab61-36a188222be7
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Implementación con AJAX

Implementar con AJAX es exactamente igual que implementar código en una página HTML estándar.

La empresa tiene preguntas que necesitan respuesta, se evalúan las necesidades y se asignan las variables. Después, se aplica y se implementa el diseño. Estos conceptos le resultarán familiares si ya ha pasado por las fases iniciales de la implementación.

## Diseño de la solución {#section_78F1C7AFBB4E4175A6FE04A962C9C9D0}

La diferencia respecto a incluir [!UICONTROL AJAX] en la combinación es que hay que comprender primero el nivel de detalle que debe recopilarse. El potencial de cambio del contenido de la página (macronivel) o del seguimiento de atributos de la aplicación (micronivel) determina qué variables deben configurarse y qué método de envío de datos a Adobe funciona mejor.

## Implementación del código {#section_F3FC6F07A3E148D89A4C9ABC442920C3}

Hay dos funciones en el código de JavaScript que permite enviar datos. Hay algunas directrices diferentes que deben seguirse para saber qué método se debe utilizar para enviar datos.
Si ya se ha realizado una solicitud de imagen en la página, debe borrar los valores de las variables establecidas con anterioridad. Use la función `clearVars()` en [!DNL AppMeasurement] para JavaScript o escriba una función JavaScript simple para borrar las variables si usa código H. Configure los valores apropiados para el contenido cambiado, concretamente la variable *`pageName`*. Una vez configuradas las variables, llame a la función *`t()`*.

> [!NOTE] Antes de llamar a `s.t()`, borre los valores del objeto s que no deban conservarse. Si usa [!DNL AppMeasurement] para JavaScript, puede llamar a `s.clearVars()`. Si usa código H, establezca las variables para una cadena vacía escribiendo una rutina simple.

```js
s.clearVars(); 
s.pageName="New Page" 
s.prop1="some value" 
void(s.t());
```

En el ejemplo siguiente se muestra una llamada de seguimiento de la llamada de retorno `done` de la función `.ajax` de JQuery:

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
* Configure las variables  *`linkTrackVars`* y *`linkTrackEvents`* en el archivo [!DNL s_code.js], si aún no lo ha hecho.

* Configure los valores apropiados para el contenido cambiado, concretamente la variable *`pageName`*.
* Una vez configuradas las variables, llame a la función *`tl()`*.

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


---
description: Captura el valor de una variable de Analytics en la siguiente vista de página. Por ejemplo, puede usar el complemento para capturar el valor s.pageName de la vista de página anterior a una variable de tráfico personalizado. También dispone de una opción para capturar un valor anterior solamente cuando los eventos de éxito designados están configurados.
keywords: Implementación de Analytics
seo-description: Captura el valor de una variable de Analytics en la siguiente vista de página. Por ejemplo, puede usar el complemento para capturar el valor s.pageName de la vista de página anterior a una variable de tráfico personalizado. También dispone de una opción para capturar un valor anterior solamente cuando los eventos de éxito designados están configurados.
seo-title: getPreviousValue
solution: Analytics
subtopic: Complementos
title: getPreviousValue
topic: Desarrollador e implementación
uuid: 20 da 7 b 4 a -9820-4690-a 1 cc-d 10 b 6 dd 627 a 7
translation-type: tm+mt
source-git-commit: ee0cb9b64a3915786f8f77d80b55004daa68cab6

---


# getPreviousValue

Captura el valor de una variable de Analytics en la siguiente vista de página. Por ejemplo, puede usar el complemento para capturar el valor s.pageName de la vista de página anterior a una variable de tráfico personalizado. También dispone de una opción para capturar un valor anterior solamente cuando los eventos de éxito designados están configurados.

>[!NOTE]
>
>Las instrucciones siguientes requieren modificar el código de recopilación de datos en el sitio. Esto puede afectar a la recopilación de datos en el sitio y solamente debe hacerlo un desarrollador con experiencia en el uso y la implementación de [!DNL Analytics].

## Implementación y código de complemento {#section_92E94A96A4764113B5588F1B83E3DE2C}

**SECCIÓN CONFIG**: esta sección no requiere ninguna modificación. 

**Configuración de complemento**

Inserte el código siguiente en la función *`s_doPlugins()`* , que se encuentra en el área del *`s_code.js`* archivo rotulada Configuración *de complemento*. Seleccione una variable de tráfico personalizado (término de búsqueda interna s.prop) o una variable de conversión personalizada (s.eVar) que se utilizarán en la captura de datos de valores persistentes. Debe ser una variable que se haya activado mediante Admin Console pero que en la actualidad no se esté utilizando para ningún otro fin. Puede utilizar el ejemplo siguiente y actualizarlo según sus necesidades.

`s.prop1=s.getPreviousValue(s.pageName,'gpv_pn','event1');`

*`s.getPreviousValue`* tiene tres argumentos:

1. The variable to be captured from the previous page ( *`s.pageName`* above).
1. The cookie name for use in storing the value for retrieval ( *`gpv_pn`* above).
1. The events that must be set on the page view in order to trigger the retrieval of the previous value ( *`event1`* above). Si se deja en blanco o se omite, el complemento captura el valor anterior en todas las vistas de página.

**SECCIÓN DE COMPLEMENTOS**: Agregue el siguiente código al área del [!DNL s_code.js] archivo rotulada SECCIÓN DE COMPLEMENTOS. No realice ningún cambio en esta parte del código de complemento.

```js
/* 
 * Plugin: getPreviousValue_v1.0 - return previous value of designated 
 * variable (requires split utility) 
 */ 
s.getPreviousValue=new Function("v","c","el","" 
+"var s=this,t=new Date,i,j,r='';t.setTime(t.getTime()+1800000);if(el" 
+"){if(s.events){i=s.split(el,',');j=s.split(s.events,',');for(x in i" 
+"){for(y in j){if(i[x]==j[y]){if(s.c_r(c)) r=s.c_r(c);v?s.c_w(c,v,t)" 
+":s.c_w(c,'no value',t);return r}}}}}else{if(s.c_r(c)) r=s.c_r(c);v?" 
+"s.c_w(c,v,t):s.c_w(c,'no value',t);return r}"); 
/* 
 * Utility Function: split v1.5 - split a string (JS 1.0 compatible) 
 */ 
s.split=new Function("l","d","" 
+"var i,x=0,a=new Array;while(l){i=l.indexOf(d);i=i>-1?i:l.length;a[x" 
+"++]=l.substring(0,i);l=l.substring(i+d.length);}return a"); 
```

**Notas**

* Antes de su implementación en un entorno de desarrollo, realice pruebas exhaustivas de las instalaciones de complementos para asegurarse de que la recopilación de datos se comporta según lo esperado.
* Si no hay ningún valor presente para la variable seleccionada en una página dada, en la cookie se establecerá el texto *no value*.
* Ahora, cada cookie tiene una caducidad fija de 30 minutos y se actualiza con cada carga de página. El complemento funciona durante la duración de una visita.
* Dado que la función debe llamarse como parte de la sección de código de complementos, el código se ejecuta cada vez que se llama a *`s.t()`* o se *`s.tl()`* le llama.

* La variable elegida debe rellenarse con un valor con anterioridad a la llamada a *`s.getPreviousValue`*. Because the *`s_doPlugins()`* function is executed after the variables on the page are populated, this issue rarely occurs. It should only be a matter of concern if the variable used with this plug-in is populated within the *`s_doPlugins()`* function and after the call to *`s.getPreviousValue`*.


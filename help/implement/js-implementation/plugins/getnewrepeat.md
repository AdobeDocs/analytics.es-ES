---
description: Determina si un visitante es un visitante nuevo o uno habitual y captura esta información en una variable de Analytics.
keywords: Implementación de Analytics
seo-description: Determina si un visitante es un visitante nuevo o uno habitual y captura esta información en una variable de Analytics.
seo-title: getNewRepeat
solution: Analytics
subtopic: Complementos
title: getNewRepeat
topic: Desarrollador e implementación
uuid: e 3 e 9 f 362-e 0 b 1-4 a 2 b-bb 5 b -98 eddaa 0 a 7 f 4
translation-type: tm+mt
source-git-commit: ee0cb9b64a3915786f8f77d80b55004daa68cab6

---


# getNewRepeat

Determina si un visitante es un visitante nuevo o uno habitual y captura esta información en una variable de Analytics.

Use este complemento para responder a las preguntas siguientes:

* ¿Qué porcentaje de mis visitantes son nuevos (en contraposición a los visitantes que repiten)?
* ¿Los visitantes de retorno generan una mayor conversión per cápita que los visitantes nuevos? ¿Cuál es esta tasa?
* ¿Mis campañas de marketing causan persistencia entre visitas? Por ejemplo, ¿los usuarios que hacen clic en mis campañas regresan posteriormente?

>[!NOTE]
>
>Las instrucciones siguientes requieren modificar el código de recopilación de datos en el sitio. Esto puede afectar a la recopilación de datos en el sitio y solamente debe hacerlo un desarrollador con experiencia en el uso y la implementación de [!DNL Analytics].

## Implementación y código de complemento {#section_92E94A96A4764113B5588F1B83E3DE2C}

**SECCIÓN CONFIG**: esta sección no requiere ninguna modificación. 

**Configuración de complemento**

Inserte el código siguiente en la función *`s_doPlugins()`* , que se encuentra en el área del *`s_code.js`* archivo rotulada Configuración *de complemento*. Seleccione una variable de tráfico personalizado (término de búsqueda interna s.prop) o una variable de conversión personalizada (s.eVar) que se utilizarán en la captura de datos de valores persistentes. Debe ser una variable que se haya activado mediante Admin Console pero que en la actualidad no se esté utilizando para ningún otro fin. Puede utilizar el ejemplo siguiente y actualizarlo según sus necesidades.

`s.prop1=s.getNewRepeat(30,'s_getNewRepeat');`

*`s.getNewRepeat`* tiene dos argumentos opcionales:

1. El primer argumento opcional es la cantidad de días que debe durar la cookie. Si se omite este argumento, el valor predeterminado es 30 días.
1. El segundo argumento opcional es el nombre de la cookie. Si se omite este argumento, se utiliza un valor predeterminado.

**SECCIÓN DE COMPLEMENTOS**: Agregue el siguiente código al área del [!DNL s_code.js] archivo rotulada SECCIÓN DE COMPLEMENTOS. No realice ningún cambio en esta parte del código de complemento.

```js
/* 
 * Plugin: getNewRepeat 1.2 - Returns whether user is new or repeat 
 */ 
s.getNewRepeat=new Function("d","cn","" 
+"var s=this,e=new Date(),cval,sval,ct=e.getTime();d=d?d:30;cn=cn?cn:" 
+"'s_nr';e.setTime(ct+d*24*60*60*1000);cval=s.c_r(cn);if(cval.length=" 
+"=0){s.c_w(cn,ct+'-New',e);return'New';}sval=s.split(cval,'-');if(ct" 
+"-sval[0]<30*60*1000&&sval[1]=='New'){s.c_w(cn,ct+'-New',e);return'N" 
+"ew';}else{s.c_w(cn,ct+'-Repeat',e);return'Repeat';}"); 
/* 
* Utility Function: split v1.5 (JS 1.0 compatible) 
*/ 
s.split=new Function("l","d","" 
+"var i,x=0,a=new Array;while(l){i=l.indexOf(d);i=i>-1?i:l.length;a[x" 
+"++]=l.substring(0,i);l=l.substring(i+d.length);}return a");
```

Antes de su implementación en un entorno de desarrollo, realice pruebas exhaustivas de las instalaciones de complementos para asegurarse de que la recopilación de datos se comporta según lo esperado.

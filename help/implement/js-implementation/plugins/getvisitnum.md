---
description: El complemento getVisitNum determina cuántas visitas al sitio ha realizado un usuario y captura este número en una variable de Analytics.
keywords: Implementación de Analytics
seo-description: El complemento getVisitNum determina cuántas visitas al sitio ha realizado un usuario y captura este número en una variable de Analytics.
seo-title: getVisitNum
solution: Analytics
subtopic: Complementos
title: getVisitNum
topic: Desarrollador e implementación
uuid: 27 d 57 f 92-fffb -44 d 0-b 9 ca -9 da 93323 f 64 c
translation-type: tm+mt
source-git-commit: ee0cb9b64a3915786f8f77d80b55004daa68cab6

---


# getVisitNum

El complemento getVisitNum determina cuántas visitas al sitio ha realizado un usuario y captura este número en una variable de Analytics.

## Implementación y código de complemento {#section_92E94A96A4764113B5588F1B83E3DE2C}

**SECCIÓN CONFIG**: esta sección no requiere ninguna modificación. 

**Configuración de complemento**

Inserte el código siguiente en la función *`s_doPlugins()`* , que se encuentra en el área del *`s_code.js`* archivo rotulada Configuración *de complemento*. Seleccione una variable de tráfico personalizado (término de búsqueda interna s.prop) o una variable de conversión personalizada (s.eVar) que se utilizarán en la captura de datos del número de visitas. Debe ser una variable que se haya activado mediante Admin Console pero que en la actualidad no se esté utilizando para ningún otro fin. Puede utilizar el ejemplo siguiente y actualizarlo según sus necesidades.

`s.prop1=s.getVisitNum();`

>[!NOTE]
>
>Las instrucciones siguientes requieren modificar el código de recopilación de datos en el sitio. Esto puede afectar a la recopilación de datos en el sitio y solamente debe hacerlo un desarrollador con experiencia en el uso y la implementación de [!DNL Analytics].

**SECCIÓN DE COMPLEMENTOS**: Agregue el siguiente código al área del [!DNL s_code.js] archivo rotulada SECCIÓN DE COMPLEMENTOS. No realice ningún cambio en esta parte del código de complemento.

```js
/* 
* Plugin: getVisitNum - version 3.0 
*/ 
s.getVisitNum=new Function("tp","c","c2","" 
+"var s=this,e=new Date,cval,cvisit,ct=e.getTime(),d;if(!tp){tp='m';}" 
+"if(tp=='m'||tp=='w'||tp=='d'){eo=s.endof(tp),y=eo.getTime();e.setTi" 
+"me(y);}else {d=tp*86400000;e.setTime(ct+d);}if(!c){c='s_vnum';}if(!" 
+"c2){c2='s_invisit';}cval=s.c_r(c);if(cval){var i=cval.indexOf('&vn=" 
+"'),str=cval.substring(i+4,cval.length),k;}cvisit=s.c_r(c2);if(cvisi" 
+"t){if(str){e.setTime(ct+1800000);s.c_w(c2,'true',e);return str;}els" 
+"e {return 'unknown visit number';}}else {if(str){str++;k=cval.substri" 
+"ng(0,i);e.setTime(k);s.c_w(c,k+'&vn='+str,e);e.setTime(ct+1800000);" 
+"s.c_w(c2,'true',e);return str;}else {s.c_w(c,e.getTime()+'&vn=1',e)" 
+";e.setTime(ct+1800000);s.c_w(c2,'true',e);return 1;}}"); 
s.dimo=new Function("m","y","" 
+"var d=new Date(y,m+1,0);return d.getDate();"); 
s.endof=new Function("x","" 
+"var t=new Date;t.setHours(0);t.setMinutes(0);t.setSeconds(0);if(x==" 
+"'m'){d=s.dimo(t.getMonth(),t.getFullYear())-t.getDate()+1;}else if(" 
+"x=='w'){d=7-t.getDay();}else {d=1;}t.setDate(t.getDate()+d);return " 
+"t;");
```

**Parámetros**

* tp = (cadena, opcional) Período de seguimiento. Use "d" para día, "w" para semana, "m" para mes o un número para un número personalizado de días.

   * Si se selecciona día, semana o mes, el número de visita se restaurará al final del día/mes/semana.
   * Si se selecciona un número personalizado de días, el número de visita se restaurará tras ese número de días.
   * Si no se proporciona ningún valor, se usará "m".

* c = (cadena, opcional) Especifique el nombre de cookie persistente. El valor predeterminado es 's_vnum'.
* c2 = (cadena, opcional) Especifique el nombre de cookie de sesión. El valor predeterminado es 's_invisit'

**Valores devueltos**

* Devuelve el número (1, 2, 3, etc.) de la visita. Este número solo se incrementa en la primera página de cada visita.
* Devuelve "número de visita desconocido" si el complemento no puede identificar el número de visita (las cookies están bloqueadas).

**Ejemplos**

```js
s.prop1=s.getVisitNum(365); //custom length, 365 days. Default cookie names 
s.prop1=s.getVisitNum('w'); //resets weekly 
s.prop1=s.getVisitNum('m','s_vmonthnum','s_monthinvisit'); //resets montly, custom cookie names 
s.prop1=s.getVisitNum('d'); //resets daily
```

**Notas**

* Antes de su implementación en un entorno de desarrollo, realice pruebas exhaustivas de las instalaciones de complementos para asegurarse de que la recopilación de datos se comporta según lo esperado.
* Este complemento depende de la capacidad de establecer cookies en el explorador web del usuario. Si el usuario no acepta cookies, todas las visitas se considerarán primeras visitas.


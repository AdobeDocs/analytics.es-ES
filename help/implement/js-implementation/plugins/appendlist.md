---
description: El complemento APL (o appendList) permite anexar un valor a cualquier lista delimitada, con la opción de distinción de mayúsculas habilitada o deshabilitada para asegurarse de que el valor no exista en la lista. Hay varios complementos estándar que hacen referencia al complemento APL, pero puede utilizarse directamente en diversas situaciones.
keywords: Implementación de Analytics
seo-description: El complemento APL (o appendList) permite anexar un valor a cualquier lista delimitada, con la opción de distinción de mayúsculas habilitada o deshabilitada para asegurarse de que el valor no exista en la lista. Hay varios complementos estándar que hacen referencia al complemento APL, pero puede utilizarse directamente en diversas situaciones.
seo-title: appendList
solution: Analytics
subtopic: Complementos
title: appendList
topic: Desarrollador e implementación
uuid: e 923 c 86 c-eaa 6-4 e 17-a 3 a 4-0 e 08 af 886674
translation-type: tm+mt
source-git-commit: ee0cb9b64a3915786f8f77d80b55004daa68cab6

---


# appendList

El complemento APL (o appendList) permite anexar un valor a cualquier lista delimitada, con la opción de distinción de mayúsculas habilitada o deshabilitada para asegurarse de que el valor no exista en la lista. Hay varios complementos estándar que hacen referencia al complemento APL, pero puede utilizarse directamente en diversas situaciones.

Este complemento es útil para:

* Agregar un evento a la variable de eventos actual
* Agregar un valor a una variable de lista sin duplicar un valor en la lista
* Agregar un producto a la variable products actual con base en alguna lógica de página
* Agregar valores a los parámetros *`linkTrackVars`* y *`linkTrackEvents`*

**Caso de uso 1**

<table id="table_5AAC1D9892CD4E5C9060E119EE4E7DC8"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Situación </p> </td> 
   <td colname="col2"> <p>Agregue <span class="term"> event 1 </span> a la variable de eventos actual al garantizar que el evento no está duplicado. </p> <p>s.events="scCheckout" </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Código </p> </td> 
   <td colname="col2"> <p>s.events=s.apl(s.events,"event1",",",1) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Resultados </p> </td> 
   <td colname="col2"> <p>s.events="scCheckout,event1" </p> </td> 
  </tr> 
 </tbody> 
</table>

**Caso de uso 2**

<table id="table_C4356C9AB95948F3929A7B75E07AE9E7"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Situación </p> </td> 
   <td colname="col2"> <p>Agregue el valor <span class="term"> history </span> to the list variable <span class="varname"> prop 1 </span>, with <span class="term"> history </span> and <span class="term"> History </span> considerados el mismo valor. </p> <p>s.prop1="Science,History" </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Código </p> </td> 
   <td colname="col2"> <p>s.prop1=s.apl(s.prop1,"history",",",2) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Resultados </p> </td> 
   <td colname="col2"> <p>s.prop1="Science,History" </p> <p> <span class="term"> no </span> se añade el historial porque <span class="term"> el historial </span> ya está en la lista. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Las instrucciones siguientes requieren modificar el código de recopilación de datos en el sitio. Esto puede afectar a la recopilación de datos en el sitio y solamente debe hacerlo un desarrollador con experiencia en el uso y la implementación de [!DNL Analytics].

## Implementación {#section_F4C91CA2037F478C9F7B53F357E6A5F0}

Siga estos pasos para implementar el complemento APL.

1. Solicite el código del complemento al Servicio de atención al cliente o al asesor de Adobe que tenga asignado.
1. Add call(s) to the API function as needed within the *`s_doPlugins`* function

Esta sería la apariencia del código en el sitio:

```js
/* Plugin Config */ 
 
s.usePlugins=true 
 
function s_doPlugins(s) { 
 
/* Add calls to plugins here */ 
 
s.events=s.apl(s.events,"event1",",",1) 
 
} 
 
s.doPlugins=s_doPlugins
```

**Exploradores admitidos**

Este complemento requiere que el explorador admita JavaScript versión 1.0.

**Información del complemento**

<table id="table_7B9EDD616C164D6B8B53558337DF12C2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Información del complemento </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Parámetros </p> </td> 
   <td colname="col2"> <p>apl((L,v,d,u) </p> <p>L= lista fuente, se acepta que esté vacía </p> <p> v= valor para anexar </p> <p> d = delimitador de lista </p> <p> u (opcional, el valor predeterminado es 0) Comprobación de valor único. 0=sin comprobación de valor único, el valor se anexa siempre. 1=comprobación sin diferenciación de mayúsculas, anexar solo si el valor no está en la lista. 2=comprobación sin diferenciación de mayúsculas, anexar solo si el valor no está en la lista. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Valor de devolución </p> </td> 
   <td colname="col2"> <p>lista original, con valor anexado si se agrega </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ejemplos de uso </p> </td> 
   <td colname="col2"> <p>s.events=s.apl(s.events,"event1",",",1); </p> </td> 
  </tr> 
 </tbody> 
</table>

La lista fuente L puede ser una lista vacía como, por ejemplo, *`L=""`*. El valor devuelto será una lista vacía o una lista con un solo valor.

**Código de complemento**

```js
/******************************************************************** 
 * 
 * Main Plug-in code (should be in Plug-ins section) 
 * 
 *******************************************************************/ 
/* 
 * Plugin Utility: apl v1.1 
 */ 
s.apl=new Function("l","v","d","u","" 
+"var s=this,m=0;if(!l)l='';if(u){var i,n,a=s.split(l,d);for(i=0;i<a." 
+"length;i++){n=a[i];m=m||(u==1?(n==v):(n.toLowerCase()==v.toLowerCas" 
+"e()));}}if(!m)l=l?l+d+v:v;return l"); 
 
/******************************************************************** 
 * 
 * Commented example of how to use this is doPlugins function 
 * 
 *******************************************************************/ 
  
 Not Applicable - Utility function only 
 
/******************************************************************** 
 * 
 * Config variables (should be above doPlugins section) 
 * 
 *******************************************************************/ 
 
 None 
 
/******************************************************************** 
 * 
 * Utility functions that may be shared between plug-ins (name only) 
 * 
 *******************************************************************/ 
  
 s.split
```


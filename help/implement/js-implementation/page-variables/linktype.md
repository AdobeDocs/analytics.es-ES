---
description: Las variables de página rellenan directamente un informe, como pageName, Props de lista, Variables de lista, etc.
keywords: Analytics Implementation
solution: Analytics
subtopic: Variables
title: Variables de página
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 47291fb3d55ab3eb5ef181770bf2078c7ea55bc4

---



# linkType

La variable es una variable opcional utilizada para el seguimiento de vínculos que determina qué informe mostrará el nombre del vínculo o la dirección URL (vínculos de salida, de descarga o personalizados).


<!-- 

linkType.xml

 -->

La variable *`linkType`* no suele ser necesaria ya que el segundo parámetro de la función *`tl()`* la sustituye.

<table id="table_3D1A2FC1CECD4709BE2F9E32AC2DC730"> 
 <thead> 
  <tr> 
   <th class="entry"> Tamaño máximo </th> 
   <th class="entry"> Parámetro depurador </th> 
   <th class="entry"> Informes rellenados </th> 
   <th class="entry"> Valor predeterminado </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> Un carácter </td> 
   <td> pe=[lnk_o|lnk_d|lnk_e] </td> 
   <td> <p>Descargas de archivos </p> <p>Vínculos personalizados </p> <p>Vínculos de salida </p> </td> 
   <td> "" </td> 
  </tr> 
 </tbody> 
</table>

Los vínculos personalizados envían datos a Analytics. La variable *`linkType`* (o el segundo parámetro de la función *`tl()`*) se utiliza para identificar el informe en el que se mostrará el nombre del vínculo o la URL (informe de vínculos [!UICONTROL de salida], [!UICONTROL de descarga] o [!UICONTROL personalizados]).

Para los vínculos de salida y de descarga, la variable *`linkType`* se rellena automáticamente en función de si el vínculo en el que se hizo clic es de salida o de descarga. Se puede configurar un vínculo personalizado para enviar datos a cualquiera de los tres informes con esta variable o con el segundo parámetro en la función *`tl()`*. Al establecer *`linkType`* en “o”, “e” o “d”, la dirección URL *`linkName`* o del vínculo se envía respectivamente al informe Vínculos [!UICONTROL personalizados], [!UICONTROL de salida] o [!UICONTROL Descargas de archivos].

**Sintaxis y valores posibles** {#section_18DB3A8083FB4F75B970055ED336DA4E}

La sintaxis de la variable *`linkType`* depende de si utiliza XML o una cadena de consulta.

Si utiliza XML, la variable puede contener un único carácter, ya sea “o”, “e” o “d”.

```js
s.tl(this,'o','Link Name');
```

Si utiliza la cadena de consulta `pe`, debe utilizar `lnk_d`, `lnk_e` o `lnk_o`.

**Ejemplos** {#section_242B5DFFD1C9462A9A8EB1556B2E3160}

```js
<a href="index.html" onClick=" 
 var s=s_gi('rsid'); **see note below on the rsid** 
 s.tl(this,'o','Link Name'); 
 ">My Page</a> 
```

**Parámetros de configuración** {#section_59738AD1B5E94294B8D36F4E772DEDB3}

Ninguna

**Problemas, preguntas y consejos** {#section_F0D01DDE3FDA486C987162DA50A79C45}

* Si no se especifica el valor de *`linkType`*, se usarán como vínculos personalizados (“o”).

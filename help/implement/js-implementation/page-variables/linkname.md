---
description: Las variables de página rellenan directamente un informe, como pageName, Props de lista, Variables de lista, etc.
keywords: Analytics Implementation
subtopic: Variables
title: Variables de página
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---



# linkName

La variable es una variable opcional utilizada en el [!UICONTROL seguimiento de vínculos] que determina el nombre de un vínculo de salida, de descarga o personalizado.


<!-- 

linkName.xml

 -->

La variable *`linkName`* no suele ser necesaria ya que el tercer parámetro de la función *`tl()`* la sustituye.

<table id="table_4B0D1C9AADA542A59B626E077D5FC568"> 
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
   <td> 100 bytes </td> 
   <td> pev2 </td> 
   <td> <p>Descargas de archivos </p> <p>Vínculos personalizados </p> <p>Vínculos de salida </p> </td> 
   <td> "" </td> 
  </tr> 
 </tbody> 
</table>

[!UICONTROL Vínculos personalizados] hace referencia a los vínculos que envían datos de seguimiento. La variable *`linkName`* (o el tercer parámetro de la función *`tl()`*) identifica el valor que aparece en los informes de vínculos [!UICONTROL personalizados], [!UICONTROL de descarga] o [!UICONTROL de salida]. Si *`linkName`* no se rellena, la dirección URL del vínculo aparecerá en el informe.

**Sintaxis y valores posibles** {#section_C8D89834C98B4C7A858C947293C4148E}

```js
s.linkName="Link Name"
```

No existen limitaciones de *`linkName`* además de las limitaciones estándar de las variables.

**Ejemplos** {#section_5F68766210184E82A23D2A6ECD80BA0B}

```js
s.linkName="Nav Bar Home Link"
```

```js
s.linkName="Partner Link to A.com"
```

**Parámetros de configuración** {#section_F15FF429FC274F708D50DF79D4668EA3}

Ninguna

**Problemas, preguntas y consejos** {#section_170A78452A7340B5B229713AC1FB71FA}

* La variable *`linkName`* se reemplaza con el tercer parámetro en la función *`tl()`*.

* Si la variable *`linkName`* y el tercer parámetro en la función *`tl()`* están vacíos, la URL completa del vínculo (con excepción de la cadena de consulta) se verá en el informe (aunque el vínculo sea relativo).

---
description: Lista de variables personalizadas que se usan en Analytics.
keywords: Implementación de Analytics
seo-description: Lista de variables personalizadas que se usan en Analytics.
seo-title: Variables personalizadas
solution: Analytics
title: Variables personalizadas
topic: Desarrollador e implementación
uuid: 54 adf 622-7 f 05-49 c 0-b 7 e 6-702 bb 2 f 17 b 1 c
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Variables personalizadas

Lista de variables personalizadas que se usan en Analytics.

<table id="table_E8C7871F63F648A59644638FB56BD0E1"> 
 <thead> 
  <tr> 
   <th class="entry"> Variable </th> 
   <th class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> Variables de tráfico </td> 
   <td> Compruebe el valor de prop1 - 75. Esta es una lista de los elementos para comprobar. 
    <ul id="ul_0EE2D50BA90F4F21BD63268A5082F980"> 
     <li id="li_A6E4D66E8A03400491A26A08E4945908">¿Se han utilizado las mayúsculas y minúsculas correctamente? El registro "ValueA" es diferente de "valueA". Puede usar todo en minúsculas porque un pequeño subconjunto de exploradores convierte todas las variables a minúsculas. </li> 
     <li id="li_65CBFB908E7B4ED5AF9518FE5B58D4E2">¿Los valores tienen menos de 100 caracteres de longitud? Si no es así, se podrían recortar algunos valores. </li> 
     <li id="li_CC506D114AFE44699D89AB84BBCCEBFC"> ¿Están relacionados todos los valores de una única variable de propiedad o algunos valores parecen estar fuera de lugar? </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td> Variables de conversión </td> 
   <td>  Las variables <span class="wintitle">econversion</span> incluyen las eVar de 1 a 75. Esta es una lista de los elementos para comprobar. 
    <ul id="ul_CA10C5B9F24B4C49A64CA84A9DCE8E63"> 
     <li id="li_8CCD92F3AD5E49EBA91C9B008DA47016">¿Se han utilizado las mayúsculas y minúsculas correctamente? El registro "ValueA" es diferente de "valueA". Puede usar todo en minúsculas porque un pequeño subconjunto de exploradores convierte todas las variables a minúsculas. </li> 
     <li id="li_5B6FDEDB2C32409AA59D6BB0DF2346CB">¿Los valores tienen menos de 255 caracteres de longitud? Si no es así, se podrían recortar algunos valores. </li> 
     <li id="li_C31AFBAC99D84E96A1244E795CE7765D">¿Están relacionados todos los valores de una única eVar o algunos valores parecen estar fuera de lugar? </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td> Eventos personalizados </td> 
   <td> Los eventos incluyen valores estándar (<span class="wintitle">prodView</span>, <span class="wintitle">scOpen</span>, <span class="wintitle">scAdd</span>, <span class="wintitle">scCheckout</span>, <span class="wintitle">purchase</span>) y eventos personalizados desde event1 a event100. Todos los eventos se envían en la variable events. Si hay varios eventos en una página, deben separarse con comas (sin espacios en blanco). 
    <ul id="ul_2213CC9DE892433FAF6FC1F5A2B841B4"> 
     <li id="li_15E31A9FF1654DFA93C158F422B9EAE3">Para todos los eventos de conversión estándar, los productos también deben rellenarse con los productos correspondientes. Para todos los eventos excepto las compras, los elementos qty y price son opcionales. </li> 
     <li id="li_03ED9AAC45DA47A58AB482E2CEBF5108">El evento de <span class="wintitle">compras</span> debe configurarse solo una vez en una sesión después de completar y confirmar la compra. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>


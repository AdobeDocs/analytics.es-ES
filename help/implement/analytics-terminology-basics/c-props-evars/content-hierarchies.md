---
description: Un uso habitual de las jerarquías de contenido es mostrar las diferentes rutas que los visitantes han seguido desde una determinada página o nivel.
keywords: Implementación de Analytics; content hierachos; hier
seo-description: Un uso habitual de las jerarquías de contenido es mostrar las diferentes rutas que los visitantes han seguido desde una determinada página o nivel.
seo-title: Recuento de jerarquías de contenido
solution: Analytics
title: Recuento de jerarquías de contenido
topic: Desarrollador e implementación
uuid: d 41 df 92 d -65 fb -44 de-bf 46-8 fac 24303 papá
translation-type: tm+mt
source-git-commit: 1bc1c7a1e00d7b59cd39f368ac9afb745bea9e47

---


# Recuento de jerarquías de contenido

Un uso habitual de las jerarquías de contenido es mostrar las diferentes rutas que los visitantes han seguido desde una determinada página o nivel.

**¿Cómo puedo realizar un seguimiento de mi[!UICONTROL jerarquía de contenido]?** 

Primero debe comprender los requisitos de informes para el seguimiento de [!UICONTROL jerarquías de contenido]. Si los requisitos para realizar un seguimiento de la jerarquía son muy detallados, a menudo se recomienda la variable hierarchy ( *`hier`*) se recomienda. Las jerarquías suelen requerir una taxonomía predefinida estricta en la que el mismo nodo secundario rara vez reside debajo de varios nodos primarios. Consideremos el siguiente ejemplo:

[!UICONTROL Jerarquía global]

Todos los sitios &gt; Regiones &gt; Países &gt; Idioma &gt; Categoría

En este ejemplo, la jerarquía podría comenzar a desglosarse en el nivel del idioma. Si un requisito es notificar el tráfico en "Inglés" general, puede tener problemas si Inglés aparece en EE. UU., Inglaterra, Australia, etc. Las jerarquías solo permiten explorar en profundidad. Para fraccionar varias jerarquías horizontalmente, el práctica recomendada es usar una [!UICONTROL variable de tráfico personalizada] (prop).

Si quiere que los usuarios puedan explorar en profundidad el sitio (de forma similar a cómo los usuarios explorarían el sitio) y crear un informe por [!UICONTROL Visitantes únicos] en cada nivel de la jerarquía, se recomienda la variable hierarchy.

Hay ocasiones en que cabe utilizar tanto props como la variable *`hier`*. Las siguientes son las props admitidas para cada tipo de variable:

<table id="table_E960D100DA0F433A94A4B246D6EF0D0A"> 
 <thead> 
  <tr> 
   <th class="entry"> </th> 
   <th class="entry"> Props </th> 
   <th class="entry"> Jerarquía </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> Correlaciones </td> 
   <td> <p><img  src="assets/check-mark.png" id="image_2832E346D220429DA643B908EC10260D" /> </p> </td> 
   <td> <p><img  src="assets/check-mark.png" id="image_2A70A61A78024204B6CEE4FFF9A0851E" /> </p> </td> 
  </tr> 
  <tr> 
   <td> Control de rutas </td> 
   <td> <p><img  src="assets/check-mark.png" id="image_EE5ED36AC75F4D648F54858D796F82BD" /> </p> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Vista de la página </td> 
   <td> <p><img  src="assets/check-mark.png" id="image_5BB82776D41642E78C2ECFD71DD33164" /> </p> </td> 
   <td> <p><img  src="assets/check-mark.png" id="image_18F34EE8957946AF9D6C2C9B492CEDB7" /> </p> </td> 
  </tr> 
  <tr> 
   <td> Visitantes únicos </td> 
   <td> <p><img  src="assets/check-mark.png" id="image_A475267547B94DB4A1EEFD903B2CA1EB" /> </p> </td> 
   <td> <p><img  src="assets/check-mark.png" id="image_1E9E302D999146128CDBCE13E52BC38C" /> </p> </td> 
  </tr> 
  <tr> 
   <td> Clasificaciones </td> 
   <td> <p><img  src="assets/check-mark.png" id="image_FC5FEFE7BA8C4475BA4F31D57302BE6B" /> </p> </td> 
   <td> </td> 
  </tr> 
 </tbody> 
</table>


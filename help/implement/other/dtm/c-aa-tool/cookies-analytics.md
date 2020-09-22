---
description: Descripciones de los campos de la configuración global de cookies que se utiliza para implementar Dynamic Tag Management en Adobe Analytics.
keywords: Dynamic Tag Management;cookies;visitor id;visitor namespace;domain periods;fp domain periods;transaction id;cookie lifetime
solution: Experience Cloud,Analytics
title: Cookies
uuid: 9c81ecbb-0f02-4c1a-a5a5-426cdea57f38
translation-type: tm+mt
source-git-commit: a4542164031fc9f181dfdc471a1d54b5056b1223
workflow-type: tm+mt
source-wordcount: '164'
ht-degree: 100%

---


# Cookies

Descripciones de los campos de la configuración global de cookies que se utiliza para implementar [!UICONTROL Dynamic Tag Management] en Adobe Analytics.

*`Property`* > Editar herramienta > Cookies

<table id="table_2758C770C91B4025AD74009B360D71F7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> ID de visitante </td> 
   <td colname="col2"> <p>Valor no repetido que representa a un cliente en ambos sistemas (en línea y sin conexión). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Área de nombres del visitante </td> 
   <td colname="col2"> <p>Variable para identificar el dominio con el que se configuran las cookies. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> Períodos del dominio </td> 
   <td colname="col2"> <p>Dominio en el cual se configuran las cookies de Analytics <code> s_cc</code> y <code> s_sq</code>; para ello, determina el número de períodos en la dirección URL de la página. Algunos complementos también usan esta variable para determinar el dominio correcto donde se configurará la cookie del complemento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Períodos del dominio de FP </td> 
   <td colname="col2"> <p>La variable <span class="term"> fpCookieDomainPeriods</span> está destinada a cookies configuradas por JavaScript (<code> s_sq</code>, <code> s_cc</code>, complementos), que son cookies inherentemente de origen, aunque su implementación utilice los dominios de terceros <span class="filepath">2o7.net</span> u <span class="filepath">omtrdc.net</span>. </p> <p>Consulte <a href="/help/implement/vars/config-vars/fpcookiedomainperiods.md"  >s.fpCookieDomainPeriods</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ID de transacción </td> 
   <td colname="col2"> <p>Valor no repetido que representa una transacción en línea que dio lugar a una actividad sin conexión. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Duración de la cookie </td> 
   <td colname="col2"> <p>Determina la vida útil de una cookie. </p> </td> 
  </tr> 
 </tbody> 
</table>


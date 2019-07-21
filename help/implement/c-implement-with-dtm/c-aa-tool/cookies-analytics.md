---
description: Descripciones de los campos de la configuración global de cookies que se utiliza para implementar Dynamic Tag Management en Adobe Analytics.
keywords: Administración dinámica de etiquetas; cookies; ID de visitante; visitor namespace; períodos de dominio; períodos de dominio de FP; transaction id; duración de la cookie
seo-description: Descripciones de los campos de la configuración global de cookies que se utiliza para implementar Dynamic Tag Management en Adobe Analytics.
seo-title: Cookies
solution: Marketing Cloud, Analytics, Administración dinámica de etiquetas
title: Cookies
uuid: 9 c 81 ecbb -0 f 02-4 c 1 a-a 5 a 5-426 cdea 57 f 38
translation-type: tm+mt
source-git-commit: 01a6fc7e44dc71b868bd38a4f6a5a4089eae6349

---


# Cookies

Field descriptions for the Cookies global settings used for deploying [!UICONTROL Dynamic Tag Management] in Adobe Analytics.

**[!UICONTROL *`Property`*]** &gt;** [! UICONTROL ![](assets/settings_gear.png)

Edit Tool]** &gt; **[!UICONTROL Cookies]**

<table id="table_2758C770C91B4025AD74009B360D71F7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> ID del visitante </td> 
   <td colname="col2"> <p>Valor no repetido que representa a un cliente en ambos sistemas (conectado a Internet y sin conexión). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Espacio de nombres de visitantes </td> 
   <td colname="col2"> <p>Variable que identifica el dominio con el cual se definen las cookies. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> Períodos del dominio </td> 
   <td colname="col2"> <p>Dominio en el cual se configuran las cookies de Analytics <code>s_cc</code> y <code>s_sq</code>; para ello, determina el número de períodos en la dirección URL de la página. Algunos complementos también usan esta variable para determinar el dominio correcto donde se configurará la cookie del complemento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Períodos del dominio de FP </td> 
   <td colname="col2"> <p>La variable <span class="term"> Fpcookiedomainperiods</span> es para cookies configuradas por JavaScript (<code> s_ sq</code>, <code> s_ cc</code>, complementos) que son cookies inherentemente de origen, incluso si su implementación utiliza los dominios <span class="filepath"> de terceros 2 o 7. net</span> u <span class="filepath"> omtrdc. net</span> . </p> <p>See <a href="../../../implement/js-implementation/c-variables/configuration-variables.md#concept_8FCA630706334F54B4DCB607378BCD00" format="dita" scope="local"> s.fpCookieDomainPeriods</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ID de la transacción </td> 
   <td colname="col2"> <p>Valor no repetido que representa una transacción en línea que dio lugar a una actividad sin conexión. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Vida de la cookie </td> 
   <td colname="col2"> <p>Determina la duración de una cookie. </p> </td> 
  </tr> 
 </tbody> 
</table>


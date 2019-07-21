---
description: Descripciones de los campos de Dynamic Tag Management para opciones de referentes y campañas al implementar Dynamic Tag Management en Adobe Analytics.
keywords: Administración dinámica de etiquetas; referrers; campañas; referrer override; variable de campaña; parámetro de consulta
seo-description: Descripciones de los campos de Dynamic Tag Management para opciones de referentes y campañas al implementar Dynamic Tag Management en Adobe Analytics.
seo-title: Referentes y campañas
solution: Marketing Cloud, Analytics, Administración dinámica de etiquetas
title: Referentes y campañas
uuid: 56580206-a 382-4993-9 bba-a 488 da 65 cf 89
translation-type: tm+mt
source-git-commit: e271cf73e7fd31d8893ed57112f2f3bb7821fbdd

---


# Referentes y campañas

Field descriptions in [!UICONTROL Dynamic Tag Management] for referrers and campaign options when deploying [!UICONTROL Dynamic Tag Management] in Adobe [!DNL Analytics].

**[!UICONTROL *`Property`*]** &gt; ![](assets/settings_gear.png)**[!UICONTROL Editar herramienta]** &gt; **[!UICONTROL Referentes y campañas]**

<table id="table_09AE3BFF0F12442F9C19CD96451F93E4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Anulación de referente </td> 
   <td colname="col2"> <p>Anula el valor configurado en la variable <span class="varname"> variable s. referrer</span> , que suele rellenar el referente configurado en el explorador. </p> <p>Consulte [Variables de página] (/help/implementation/js-implementation/c-variables/page-variables. md). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Campaña </td> 
   <td colname="col2"> <p>Una variable que identifica las campañas de marketing utilizadas para atraer visitantes a un sitio. El valor de campaña generalmente se toma de un parámetro de cadena de consultas. </p> <p>Consulte [Variables de página] (/help/implementation/js-implementation/c-variables/page-variables. md). </p> </td> 
  </tr> 
 </tbody> 
</table>

Utilice la interfaz de la DTM para elegir si desea utilizar un valor o una cadena de consulta (que se puede extraer de un elemento de datos):

![](assets/dtm-queryparam.png)

Puede introducir la cadena de consulta directamente en la interfaz o hacer referencia a un elemento de datos independiente si dispone de otro medio para rastrear una campaña. 

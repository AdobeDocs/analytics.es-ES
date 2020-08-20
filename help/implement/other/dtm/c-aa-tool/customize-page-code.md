---
description: Descripciones de los campos de Dynamic Tag Management para personalizar el código de la página al implementar Analytics.
keywords: Dynamic Tag Management;customize page code;open editor;execute
solution: Experience Cloud,Analytics,Target,Dynamic Tag Management
title: Personalización del código de la página
uuid: b7cad069-3eb8-4388-b0b0-34f54001e05f
translation-type: tm+mt
source-git-commit: 4b6107fe57787e639fb06ef957d6230d1bc45bd1
workflow-type: tm+mt
source-wordcount: '101'
ht-degree: 95%

---


# Personalización del código de la página

Descripciones de los campos de Dynamic Tag Management para personalizar el código de la página al implementar Analytics.

**[!UICONTROL `Property`]** > **[!UICONTROL Editar herramienta]** ![](assets/settings_gear.png) > **[!UICONTROL Personalizar código de página]**

<table id="table_A4676A5FEE814DF9A05DA0E56F8B4C6D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Abrir editor </p> </td> 
   <td colname="col2"> <p>Puede insertar cualquier llamada a JavaScript que deba desencadenarse antes de la llamada <code> s.t()</code> final, que se encuentra en <code> s_code</code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ejecutar </p> </td> 
   <td colname="col2"> <p> <b>Antes de la IU</b>: La configuración de la interfaz tiene prioridad sobre el código personalizado (por ejemplo, si desea anular un elemento eVar en caso de activar un ajuste en la interfaz). </p> <p> <b>Después de la IU</b>: El código personalizado tiene prioridad sobre la configuración de la interfaz. </p> </td> 
  </tr> 
 </tbody> 
</table>


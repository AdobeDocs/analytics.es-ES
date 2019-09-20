---
description: Descripciones de los campos de Dynamic Tag Management para personalizar el código de la página al implementar Analytics.
keywords: Administración dinámica de etiquetas;personalizar código de página;abrir editor;ejecutar
seo-description: Descripciones de los campos de Dynamic Tag Management para personalizar el código de la página al implementar Analytics.
seo-title: Personalización del código de la página
solution: Experience Cloud,Analytics,Target,Administración dinámica de etiquetas
title: Personalización del código de la página
uuid: b7cad069-3eb8-4388-b0b0-34f54001e05f
translation-type: tm+mt
source-git-commit: e060fb745d611f37f28708b3fe103c1191aa483b

---


# Personalización del código de la página

Descripciones de los campos de Dynamic Tag Management para personalizar el código de la página al implementar Analytics.

Agregue complementos para asegurarse de que el código se ejecuta en el mismo momento que la herramienta Analytics. Para obtener más información acerca de los complementos de Analytics, consulte [Complementos de implementación](../../../implement/js-implementation/plugins/impl-plugins.md#concept_021F5E4A6BD745AE91E85E7138BE930F).

**[!UICONTROL *`Property`*]** &gt; **[!UICONTROL ![](assets/settings_gear.png)

Edit Tool]** &gt; **[!UICONTROL Customize Page Code]**

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
   <td colname="col2"> <p>Puede insertar cualquier llamada a JavaScript que deba desencadenarse antes de la llamada <code>s.t()</code> final, que se encuentra en <code>s_code</code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ejecutar </p> </td> 
   <td colname="col2"> <p> <b>Antes de la IU</b>: La configuración de la interfaz tiene prioridad sobre el código personalizado (por ejemplo, si desea anular un elemento eVar en caso de activar un ajuste en la interfaz). </p> <p> <b>Después de la IU</b>: El código personalizado tiene prioridad sobre la configuración de la interfaz. </p> </td> 
  </tr> 
 </tbody> 
</table>


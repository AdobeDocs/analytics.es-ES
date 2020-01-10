---
description: Descripciones de los campos de Dynamic Tag Management para personalizar el código de la página al implementar Analytics.
keywords: Dynamic Tag Management;customize page code;open editor;execute
solution: Experience Cloud,Analytics,Target,Dynamic Tag Management
title: Personalización del código de la página
uuid: b7cad069-3eb8-4388-b0b0-34f54001e05f
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Personalización del código de la página

Descripciones de los campos de Dynamic Tag Management para personalizar el código de la página al implementar Analytics.

Agregue complementos para asegurarse de que el código se ejecuta en el mismo momento que la herramienta Analytics. Para obtener más información acerca de los complementos de Analytics, consulte [Complementos de implementación](/help/implement/js-implementation/plugins/impl-plugins.md).

**[!UICONTROL *`Property`*]** &gt; **[!UICONTROL   ![](assets/settings_gear.png)

Editar herramienta]** &gt; **[!UICONTROL Personalizar código de página]**

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


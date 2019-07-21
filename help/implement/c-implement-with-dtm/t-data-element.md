---
description: Cree un elemento de datos en Dynamic Tag Management.
keywords: Administración dinámica de etiquetas; data element; crear nuevo elemento de datos; name; type; valor predeterminado; forzar valor en minúsculas; recordar este valor para
seo-description: Cree un elemento de datos en Dynamic Tag Management.
seo-title: Creación de un elemento de datos
solution: Marketing Cloud, Analytics, Target, Administración dinámica de etiquetas
title: Creación de un elemento de datos
uuid: eacd 5 c 60-6197-4129-a 9 e 1-a 39 e 9 a 58 b 38 a
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Creación de un elemento de datos

Creación de un elemento de datos en Administración dinámica de etiquetas.

1. [Cree una propiedad web](../../implement/c-implement-with-dtm/t-create-web-property.md#task_960467FBB7A54499AC228CB3AA3C4123), si aún no lo ha hecho.
1. En la propiedad web, haga clic en **Reglas** &gt; **[!UICONTROL Elementos de datos]**.
1. Haga clic en **[!UICONTROL Crear nuevo elemento de datos]**.
1. Complete las opciones y los campos siguientes:

   <table id="choicetable_681F7D5B86534FF0B6DB67E117B8E381"> 
    <thead class="chhead sthead"> 
      <th class="choptionhd"> Opción</th> 
      <th class="chdeschd"> Descripción</th> 
    </thead> 
    <tr class="chrow strow"> 
      <td class="choption"><strong>Nombre</strong></td> 
      <td class="chdesc stentry"> <p>Nombre sencillo del elemento de datos que el especialista en mercadotecnia pueda reconocer. Por ejemplo, 
        <code>
          ID del producto
        </code>. </p> <p> <p>Nota: El nombre es una referencia para el generador de reglas, no un ID. Si cambia el nombre del elemento de datos, debe cambiar su referencia en todas las reglas que lo utilicen. </p> </p> </td> 
    </tr> 
    <tr class="chrow strow"> 
      <td class="choption"><strong>Tipo</strong></td> 
      <td class="chdesc stentry"> <p> Especifica la ubicación de la cual se extraen los datos, como, por ejemplo, objeto de JS, selector de CSS, cookie, parámetro de URL o script personalizado. </p> <p>Se mostrarán diversas opciones en función del tipo seleccionado. Consulte <a href="https://marketing.adobe.com/resources/help/en_US/dtm/data_elements.html" format="html" scope="external">Tipos de elementos de datos</a> en Documentación del producto de Dynamic Tag Management para obtener más información y ejemplos. </p> </td> 
    </tr> 
    <tr class="chrow strow"> 
      <td class="choption"><strong>Valor predeterminado</strong></td> 
      <td class="chdesc stentry"> <p>Un elemento predeterminado. Este valor asegura que el elemento de datos siempre cuenta con un valor, incluso si un parámetro de URL no existe o Dynamic Tag Management no lo encuentra. </p> <p> <p>Nota: Si no hay ningún valor ni ningún valor predeterminado, no ocurrirá nada. No se definirá ninguna variable que haga referencia a ese elemento de datos. También debe tener en cuenta que se ignorará el campo de valor predeterminado si se trata de un elemento de datos de “código personalizado”. </p> </p> </td> 
    </tr> 
    <tr class="chrow strow"> 
      <td class="choption"><strong>Forzar valor de minúsculas</strong></td> 
      <td class="chdesc stentry"> <p>Dynamic Tag Management convertirá automáticamente el valor en minúsculas. </p> </td> 
    </tr> 
    <tr class="chrow strow"> 
      <td class="choption"><strong>Recordar este valor durante</strong></td> 
      <td class="chdesc stentry"> <p>El tiempo que desea que Dynamic Tag Management recuerde este valor. </p> <p> Los valores válidos son los siguientes: </p> 
      <ul id="ul_52F6CD8FC22942208F3F45492E914104"> 
        <li id="li_32E4366C5B2E46D788CD8478620FE3E0"> <p>Sesión: la temporización basada en sesión puede variar según la implementación. Los elementos de datos de la sesión se establecen en la cookie de sesión. Sin embargo, este ajuste puede basarse en un servidor web o en un explorador. No está relacionado con la sesión que se utiliza en los Reports &amp; Analytics de marketing. </p> </li> 
        <li id="li_8A944564BF7643E4B21F0EF2394B3FE8"> <p>Vista de página </p> </li> 
        <li id="li_5C8A2F2392FD475AA89DDA7D5B5CF88B"> <p>API </p> </li> 
      </ul> </td> 
    </tr> 
   </table>

   Consulte [Elementos de datos](https://marketing.adobe.com/resources/help/en_US/dtm/data_elements.html) en Documentación del producto de Tag Management de Adobe para obtener más información sobre el uso de los elementos de datos.
1. Haga clic en **[!UICONTROL Guardar elemento de datos]**.

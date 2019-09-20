---
description: Descripciones de los campos y las opciones del ajuste Administración de biblioteca de Dynamic Tag Management.
keywords: administración de biblioteca;código de página;cargar biblioteca en;administrado por adobe;personalizado;código alojado;s_code alojado
seo-description: Descripciones de los campos y las opciones del ajuste Administración de biblioteca de Dynamic Tag Management.
seo-title: Administración de biblioteca
solution: Experience Cloud, administración dinámica de etiquetas
title: Administración de biblioteca
uuid: 4cfa47f9-ae98-4feb-a58d-a3a6e45f8d5b
translation-type: tm+mt
source-git-commit: e060fb745d611f37f28708b3fe103c1191aa483b

---


# Administración de biblioteca

Descripciones de los campos y las opciones del ajuste Administración de biblioteca de Dynamic Tag Management.

**[!UICONTROL *`Property`*]** &gt; ![](assets/settings_gear.png) Herramienta **** Editar &gt; Administración **[!UICONTROL de biblioteca]**

>[!NOTE]
>
>Si se utiliza más de una herramienta de Adobe Analytics en una única propiedad web, cada herramienta debe tener un nombre de variable de rastreador único. Si existen duplicados de nombres de variables de objetos entre distintas herramientas Adobe Analytics en una misma propiedad web, se podría producir un conflicto.

<table id="table_2758C770C91B4025AD74009B360D71F7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Código de la página ya presente </p> </td> 
   <td colname="col2"> <p> Evita que Dynamic Tag Management instale código de página de <span class="keyword">Adobe Analytics</span> que ya se encuentra en el sitio. </p> <p>Esta función le permite utilizar Dynamic Tag Management para añadirla a la implementación existente en lugar de empezar desde cero. Asegúrese de establecer correctamente el nombre de la variable de rastreador al marcar esta casilla. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Cargar biblioteca en &lt;<span class="term"> Principio</span> de página o Final <span class="term"> de página</span>&gt; </p> </td> 
   <td colname="col2"> <p>Especifica cuándo y dónde cargar el código de página. Independientemente de su selección, todas las reglas que utilicen la herramienta Analytics deberán tener la misma configuración. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Administrado por Adobe (recomendado) </p> </td> 
   <td colname="col2"> <p>Habilite Dynamic Tag Management para administrar su biblioteca. </p> <p>Si selecciona esta opción, aparecerá disponible la siguiente opción: </p> <p> <b>Versión de biblioteca:</b> seleccione la última versión en el menú <span class="wintitle">Versión de biblioteca</span>. Dynamic Tag Management le informa cuando hay disponibles nuevas versiones. Si es necesario, puede revertir a una versión anterior. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Personalizado </p> </td> 
   <td colname="col2"> <p>Puede configurar el código de biblioteca. </p> <p>Si selecciona esta opción, aparecerán disponibles las siguientes opciones: </p> <p> <b>Definir grupos de informes con el siguiente código personalizado:</b> al marcar esta casilla, Dynamic Tag Management busca una variable en su código personalizado con el nombre <span class="varname"> s_account</span>. Esta variable debe contener una lista separada por comas de los grupos de informes a los que desea enviar datos. </p> <p> <b>Código alojado:</b> elija una opción para alojar el <span class="filepath">s_code</span>: </p> 
    <ul id="ul_FC395283365A4BBAA8A5FE5871D16EC6"> 
     <li id="li_36D733C533CE40F1868309130551D4DE"> <b>En DTM</b>: Puede alojar <span class="filepath">s_code</span> en Dynamic Tag Management. Haga clic en <span class="uicontrol">Editar código</span> para cortar y pegar el archivo directamente en el editor. </li> 
     <li id="li_A64734C66D254079A5E16DC8DBEDA3F6"> <b>URL</b>: si dispone de un archivo <span class="filepath">s_code</span> satisfactorio y es el que le gustaría actualizar, puede proporcionar la URL del archivo aquí. A continuación, Dynamic Tag Management consumirá ese archivo <span class="filepath">s_code</span> para la implementación de <span class="keyword">Adobe Analytics</span>. </li> 
    </ul> <p> <b>Abrir editor: </b>Permite <a href="../../../implement/c-implement-with-dtm/c-aa-tool/t-appmeasurement-code.md#task_068D72664B2743359A64ADB8692D3658" format="dita" scope="local"> insertar el código</a>principal de AppMeasurement. This code is populated automatically when using the automatic configuration method described in <a href="../../../implement/c-implement-with-dtm/c-aa-tool/analytics-dtm.md#concept_FBA6679A0B79490F8296437F11E5E4F8" format="dita" scope="local"> Adobe Analytics Settings</a>. </p> <p> <b>Nombre de la variable del rastreador: </b>Si desea ejecutar dos instancias de <span class="keyword"> Adobe Analytics</span> en paralelo (una en la administración dinámica de etiquetas y otra de forma nativa), puede cambiar el nombre del objeto <span class="term"> s</span> principal. Al cambiar el nombre del objeto se evitan colisiones. </p> </td> 
  </tr> 
 </tbody> 
</table>


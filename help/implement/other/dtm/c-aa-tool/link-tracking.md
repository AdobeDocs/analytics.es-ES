---
description: Descripciones de los campos de Dynamic Tag Management de seguimiento de vínculos al implementar Analytics.
keywords: Dynamic Tag Management;link tracking;enable clickmap;track download links;download extensions;track outbound links;keep url parameters
solution: Experience Cloud,Analytics,Dynamic Tag Management
title: Seguimiento de vínculos
uuid: 982b744b-5696-4c31-b1d1-410486b0eedd
translation-type: ht
source-git-commit: 354785439a5920d8fc53d566fa9306c74e2504d2
workflow-type: ht
source-wordcount: '268'
ht-degree: 100%

---


# Seguimiento de vínculos

Descripciones de los campos de Dynamic Tag Management de seguimiento de vínculos al implementar Analytics.

**[!UICONTROL Propiedad]** > ![Icono de configuración](assets/settings_gear.png) **[!UICONTROL Editar herramienta]** > **[!UICONTROL Seguimiento de vínculos]**

<table id="table_F23FB0B284E74B66A107B1D69D22A51C">
 <thead>
  <tr>
   <th colname="col1" class="entry"> Elemento </th>
   <th colname="col2" class="entry"> Descripción </th>
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Habilitar ClickMap </td>
   <td colname="col2"> <p>Determina si se recopilarán los datos del mapa de clics de visitantes. </p> <p>Consulte <a href="../../../vars/config-vars/trackinlinestats.md">trackInlinestats</a>. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> Rastrear vínculos de descarga </td>
   <td colname="col2"> <p>Rastrea los vínculos a archivos descargables del sitio. </p> <p>Consulte <a href="../../../vars/config-vars/trackdownloadlinks.md">trackDownloadLinks</a>.</p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> Extensiones de descarga </td> 
   <td colname="col2"> <p>Si su sitio contiene vínculos a archivos con cualquiera de las extensiones enumeradas, las direcciones URL de estos vínculos aparecerán en el informe. </p>Consulte <a href="../../../vars/config-vars/linkdownloadfiletypes.md">linkDownloadFileTypes</a>. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> Rastrear vínculos salientes </td>
   <td colname="col2"> <p>Determina si un vínculo en el que se hace clic es un vínculo de salida. </p> <p>Consulte <a href="../../../vars/config-vars/trackexternallinks.md">trackExternalLinks</a>. </p> <p><b>Consideraciones para aplicaciones de una sola página:</b> debido al tipo de codificación de algunos sitios web de SPA, es posible que los vínculos internos a una página de la SPA parezcan un vínculo de salida. </p> <p>Puede utilizar uno de los siguientes métodos para rastrear los vínculos de salida de los sitios de la SPA: </p>
    <ul id="ul_A4179633ED0644C3BA5F548A58CA4EC9">
     <li id="li_1959FBF14E42469FA8724B37EB58BC54"> <p>Si no desea rastrear ningún vínculo de salida de su SPA, introduzca una entrada en la sección <span class="wintitle">No rastrear nunca</span>. </p> <p>Por ejemplo: <span class="filepath">https://testsite.com/spa/#</span> </p> <p>Se ignorarán todos los vínculos #. Se rastrearán todos los vínculos de salida a otros hosts, como <span class="filepath">https://www.google.com</span>. </p> </li>
     <li id="li_37DD4D37887243FB928C9C04ACE9D39E"> <p>Si hay algún vínculo que quiera rastrear en su SPA, utilice la sección <span class="wintitle">Rastrear siempre</span>. </p> <p>Por ejemplo, si tiene una página <span class="filepath">spa/#/about</span>, puede poner “about” en la sección <span class="wintitle">Rastrear siempre</span>. </p> <p>La página “about” será el único vínculo de salida que se rastreará. No se rastreará ningún otro vínculo de la página (por ejemplo, <span class="filepath">https://www.google.com</span>). </p> </li>
    </ul> <p>Tenga en cuenta que estas dos opciones se excluyen mutuamente. </p> </td> 
  </tr>
  <tr>
   <td colname="col1"> Mantener parámetros de URL </td>
   <td colname="col2"> <p>Conserva las cadenas de consulta. </p> <p>Consulte <a href="../../../vars/config-vars/linkleavequerystring.md">linkLeaveQueryString</a>. </p> </td>
  </tr>
 </tbody>
</table>

---
description: Puede implementar Dynamic Tag Management utilizando una o varias de las opciones de alojamiento disponibles.
keywords: Implementación de Analytics, método de implementación, Dynamic Tag Management, dtm, alojamiento, opciones de alojamiento, akamai, autoalojamiento, auto alojamiento, entrega ftp, alojamiento ftp, descarga de biblioteca
title: Configurar las opciones de alojamiento
topic-fix: Developer and implementation
uuid: 04268f2d-e76f-4fe4-8fcc-f0db3a016502
exl-id: cef5205e-bb21-4d8d-862b-33dc800e1118
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '536'
ht-degree: 100%

---

# Configurar las opciones de alojamiento

Puede implementar [!UICONTROL Dynamic Tag Management] utilizando una o varias de las opciones de alojamiento disponibles.

[!UICONTROL Dynamic Tag Management ofrece diferentes opciones para alojar los archivos JavaScript necesarios].

Para obtener información detallada sobre el alojamiento, consulte [Alojamiento: Ficha Insertar](https://docs.adobe.com/content/help/es-ES/dtm/using/client-side/client-side-information.html) en Documentación del producto de [!UICONTROL Dynamic Tag Management].

En la ficha Insertar, seleccione una opción de alojamiento.

<table id="table_229298207DB64838B6F2477DFFAE073F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Opción de alojamiento </th> 
   <th colname="col2" class="entry"> Descripción </th> 
   <th colname="col3" class="entry"> Implementación </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Akamai </p> </td> 
   <td colname="col2"> <p> La opción de alojamiento más fácil de implementar. </p> <p>Red de envío distribuida globalmente. </p> <p>Agrega dependencias adicionales de infraestructura de terceros (búsqueda en DNS, disponibilidad de Akamai). </p> <p>Para obtener información más detallada, consulte <a href="https://docs.adobe.com/content/help/es-ES/dtm/using/client-side/deployment.html#concept_722B01555D0441ACBB052BC34DC5B67D">Akamai</a> en Documentación del producto de Dynamic Tag Management. </p> </td> 
   <td colname="col3"> 
    <ol id="ol_EF148EF091A645B3962B084963B3C0B0"> 
     <li id="li_7ECE0C331EEE4907A563D581DF1DFEFE">Dynamic Tag Management genera bibliotecas de JavaScript personalizadas. </li> 
     <li id="li_8E2C858290EF4665B2F45ACAFA121CB3">Dynamic Tag Management exporta las bibliotecas de JavaScript personalizadas a Akamai. </li> 
     <li id="li_CE88B10B6E844A56BBB8C575A9363BA9">El sitio web de destino hace referencia a las bibliotecas de Dynamic Tag Management alojadas en Akamai directamente en el nivel de la página. </li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Alojamiento propio: Entrega en FTP </td> 
   <td colname="col2"> <p>Un proceso de <span class="term">push</span>, a través del cual Dynamic Tag Management exporta las bibliotecas de JavaScript personalizadas directamente al servidor de host de contenido web a través del protocolo FTP. </p> <p>Esta solución requiere credenciales y un servidor FTP disponibles en el servidor de contenido web para poder publicar cambios en las bibliotecas personalizadas de Dynamic Tag Management. </p> <p>Para obtener información más detallada, consulte <a href="https://docs.adobe.com/help/es-ES/dtm/using/client-side/deployment.html#task_A7B37CB2C89941A4A4D1F9AF06FC493D">FTP</a> en Documentación del producto de Dynamic Tag Management. </p> </td> 
   <td colname="col3"> 
    <ol id="ol_60348F9C991D4F2B9457006B0F98C834"> 
     <li id="li_24A141C3C7074BF9897C022A22CAE78C">Dynamic Tag Management genera bibliotecas de JavaScript personalizadas. </li> 
     <li id="li_E1E0843060F7447E853EA416A0B033BE">Dynamic Tag Management exporta las bibliotecas de JavaScript personalizadas al servidor host a través de FTP. </li> 
     <li id="li_EAF5D2ABD03B4911A0CFA464AD8791CE">El sitio web de destino hace referencia localmente a las bibliotecas de Dynamic Tag Management personalizadas. </li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Alojamiento propio: Descarga de biblioteca </td> 
   <td colname="col2"> <p>Un proceso de <span class="term">pull</span>, a través del cual la aplicación exporta bibliotecas JavaScript personalizadas
    <!-- to Amazon S3-->. En este caso, se puede acceder a las bibliotecas a través de un proceso alojado en el lado del servidor. </p> <p>Además, las bibliotecas están disponibles a través de descarga de sitios web desde la interfaz de Dynamic Tag Management. </p> <p>Esta solución requiere una recuperación manual y la publicación de las bibliotecas de Dynamic Tag Management o la creación de un proceso automatizado que dirija las bibliotecas de Akamai al servidor de contenido web. </p> <p>Este es el enfoque que más tarda en configurarse, pero también se trata de la opción más flexible y segura. </p> <p>Para comprobar si se hace referencia a la versión más reciente del archivo de biblioteca, utilice el comando. </p> <p>Para obtener información más detallada, consulte <a href="https://docs.adobe.com/content/help/es-ES/dtm/using/client-side/deployment.html#task_B7A42F3B1D3E4B71B0BADD17C181F22A">Descarga de biblioteca</a> en Documentación del producto de Dynamic Tag Management. </p> </td> 
   <td colname="col3"> 
    <ol id="ol_F40B721306FE473496BD657262DFD585"> 
     <li id="li_4EA4D6B555CE4E9CA476C7550C18C061">Dynamic Tag Management genera bibliotecas de JavaScript personalizadas. </li> 
     <li id="li_BA40EBD7AD1546F29D8A209034D06477">Dynamic Tag Management exporta las bibliotecas de JavaScript personalizadas a Akamai. </li> 
     <li id="li_E107E69E386A40F3B067F9991C2979AF">Las bibliotecas de Dynamic Tag Management personalizadas se mueven de forma manual o mediante programación al servidor de contenido web. </li> 
     <li id="li_0809038453B544168A20CE09D7E5AC59">El sitio web de destino hace referencia localmente a las bibliotecas de Dynamic Tag Management personalizadas. </li> 
    </ol> </td> 
  </tr> 
 </tbody> 
</table>

Puede utilizar más de una opción de alojamiento. Por ejemplo, podría alojar los archivos clasificados utilizando Akamai, pero autoalojar el sitio de producción. Tenga en cuenta que cada tipo de alojamiento cuenta con su propio código incrustado y que a una página puede agregarse un solo código incrustado.

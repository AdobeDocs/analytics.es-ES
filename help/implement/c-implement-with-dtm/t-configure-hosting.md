---
description: Puede implementar Dynamic Tag Management utilizando una o varias de las opciones de alojamiento disponibles.
keywords: Implementación de Analytics; método de implementación; administración dinámica de etiquetas; dtm; hosting; opciones de alojamiento; akamai; self hosting; autoalojamiento; ftp delivery; ftp hosting; descarga de biblioteca
seo-description: Puede implementar Dynamic Tag Management utilizando una o varias de las opciones de alojamiento disponibles.
seo-title: Configuración de las opciones de alojamiento
solution: Analytics
title: Configuración de las opciones de alojamiento
topic: Desarrollador e implementación
uuid: 04268 f 2 d-e 76 f -4 fe 4-8 fcc-f 0 db 3 a 016502
translation-type: tm+mt
source-git-commit: 6250335d05c8e7799802fce26192896a7a6598fe

---


# Configuración de las opciones de alojamiento

You can deploy [!UICONTROL Dynamic Tag Management] using one or more of the available hosting options.

[!UICONTROL Dynamic Tag Management ofrece diferentes opciones para alojar los archivos JavaScript necesarios.]

Para obtener información detallada sobre el alojamiento, consulte [Alojamiento: Ficha Insertar](https://marketing.adobe.com/resources/help/en_US/dtm/deployment.html) en Documentación del producto de Dynamic Tag Management.

En la ficha Insertar, seleccione una opción de alojamiento.

<table id="table_229298207DB64838B6F2477DFFAE073F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Opción de alojamiento  </th> 
   <th colname="col2" class="entry"> Descripción </th> 
   <th colname="col3" class="entry"> Implementación </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Akamai </p> </td> 
   <td colname="col2"> <p> La opción de alojamiento más fácil de implementar. </p> <p>Red de envío distribuida globalmente. </p> <p>Agrega dependencias adicionales de infraestructura de terceros (búsqueda en DNS, disponibilidad de Akamai). </p> <p>Para obtener información más detallada, consulte <a href="https://marketing.adobe.com/resources/help/en_US/dtm/akamai.html" format="html" scope="external">Akamai</a> en Documentación del producto de Dynamic Tag Management. </p> </td> 
   <td colname="col3"> 
    <ol id="ol_EF148EF091A645B3962B084963B3C0B0"> 
     <li id="li_7ECE0C331EEE4907A563D581DF1DFEFE">Dynamic Tag Management genera bibliotecas de JavaScript personalizadas. </li> 
     <li id="li_8E2C858290EF4665B2F45ACAFA121CB3">Dynamic Tag Management exporta las bibliotecas de JavaScript personalizadas a Akamai. </li> 
     <li id="li_CE88B10B6E844A56BBB8C575A9363BA9">El sitio web de destino hace referencia a las bibliotecas de Dynamic Tag Management alojadas en Akamai directamente en el nivel de la página. </li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Alojamiento propio: Entrega en FTP </td> 
   <td colname="col2"> <p>A <span class="term"> push</span> approach, whereby Dynamic Tag Management exports custom JavaScript libraries directly to the web content server host via the FTP protocol. </p> <p>Esta solución requiere credenciales y un servidor FTP disponibles en el servidor de contenido web para poder publicar cambios en las bibliotecas personalizadas de Dynamic Tag Management. </p> <p>Para obtener información más detallada, consulte <a href="https://marketing.adobe.com/resources/help/en_US/dtm/deployment_ftp.html" format="html" scope="external">FTP</a> en Documentación del producto de Dynamic Tag Management. </p> </td> 
   <td colname="col3"> 
    <ol id="ol_60348F9C991D4F2B9457006B0F98C834"> 
     <li id="li_24A141C3C7074BF9897C022A22CAE78C">Dynamic Tag Management genera bibliotecas de JavaScript personalizadas. </li> 
     <li id="li_E1E0843060F7447E853EA416A0B033BE">Dynamic Tag Management exporta las bibliotecas de JavaScript personalizadas al servidor host a través de FTP. </li> 
     <li id="li_EAF5D2ABD03B4911A0CFA464AD8791CE">El sitio web de destino hace referencia localmente a las bibliotecas de Dynamic Tag Management personalizadas. </li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Alojamiento propio: Descarga de biblioteca </td> 
   <td colname="col2"> <p>A <span class="term"> pull</span> approach, whereby the application exports custom JavaScript libraries
     <!-- to Amazon S3-->. En este caso, se puede acceder a las bibliotecas a través de un proceso alojado en el lado del servidor. </p> <p>Además, las bibliotecas están disponibles a través de descarga de sitios web desde la interfaz de Dynamic Tag Management. </p> <p>Esta solución requiere una recuperación manual y la publicación de las bibliotecas de Dynamic Tag Management o la creación de un proceso automatizado que dirija las bibliotecas de Akamai al servidor de contenido web. </p> <p>Este es el enfoque que más tarda en configurarse, pero también se trata de la opción más flexible y segura. </p> <p>Para comprobar si se hace referencia a la versión más reciente del archivo de biblioteca, utilice el comando </p> <p>Para obtener información más detallada, consulte <a href="https://marketing.adobe.com/resources/help/en_US/dtm/deployment_download.html" format="html" scope="external">Descarga de biblioteca</a> en Documentación del producto de Dynamic Tag Management. </p> </td> 
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

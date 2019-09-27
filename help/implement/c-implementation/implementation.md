---
description: 'null'
seo-description: 'null'
seo-title: Hoja de ruta de implementación
title: Hoja de ruta de implementación
uuid: 988bcca5-67ae-4e3f-97e6-6a42030b1962
translation-type: tm+mt
source-git-commit: 3c5cc9275c9978caf57e4e29704e23405ac24b65

---


# Hoja de ruta de implementación

## Nuevos usuarios {#section_77433E4FC5ED4C6BAFC1E72EB61C4503}

Si es nuevo en Adobe Analytics, puede crear rápidamente su primer grupo de informes (repositorio de datos) de Analytics con la guía de [Introducción a Adobe Analytics](https://marketing.adobe.com/resources/help/en_US/analytics/getting-started/). Then, you can deploy Analytics code using [Experience Platform Launch](https://docs.adobelaunch.com/).

## Hoja de ruta de implementación {#section_E3DD8D199B744FFB9E9B386A44220206}

<table id="table_1683413EA0E34DBC9291832647B68E96"> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> Paso </th> 
   <th colname="col1" class="entry"> Tarea </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <img  src="assets/step1_icon.png" id="image_21F30BBFC0A249F8B0E1A50EBBEED77D" /> </td> 
   <td colname="col1"> Elegir un método de implementación. </td> 
   <td colname="col2"> <p>Estas son algunas maneras comunes de implementar Analytics: </p> <p> 
     <ul id="ul_A7475867861540EFBD77AEE8C6DAD418"> 
      <li id="li_035E2619670F4D04A7F708625A9C01EF"> <a href="https://docs.adobelaunch.com/" format="https" scope="external"> Inicio de la plataforma de experiencias </a> (recomendado) <p>Esta guía le explica cuanto necesita saber acerca del uso de las capacidades de administración de etiquetas de sitios web y los SDK móviles de Adobe, y sobre el modo de implementarlas. </p> </li> 
      <li id="li_996FA2F5B0E149399CED391AB5235D8A"> <a href="../../implement/c-implement-with-dtm/dtm-implementation-overview.md" format="dita" scope="local"> Dynamic Tag Management </a> <p>Esta guía contiene información específica de Analytics que lo guiará en la implementación de Dynamic Tag Management. </p> </li> 
      <li id="li_18E6AD6D864246D0BA26DAA1D91DD811"> <a href="../../implement/js-implementation/javascript-implementation-overview.md" format="dita" scope="local"> JavaScript </a> <p>Esta guía contiene una descripción de las variables de recopilación de datos y detalles sobre cómo implementar el código de recopilación de datos en JavaScript, e incluye un <a href="https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/video/video_js.html" format="https" scope="external">vídeo </a>. </p> </li> 
      <li id="li_85EC7A0AC5E04EE6981ED72A88C5D1FD"> <a href="https://marketing.adobe.com/resources/help/en_US/reference/developer.html" format="html" scope="external"> SDK de Analytics </a> <p>Utilice los SDK de Analytics para gestionar lo siguiente: </p> <p> 
        <ul id="ul_F67F2E1964724800A84445A36DFB8E86"> 
         <li id="li_9C43F051EB5B4EA7A4C14EC1513DB824"> <a href="https://marketing.adobe.com/resources/help/en_US/mobile/ios/analytics_main.html" format="html" scope="external"> Aplicaciones móviles en iOS </a> </li> 
         <li id="li_4354E44EB8B3494A88578C1621EF5BAC"> <a href="https://marketing.adobe.com/resources/help/en_US/mobile/android/analytics_main.html" format="html" scope="external"> Aplicaciones móviles en Android </a> </li> 
        </ul> </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <img  src="assets/step2_icon.png" id="image_02CFDC007BF1486AA312698EBFFA79F7" /> </td> 
   <td colname="col1"> Configure el servicio de identidad. </td> 
   <td colname="col2"> <p>(Formerly <span class="term"> Visitor ID service </span>.) Consulte <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-setup-analytics.html" format="https" scope="external"> Configurar el servicio de identidad para Analytics </a>. </p> 
    <draft-comment> 
     <p>En <code>VisitorAPI.js</code>, añada el siguiente código de inicialización de ID de visitante al principio del archivo: </p> 
     <code class="syntax javascript">
       var visitor = Visitor.getInstance("INSERT-MCORG-ID-HERE"); 
      visitor.trackingServer = "INSERT-TRACKING-SERVER-HERE"; // igual que s.trackingServer visitor.trackingServerSecure = "INSERT-SECURE-TRACKING-SERVER-HERE"; //igual que s.trackingServerSecure /* =========== DO NOT ALTER ANYTHING BELOW LINE ! ============ </code> 
     <ul id="ul_769BA118CC244308A805079C2CBECC12"> 
      <li id="li_D366EBDE24CB433EA523DB228CB2FAF1"> <code> "INSERT-MCORG-ID-HERE" </code> : (obligatorio) este ID de organización de Adobe Experience Cloud se envía a su administrador cuando se aprovisiona su empresa para Adobe Experience Cloud. </li> 
      <li id="li_4F9704A6A6EA4334A3758F99B8D67C9D"> <code> "INSERT-TRACKING-SERVER-HERE"</code> (obligatorio): su servidor de seguimiento de Analytics. </li> 
      <li id="li_C578420458D649228E54D9809AF62627"> <code> "INSERT-SECURE-TRACKING-SERVER-HERE"</code>: (requerido si está habilitado SSL) su servidor de seguimiento seguro de Analytics. </li> 
     </ul> 
    </draft-comment> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <img  src="assets/step3_icon.png" id="image_76B61DEABE3849CCB39135FDD7399EAA" /> </td> 
   <td colname="col1"> Utilizar el método de implementación elegido para actualizar e implementar el código de página. </td> 
   <td colname="col2"> <p>Coloque el código de página inmediatamente después de la etiqueta <code>&lt;body&gt;</code> de apertura de todas las páginas que desee rastrear. Como mínimo, actualice las siguientes variables: </p> 
    <ul id="ul_29200A6E8DA14386BDA242AD8B270FEB"> 
     <li id="li_FB24D2CB9241401A83BD13EE342A7810"> <code> var s=s_gi("INSERT-RSID-HERE") </code> </li> 
     <li id="li_463A35BA06CC4618B4AF17CD7E83AED5"> <code> s.pageName="INSERT-NAME-HERE" // for example, s.pageName=document.title </code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <img  src="assets/step4_icon.png" id="image_B255E5EAE7BB43FC946D0E9DFCA83003" /> </td> 
   <td colname="col1"> Validar la implementación. </td> 
   <td colname="col2"> <p> <a href="../../implement/impl-testing/impl-validation/impl-validation.md" format="dita" scope="local"> Prueba y validación</a> Proporciona información sobre la validación de la implementación. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <img  src="assets/step5_icon.png" id="image_844E896941E2489A943BE10AD710ED36" /> </td> 
   <td colname="col1"> Usar Adobe Experience Cloud Debugger para verificar que se están enviando los datos. </td> 
   <td colname="col2"> <p>Install the <a href="../../implement/impl-testing/debugger.md#topic_E05CEAF0682E483A9AB147D774CF2188" format="dita" scope="local"> Experience Cloud Debugger </a>. A continuación, cargue una página en la que haya implementado el código de página y abra el depurador. El depurador mostrará los detalles sobre los datos de recopilación que se han enviado. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Más información {#section_64B6A948DF4A4B5E9E1D22549F8C508B}

Para obtener información sobre las diferencias entre los métodos [!UICONTROL Experience Platform Launch], [!UICONTROL Dynamic Tag Management]y JavaScript, consulte [Elegir un método](../../implement/c-implementation-methods/choose-implementation-method.md#concept_97CE27B16410422EB28B4B9CE3B9529B)de implementación.

Para obtener una descripción concisa del proceso y ayuda para la configuración rápida de su primer grupo de informes de Analytics, consulte [Introducción a la implementación de Analytics](https://marketing.adobe.com/resources/help/en_US/dtm/get_started.html) en la guía Introducción a Analytics.

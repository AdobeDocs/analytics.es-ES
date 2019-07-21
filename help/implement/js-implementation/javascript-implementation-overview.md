---
description: Para comenzar a utilizar Analytics, los datos deben enviarse a un grupo de informes para que se muestren en los informes.
keywords: Implementación de Analytics; javascript; implementación de javascript; appmeasurement; descargar appmeasurement; Servicio de identidad; visitorapi. js; almacenamiento en caché; appmeasurement compression
seo-description: Para comenzar a utilizar Analytics, los datos deben enviarse a un grupo de informes para que se muestren en los informes.
seo-title: Descripción general de la implementación de JavaScript
solution: Analytics
title: Descripción general de la implementación de JavaScript
topic: Desarrollador e implementación
uuid: bb 661 d 8 c-faf 9-4454-ac 3 c -0 c 1 a 4 c 0 a 9336
translation-type: tm+mt
source-git-commit: 4e7a8bab956503093633deff0a64e8c7af2d5497

---


# Descripción general de la implementación de JavaScript

Para comenzar a utilizar Analytics, los datos deben enviarse a un grupo de informes para que se muestren en los informes.

The easiest and recommended way to send data to [!DNL Analytics] is by using [Dynamic Tag Management](../../implement/c-implement-with-dtm/dtm-implementation-overview.md). Sin embargo, en algunos casos tal vez prefiera implementar Analytics utilizando el método JavaScript, más antiguo.

>[!NOTE]
>
>Esta sección describe el método heredado de implementación de Analytics. Todos los clientes de Analytics tienen acceso a [Dynamic Tag Management](https://marketing.adobe.com/resources/help/en_US/dtm/), el método estándar para implementar etiquetas de Experience Cloud.

## Pasos de la implementación {#section_73961BAD5BB4430A95E073DE5C026277}

A la hora de implementar correctamente una página con código de recopilación de datos, debe disponer de acceso a los servidores de alojamiento para cargar contenido nuevo en el sitio web. También resulta útil contar con un sitio existente en el que implementar el código.

A continuación se muestran los pasos de una implementación básica de Analytics.

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
   <td colname="col1"> Descargar AppMeasurement para JavaScript y el servicio de ID de visitante. </td> 
   <td colname="col2"> <p>La descarga se encuentra disponible en <a href="https://marketing.adobe.com/resources/help/en_US/reference/?f=code_manager_admin" format="http" scope="external">Administrador de códigos </a>. </p> <p>Este zip de descarga contiene varios archivos. <code> AppMeasurement.js</code> y <code>VisitorAPI.js</code> son los archivos relevantes para la implementación de Analytics. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <img  src="assets/step2_icon.png" id="image_02CFDC007BF1486AA312698EBFFA79F7" /> </td> 
   <td colname="col1"> Configure el servicio de identidad. </td> 
   <td colname="col2"> <p>(Formerly <span class="term"> Visitor ID service </span>.) See <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-setup-analytics.html" format="https" scope="external"> Set Up the Identity Service for Analytics </a>. </p> 
    <draft-comment> 
     <p>En <code>VisitorAPI.js</code>, añada el siguiente código de inicialización de ID de visitante al principio del archivo: </p> 
     <code class="syntax javascript">
       var&nbsp;visitor&nbsp;=&nbsp;Visitor.getInstance("INSERT-MCORG-ID-HERE"); visitor.trackingServer&nbsp;=&nbsp;"INSERT-TRACKING-SERVER-HERE";&nbsp;//&nbsp;same&nbsp;as&nbsp;s.trackingServer visitor.trackingServerSecure&nbsp;=&nbsp;"INSERT-SECURE-TRACKING-SERVER-HERE";&nbsp;//same&nbsp;as&nbsp;s.trackingServerSecure /* == DO NOT ALTER ANYTHING BELOW THIS LINE ==
     </code> 
     <ul id="ul_769BA118CC244308A805079C2CBECC12"> 
      <li id="li_D366EBDE24CB433EA523DB228CB2FAF1"> <code> "INSERT-MCORG-ID-HERE" </code> - (Obligatorio) Este ID de organización de Adobe Experience Cloud se envía al administrador cuando se aprovisiona su empresa para Adobe Experience Cloud. </li> 
      <li id="li_4F9704A6A6EA4334A3758F99B8D67C9D"> <code> "INSERT-TRACKING-SERVER-HERE" </code> - (Obligatorio) Su servidor de seguimiento de Analytics. </li> 
      <li id="li_C578420458D649228E54D9809AF62627"> <code> "INSERT-SECURE-TRACKING-SERVER-HERE" </code> - (Requerido si está habilitado SSL) Su servidor de seguimiento seguro de Analytics. </li> 
     </ul> 
    </draft-comment> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <img  src="assets/step3_icon.png" id="image_76B61DEABE3849CCB39135FDD7399EAA" /> </td> 
   <td colname="col1"> Actualizar <code> AppMeasurement.js </code>. </td> 
   <td colname="col2"> <p>Copie el <a href="../../implement/js-implementation/appmeasure-mjs-pagecode.md#section_4351543F2D6049218E18B48769D471E2" format="dita" scope="local"> Ejemplo de código de AppMeasurement.js</a> y péguelo al principio del archivo <code> AppMeasurement.js </code>. Como mínimo, actualice las siguientes variables: </p> 
    <ul id="ul_62FA640BD2604E589650A92158272615"> 
     <li id="li_54E56B483B3A416EA27D7B540D60E39F"> <code> s.account="INSERT-RSID-HERE" </code> </li> 
     <li id="li_00A958289BB045379B436F13287E03D5"> <code> s.trackingServer="INSERT-TRACKING-SERVER-HERE" </code> </li> 
     <li id="li_C0779ADF780440ED876236AEB1FB5DCC"> <code> s.visitorNamespace = "INSERT-NAMESPACE-HERE" </code> </li> 
     <li id="li_93072B656C134D8C89195B7F2D7D8F05"> <code> s.visitor = Visitor.getInstance("INSERT-MCORG-ID-HERE") </code> </li> 
    </ul> <p> See <a href="https://helpx.adobe.com/analytics/kb/determining-data-center.html" format="https" scope="external"> Correctly populate the trackingServer and trackingServerSecure variable </a> or contact Client Care if you are unsure about any of these values. Si no están correctamente configurados, su implementación no recopilará los datos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <img  src="assets/step4_icon.png" id="image_B255E5EAE7BB43FC946D0E9DFCA83003" /> </td> 
   <td colname="col1"> Alojar <code> AppMeasurement.js </code> y <code> VisitorAPI.js </code>. </td> 
   <td colname="col2"> <p>Estos archivos JavaScript principales deben alojarse en un servidor web al que se pueda acceder desde todas las páginas del sitio. En el siguiente paso necesitará la ruta a estos archivos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <img  src="assets/step5_icon.png" id="image_844E896941E2489A943BE10AD710ED36" /> </td> 
   <td colname="col1"> Introducir una referencia a <code> AppMeasurement.js </code> y <code> VisitorAPI.js </code> en todas las páginas del sitio. </td> 
   <td colname="col2"> <p> Para incluir el servicio de ID de visitante, agregue la línea de código siguiente en la etiqueta <code> &lt;head&gt; </code> o &lt;body&gt; de cada página. <code> VisitorAPI.js </code> debe incluirse antes de <code> AppMeasurement.js </code>: </p> 
    <code class="syntax html">
      &lt;script language="JavaScript" type="text/javascript" src="https://INSERT-DOMAIN-AND-PATH-TO-CODE-HERE/VisitorAPI.js" &gt; &lt;/script &gt;
    </code> <p> Para incluir AppMeasurement para JavaScript, agregue la línea de código siguiente en la etiqueta <code> &lt;head&gt; </code> o <code> &lt;body&gt; </code> de cada página: </p> 
    <code class="syntax html">
      &lt;script language="JavaScript" type="text/javascript" src="https://INSERT-DOMAIN-AND-PATH-TO-CODE-HERE/AppMeasurement.js"&gt;&lt;/script &gt; 
      </code>
  </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <img  src="assets/step6_icon.png" id="image_1C4293CA98F04EE2ADA69EAB95BDE8B1" /> </td> 
   <td colname="col1"> Actualizar e implementar el código de página. </td> 
   <td colname="col2"> <p>Copie el contenido de <a href="../../implement/js-implementation/appmeasure-mjs-pagecode.md#section_042412C29CC249E298F19B2BC2F43CE7" format="dita" scope="local">Ejemplo de código de página</a> y péguelo inmediatamente después de la etiqueta <code>&lt;body&gt;</code> de apertura de todas las páginas que desee rastrear. Como mínimo, actualice las siguientes variables: </p> 
    <ul id="ul_29200A6E8DA14386BDA242AD8B270FEB"> 
     <li id="li_FB24D2CB9241401A83BD13EE342A7810"> <code> var s=s_gi("INSERT-RSID-HERE") </code> </li> 
     <li id="li_463A35BA06CC4618B4AF17CD7E83AED5"> <code> s.pageName="INSERT-NAME-HERE" // for example, s.pageName=document.title </code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <img  src="assets/step7_icon.png" id="image_A423CBF386AF4E5986E8CBB6E31CD3E5" /> </td> 
   <td colname="col1"> Usar DigitalPulse Debugger para verificar que se están enviando los datos. </td> 
   <td colname="col2"> <p>Instale el bookmarklet <a href="../../implement/impl-testing/debugger.md#concept_B26FFE005EDD4E0FACB3117AE3E95AA2" format="dita" scope="local"> Adobe Debugger</a>. A continuación, cargue una página en la que haya implementado el código de página y abra el depurador. El depurador mostrará los detalles sobre los datos de recopilación que se han enviado. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Almacenamiento en caché {#section_4E2D1D962DF046418134C43CFC49AD4A}

El archivo JavaScript se almacena en caché en el explorador del visitante cuando se carga por primera vez y, por lo general, solo se descarga una vez por sesión. El archivo no se descarga en cada página, aunque lo usen todas las páginas del sitio. El cálculo promedio indica que, en la mayoría de sitios web, se registran varias vistas de página por sesión por usuario. De este modo, si se transfieren a este archivo los elementos JavaScript que se usan varias veces, se pueden reducir los datos que se descargan de forma general.

## Compresión de AppMeasurement para JavaScript {#section_C10BBC84C81C414088F97363D29E021B}

Si le preocupa el tamaño de página del código H (AppMeasurement para JavaScript 1.0 ya viene comprimido), Adobe recomienda considerar la posibilidad de comprimir el archivo con GZIP. Todos los exploradores principales admiten GZIP, que ofrece un mejor rendimiento que la compresión de JavaScript para comprimir y descomprimir el archivo JavaScript [!DNL s_code.js] principal.

Los siguientes vínculos explican cómo usar la funcionalidad GZIP en el sitio para gestionar la compresión del código JavaScript de [!DNL s_code.js]:

[Módulo mod_deflate de Apache](https://httpd.apache.org/docs/2.0/mod/mod_deflate.html)

[Habilitar la compresión gzip con Tomcat y Flex](https://www.cubicleman.com/2007/04/06/enabling-gzip-compression-with-tomcat-and-flex/)

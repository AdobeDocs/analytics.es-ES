---
description: El sistema de fuentes de datos admite las siguientes variables al procesar datos como una llamada a servidor estándar (Genérico > Procesamiento completo).
title: Procesamiento completo
topic: Desarrollador e implementación
translation-type: tm+mt
source-git-commit: 4359f451692b86087efe27d4b3ec49ca85b7addc
workflow-type: tm+mt
source-wordcount: '727'
ht-degree: 98%

---


# Procesamiento completo

>[!IMPORTANT]
>
>Adobe recomienda que los clientes utilicen la [API de inserción masiva de datos (BDIA)](https://www.adobe.io/apis/experiencecloud/analytics/docs.html) en lugar de las fuentes de datos de procesamiento completo. Adobe tiene planificado retirar las fuentes de datos de procesamiento completo en el futuro. [Más información](/help/import/c-data-sources/c-datasrc-types/datasrc-fullproc-eol.md)

El sistema de fuentes de datos admite las siguientes variables al procesar datos como una llamada a servidor estándar (Genérico > Procesamiento completo).

Los datos de fuentes de datos de procesamiento completo se procesan como si se recibieran en los servidores de Adobe a la hora especificada (cada visita contiene una marca de tiempo).

* [Perfil del visitante](/help/import/c-data-sources/c-datasrc-types/datasrc-full-processing.md#section_6065627D0C144506965F562C80AE67F8)
* [Referencia sobre columnas](/help/import/c-data-sources/c-datasrc-types/datasrc-full-processing.md#section_92BAE76639E3404E97276B1BE0581078)

## Perfil del visitante {#section_6065627D0C144506965F562C80AE67F8}

Los datos de fuentes de datos de procesamiento completo se procesan con perfiles de visitante independientes, de modo que, aunque el ID de visitante indicado en los datos cargados coincida con los datos recopilados mediante JavaScript u otra biblioteca de AppMeasurement, los perfiles de visitante no están conectados desde un punto de vista de asignación de eVar.

Pongamos como ejemplo que un usuario que tiene el ID de visitante `"user@example.com"` visita su sitio web desde una campaña de marketing llamada “Rebajas de primavera”, que se almacena en la variable de campaña. Si más tarde se carga una transacción con el mismo ID de visitante, los ingresos y los eventos de éxito cargados mediante fuentes de datos de procesamiento completo no se atribuyen a la campaña &quot;Rebajas de primavera&quot;.

## Referencia sobre columnas {#section_92BAE76639E3404E97276B1BE0581078}

<table id="table_AAC04491D643467B9C80FDEF88130B13"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Variable JavaScript </th> 
   <th colname="col2" class="entry"> Variable de columna de procesamiento completo </th> 
   <th colname="col3" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>campaign </p> </td> 
   <td colname="col2"> <p>campaign </p> </td> 
   <td colname="col3"> <p>Código de seguimiento de la campaña de conversión. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>canal </p> </td> 
   <td colname="col2"> <p>canal </p> </td> 
   <td colname="col3"> <p>Cadena correspondiente al canal (por ejemplo, Sección de deportes). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>currencyCode </p> </td> 
   <td colname="col2"> <p>currencyCode </p> <p>Nota: en fuentes de datos estándar esta variable también se puede indicar como <code> currency code </code>. </p> </td> 
   <td colname="col3"> <p>Código de la moneda en que están expresados los ingresos (por ejemplo, USD). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>timestamp </p> </td> 
   <td colname="col2"> <p>date </p> </td> 
   <td colname="col3"> <p>Use el formato de fecha ISO 8601 <code> YYYY-MM-DDThh:mm:ss±UTC_offset </code> (por ejemplo, <code> 2013-09-01T12:00:00-07:00 </code>) o el formato de tiempo de Unix (UTF; la cantidad de segundos transcurridos desde el 1 de enero de 1970). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>eVar<i>N</i> </p> </td> 
   <td colname="col2"> <p>eVar<i>N</i> (es decir, &lt;eVar2&gt;…&lt;/eVar2&gt;) </p> </td> 
   <td colname="col3"> <p>Nombre de la eVar de conversión. Se pueden usar hasta 75 eVars ( <span class="varname"> eVar1 </span> - <span class="varname"> eVar75 </span>). </p> <p>Puede indicar el nombre de la eVar (eVar12) o un nombre descriptivo ("Campaña publicitaria 3"). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Events </p> </td> 
   <td colname="col2"> <p>Events </p> </td> 
   <td colname="col3"> <p>Cadena de eventos. El formato se aplica con la misma sintaxis que la variable <a href="https://docs.adobe.com/content/help/es-ES/analytics/implementation/vars/page-vars/events/event-serialization.html"  >s.events</a>. </p> <p>Por ejemplo: </p> 
    <code>
      scAdd,event1,event7 
    </code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>hier<i>N</i> </p> </td> 
   <td colname="col2"> <p>hier<i>N</i> (es decir, &lt;hier2&gt;…&lt;/hier2&gt;) </p> </td> 
   <td colname="col3"> <p>Nombre de la jerarquía. Se pueden usar hasta cinco jerarquías ( <span class="varname"> hier1</span> - <span class="varname">hier5 </span>). </p> <p>Puede indicar el nombre predeterminado de la jerarquía (<span class="varname">hier2</span>) o un nombre descriptivo (<span class="term">Barcelona </span>). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>linkName </p> </td> 
   <td colname="col2"> <p>linkName </p> </td> 
   <td colname="col3"> <p>Nombre del vínculo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>linkType </p> </td> 
   <td colname="col2"> <p>linkType </p> </td> 
   <td colname="col3"> <p>Tipo de vínculo. Los valores admitidos son: </p> 
    <ul id="ul_E441013055A9447AB6C3FB05B6099F7D"> 
     <li id="li_A33F66F30B60479284F72AE3AD4BF499"> <b>d</b>: vínculo de descarga </li> 
     <li id="li_182F695AA2D044DAB036BAFE38BC3915"> <b>e</b>: vínculo de salida </li> 
     <li id="li_4FD4D542D1774607860BEF41C1B090D1"> <b>o</b>: vínculo personalizado. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>linkURL </p> </td> 
   <td colname="col2"> <p>linkURL </p> </td> 
   <td colname="col3"> <p>HREF del vínculo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>pageName </p> </td> 
   <td colname="col2"> <p>pageName </p> </td> 
   <td colname="col3"> <p>Nombre de la página </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>pageType </p> </td> 
   <td colname="col2"> <p>pageType </p> </td> 
   <td colname="col3"> <p>Tipo de página (“Página de error”). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>pageURL </p> </td> 
   <td colname="col2"> <p>pageURL </p> </td> 
   <td colname="col3"> <p>Dirección URL de la página (por ejemplo, <code>https://www.example.com/index.html)</code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>products </p> </td> 
   <td colname="col2"> <p>products </p> </td> 
   <td colname="col3"> <p>Lista de productos (por ejemplo, <code> "Sports;Ball;1;5.95"</code>). Puede contener un valor máximo de 4096 bytes por fila.</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>prop1 - prop75 </p> </td> 
   <td colname="col2"> <p>prop<i>N</i> (es decir, &lt;prop2&gt;…&lt;/prop2&gt;) </p> </td> 
   <td colname="col3"> <p>Cadena de número de propiedad (por ejemplo, <span class="term"> Sección de deportes </span>). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>purchaseID </p> </td> 
   <td colname="col2"> <p>purchaseID </p> </td> 
   <td colname="col3"> <p>Número de ID de la compra. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>s_account </p> </td> 
   <td colname="col2"> <p>reportSuiteID </p> </td> 
   <td colname="col3"> <p>ID del grupo de informes a los cuales atribuir la visita. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>servidor </p> </td> 
   <td colname="col2"> <p>servidor </p> </td> 
   <td colname="col3"> <p>Cadena del servidor. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>state </p> </td> 
   <td colname="col2"> <p>state </p> </td> 
   <td colname="col3"> <p>Cadena de estado de la conversión. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>zip </p> </td> 
   <td colname="col2"> <p>zip </p> </td> 
   <td colname="col3"> <p>Código postal de la conversión. </p> </td> 
  </tr> 
 </tbody> 
</table>

En la tabla siguiente se muestran las variables de tráfico que se llenan automáticamente cuando se usan las bibliotecas JavaScript. Estas propiedades no tienen variables asociadas, pero se pueden importar mediante fuentes de datos.

<table id="table_FDBC5BD225644AA09078C0570BE709FE"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Variable de columna de procesamiento completo </p> </th> 
   <th colname="col2" class="entry"> <p>Descripción </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>browserHeight </p> </td> 
   <td colname="col2"> <p>Altura de la ventana del navegador, en píxeles (por ejemplo, 768). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>browserWidth </p> </td> 
   <td colname="col2"> <p>Ancho de la ventana del navegador, en píxeles (por ejemplo, 1024). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>charSet </p> </td> 
   <td colname="col2"> <p>Conjunto de caracteres admitido para el sitio web. Por ejemplo: UTF-8, ISO-8859-1, etc. </p> <p>Consulte el documento técnico <a href="https://docs.adobe.com/content/help/es-ES/analytics/implementation/vars/config-vars/configuration-variables.html#concept_E65B9A8F75C3482C87D0D455805F89BD"  >Conjunto de caracteres de byte múltiple</a> (internacionalización) para obtener una lista exhaustiva. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>clickAction </p> </td> 
   <td colname="col2"> <p>Identificador de objeto correspondiente al mapa de clics del visitante (oid) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>clickActionType </p> </td> 
   <td colname="col2"> <p>Tipo de identificador de objeto correspondiente al mapa de clics del visitante (oidt) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>clickContext </p> </td> 
   <td colname="col2"> <p>Identificador de página correspondiente al mapa de clics del visitante (pid) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>clickContextType </p> </td> 
   <td colname="col2"> <p>Tipo de identificador de página correspondiente al mapa de clics del visitante (pidt) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>clickSourceID </p> </td> 
   <td colname="col2"> <p>Índice de fuentes correspondiente al mapa de clics del visitante (oi) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>clickTag </p> </td> 
   <td colname="col2"> <p>Nombre de etiqueta de objetos correspondiente al mapa de clics del visitante (ot) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>colorDepth </p> </td> 
   <td colname="col2"> <p>Profundidad de color del monitor en bits (por ejemplo, 24). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>connectionType </p> </td> 
   <td colname="col2"> <p>Tipo de conexión del visitante (<span class="term">lan</span> o <span class="term">modem</span>). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>cookiesEnabled </p> </td> 
   <td colname="col2"> <p>Y o N para indicar si el visitante admite cookies de sesión del sitio original. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>currencyCode </p> </td> 
   <td colname="col2"> <p>El código de moneda predeterminado que se usa en el sitio web. </p> <p>Por ejemplo, USD = dólares estadounidenses, EUR = euros, JPY = yen japonés, etc. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>homePage </p> </td> 
   <td colname="col2"> <p>Y o N, según si la página actual es la página principal del visitante. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>javaEnabled </p> </td> 
   <td colname="col2"> <p>Y o N para indicar si el visitante tiene Java habilitado. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>javaScriptVersion </p> </td> 
   <td colname="col2"> <p>Versión de JavaScript (por ejemplo, 1.3). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>plugins </p> </td> 
   <td colname="col2"> <p>Lista separada por punto y coma de los nombres de los complementos del navegador. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>propN </p> </td> 
   <td colname="col2"> <p>Valores de las propiedades. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>referente </p> </td> 
   <td colname="col2"> <p>Dirección URL del referente de la página. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>resolution </p> </td> 
   <td colname="col2"> <p>Resolución de pantalla (por ejemplo, 1024x768). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>scXmlVer </p> </td> 
   <td colname="col2"> <p>Número de versión de la solicitud XML de los informes de marketing (por ejemplo, 1.0). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>timezone </p> </td> 
   <td colname="col2"> <p>Diferencia entre la zona horaria del visitante y GMT, en horas (por ejemplo, -8). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>visitorID </p> </td> 
   <td colname="col2"> <p>Número de ID del visitante. </p> </td> 
  </tr> 
 </tbody> 
</table>


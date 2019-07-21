---
description: Las dimensiones que pueden leerse y escribirse (a menos que se indique lo contrario) con reglas de procesamiento.
seo-description: Las dimensiones que pueden leerse y escribirse (a menos que se indique lo contrario) con reglas de procesamiento.
seo-title: Dimensiones disponibles para las reglas de procesamiento
solution: Analytics
subtopic: Reglas de procesamiento
title: Dimensiones disponibles para las reglas de procesamiento
topic: Herramientas de administración
uuid: ba 73 ab 59-a 8 cf -491 c -8757-5 fb 03 d 6 b 0745
translation-type: tm+mt
source-git-commit: 01a6fc7e44dc71b868bd38a4f6a5a4089eae6349

---


# Dimensiones disponibles para las reglas de procesamiento

Las dimensiones que pueden leerse y escribirse (a menos que se indique lo contrario) con reglas de procesamiento.

## Valores personalizados y datos de contexto {#section_7A5E1810CAC34B0BBC69F8F5F7C75AA5}

<table id="table_5011C501D5DC489E87A42FFC51DEB40D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Valor </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Valor personalizado </p> </td> 
   <td colname="col2"> <p>Texto o valores personalizados escritos directamente en la acción de una regla de procesamiento. Estos valores están disponibles en reglas y condiciones subsiguientes. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Valor concatenado </p> </td> 
   <td colname="col2"> <p>Valores creados combinando dos valores. Por ejemplo, se puede combinar categoría y nombre de página para crear una subcategoría. Estos valores están disponibles en reglas y condiciones subsiguientes. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Valores modificados </p> </td> 
   <td colname="col2"> <p>Si se cambia un valor de variable usando reglas de procesamiento, el valor modificado se usa en reglas y condiciones subsiguientes. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Variables de datos de contexto </p> </td> 
   <td colname="col2"> <p>Variables con nombre que se envían con una visita. </p> <p>Nota: Los datos de las variables de datos de contexto se deben copiar en variables de informes para que aparezcan en los informes. Tampoco pueden verse en ninguna interfaz de informes, ni siquiera en las fuentes de datos del flujo de navegación. </p> <p> <a href="../../../admin/admin/c-processing-rules/processing-rules-examples/processing-rules-copy-context-data.md#concept_43AA4980A2D847D6A3BEC50BCC0780E7" format="dita" scope="local"> Copiar una variable de datos de contexto en una eVar </a> </p> <p> <a href="../../../admin/admin/c-processing-rules/processing-rules-examples/processing-rules-copy-context-data-event.md#concept_359B4E165ED442938A8EB6A55A725682" format="dita" scope="local"> Definir un evento con una variable de datos de contexto </a> </p> <p> <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/index.html?f=context_data_variables" format="http" scope="external"> Variables de datos de contexto</a> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Variables de tráfico {#section_225156106F8B41F8BC1E68D58DDC2652}

<table id="table_575F618C59DC4933BC77F935518EAE39"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Variable </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>prop 1-75 </p> </td> 
   <td colname="col2"> <p> <code> prop1 - prop75</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Jerarquía 1-5 </p> </td> 
   <td colname="col2"> <p> <code> hier1 - hier5</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Sección del sitio </p> </td> 
   <td colname="col2"> <p> <code>s.channel</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Servidor </p> </td> 
   <td colname="col2"> <p> <code>s.server</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Atributos de visita {#section_07E69A86A47741A083FD84F112EB80D0}

<table id="table_9011B1FA462B4DBBAA58FC2D6D638DA1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Atributo </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>ID de grupo de informes (solo lectura) </p> </td> 
   <td colname="col2"> <p>Grupo de informes en el que se procesa la regla de procesamiento, el cual puede no ser el grupo de informes original especificado en AppMeasurement. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Nombre de la página </p> </td> 
   <td colname="col2"> <p> <code> s.pageName</code> </p> <p>Nota: Una vista de página se cuenta en todas las visitas individuales donde no está vacío el nombre de la página. Cuando se realiza el seguimiento de un vínculo, el servidor de recopilación de datos elimina de la visita individual el nombre de página de modo que no se cuentan las vistas de esa página. Si vuelve a insertar un nombre de página en estas celdas con reglas de procesamiento, se cuenta una vista de página. Se recomienda asegurarse de que ese nombre de página ya esté establecido antes de modificar el nombre de la página. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>URL de la página </p> </td> 
   <td colname="col2"> <code> s.pageURL</code> o la dirección URL de la página actual si <code>s.pageURL</code> no se especifica. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Parámetro de cadena de consulta </p> </td> 
   <td colname="col2"> <p>Valor de un parámetro de cadena de consulta especificado en la URL actual, o nulo si no existe ningún parámetro. For the URL <b>https://www.example.com/a.html?cid=ad1&amp;node=4</b>, the value of Query String Parameter <span class="syntax codeph"> cid</span> is <b>ad1</b>, and the value of Query String Parameter <span class="syntax codeph"> node</span> is <b>4</b>. </p> <p>Si se ejecuta AppMeasurement para JavaScript H.25.2 o anterior, la dirección URL de la página puede truncarse al superar los 255 caracteres. AppMeasurement para JavaScript H.25.3 (versión de junio de 2013) y posteriores proporcionan las direcciones URL completas para las reglas de procesamiento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ruta de página </p> </td> 
   <td colname="col2"> <p>Ruta de la URL de la página. The path of the URL <b>https://www.example.com/news/a.html?cid=ad1</b> is <span class="syntax codeph"> news/a.html</span> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dominio de página </p> </td> 
   <td colname="col2"> <p>Nombre del host completo especificado en la URL. https://<span class="syntax codeph"> en.main.example.co.uk</span>/index.jsp?q=value </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dominio raíz de página </p> </td> 
   <td colname="col2"> <p>Las dos últimas secciones del nombre del host de la página. https://en.main.example.<span class="syntax codeph"> co.uk</span>/index.jsp?q=value </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Cadena de consulta de página </p> </td> 
   <td colname="col2"> <p>Cadena de consulta completa de la URL. https://en.main.example.co.uk/index.jsp?<span class="syntax codeph"> q=value</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Referente* (solo lectura) </p> </td> 
   <td colname="col2"> <p>Referente HTTP. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Parámetro de cadena de consulta referente (solo lectura) </p> </td> 
   <td colname="col2"> <p>Valor de un parámetro de cadena de consulta especificado en la URL referente, o nulo si no existe ningún parámetro. For the URL <b>https://www.example.com/a.html?cid=ad1&amp;node=4</b>, the value of Query String Parameter <span class="syntax codeph"> cid</span> is <b>ad1</b>, and the value of Query String Parameter <span class="syntax codeph"> node</span> is <b>4</b>. </p> <p>Si se ejecuta AppMeasurement para JavaScript H.25.2 o anterior, la dirección URL de la página puede truncarse al superar los 255 caracteres. AppMeasurement para JavaScript H.25.3 (versión de junio de 2013) y posteriores proporcionan las direcciones URL completas para las reglas de procesamiento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dominio de referencia (solo lectura) </p> </td> 
   <td colname="col2"> <p>El nombre del host completo del referente. https://<span class="syntax codeph"> en.main.example.co.uk</span>/index.jsp?q=value </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dominio raíz referente (solo lectura) </p> </td> 
   <td colname="col2"> <p>Las dos últimas secciones del nombre del host del referente. https://en.main.example.<span class="syntax codeph"> co.uk</span>/index.jsp?q=value </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Cadena de consulta referente (solo lectura) </p> </td> 
   <td colname="col2"> <p>Parámetros de cadena de consulta incluidos en la URL referente. https://en.main.example.co.uk/index.jsp?<span class="syntax codeph"> q=value</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dirección IP (solo lectura) </p> </td> 
   <td colname="col2"> <p>Dirección IP indicada por el navegador. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Agente de usuario (solo lectura) </p> </td> 
   <td colname="col2"> <p>Agente de usuario indicado por el navegador. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Versión del código de AppMeasurement (solo lectura) </p> </td> 
   <td colname="col2"> <p>Versión de la biblioteca de AppMeasurement utilizada para realizar la petición. Cuando use señalizaciones de imagen, puede rellenar esto con un valor personalizado que se lee usando reglas de procesamiento. Este valor aparece en la siguiente posición de la URL: </p> <p>https://server.net/b/ss/report-suite-ID/1/<span class="syntax codeph"> CODEVERSION</span>/... </p> </td> 
  </tr> 
 </tbody> 
</table>

## Variables de conversión {#section_311856B21B3B49DBAA0539CFA06C409F}

<table id="table_E28729026EDA485989178A3B887B5983"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Variable </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>eVar 1-N </p> </td> 
   <td colname="col2"> <p> <code> evar1</code> - <code>evarN</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Código de seguimiento de campaña </p> </td> 
   <td colname="col2"> <p> <code> s.campaign</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Código de moneda </p> </td> 
   <td colname="col2"> <p> <code> s.currencyCode</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Variables de lista 1-3 </p> </td> 
   <td colname="col2"> <p> <code> s.list1</code> - <code>s.list3</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID de compra </p> </td> 
   <td colname="col2"> <p> <code> s.purchaseID</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>El ID de transacción </p> </td> 
   <td colname="col2"> <p> <code> s.transactionID </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Estado del visitante </p> </td> 
   <td colname="col2"> <p> <code> s.state</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Código postal del visitante </p> </td> 
   <td colname="col2"> <p> <code> s.zip</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Eventos de éxito {#section_C1946FEB64FC4F579671EC5E0D06AE8A}

Las reglas de procesamiento pueden definir eventos pero no pueden leerlos como condiciones.

<table id="table_926ED12B58CA4FB685D799DC6EE567C0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Evento </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Evento 1-1000 </p> <p>(Para clientes de SiteCatalyst 15, evento 1-100). </p> </td> 
   <td colname="col2"> <p> <code> event1</code> - <code>event1000</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>purchase, scView, scAdd y otros eventos de carrito de compra </p> </td> 
   <td colname="col2"> <p>Eventos predefinidos. </p> </td> 
  </tr> 
 </tbody> 
</table>


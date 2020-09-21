---
description: Las dimensiones que pueden leerse y escribirse (a menos que se indique lo contrario) con reglas de procesamiento.
subtopic: Processing rules
title: Dimensiones disponibles para las reglas de procesamiento
topic: Admin tools
uuid: ba73ab59-a8cf-491c-8757-5fb03d6b0745
translation-type: tm+mt
source-git-commit: ec6d8e6a3cef3a5fd38d91775c83ab95de47fd55
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

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
   <td colname="col2"> <p>Variables con nombre que se envían con una visita. </p> <p>Nota: Los datos de las variables de datos de contexto se deben copiar en variables de informes para que aparezcan en los informes. Tampoco pueden verse en ninguna interfaz de informes, ni siquiera en las fuentes de datos del flujo de navegación. </p> <p> <a href="/help/admin/admin/c-processing-rules/processing-rules-examples/processing-rules-copy-context-data.md"> Copiar una variable de datos de contexto en una eVar </a> </p> <p> <a href="/help/admin/admin/c-processing-rules/processing-rules-examples/processing-rules-copy-context-data-event.md"> Definir un evento con una variable de datos de contexto </a> </p> <p> <a href="/help/implement/vars/page-vars/contextdata.md"> Variables de datos de contexto</a> </p> </td> 
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
   <td colname="col2"> <p> <code> s.channel </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Servidor </p> </td> 
   <td colname="col2"> <p> <code> s.server </code> </p> </td> 
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
   <td colname="col2"> <p> <code> s.pageName</code> </p> <p>Nota:  Las llamadas de seguimiento de vínculos eliminan la <code>pageName</code> variable antes de alcanzar las reglas de procesamiento. Si vuelve a insertar un valor de nombre de página mediante reglas de procesamiento, la visita se considera una vista de página en lugar de una llamada de seguimiento de vínculo. Adobe recomienda comprobar si el nombre de la página ya está establecido antes de modificarlo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>URL de la página </p> </td> 
   <td colname="col2"> <code> s.pageURL</code> o la dirección URL de la página actual si <code> s.pageURL</code> no se especifica. <p>Nota:  Las llamadas de seguimiento de vínculos eliminan la <code>pageURL</code> variable antes de alcanzar las reglas de procesamiento. Si vuelve a insertar un valor de URL de página mediante reglas de procesamiento, la visita se considera una vista de página en lugar de una llamada de seguimiento de vínculo. Adobe recomienda comprobar que la dirección URL de la página ya está establecida antes de modificarla. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Parámetro de cadena de consulta </p> </td> 
   <td colname="col2"> <p>Valor de un parámetro de cadena de consulta especificado en la URL actual, o nulo si no existe ningún parámetro. Para la dirección URL <b>https://www.example.com/a.html?cid=ad1&amp;node=4</b>, el valor del parámetro de cadena de consulta <span class="syntax codeph"> cid</span> es <b>ad1</b> y el valor del <span class="syntax codeph"> nodo</span> del parámetro de cadena de consulta es <b>4</b>. </p> <p>Si se ejecuta AppMeasurement para JavaScript H.25.2 o anterior, la dirección URL de la página puede truncarse al superar los 255 caracteres. AppMeasurement para JavaScript H.25.3 (versión de enero de 2013) y posteriores proporcionan las direcciones URL completas para las reglas de procesamiento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ruta de página </p> </td> 
   <td colname="col2"> <p>Ruta de la URL de la página. La ruta de la dirección URL <b>https://www.example.com/news/a.html?cid=ad1</b> es <span class="syntax codeph">/news/a.html</span>. </p> </td> 
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
   <td colname="col2"> <p>Valor de un parámetro de cadena de consulta especificado en la URL referente, o nulo si no existe ningún parámetro. Para la dirección URL <b>https://www.example.com/a.html?cid=ad1&amp;node=4</b>, el valor del parámetro de cadena de consulta <span class="syntax codeph"> cid</span> es <b>ad1</b> y el valor del <span class="syntax codeph"> nodo</span> del parámetro de cadena de consulta es <b>4</b>. </p> <p>Si se ejecuta AppMeasurement para JavaScript H.25.2 o anterior, la dirección URL de la página puede truncarse al superar los 255 caracteres. AppMeasurement para JavaScript H.25.3 (versión de enero de 2013) y posteriores proporcionan las direcciones URL completas para las reglas de procesamiento. </p> </td> 
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
   <td colname="col2"> <p> <code> evar1</code> - <code> evarN</code> </p> </td> 
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
   <td colname="col2"> <p> <code> s.list1</code> - <code> s.list3</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID de compra </p> </td> 
   <td colname="col2"> <p> <code> s.purchaseID</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID de transacción </p> </td> 
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
   <td colname="col2"> <p> <code> event1</code> - <code> event1000</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>purchase, scView, scAdd y otros eventos de carrito de compra </p> </td> 
   <td colname="col2"> <p>Eventos predefinidos. </p> </td> 
  </tr> 
 </tbody> 
</table>


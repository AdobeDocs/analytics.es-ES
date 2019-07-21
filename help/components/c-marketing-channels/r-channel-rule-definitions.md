---
description: Esta tabla de referencia define los campos, las opciones y los atributos de visita que puede seleccionar en la página Reglas de procesamiento de canal de mercadotecnia.
seo-description: Esta tabla de referencia define los campos, las opciones y los atributos de visita que puede seleccionar en la página Reglas de procesamiento de canal de mercadotecnia.
seo-title: 'Reglas de procesamiento de canal de mercadotecnia: definiciones'
solution: Analytics
subtopic: Canales de mercadotecnia
title: 'Reglas de procesamiento de canal de mercadotecnia: definiciones'
topic: Reports and Analytics
uuid: 4 e 71 ff 5 b -912 a -4 dc 0-9 c 22-4 be 74 c 5 e 3 cc 0
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Reglas de procesamiento de canal de mercadotecnia: definiciones

Esta tabla de referencia define los campos, las opciones y los atributos de visita que puede seleccionar en la página Reglas de procesamiento de canal de mercadotecnia.

<table id="table_C18A0F1C9E214EB585A29801BA2400F8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Término </p> </th> 
   <th colname="col2" class="entry"> <p>Definición </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Todos </p> </td> 
   <td colname="col2"> <p>Activa este canal solamente cuando todas las reglas de la regla numerada son verdaderas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Cualquiera </p> </td> 
   <td colname="col2"> <p>Activa este canal cuando cualquiera de las reglas del conjunto de reglas es verdadera. Esta opción está disponible solamente si existe más de una regla en la regla numerada. </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p>ID de AMO </p> </td> 
   <td colname="col2"> <p>Código de seguimiento principal utilizado por las integraciones de Advertising Cloud y Advertising Analytics. Cuando una de estas integraciones está habilitada, el prefijo del código de seguimiento se puede utilizar para identificar canales específicos de Advertising Cloud. Utilice "AMO ID" con "AL" para la búsqueda, "AC" para Mostrar o "AO" para Social. Cuando se utiliza el ID de AMO en los canales de mercadotecnia, las métricas de costo/costo/impresión pueden atribuirse al canal correcto (cuando no se configura, estas métricas se dirigen a Directas o Ninguna). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID ED ED </p> </td> 
   <td colname="col2"> <p>Código de seguimiento secundario utilizado por Advertising Cloud. El principal objetivo de este código de seguimiento es servir como clave para enviar datos nuevamente a la nube de publicidad. No obstante, también se puede utilizar para identificar pulsaciones de visualización vs. visualizaciones de visualización si desea verlos como dos canales de mercadotecnia separados. Esto se puede hacer configurando la lógica de canal de mercadotecnia para "AMO EF ID" en ": d "para Mostrar clickthroughs o" AMO EF ID "termina con": i "para Visualizaciones de visualización. Si no desea dividir la visualización en dos canales, use la dimensión ID de AMO en su lugar. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Variables de conversión </p> </td> 
   <td colname="col2"> <p>Contiene eVars que se han habilitado para este grupo de informes y se aplica solamente cuando las variables se definen mediante el código de Adobe en la página. </p> <p>Consulte la <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/oms_sc_implement.pdf" scope="external" format="html">Guía de implementación </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Existe </p> </td> 
   <td colname="col2"> <p>Se ofrecen varias opciones, entre ellas: </p> <p> 
     <ul id="ul_FE39B5F36235441FB757CC73CA2C4F51"> 
      <li id="li_6DC09918D69B443091AB94DB773D5189"> <p> <span class="uicontrol"> No existe</span>: indica que el atributo de visita no existe en la solicitud. Por ejemplo, en un dominio referente, si el usuario escribe una dirección URL o hace clic en un marcador, el atributo de dominio referente no existe. </p> </li> 
      <li id="li_3AB958F997974682824E85014CA266D6"> <p> <span class="uicontrol"> Está vacío</span>: indica que existe un atributo de visita que, generalmente, es un parámetro de eVar o de cadena de consulta, pero que no hay ningún valor asociado al atributo de visita. </p> </li> 
      <li id="li_25EDA39748D141BA8173CC4C41035ABA"> <p> <span class="uicontrol"> No contiene </span>: Permite especificar, por ejemplo, que un dominio de referencia no contiene un valor específico (en oposición a utilizar la selección <span class="term"> Contiene </span>. </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Identificar el canal como </p> </td> 
   <td colname="col2"> <p>Asocia la regla con un canal de mercadotecnia que haya agregado a la página <span class="wintitle">Administrador de canales de mercadotecnia</span>. </p> <p>See <a href="../../components/c-marketing-channels/c-channels.md#task_98C9D3F5DBBC4B198E0A9ED4D3891E03" type="task" format="dita" scope="local"> Add marketing channels </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Concuerda con las reglas de detección de búsqueda paga </p> </td> 
   <td colname="col2"> <p>Búsqueda paga detectada por Adobe. Las búsquedas pagas se dan cuando las empresas pagan una tarifa al motor de búsqueda para que las incluyan en las listas de su sitio. Por lo general, la búsqueda paga aparece en la parte superior o en el lado derecho de los resultados de búsqueda. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Concuerda con las reglas de detección de búsqueda natural </p> </td> 
   <td colname="col2"> <p>Búsqueda no paga detectada por los informes de Adobe. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>El referente concuerda con los filtros de dirección URL internos </p> </td> 
   <td colname="col2"> <p> Visita cuya dirección URL de página coincide con un filtro de dirección de URL interno, tal como se define en el grupo de informes de las Herramientas de administración. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>El referente no concuerda con los filtros de dirección URL internos </p> </td> 
   <td colname="col2"> <p>La dirección URL de referencia no coincide con un filtro de dirección de URL interno, tal como se define en el grupo de informes de las Herramientas de administración. Puede utilizar esta configuración con <span class="term"> URL de página </span> y <span class="term"> Existe </span> para configurar una regla de captador global, de modo que ninguna visita aterrice en la sección <a href="../../components/c-marketing-channels/c-faq.md#section_451E42994DA247A8A7B8559C715A5EE7" type="section" format="dita" scope="local"> No se identificó </a> el canal del informe. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Hacer caso omiso de visitas que coincidan con los filtros de direcciones de URL internas </p> </td> 
   <td colname="col2"> <p>(Para los referentes) Realiza un seguimiento, solamente, de las visitas que provienen de sitios de referencia externos. Por lo general, se deja sin activar, salvo que desee incluir el tráfico interno. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Es la primera página de la visita </p> </td> 
   <td colname="col2"> <p>Primera página de una visita detectada por los informes de Adobe. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Página </p> </td> 
   <td colname="col2"> <p>El nombre de una página web del sitio que está etiquetada con la señalización web de Adobe. Este valor equivale a <span class="varname"> s.pageName </span>. Examples include <span class="varname"> Home Page </span> and <span class="varname"> About Us </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dominio de página </p> </td> 
   <td colname="col2"> <p>El dominio de la página en la que aterriza el visitante como, por ejemplo, <span class="filepath">productos.ejemplo.es </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dominio y ruta de página </p> </td> 
   <td colname="col2"> <p>El dominio y la ruta de acceso como, por ejemplo, <span class="filepath">productos.ejemplo.es/hombre/pantalones/general.html </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dominio raíz de página (TLD+1) </p> </td> 
   <td colname="col2"> <p>El dominio raíz de la página donde aterriza el visitante como, por ejemplo, <span class="filepath">ejemplo.es </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>URL de la página </p> </td> 
   <td colname="col2"> <p>La dirección URL de una página web de su sitio. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dominio de referencia </p> </td> 
   <td colname="col2"> <p>El dominio del que salieron los visitantes antes de visitar su sitio web como, por ejemplo, los referentes de <span class="filepath">sitioabc.com</span> a <span class="filepath">sitioxyz.com </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Parámetro de cadena de consulta </p> </td> 
   <td colname="col2"> <p>If a page URL on your site looks like <span class="filepath"> https://example.com/?page=12345&amp;cat=1 </span>, then page and cat are both query string parameters. (See <span class="filepath"> https://en.wikipedia.org/wiki/Query_string </span>.) </p> <p>Puede especificar solamente un parámetro de cadena de consulta por cada conjunto de reglas. Para agregar más parámetros de cadena de consulta, utilice <span class="uicontrol">CUALQUIERA</span> como operador y luego agregue nuevos parámetros de cadena de consulta a la regla. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Referente </p> </td> 
   <td colname="col2"> <p>Ubicación de la página web (dirección URL completa) en la que se encontraban los visitantes antes de entrar en el sitio. El referente existe fuera del dominio que haya definido. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dominio y ruta de referencia </p> </td> 
   <td colname="col2"> <p>Una concatenación del dominio de referencia y la ruta URL. Algunos ejemplos son: </p> <p> <span class="filepath"> www.example.com/products/id/12345 </span> </p> <p> <span class="filepath"> ad.example.com/foo </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Parámetro de referencia </p> </td> 
   <td colname="col2"> <p>Un parámetro de cadena de consulta de la dirección URL de referencia. Por ejemplo, si los visitantes provienen de <span class="filepath">ejemplo.com/?pag=12345&amp;cat=1</span>, pag y cat son los parámetros de referencia. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dominio raíz de referencia </p> </td> 
   <td colname="col2"> <p>El dominio raíz del referente. El referente existe fuera del dominio que haya definido. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Motor de búsqueda </p> </td> 
   <td colname="col2"> <p>Un motor de búsqueda, como Google o Yahoo!, que trajo visitantes al sitio. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Palabras clave de búsqueda </p> </td> 
   <td colname="col2"> <p>Una palabra que se utiliza para llevar a cabo una búsqueda mediante un motor de búsqueda. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Motor de búsqueda + Palabras clave </p> </td> 
   <td colname="col2"> <p>Una concatenación de la palabra clave de búsqueda y el motor de búsqueda que identifica de forma exclusiva el motor de búsqueda. Por ejemplo, si busca la palabra ordenador, el motor de búsqueda y la palabra clave se identifican de este modo: </p> 
    <code>Código de seguimiento de búsqueda = " &lt; tipo_ de_ búsqueda &gt;: &lt; motor de búsqueda &gt;: &lt; palabra clave de búsqueda &gt; "donde search_ type =" n "o" p ", motor_ de_ búsqueda =" Google "y palabra_ clave_ de_ búsqueda =" equipo " </code>
  <p><b>Nota:</b> n = natural; p = paga </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Definir el valor del canal en </p> </td> 
   <td colname="col2"> <p>Además de saber qué canal de mercadotecnia lleva al visitante a su sitio, puede saber también qué anuncio de banner, palabra clave de búsqueda o campaña de correo electrónico del canal recibe crédito por la actividad del visitante en el sitio. Este identificador es un valor de canal que se almacena junto con el canal. A menudo, este valor es un identificador de campaña integrado en la página de aterrizaje o en la dirección URL de referencia; en otros casos es la combinación del motor de búsqueda y la palabra clave de búsqueda, o bien, la dirección URL de referencia que identifica de forma más correcta al visitante en un canal particular. </p> </td> 
  </tr> 
 </tbody> 
</table>




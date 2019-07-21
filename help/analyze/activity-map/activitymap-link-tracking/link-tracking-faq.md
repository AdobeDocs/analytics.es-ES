---
description: Preguntas frecuentes sobre el seguimiento de vínculos en Activity Map.
seo-description: Preguntas frecuentes sobre el seguimiento de vínculos en Activity Map.
seo-title: Preguntas frecuentes sobre seguimiento de vínculos
solution: Analytics
title: Preguntas frecuentes sobre seguimiento de vínculos
topic: Activity Map
uuid: 10172073-b 98 b -4950-8397-67 a 18 b 37 b 3 b 4
translation-type: tm+mt
source-git-commit: d877f86dd5a05d0aa452ecebce47468ebf94cbb2

---


# Preguntas frecuentes sobre seguimiento de vínculos

Preguntas frecuentes sobre el seguimiento de vínculos en Activity Map.

>[!CAUTION]
>
>By turning on Activity Map tracking, **you may be** **collecting personally identifiable information (PII) data.** This data can be used on its own or with other information to identify, contact, or locate a single person, or to identify an individual in context.

A continuación se indican algunos casos conocidos en los que pueden recopilarse datos PII con el seguimiento de Activity Map:

* `Mailto` vínculos. Un vínculo mailto es un tipo de vínculo HTML que activa el cliente de correo predeterminado en el equipo para enviar un mensaje de correo electrónico.
* `User ID` vínculos que pueden aparecer en el encabezado o pie de página de un sitio web una vez que el usuario haya iniciado sesión.
* Para las instituciones financieras, es posible que se muestre como vínculo el número de cuenta. Al hacer clic en dicho vínculo, se recopilará el texto que contenga.
* Los sitios web de entidades sanitarias también pueden mostrar datos PII como vínculos. Al hacer clic en dichos vínculos, se recopilará el texto que contengan, por lo que se recopilarán datos PII.

<table id="table_0951EAC617344156BAE43000CCD838AF"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <b>P: ¿Cuándo se produce el seguimiento de vínculos?</b> <p> </p> </td> 
   <td colname="col2"> R: La identificación de vínculos y regiones de Activity Map se lleva a cabo cuando los usuarios hacen clic en una página. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>P: ¿De qué elementos se realiza el seguimiento de forma predeterminada?</b> <p> </p> </td> 
   <td colname="col2"> R: Si se da un evento de clic en un elemento, este tiene que pasar algunas comprobaciones para determinar si AppMeasurement lo tratará como un vínculo. Las comprobaciones son: 
    <ul id="ul_81B9A5A7F8534E71AEF68F2199A154F0"> 
     <li id="li_49F6DDD9DC124AE5846EC5B7D7BEA20E">¿Se trata de una etiqueta &lt;A&gt; o &lt;AREA&gt; con una propiedad HREF? </li> 
     <li id="li_77828D24D54343E5B9A1FF7345221781">¿Hay un atributo en el que se hace clic y que define una variable s_objectID? </li> 
     <li id="li_D4B0AEEEA58A4F82A1BCBD3971A60D02">¿Se trata de una etiqueta INPUT o un botón SUBMIT con un valor o texto secundario? </li> 
     <li id="li_F7ABE88308E1413E9B9C2224DEC91BAB">¿Se trata de una etiqueta INPUT con el tipo IMAGE y una propiedad src? </li> 
     <li id="li_F34A0C986E8040109A1DDF88C26E56D5">¿Es un &lt;Button&gt;? </li> 
    </ul> <p>Si la respuesta a alguna de estas preguntas es <b>Sí</b>, el elemento se trata como vínculo y se le realiza un seguimiento. </p> <p>Importante: AppMeasurement no considera las etiquetas Button con el atributo type="button" como vínculos. Considere la posibilidad de quitar el atributo "type='button'" de las etiquetas Button y agregar en su lugar el atributo role="button" o submit="button". </p> <p>Importante: Las etiquetas de anclaje con un href que comienza con " #" se consideran una ubicación de destino interna por appmeasurement, no un vínculo (ya que no se abandona la página). De forma predeterminada, Activity Map no rastrea estas ubicaciones de objetivos internas. Rastrea únicamente vínculos que navegan por el usuario a una nueva página.</p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>P: ¿Cómo realiza Activity Map el seguimiento de otros elementos HTML visuales?</b> </td> 
   <td colname="col2"> 
    <ol id="ol_DA3AED165CFF44B08DFB386D4DEE26C5"> 
     <li id="li_E3E3F498F37B4FADAFDA39CCAE41511F"> <b>A través de la función <code>s.tl()</code>.</b> <p>Si el clic se produjo a través de una invocación de s.tl, Activity Map también recibirá este evento de clic y determinará si se encontró la variable de cadena linkName. Durante la ejecución de s.tl, el linkName se definirá como ID del vínculo de Activity Map. El elemento donde se hizo clic y que originó la llamada de s.tl() se utilizará para determinar la región. Ejemplo: </p> <p> 
       <code>&lt; img &amp; amp; nbsp; onclick = "s. tl (true,' o ',' abc ')" &amp; amp; nbsp; src = "someimageurl. png"/&gt; </code>
  </p> </li> 
     <li id="li_A93725B810FE408BA5E6B267CF8CEAE5"> <b>A través de la variable <code>s_objectID</code>.</b> <p>Ejemplo: </p> <p> 
       <code>&lt; img onclick = "s_ objectid =' abc '; " src = "someimageurl. png"/&gt; &lt; a href = "some-url.html" onclick = "s_ objectid =' abc '; " &gt; Texto del vínculo aquí &lt;/a &gt; </code>
  </p> <p>Importante: Tenga en cuenta que es obligatorio el uso de un punto y coma de cierre (;) al usar s_objectID en Activity Map. </p> </li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>P: ¿Pueden dar ejemplos de vínculos de los que se realizará un seguimiento?</b> </td> 
   <td colname="col2"> 
    <ol id="ol_697E5CE0B84D4A309DD80670697A02BA"> 
     <li id="li_2C511EFD10F14F438B1F3A1BAB4B45E0"> 
      <code>&lt; a &amp; amp; nbsp; href = "/home" &gt; Home &lt;/a &gt; </code>
  </li> 
     <li id="li_76F3DB36ED734132A2386871E6EB4929"> 
      <code>&lt; input &amp; amp; nbsp; type = "submit" &amp; amp; nbsp; value = "Submit"/&gt; </code>
  </li> 
     <li id="li_10CF9EDA224645169E7CDF74956DB98B"> 
      <code>&lt; input &amp; amp; nbsp; type = "image" &amp; amp; nbsp; src = "submit-button. png"/&gt; </code>
  </li> 
     <li id="li_9FA171D7F49547E798DE21869F73A402"> 
      <code>&lt; p onclick = "var s_ objectid =' custom link id '; " &gt; &lt; span class = "title" &gt; Tasas de mercado actuales &lt;/span &gt; &lt; span class = "subtitle" &gt; 1,45 USD &lt;/span &gt; &lt;/p &gt; </code>
  </li> 
     <li id="li_C5D77589006E4514AA6F3AEB509A0BAF"> 
      <code>&lt; div onclick = "s. tl (true,' o ',' custom link id ')" &gt; &lt; span class = "title" &gt; Current Market Rates &lt;/span &gt; &lt; span class = "subtitle" &gt; 1,45 USD &lt;/span &gt; &lt;/div &gt; </code>
  </li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>P: ¿Pueden dar ejemplos de vínculos de los que NO se realizará un seguimiento?</b> </td> 
   <td colname="col2"> 
    <ol id="ol_CDFDB572F76B4F68A64B66A6B0237547"> 
     <li id="li_99372060646B43EF94C13A9C682CE693">Razón: la etiqueta de anclaje no tiene una href válida. 
      <code>&lt; a &amp; amp; nbsp; name = "inneranchor" &gt; Section &amp; amp; nbsp; header &lt;/a &gt; </code>
  </li> 
     <li id="li_736A5F7DC2D74B4DA1CECEE3AD10EB19">Reason: Neither <code> s_ObjectID </code> nor <code> s.tl() </code> present 
      <code>
        &lt;p onclick="showPanel('market rates')"&gt;     &lt;span class="title"&gt;Current Market Rates&lt;/span&gt;&lt;span  class="subtitle"&gt;1.45USD&lt;/span&gt; &lt;/p&gt;
      </code> </li> 
     <li id="li_45F9ED97140F47F99F8C167BC1DC546F">Reason: Neither <code> s_ObjectID </code> nor <code> s.tl() </code> present 
      <code>
        &lt;input type="radio" onclick="changeState(this)" name="group1" value="A"/&gt; &lt;input type="radio" onclick="changeState(this)" name="group1" value="B"/&gt; &lt;input type="radio" onclick="changeState(this)" name="group1" value="C"/&gt;
      </code> </li> 
     <li id="li_9EBFCC58F3A94F30BA62156F14B15D55">Reason: src property is missing a form input element 
      <code>
        &lt;input&amp;nbsp;type="image"/&gt; 
      </code> </li> 
    </ol> </td> 
  </tr> 
 </tbody> 
</table>


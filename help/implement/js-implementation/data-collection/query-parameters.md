---
description: En las tablas siguientes se describe el parámetro de consulta que contiene el valor de las distintas variables de Analytics que se envían a la recopilación de datos.
keywords: Implementación de Analytics
seo-description: En las tablas siguientes se describe el parámetro de consulta que contiene el valor de las distintas variables de Analytics que se envían a la recopilación de datos.
seo-title: Parámetros de consulta de recopilación de datos
solution: Analytics
title: Parámetros de consulta de recopilación de datos
topic: Desarrollador e implementación
uuid: 4 d 5 af 486-df 27-42 fe-bb 9 c -28938 dddf 2 b 2
translation-type: tm+mt
source-git-commit: 5a30ea6ac47ddd8612728e488afda868491a1ddc

---


# Parámetros de consulta de recopilación de datos

En las tablas siguientes se describe el parámetro de consulta que contiene el valor de las distintas variables de Analytics que se envían a la recopilación de datos.

Esta información puede usarse para depurar con [analizadores](../../../implement/impl-testing/packet-monitor.md#concept_490DF35E06D44234A91B5FC57C0BF258)de paquetes, al construir manualmente solicitudes de imagen o al utilizar [variables dinámicas](../../../implement/js-implementation/c-variables/dynvars-overview.md#concept_B016789733A94070A9EAB209EEC05262).

<table id="table_5442E15BF0AE4BDA92DDADD1C08F7C13"> 
 <thead> 
  <tr> 
   <th class="entry"> Parámetro </th> 
   <th class="entry"> Variable de Analytics </th> 
   <th class="entry"> Información introducida en el informe </th> 
   <th class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> aamlh </td> 
   <td colname="col2"> Ninguna </td> 
   <td colname="col3"> Ninguno </td> 
   <td colname="col4"> Indicación de ubicación de Audience Manager (usado en la integración de Experience Cloud Shared Profile) </td> 
  </tr> 
  <tr> 
   <td colname="col1"> aamb </td> 
   <td colname="col2"> Ninguna </td> 
   <td colname="col3"> Ninguno </td> 
   <td colname="col4"> Blob de Audience Manager (usado en la integración de Experience Cloud Shared Profile) </td> 
  </tr> 
  <tr> 
   <td colname="col1"> aid </td> 
   <td colname="col2"> Ninguna </td> 
   <td colname="col3"> Ninguna </td> 
   <td colname="col4"> ID de visitante de Analytics </td> 
  </tr> 
  <tr> 
   <td> AQB </td> 
   <td> Ninguna </td> 
   <td> Ninguna </td> 
   <td> Indica el comienzo de una solicitud de imagen. </td> 
  </tr> 
  <tr> 
   <td> AQE </td> 
   <td> Ninguna </td> 
   <td> Ninguna </td> 
   <td> Indica el final de una solicitud de imagen, indicando que no se truncó la solicitud. </td> 
  </tr> 
  <tr> 
   <td> bh </td> 
   <td> Ninguna </td> 
   <td> Perfil del visitante | Tecnología | Altura del explorador </td> 
   <td> Altura de la ventana del explorador (en píxeles). </td> 
  </tr> 
  <tr> 
   <td> bw </td> 
   <td> Ninguna </td> 
   <td> Perfil del visitante | Tecnología | Ancho del explorador </td> 
   <td> Ancho de la ventana del explorador (en píxeles). </td> 
  </tr> 
  <tr> 
   <td> c </td> 
   <td> Ninguna </td> 
   <td> Perfil del visitante | Tecnología | Profundidad de color del monitor </td> 
   <td> Calidad de color (en bits). </td> 
  </tr> 
  <tr> 
   <td> <code> c. <span class="varname"> [key] </code></span> </td> 
   <td> <p>s.contextData </p> </td> 
   <td> <p>Ninguno. </p> </td> 
   <td> <p>Los pares clave-valor se especifican en uno de los siguientes formatos: </p> <p> <code> &lt;my.a&gt;red&lt;/my.a&gt; </code> </p> <p>O bien: </p> <p> <code> &lt;my&gt;&lt;a&gt;red&lt;/a&gt;&lt;/my&gt; </code> </p> <p>Cada uno de estos ejemplos genera un valor de datos de contexto de <code>my.a = red </code>. Pueden especificarse varios pares de clave-valor. </p> <p>In the query string, this context data variable would appear as <code> c.&amp;my.a=red </code> </p> </td> 
  </tr> 
  <tr> 
   <td> c1 - c75 </td> 
   <td> s.prop1 - s.prop75 </td> 
   <td> Todos los informes de tráfico personalizados </td> 
   <td> Variables de tráfico utilizadas en los informes de tráfico personalizados. </td> 
  </tr> 
  <tr> 
   <td> cc </td> 
   <td> s.currencyCode </td> 
   <td> Ninguna </td> 
   <td> El tipo de moneda que se usa en el sitio. </td> 
  </tr> 
  <tr> 
   <td> cdp </td> 
   <td> s.cookieDomainPeriods </td> 
   <td> Ninguna </td> 
   <td> Indica el número de períodos en un domino para el seguimiento de cookies; ajuste manual. </td> 
  </tr> 
  <tr> 
   <td> ce </td> 
   <td> s.charSet </td> 
   <td> Ninguna </td> 
   <td> La codificación de caracteres de la solicitud de imagen. </td> 
  </tr> 
  <tr> 
   <td> cl </td> 
   <td> s.cookieLifetime (vida de la cookie s_vi en segundos) </td> 
   <td> Ninguno. </td> 
   <td> La duración de la cookie del visitante. </td> 
  </tr> 
  <tr> 
   <td> ch </td> 
   <td> s.channel </td> 
   <td> Contenido del sitio | Secciones del sitio </td> 
   <td> La variable Secciones del sitio usada en los informes de tráfico. </td> 
  </tr> 
  <tr> 
   <td> cp </td> 
   <td> Tipo de visita </td> 
   <td> Tipo de visita </td> 
   <td> Indica si el comportamiento es resultado de una interacción directa en primer plano o de información que el dispositivo envía sin interacción directa en segundo plano. </td> 
  </tr> 
  <tr> 
   <td> ct </td> 
   <td> Ninguna </td> 
   <td> Perfil del visitante | Tecnología | Tipos de conexión </td> 
   <td> Tipo de conexión (módem, LAN, etc.; solo se puede rellenar en exploradores IE). </td> 
  </tr> 
  <tr> 
   <td> <code> D </code> </td> 
   <td> dynamicVariablePrefix </td> 
   <td> Ninguno. </td> 
   <td> <p>Consulte <a href="../../../implement/js-implementation/c-variables/dynvars-overview.md#concept_B016789733A94070A9EAB209EEC05262" format="dita" scope="local"> Variables dinámicas </a>. </p> </td> 
  </tr> 
  <tr> 
   <td> events o ev </td> 
   <td> s.events </td> 
   <td> Tráfico del sitio | Compras, Cesta, Eventos personalizados </td> 
   <td> Los eventos de comercio y eventos personalizados ocurridos en la página; se emplea en informes de conversión. </td> 
  </tr> 
  <tr> 
   <td> g </td> 
   <td> Ninguna </td> 
   <td> Ninguna </td> 
   <td> URL actual de la página., hasta 255 bytes. </td> 
  </tr> 
  <tr> 
   <td> -g </td> 
   <td> Ninguna </td> 
   <td> Ninguna </td> 
   <td> Las direcciones URL superiores a 255 bytes se dividen: los primeros 255 bytes aparecen en el parámetro g y los bytes restantes se muestran más adelante en la cadena de consulta, en el parámetro de consulta -g=. </td> 
  </tr> 
  <tr> 
   <td> h1 - h5 </td> 
   <td> s.hier1 - s.hier5 </td> 
   <td> Contenido del sitio | Informes de jerarquía </td> 
   <td> Variables de jerarquía; se utilizan en los informes de tráfico. </td> 
  </tr> 
  <tr> 
   <td> hp </td> 
   <td> Ninguna </td> 
   <td> Perfil del visitante | Página de inicio del visitante </td> 
   <td> Indica si la página actual es la página de inicio del explorador (Y o N; solo se puede rellenar en exploradores IE). </td> 
  </tr> 
  <tr> 
   <td> j </td> 
   <td> Ninguna </td> 
   <td> Perfil del visitante | Tecnología | Versión de JavaScript </td> 
   <td> Muestra la versión de Javascript actualmente instalada (normalmente 1.x). </td> 
  </tr> 
  <tr> 
   <td> k </td> 
   <td> Ninguna </td> 
   <td> Perfil del visitante | Tecnología | Cookies </td> 
   <td> Si se admiten cookies en el explorador (Y, N o U). </td> 
  </tr> 
  <tr> 
   <td> l1-l3 </td> 
   <td> s.list1 - s.list3 </td> 
   <td> Conversión personalizada </td> 
   <td> Una lista delimitada de valores que se pasan a una variable y se incluyen en los informes como elementos de línea individuales. </td> 
  </tr> 
  <tr> 
   <td> mid </td> 
   <td> Ninguna </td> 
   <td> Ninguno </td> 
   <td> ID de visitante de Experience Cloud </td> 
  </tr> 
  <tr> 
   <td> ndh </td> 
   <td> Ninguna </td> 
   <td> Ninguna </td> 
   <td> Indica si la solicitud de imagen proviene de un archivo JS (1 o 0). </td> 
  </tr> 
  <tr> 
   <td> ns </td> 
   <td> s.visitorNameSpace </td> 
   <td> Ninguna </td> 
   <td> Especifica en qué dominio están activadas las cookies. </td> 
  </tr> 
  <tr> 
   <td> oid </td> 
   <td> s.objectID </td> 
   <td> Contenido del sitio | Enlaces | ClickMap </td> 
   <td> Identificador de objeto de la última página; se usa en ClickMap. </td> 
  </tr> 
  <tr> 
   <td> ot </td> 
   <td> Ninguna </td> 
   <td> Contenido del sitio | Enlaces | ClickMap </td> 
   <td> Etiqueta de objeto de la última página; se usa en ClickMap. </td> 
  </tr> 
  <tr> 
   <td> p </td> 
   <td> Ninguna </td> 
   <td> Perfil del visitante | Tecnología | Complementos de Netscape </td> 
   <td> Nombres de complementos separados por punto y coma. </td> 
  </tr> 
  <tr> 
   <td> pageName (o gn) </td> 
   <td> s.pageName </td> 
   <td> Contenido del sitio | Páginas </td> 
   <td> El nombre asignado a la página en los informes. </td> 
  </tr> 
  <tr> 
   <td> pageType (o gt) </td> 
   <td> s.pageType </td> 
   <td> Contenido del sitio | Páginas no encontradas </td> 
   <td> Indica si es una página 404 o no ("error" o en blanco). </td> 
  </tr> 
  <tr> 
   <td> pccr </td> 
   <td> Ninguna </td> 
   <td> Ninguna </td> 
   <td> Solo relevante para nuevos visitantes; impide que se produzcan redireccionamientos infinitos (siempre verdadero). </td> 
  </tr> 
  <tr> 
   <td> pe </td> 
   <td> s.linkType </td> 
   <td> Contenido del sitio | Enlaces | Enlaces de salida, Descargas de archivos, Enlaces personalizados </td> 
   <td> Determina el tipo de enlace personalizado del enlace activado. </td> 
  </tr> 
  <tr> 
   <td> pev1 </td> 
   <td> Ninguna </td> 
   <td> Contenido del sitio | Enlaces | Enlaces de salida, Descargas de archivos, Enlaces personalizados </td> 
   <td> URL del enlace personalizado activado. </td> 
  </tr> 
  <tr> 
   <td> pev2 </td> 
   <td> Ninguna </td> 
   <td> Contenido del sitio | Enlaces | Enlaces de salida, Descargas de archivos, Enlaces personalizados </td> 
   <td> Nombre común del enlace personalizado. </td> 
  </tr> 
  <tr> 
   <td> pev3 </td> 
   <td> Ninguna </td> 
   <td> Todos los informes de vídeo </td> 
   <td> Se utiliza para seguir hitos en informes de vídeo heredado; obsoleto con v15. </td> 
  </tr> 
  <tr> 
   <td> pf </td> 
   <td> Ninguno </td> 
   <td> Ninguno </td> 
   <td> Solo para uso de Adobe. No se debe alterar. </td> 
  </tr> 
  <tr> 
   <td> pid </td> 
   <td> Ninguna </td> 
   <td> Contenido del sitio | Enlaces | ClickMap </td> 
   <td> Identificador de página de la última página; se usa en ClickMap. </td> 
  </tr> 
  <tr> 
   <td> pidt </td> 
   <td> Ninguna </td> 
   <td> Contenido del sitio | Enlaces | ClickMap </td> 
   <td> Tipo de identificador de página de la última página; se usa en ClickMap. </td> 
  </tr> 
  <tr> 
   <td> products (o pl) </td> 
   <td> s.products </td> 
   <td> Productos | Productos </td> 
   <td> Variable Products usada en los informes de conversión. </td> 
  </tr> 
  <tr> 
   <td> purchaseID (o pi) </td> 
   <td> s.purchaseID </td> 
   <td> Ninguna </td> 
   <td> Se utiliza para duplicar compras, evitando la inflación de ingresos. </td> 
  </tr> 
  <tr> 
   <td> r </td> 
   <td> s.referrer </td> 
   <td> Todos los informes de origen de tráfico. </td> 
   <td> Dirección URL de referencia </td> 
  </tr> 
  <tr> 
   <td> s </td> 
   <td> Ninguna </td> 
   <td> Perfil del visitante | Tecnología | Resolución del monitor </td> 
   <td> Resolución de la pantalla (ancho x alto) </td> 
  </tr> 
  <tr> 
   <td> server (o sv) </td> 
   <td> s.server </td> 
   <td> Contenido del sitio | Servidores </td> 
   <td> El servidor de la página; se usa en los informes de tráfico. </td> 
  </tr> 
  <tr> 
   <td> state </td> 
   <td> s.state </td> 
   <td> Perfil del visitante | Estado de visitante </td> 
   <td> Especifica el estado tal como lo define la variable. </td> 
  </tr> 
  <tr> 
   <td> t </td> 
   <td> (automático; se envía con todas las visitas que no tengan una variable timestamp personalizada) </td> 
   <td> Ninguno. </td> 
   <td> <p>El parámetro <code>t</code> tiene el formato siguiente: </p> 
    <code>dd/mm/aaaa &amp; amp; nbsp; hh: mm: ss &amp; amp; nbsp; D &amp; amp; nbsp; OFFSET </code>
  <p>Donde D es un número del intervalo <code>0-6</code> que especifica el día de la semana y <code>OFFSET</code> representa: </p> 
    <code>offset &amp; amp; nbsp; from &amp; amp; nbsp; GMT &amp; amp; nbsp; in &amp; amp; nbsp; horas y amp; nbsp; * &amp; amp; nbsp; 60 &amp; amp; nbsp; * &amp; amp; nbsp; -&amp; amp; nbsp; 1 </code>
  <p> Por ejemplo: </p> 
    <code>23/09/2016 &amp; amp; nbsp; 14:00:00 &amp; amp; nbsp; 1 &amp; amp; nbsp; 420 </code>
  </td> 
  </tr> 
  <tr> 
   <td> <code> ts </code> </td> 
   <td> <p>timestamp </p> </td> 
   <td> Ninguno. </td> 
   <td> <p>Variable timestamp personalizada calculada y enviada con la visita. Se suele usar para el seguimiento sin conexión. </p> </td> 
  </tr> 
  <tr> 
   <td> v </td> 
   <td> Ninguna </td> 
   <td> Perfil del visitante | Tecnología | Java </td> 
   <td> Java habilitado (S o N) </td> 
  </tr> 
  <tr> 
   <td> v0 </td> 
   <td> s.campaign </td> 
   <td> Campañas | Códigos de rastreo </td> 
   <td> La variable campaign usada en los informes de conversión. </td> 
  </tr> 
  <tr> 
   <td> v1 - v75 </td> 
   <td> s.eVar1 - s.eVar75 </td> 
   <td> Todos los informes de conversión personalizados </td> 
   <td> Variables de conversión utilizadas en los informes de conversión personalizados. </td> 
  </tr> 
  <tr> 
   <td> vid </td> 
   <td> <p>s.visitorID </p> </td> 
   <td> Ninguna </td> 
   <td> ID único de visitante tal y como se haya configurado en la variable Variable de ID de visitante. </td> 
  </tr> 
  <tr> 
   <td> vmk </td> 
   <td> s.vmk </td> 
   <td> Ninguna </td> 
   <td> Clave de migración de visitante; se usa para migrar de cookies de terceros a cookies de origen.. Obsoleta. </td> 
  </tr> 
  <tr> 
   <td> vvp </td> 
   <td> s.variableProvider </td> 
   <td> Ninguna </td> 
   <td> Se emplea en integraciones de Genesis. </td> 
  </tr> 
  <tr> 
   <td> xact </td> 
   <td> s.transactionID </td> 
   <td> Ninguna </td> 
   <td> ID de transacción usado para enlazar datos en línea con datos sin conexión. </td> 
  </tr> 
  <tr> 
   <td> zip </td> 
   <td> s.zip </td> 
   <td> Perfil del visitante | Código postal del visitante </td> 
   <td> Determina el código postal según la definición de la variable. </td> 
  </tr> 
  <tr> 
   <td> /5/ (para protocolos móviles) o /1/ (para protocolos no móviles) en la dirección URL de solicitud de imagen. </td> 
   <td> Ninguna </td> 
   <td> Ninguna </td> 
   <td> <p> Controla el orden en que se usan las cookies y otros métodos para identificar a los visitantes.  </p> </td> 
  </tr> 
 </tbody> 
</table>


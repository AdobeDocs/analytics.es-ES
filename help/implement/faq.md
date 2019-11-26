---
description: Preguntas más frecuentes sobre implementación y vínculos a más información.
keywords: Analytics Implementation;faq;frequently asked questions;evar expiration;custom event visibility;timestamp;visitor id grace period;visitor id;Experience Cloud visitor id;analytics visitor id;dtm;heartbeat;cookies;tracking server;performance;javascript;data collection;s_code version;s_code debug;track link types;track video;track mobile app;first party cookie;ssl certificate;certification expiration;certificate expiration;plugins;data insertion api;500 error;500;Manage user;manage group;users;groups
solution: Analytics
title: Preguntas frecuentes acerca de la implementación de Analytics
topic: Developer and implementation
uuid: 983d759a-c4f2-4021-84c8-0486dbb951b8
translation-type: tm+mt
source-git-commit: c3bdd39808041b2e716d3e6bbdcfbf23c37b7a24

---


# Preguntas frecuentes acerca de la implementación de Analytics

Preguntas más frecuentes sobre implementación y vínculos a más información.

<table id="table_91790388C2DE4C5E8AEF0B9981AFFE27"> 
 <tbody> 
  <tr> 
   <td> <b>Pregunta</b> </td> 
   <td> <b>Respuesta</b> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>¿Cómo administro a los usuarios y grupos de Analytics? </p> </td> 
   <td colname="col3"> <p>Para obtener información sobre la administración de usuarios y grupos, consulte <a href="https://marketing.adobe.com/resources/help/en_US/reference/user_management.html">Administración de usuarios y productos</a> en la ayuda de Adobe Experience Cloud. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Caducidad de eVar: ¿Por qué se atribuyen las eVars a 'Ninguno' en los informes? </p> </td> 
   <td colname="col3"> <p> <span class="uicontrol"> Caduca después</span> especifica un período de tiempo o un evento tras el cual caduca el valor de la eVar (ya no recibe crédito por los eventos de éxito). Si se da un evento de éxito después de que caduque la eVar, el valor Ninguno recibe crédito por el evento (no había ninguna eVar activa). Si selecciona un evento como valor de caducidad, la variable caducará solamente si ocurre el evento. Si no ocurre el evento, la variable no caducará nunca. <a href="https://marketing.adobe.com/resources/help/en_US/reference/conversion_var_admin.html"> [Más...] </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Visibilidad de Eventos personalizados. ¿Por qué los Eventos personalizados no aparecen en el menú de informes? </p> </td> 
   <td colname="col3"> <p>En la columna Visibilidad, puede ocultar las métricas (integradas), los eventos personalizados y los eventos incorporados en el menú, los selectores de métricas, el Creador de métricas calculadas y el Generador de segmentos. Esta configuración no afecta a la recopilación de datos de esa métrica o evento. Solo afecta a su visibilidad en la interfaz de usuario. <a href="https://marketing.adobe.com/resources/help/en_US/reference/metric-visibility.html"> [Más...] </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Marcas de hora. ¿Qué debo tener en cuenta antes de cambiar los ajustes de marcas de hora? </p> </td> 
   <td colname="col3"> <p>Con la característica Marcas de hora opcionales, puede combinar datos sin marca de hora con datos con marca de hora sin provocar una pérdida de datos. Los datos sin conexión con marca de hora generados en un dispositivo móvil se pueden combinar con datos activos sin marca de hora de una página web, o integrarse con datos de cualquier plataforma utilizando una llamada a la variable timestamp de lado del cliente. <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/timestamps-overview.html"> [Más...] </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>ID del visitante. ¿Cómo funciona el período de gracia del ID del visitante y cómo se habilita? </p> </td> 
   <td colname="col3"> <p>Si tiene varios archivos JavaScript que envían datos al mismo grupo de informes o si utiliza otras tecnologías en el sitio, como la medición de vídeo Flash, le recomendamos que configure un período de gracia. <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_grace_period.html"> [Más...] </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>ID del visitante. ¿Cuál es la diferencia entre el ID del visitante de Experience Cloud y el ID del visitante de Analytics? </p> </td> 
   <td colname="col3"> <p>El Servicio de identidad asigna un identificador único y persistente a todos los visitantes de su sitio. Con este ID, los visitantes y sus datos pueden compartirse entre otras soluciones de Experience Cloud. Además, este ID puede reemplazar o trabajar con ID específicos de soluciones como el ID del visitante de Analytics. <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-overview.html"> [Más...] </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>ID del visitante. ¿Cómo se establece el ID del visitante si las cookies están bloqueadas? </p> </td> 
   <td colname="col3"> <p>Si la cookie s_vi estándar no está disponible, se crea una cookie de reserva en el dominio del sitio web con un ID único generada aleatoriamente. Esta cookie, denominada s_fid, se configura con una caducidad de 2 años y se usa como método de identificación de reserva a partir de ahora. <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/visid_fallback.html"> [Más...] </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Dynamic Tag Management. ¿Por qué no se activa mi regla de DTM? </p> </td> 
   <td colname="col3"> <p>Si su regla basada en eventos no se activa, es posible que haya un problema con el selector o con la condición de la regla. Localice el elemento de su sitio donde se produce la acción deseada del evento, haga clic con el botón derecho y seleccione Inspeccionar elemento. Inspeccione la secuencia de comandos destacada en el cuadro que se abre y asegúrese de que se trata del elemento correcto. <a href="https://marketing.adobe.com/resources/help/en_US/dtm/c_Troubleshooting.html"> [Más...] </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>¿Cómo implemento Seguimiento de vídeos de Heartbeat? </p> </td> 
   <td colname="col3"> <p> <a href="https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/hbvideo/"> Esta sección</a> contiene instrucciones sobre la descarga de los SDK de Heartbeat de vídeos y guías para desarrolladores para su plataforma. Asegúrese de descargar la guía para desarrolladores que se encuentra en la carpeta de documentos cuando descargue el SDK ya que contiene instrucciones de implementación específicas para Heartbeat de vídeos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>¿Cómo agrego cookies al subdominio correcto? </p> </td> 
   <td colname="col3"> La variable <span class="varname">cookieDomainPeriods</span> determina el dominio donde se configuran las cookies de Analytics s_cc y s_sq; para ello, determina el número de puntos en la dirección URL de la página. Algunos complementos también usan esta variable para determinar el dominio correcto donde se configurará la cookie del complemento. Consulte [Variables de configuración] (/help/implementation/js-implementation/c-variables/configuration-variables.md) </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Servidor de seguimiento. ¿Cómo relleno correctamente mi servidor de seguimiento? </p> </td> 
   <td colname="col3"> <p>Cuando configura una implementación para enviar datos a servidores de Adobe Analytics, debe enviarla a la ubicación correcta. Si no lo hace, se genera inflación en el recuento de visitantes o pérdida de datos. <a href="https://helpx.adobe.com/analytics/kb/determining-data-center.html"> [Más...] </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Rendimiento: ¿Puede afectar al rendimiento un error al cargar el archivo JavaScript externo de Adobe, ya sea debido a la conexión a Internet, al proxy, al servidor de seguridad o a una interrupción del servicio en Adobe? </p> </td> 
   <td colname="col3"> <p>No. El archivo de JavaScript no se aloja en servidores de Adobe, por lo que una interrupción en Adobe no afectará a la ejecución de JavaScript. Si se utiliza Dynamic Tag Management, el archivo JavaScript se aloja en Akamai o en la ubicación del servidor que determinen los clientes. </p> <p>Consulte <i>¿Dynamic Tag Management reducirá el rendimiento de mi sitio web?</i> en las <a href="https://marketing.adobe.com/resources/help/en_US/dtm/faq.html">Preguntas más frecuentes sobre Dynamic Tag Management </a>. </p> <p>Además, puede alojar su propio archivo de Dynamic Tag Management principal si no se siente cómodo utilizando la red CDN de Akamai. Consulte <a href="https://marketing.adobe.com/resources/help/en_US/dtm/deployment.html">Incrustar código y opciones de alojamiento </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Rendimiento: ¿Puede la carga del archivo JavaScript externo de Adobe causar una reducción del rendimiento? </p> </td> 
   <td colname="col3"> <p> El archivo JavaScript se almacena en caché en el explorador del visitante cuando se carga por primera vez y, por lo general, solo se descarga una vez por sesión. El archivo no se descarga en cada página, aunque lo usen todas las páginas del sitio. El cálculo promedio indica que, en la mayoría de sitios web, se registran varias vistas de página por sesión por usuario. De este modo, si se transfieren a este archivo los elementos JavaScript que se usan varias veces, se pueden reducir los datos que se descargan de forma general. </p> <p> Compresión de JavaScript para AppMeasurement: Si le preocupa el tamaño de la página del cliente JavaScript de Adobe, Adobe le recomienda que considere la posibilidad de comprimir el archivo utilizando GZIP. Todos los exploradores principales admiten GZIP, que ofrece un mejor rendimiento que la compresión de JavaScript para comprimir y descomprimir el archivo JavaScript <span class="filepath">s_code.js</span> principal. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Rendimiento: ¿Puede reducir el rendimiento el envío de datos desde el explorador a los servicios de Adobe? </p> </td> 
   <td colname="col3"> <p> El archivo JavaScript de Adobe crea un objeto de imagen en la página HTML y, a continuación, el explorador solicita el objeto de imagen de los servidores de Adobe. Si los servidores de Adobe van lentos o no responden, el proceso que administra esa solicitud se retrasará hasta que se devuelva la imagen o se agote el tiempo de espera. Como los exploradores administran las imágenes con varios procesos, una interrupción de Adobe tendría un impacto mínimo en el tiempo de carga de la página y bloquearía un proceso mientras los otros continúan funcionando. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Rendimiento: ¿Puede un evento de JavaScript de Adobe afectar al comportamiento o al rendimiento del sistema? </p> </td> 
   <td colname="col3"> <p>No. Consulte las respuestas anteriores sobre rendimiento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> ¿Cómo puedo cambiar los datos recopilados basándome en mis propias condiciones definidas? </td> 
   <td colname="col3"> Utilice reglas de procesamiento para simplificar la recopilación de datos y administrar el contenido que se envía a los informes. <a href="https://marketing.adobe.com/resources/help/en_US/reference/processing_rules.html"> [Más...] </a> </td> 
  </tr> 
  <tr> 
   <td> ¿Cuál es la última versión del archivo s_code? </td> 
   <td> This section contains a release history for <code>AppMeasurement</code> libraries across web and mobile platforms. Se puede descargar la última versión de todas las bibliotecas en Reports &amp; Analytics de &gt; Herramientas de administración &gt; Administrador de códigos. <a href="https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/release/c_release_notes_javascript.html"> [Más...] </a> </td> 
  </tr> 
  <tr> 
   <td> ¿Cómo depuro el archivo s_code? </td> 
   <td> Adobe Debugger (anteriormente DigitalPulse Debugger) es una herramienta gratuita de Adobe que le permite ver los datos que se recopilan de su sitio o de cualquier página dada. <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/debugger.html"> [Más...] </a> </td> 
  </tr> 
  <tr> 
   <td> ¿Cómo realizo un seguimiento de los distintos tipos de vínculo? </td> 
   <td> El seguimiento de las descargas de archivos y los vínculos de salida se puede realizar automáticamente en función de los parámetros configurados en el archivo de AppMeasurement para JavaScript. <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/function_tl.html"> [Más...] </a> </td> 
  </tr> 
  <tr> 
   <td> ¿Cómo realizo seguimiento de vídeo? </td> 
   <td> Se puede utilizar JavaScript para rastrear una amplia variedad de reproductores. Para rastrear con JavaScript, debe agregar código a la página web que contenga su reproductor y rastrear el reproductor con controladores de eventos. <a href="https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/video/video_js.html"> [Más...] </a> </td> 
  </tr> 
  <tr> 
   <td> ¿Cómo realizo seguimiento de una aplicación móvil? </td> 
   <td> Los vínculos de adquisición con códigos de seguimiento únicos se pueden generar en Adobe Mobile Services. Cuando un usuario descarga y ejecuta una aplicación desde la Apple App Store después de hacer clic en el vínculo generado, el SDK recopila automáticamente y envía los datos de adquisición a Adobe Mobile Services. <a href="https://marketing.adobe.com/resources/help/en_US/mobile/ios/acquisition.html"> iOS</a> <a href="https://marketing.adobe.com/resources/help/en_US/mobile/android/acquisition.html">Android </a> </td> 
  </tr> 
  <tr> 
   <td> ¿Cómo implemento el seguimiento de vídeo? </td> 
   <td> Puede rastrear reproductores multimedia al crear funciones adjuntadas a los controladores de eventos de los reproductores de vídeo. Esto le permite llamar a Media.open, Media.play, Media.stop y Media.close en los momentos adecuados. <a href="https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/video/video_js_events.html"> [Más...] </a> </td> 
  </tr> 
  <tr> 
   <td> ¿Cómo instalo la cookie de origen? </td> 
   <td> Analytics utiliza cookies para ofrecer información sobre variables y componentes que no se mantienen entre solicitudes de imagen y sesiones del navegador. Estas cookies son inofensivas y se originan en un dominio hospedado por Adobe; se denominan cookies de terceros. <a href="https://marketing.adobe.com/resources/help/en_US/whitepapers/first_party_cookies/fpcookies_cert.html"> [Más...] </a> </td> 
  </tr> 
  <tr> 
   <td> ¿Cómo obtengo un certificado de SSL? </td> 
   <td> Averigüe si su sitio utiliza el protocolo https://. Si es así, es necesario solicitar un CSR y adquirir un certificado SSL. Nota: No necesita un certificado SSL si no tiene ninguna página ni contenido seguro. Todo este paso se puede omitir si solo utiliza el protocolo https:// en su sitio. <a href="https://marketing.adobe.com/resources/help/en_US/whitepapers/first_party_cookies/fpcookies_cert.html"> [Más...] </a> </td> 
  </tr> 
  <tr> 
   <td> ¿Dónde encuentro información sobre el aviso de caducidad del certificado? </td> 
   <td> Los certificados SSL caducan cada año, por lo que Adobe requiere una solicitud de certificado actualizado cada vez que esto ocurre. El especialista de FPC lo advierte razonablemente cuando esto sucede; sin embargo, se recomienda supervisar la caducidad de forma proactiva y facilitar a Adobe este certificado actualizado. <a href="https://marketing.adobe.com/resources/help/en_US/whitepapers/first_party_cookies/fpcookies_renewals.html"> [Más...] </a> </td> 
  </tr> 
  <tr> 
   <td> ¿Qué son los complementos? </td> 
   <td> Los complementos de AppMeasurement para JavaScript son programas o funciones que realizan algunas funciones avanzadas. Estos complementos amplían las capacidades del archivo JavaScript y aportan una funcionalidad ampliada que no se encuentra disponible con una implementación básica. Adobe ofrece otros complementos como parte de soluciones avanzadas. Póngase en contacto con su Administrador de cuentas si desea capturar datos con JavaScript pero no está seguro de cómo hacerlo. <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/impl_plugins.html"> [Más...] </a> </td> 
  </tr> 
  <tr> 
   <td> ¿Necesita información sobre API de inserción de datos? </td> 
   <td> Adobe ha creado varios métodos para enviar datos a Analytics. <a href="https://marketing.adobe.com/resources/help/en_US/reference/usecase_sending_data_to_sc.html"> [Más...] </a> </td> 
  </tr> 
  <tr> 
   <td> ¿Qué es un error 500? </td> 
   <td> Información sobre el error de servidor interno que generó un estado “Error de consulta 500”. <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/pageType.html">Consulte la variable pageType </a> </td> 
  </tr> 
 </tbody> 
</table>

| Pregunta | Respuesta |
|---|---|
| ¿Cómo administro a los usuarios y grupos de Analytics? | Para obtener información sobre la administración de usuarios y grupos, consulte [Administrar usuarios y productos](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/admin-getting-started.html) de Experience Cloud en la ayuda de Adobe Experience Cloud Core Services. |
| Caducidad de eVar: ¿Por qué se atribuyen las eVars a 'Ninguno' en los informes? | `Expire After` especifica un período de tiempo o un evento tras el cual caduca el valor de la eVar (ya no recibe crédito por los eventos de éxito). Si se da un evento de éxito después de que caduque la eVar, el valor Ninguno recibe crédito por el evento (no había ninguna eVar activa). Si selecciona un evento como valor de caducidad, la variable caducará solamente si ocurre el evento. Si no ocurre el evento, la variable no caducará nunca. [[Más...](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/conversion-variables/conversion-var-admin.html) |
| Visibilidad de Eventos personalizados. ¿Por qué los Eventos personalizados no aparecen en el menú de informes? | En la columna Visibilidad, puede ocultar las métricas (integradas), los eventos personalizados y los eventos incorporados en el menú, los selectores de métricas, el Creador de métricas calculadas y el Generador de segmentos. Esta configuración no afecta a la recopilación de datos de esa métrica o evento. Solo afecta a su visibilidad en la interfaz de usuario. [[Más...](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/metric-visibility.html) |
| Marcas de hora. ¿Qué debo tener en cuenta antes de cambiar los ajustes de marcas de hora? | Con la característica Marcas de hora opcionales, puede combinar datos sin marca de hora con datos con marca de hora sin provocar una pérdida de datos. Los datos sin conexión con marca de hora generados en un dispositivo móvil se pueden combinar con datos activos sin marca de hora de una página web, o integrarse con datos de cualquier plataforma utilizando una llamada a la variable timestamp de lado del cliente. [[Más...](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/timestamps-overview.html) |
| ID del visitante. ¿Cómo funciona el período de gracia del ID del visitante y cómo se habilita? | Si tiene varios archivos JavaScript que envían datos al mismo grupo de informes o si utiliza otras tecnologías en el sitio, como la medición de vídeo Flash, le recomendamos que configure un período de gracia.  [Más...](https://docs.adobe.com/content/help/en/id-service/using/reference/analytics-reference/grace-period.html) |
| ID del visitante. ¿Cuál es la diferencia entre el ID del visitante de Experience Cloud y el ID del visitante de Analytics? | El Servicio de identidad asigna un identificador único y persistente a todos los visitantes de su sitio. Con este ID, los visitantes y sus datos pueden compartirse entre otras soluciones de Experience Cloud. Además, este ID puede reemplazar o trabajar con ID específicos de soluciones como el ID del visitante de Analytics.  [Más...](https://docs.adobe.com/content/help/en/id-service/using/intro/overview.html) |
| ID del visitante. ¿Cómo se establece el ID del visitante si las cookies están bloqueadas? | Si la cookie s_vi estándar no está disponible, se crea una cookie de reserva en el dominio del sitio web con un ID único generada aleatoriamente. Esta cookie, denominada s_fid, se configura con una caducidad de 2 años y se usa como método de identificación de reserva a partir de ahora.  [Más...](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/unique-visitors/visid-fallback.html) |
| Dynamic Tag Management. ¿Por qué no se activa mi regla de DTM? | Si su regla basada en eventos no se activa, es posible que haya un problema con el selector o con la condición de la regla. Localice el elemento de su sitio donde se produce la acción deseada del evento, haga clic con el botón derecho y seleccione Inspeccionar elemento. Inspeccione la secuencia de comandos destacada en el cuadro que se abre y asegúrese de que se trata del elemento correcto.  [Más...](https://docs.adobe.com/content/help/en/dtm/using/admin/c-troubleshooting.html) |
| ¿Cómo implemento Seguimiento de vídeos de Heartbeat? | [Esta sección](https://docs.adobe.com/content/help/en/media-analytics/using/media-overview.html) contiene instrucciones sobre la descarga de los SDK de Heartbeat de vídeos y guías para desarrolladores para su plataforma. Asegúrese de descargar la guía para desarrolladores que se encuentra en la carpeta de documentos cuando descargue el SDK ya que contiene instrucciones de implementación específicas para Heartbeat de vídeos. |
| ¿Cómo agrego cookies al subdominio correcto? | La variable cookieDomainPeriods determina el dominio donde se configuran las cookies de Analytics s_cc y s_sq; para ello, determina el número de puntos en la dirección URL de la página. Algunos complementos también usan esta variable para determinar el dominio correcto donde se configurará la cookie del complemento. See [Configuration Variables](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/configuration-variables.html) |
| Servidor de seguimiento. ¿Cómo relleno correctamente mi servidor de seguimiento? | Cuando configura una implementación para enviar datos a servidores de Adobe Analytics, debe enviarla a la ubicación correcta. Si no lo hace, se genera inflación en el recuento de visitantes o pérdida de datos. [Más...](https://helpx.adobe.com/analytics/kb/determining-data-center.html) |
| Rendimiento: ¿Puede afectar al rendimiento un error al cargar el archivo JavaScript externo de Adobe, ya sea debido a la conexión a Internet, al proxy, al servidor de seguridad o a una interrupción del servicio en Adobe? | No. El archivo de JavaScript no se aloja en servidores de Adobe, por lo que una interrupción en Adobe no afectará a la ejecución de JavaScript. |
| Rendimiento: ¿Puede la carga del archivo JavaScript externo de Adobe causar una reducción del rendimiento? | El archivo JavaScript se almacena en caché en el explorador del visitante cuando se carga por primera vez y, por lo general, solo se descarga una vez por sesión. El archivo no se descarga en cada página, aunque lo usen todas las páginas del sitio. El cálculo promedio indica que, en la mayoría de sitios web, se registran varias vistas de página por sesión por usuario. De este modo, si se transfieren a este archivo los elementos JavaScript que se usan varias veces, se pueden reducir los datos que se descargan de forma general. <br>Compresión de JavaScript para AppMeasurement: Si le preocupa el tamaño de la página del cliente JavaScript de Adobe, Adobe le recomienda que considere la posibilidad de comprimir el archivo utilizando GZIP. Todos los exploradores principales admiten GZIP, que ofrece un mejor rendimiento que la compresión de JavaScript para comprimir y descomprimir el archivo JavaScript `s_code.js` principal. |
| Rendimiento: ¿Puede reducir el rendimiento el envío de datos desde el explorador a los servicios de Adobe? | El archivo JavaScript de Adobe crea un objeto de imagen en la página HTML y, a continuación, el explorador solicita el objeto de imagen de los servidores de Adobe. Si los servidores de Adobe van lentos o no responden, el proceso que administra esa solicitud se retrasará hasta que se devuelva la imagen o se agote el tiempo de espera. Como los exploradores administran las imágenes con varios procesos, una interrupción de Adobe tendría un impacto mínimo en el tiempo de carga de la página y bloquearía un proceso mientras los otros continúan funcionando. |
| Rendimiento: ¿Puede un evento de JavaScript de Adobe afectar al comportamiento o al rendimiento del sistema? | No. Consulte las respuestas anteriores sobre rendimiento. |
| ¿Cómo puedo cambiar los datos recopilados basándome en mis propias condiciones definidas? | Utilice reglas de procesamiento para simplificar la recopilación de datos y administrar el contenido que se envía a los informes.  ([Más...](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/processing-rules/processing-rules.html) |
| ¿Cuál es la última versión del archivo s_code? | Esta sección contiene un historial de versiones para bibliotecas de AppMeasurement en plataformas web y móviles. Se puede descargar la última versión de todas las bibliotecas en Analytics &gt; Administración &gt; Administrador de códigos. [Más...](/help/implement/appmeasurement-release-notes/c-release-notes-mjs.md) |
| ¿Cómo depuro el archivo s_code? | Experience Cloud Debugger es una herramienta gratuita de Adobe que le permite ver los datos que se recopilan de su sitio o de cualquier página. [Más...](https://docs.adobe.com/content/help/en/analytics/implementation/testing-and-validation/debugger.html) |
| ¿Cómo realizo un seguimiento de los distintos tipos de vínculo? | El seguimiento de las descargas de archivos y los vínculos de salida se puede realizar automáticamente en función de los parámetros configurados en el archivo de AppMeasurement para JavaScript. [Más...](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/function-tl.html) |
| ¿Cómo realizo seguimiento de vídeo? | Se puede utilizar JavaScript para rastrear una amplia variedad de reproductores. Para rastrear con JavaScript, debe agregar código a la página web que contenga su reproductor y rastrear el reproductor con controladores de eventos. [Más...](https://docs.adobe.com/content/help/en/media-analytics/using/media-overview.html) |
| ¿Cómo realizo seguimiento de una aplicación móvil? | Los vínculos de adquisición con códigos de seguimiento únicos se pueden generar en Adobe Mobile Services. Cuando un usuario descarga y ejecuta una aplicación desde la Apple App Store después de hacer clic en el vínculo generado, el SDK recopila automáticamente y envía los datos de adquisición a Adobe Mobile Services. [iOS](https://docs.adobe.com/content/help/en/mobile-services/ios/overview.html), [Android](https://docs.adobe.com/content/help/en/mobile-services/android/overview.html) |
| ¿Cómo implemento el seguimiento de vídeo? | Puede rastrear reproductores multimedia al crear funciones adjuntadas a los controladores de eventos de los reproductores de vídeo. Esto le permite llamar a Media.open, Media.play, Media.stop y Media.close en los momentos adecuados. [Más...](https://docs.adobe.com/content/help/en/media-analytics/using/media-overview.html) |
| ¿Cómo instalo la cookie de origen? | Analytics utiliza cookies para ofrecer información sobre variables y componentes que no se mantienen entre solicitudes de imagen y sesiones del navegador. Estas cookies son inofensivas y se originan en un dominio hospedado por Adobe; se denominan cookies de terceros. [Más...](https://marketing.adobe.com/resources/help/en_US/whitepapers/first_party_cookies/fpcookies_cert.html) |
| ¿Cómo obtengo un certificado de SSL? | Descubra si su sitio usa el protocolo `https://`. Si es así, es necesario solicitar un CSR y adquirir un certificado SSL. Nota: No necesita un certificado SSL si no tiene ninguna página ni contenido seguro. Todo este paso se puede omitir si solo utiliza el protocolo `https://` en su sitio.  [Más...](https://marketing.adobe.com/resources/help/en_US/whitepapers/first_party_cookies/fpcookies_cert.html) |
| ¿Dónde encuentro información sobre el aviso de caducidad del certificado? | Los certificados SSL caducan cada año, por lo que Adobe requiere una solicitud de certificado actualizado cada vez que esto ocurre. El especialista de FPC lo advierte razonablemente cuando esto sucede; sin embargo, se recomienda supervisar la caducidad de forma proactiva y facilitar a Adobe este certificado actualizado. [Más...](https://marketing.adobe.com/resources/help/en_US/whitepapers/first_party_cookies/adobe_managed_cert_pgm.html) |
| ¿Qué son los complementos? | Los complementos de AppMeasurement para JavaScript son programas o funciones que realizan algunas funciones avanzadas. Estos complementos amplían las capacidades del archivo JavaScript y aportan una funcionalidad ampliada que no se encuentra disponible con una implementación básica. Adobe ofrece otros complementos como parte de soluciones avanzadas. Póngase en contacto con su Administrador de cuentas si desea capturar datos con JavaScript pero no está seguro de cómo hacerlo. [Más...](/help/implement/js-implementation/c-appmeasurement-js/plugins-support.md) |
| ¿Cómo encuentro información sobre la API de inserción de datos? | Adobe ha creado varios métodos para enviar datos a Analytics. [Más...](https://helpx.adobe.com/analytics/kb/data-insertion-api-post-method-adobe-analytics.html) |
| ¿Qué es un error 500? | La información sobre el error interno del servidor que causó el estado "Error de consulta 500" se puede encontrar en la [variable](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/page-variables.html#concept_F67870238EF74491B5D3909A33CDB985)pageType. |

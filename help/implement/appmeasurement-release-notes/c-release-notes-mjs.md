---
description: Recopilación de notas de versiones de AppMeasurement para JavaScript.
seo-description: Recopilación de notas de versiones de AppMeasurement para JavaScript.
seo-title: AppMeasurement para JavaScript
solution: Analytics
subtopic: Notas de la versión
title: AppMeasurement para JavaScript
topic: Desarrollador e implementación
uuid: 1440013 d-d 266-4 dce -9807-8 b 9 adac 73315
translation-type: tm+mt
source-git-commit: 2147e95f3ebd731c161e40a212db0a9067a98f9a

---


# AppMeasurement para JavaScript{#appmeasurement-for-javascript}

Cumulative release notes for [!DNL AppMeasurement] for JavaScript.

<!-- 

<p>https://wiki.corp.adobe.com/display/omtrcache/AppMeasurement+Change+Log </p>

 -->

The latest version of each library can be downloaded in **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL Code Manager]**.

## Versiones 2.17.0

Fecha de lanzamiento: **23 de agosto de 201**

| Función/Corrección | Descripción |
| -----------| ---------- |
| Se agregó compatibilidad con Baidu | Se agregó compatibilidad con la reordenación de las cadenas de consulta Baidu. |
| Se corrigió un problema que hacía que se mostrara | Se ha corregido un problema que provocaba valores de visitantes antiguos en las visitas que se ponen en cola mientras se esperaba la inclusión. |

## Versión 2.16.0

Fecha de versión: **15 de agosto de 2019**

| Función | Descripción |
| -----------| ---------- |
| `sendBeacon` admite vínculos de salida | Se ha implementado compatibilidad con `sendBeacon` en [!UICONTROL AppMeasurement] para vínculos de salida. Esto mejorará el seguimiento de vínculos de salida y probablemente dará como resultado un incremento del tráfico. `SendBeacon` no se ejecuta en el contexto de una página, sino en el contexto del explorador. Es decir, si una página se descarga, `sendBeacon`la solicitud se completará. Esto resulta muy útil para los vínculos de salida porque hará que sea mucho más probable que se complete la solicitud de vínculo de salida. |
| Valores ECID/fid | Los valores ECID/fid ahora se almacenan en la caché en la primera visita, aunque cambie la configuración de OptIn. |
| DIL 9.3 | Módulo de Gestión de público actualizado a DIL 9.3 |
| Seguimiento de alcance de desplazamiento | Conmutador expuesto en s.ActivityMap.trackScrollReach para activar o desactivar el seguimiento de alcance de desplazamiento. |
| Servicio de ID de visitante 4.4.0 | AppMeasurement actualizado para utilizar el servicio de ID de visitante 4.4.0. |

## Versión 2.15.0

Fecha de publicación:**15 de julio de 2019**

* Se ha agregado el seguimiento de alcance de desplazamiento de Activity Map a la extensión Mapa de actividades (AN -172949)
* Se ha añadido DIL 9.2 a appmeasurement (AN -182472)

## Versión 2.14.0

Fecha de versión: **21 de mayo de 2019**

* Se han corregido los errores relacionados con la administración del estado de los parámetros del rastreador cuando hay varias visitas pendientes. (AN-176931, AN-176629, DTM-12758)
* AppMeasurement actualizado para incluir Visitor.js 4.3.0 (AN-180049)

## Versión 2.13.0

Fecha de versión: **10 de abril de 2019**

Corrección de muchos problemas informados con clearvars. El problema se produce cuando las visitas se envían antes de que el rastreador esté listo. Cuando el rastreador está listo, la biblioteca puede establecer variables que ya se hayan borrado o cambiado. (AN-176931, AN-176629, DTM-12758).

## Versión 2.12.0

Release Date: **02/22/2019**

* Módulo de Gestión de público actualizado a DIL 9.1 (AN-175255)
* Política de seguridad GTM que no permite el módulo de Activity Map. (AN-174679)
* Appmeasurement mejorada para respetar la exclusión cuando el servicio de identidad no se apruebe en la inclusión. (AN-175259)

## Versión 2.11.0

Release Date: **02/11/2019**

* Se ha agregado compatibilidad con la nueva funcionalidad Servicios de inclusión de Adobe en AppMeasurement. (AN-163546)
* Se ha agregado compatibilidad con el almacenamiento de datos de seguimiento de vínculos en el almacenamiento de sesión. (AN-162272)
* Se ha agregado compatibilidad con el tipo de flujo de medios para Audio Analytics. (AN-173265)

## Versión 2.10.0 {#section_0788526EF23049C9AEB1EE5E8FC985DD}

Release Date: **09/20/2018**

This release ensures that the [!DNL AppMeasurement] library submits cookies correctly for all connection types.

* [!DNL AppMeasurement] bloquea las transmisiones de cookies durante POST. (AN-165538)
* Se ha cancelado la compatibilidad con XDomainRequest. (AN-165733)
* Reduce [!DNL AppMeasurement] default cookie lifetime from five to two years. (AN-158572)
* Remove the Media Module from the Code Manager ( [!DNL AppMeasurement]) (AN-166590)

## Versión 2.9.0 {#section_E973B8A628F348AA9A1A1599CFE37DB9}

Fecha de la versión: **24/05/2018**

>[!NOTE]
>
>Visitor API 3.0 or higher is required for customers using the [!DNL Experience Cloud] ID Service. Adobe recomienda actualizar a la última versión de la API de visitantes cada vez que se actualicen las bibliotecas de código asociadas ([!DNL at.js], etc.).[!DNL AppMeasurement.js]

* Updated [!DNL AppMeasurement] to use the updated Visitor interface for requesting IDs. (AN-151483)
* Se ha solucionado un problema que causaba que la cookie de seguimiento seguía escribiéndose tras desactivar el seguimiento de enlaces. (AN-156332)
* Se ha solucionado un problema que provocaba los desgloses `registerPreTrackCallback` y `registerPostTrackCallback` de firma de función callback cuando al llamarla varias veces. (AN-158566)

## Versión 2.8.2 {#section_B70EAEDAB087464482DB04EC4187200D}

Fecha de la versión: **12/04/2018**

* Update [!DNL AppMeasurement] to use the updated visitor interface for requesting IDs. (AN-151483)
* La cookie de seguimiento de enlace sigue escribiéndose tras desactivar el seguimiento de enlaces. (AN-156332)
* Reduce [!DNL AppMeasurement] default cookie lifetime from five to two years. (AN-158572)

## Versión 2.8.1 {#section_6C1C4091F2EE4C90B6F3D7EE783DD884}

Fecha de la versión: **29/03/2018**

Nuevo paquete de la API de Visitante 3.1.0 (AN-159524), que incluye las correcciones: (CORE-11390, CORE-10634)

## Versión 2.8.0 {#section_A23AD604D34C497C9318D3EB211B7927}

Fecha de la versión: **15/03/2018**

Nuevo paquete de la API de Visitante 3.1.0 (AN-159524), que incluye las correcciones: (CORE-11390, CORE-10634)

* Bundle VAPI v3.1 with [!DNL AppMeasurement] v2.8. (AN-158353)
* Refactorización mediante la compilación del punto final de recopilación de datos para facilitar el uso compartido. (AN-156647)
* Adición de métricas de temporización de viajes de ida y vuelta de solicitud a [!DNL AppMeasurement]. (AN-158343)

## Versión 2.7.0 {#section_2C047D410B614CEE950DBBC75F035033}

Fecha de la versión: **18/01/2018**

* Abandono del soporte para las versiones 6 a 9 de Internet Explorer
* Inclusión de la API de visitantes 3.0.0
* Inclusión de DIL 7.00

## Versión 2.6.0 {#section_229356205EAB4D05890A00B39C42A650}

Fecha de la versión: **09/11/2017**

Fixed an issue where [!DNL AppMeasurement] library does not always set the correct account combination when s_gl is called. (AN-152153)

## Versión 2.5.0 {#section_3C0006D526CA405FA0C47E2D991012BA}

Fecha de la versión: **21/09/2017**

* Inclusion of [!DNL dil.js 6.12] ( [!DNL Audience Manager] module)

* Inclusión de la API de Visitante 2.5.0.

## Versión 2.4.0 {#section_60D01A128AEE4A97AC492DF8FBE1E7A3}

Fecha de la versión: **17/08/2017**

* Se ha incluido dil.js v6.11
* Se ha incluido la API 2.4.0 de visitante

## Versión 2.3.0 {#section_D8F9BFF0D4E44E0F876840360D56E815}

Fecha de la versión: **20/07/2017**

* Se ha solucionado un error por el que [!DNL s.Util.getQueryParam] capturaba #
* Added v6.10 of [!DNL dil.js] (AN-145701)

## Versión 2.2.0 {#section_5E23F21413B1443B9A3021CCC9578C4B}

Fecha de la versión: **08/06/2017**

* Added support for multiple [!DNL AppMeasurement] instantiation order. (AN-138237)
* Inclusión de la API de visitante 2.2.0. (AN-144042)

## Versión 2.1.0 {#section_5FE53738F9124C86811DFA08923B6F7B}

* Se ha incluido la última versión de [!DNL dil.js] (AN-140396)
* Added support for `adobe_mc_ref` parameter which overrides the page referrer. (AN-131920)
* Se ha vuelto a incluir la API 2.1.0 de visitante. (AN-140873)
* Se ha añadido `mcorgid` el parámetro. (AN-139586)
* Se ha agregado el parámetro (customerPerspective). (AN-140897)

## Versión 2.0.0 {#section_4C4A502CDFC84F06914EB16CE77736D1}

Fecha de la versión: **09/03/2017**

* Se ha movido a un nuevo proceso de creación que exige actualizar al número de versión 2.0.0. (AN-137878)
* Se ha movido el tratamiento de mboxMCSDID a la ubicación de la sección correcta, donde se efectúa la llamada de seguimiento. (AN-138483)

## Versión 1.8.0 {#section_617B2F09F3494C04901E364ACEDE17E1}

Fecha de la versión:**19/01/2017**

* Inclusión de la API de visitante 2.0.0
* La función resecuenciada llama y comprueba de modo que SDID se consuma una vez completada la comprobación de anulación. (AN-134364)
* Se han agregado los siguientes enlaces de llamadas antes y después del seguimiento. (AN-134567)

   * s.registerPreTrackCallback
   * s.registerPostTrackCallback
   Estas funciones toman como parámetros la rellamada (una función) y los parámetros que llevan a esa función. Por ejemplo:

   ```
   s.registerPreTrackCallback(function(requestUrl,a,b,c) { 
       console.log("pre track callback"); 
       console.dir(requestUrl); // Request URL 
       console.dir(a); // param1 
       console.dir(b); // param2 
       console.dir(c); // param3 
   }, "param1", "param2", "param3");
   ```

   La rellamada se invoca con `requestUrl` y cualquier parámetro que haya pasado cuando se registró la rellamada. Esto ocurre antes o después de la llamada de seguimiento, según el método que se utilice para registrar la rellamada. No se puede garantizar el orden en el que se realizan estas rellamadas. Las rellamadas que se registran en la función previa se invocan después de crearse la URL de seguimiento final. Las rellamadas posteriores se realizan cuando se ha llevado a cabo una llamada de seguimiento con éxito (si la llamada de seguimiento falla, no se llaman a estas funciones). Las rellamadas que se registren con `registerPreTrackCallback` no afectan a la llamada de seguimiento. Además, no se recomienda llamar a ninguno de los métodos de seguimiento en una rellamada registrada, ya que podría causar un bucle infinito.

## Versión 1.7.0 {#section_A93F24391B1043F4A435D1AA76D9E4F0}

Actualizado: **10/11/2016**

* Se ha incluido la API 1.10.1 de visitante.

## Versión 1.7.0 {#section_107CDB8468AE4B06B900DCDEE5AD2F0A}

Actualizado: **20/10/2016**

* Update [!DNL Audience Manager] module with Demdex Integration Library (DIL) 6.6. (AN-132065)
* Inclusión de la API de visitante 1.9.0. (AN-132072)

## Versión 1.7.0 {#section_945311938EE2480A9A697BFE1E5B2AA7}

Actualizado: **15/09/2016**

* Actualizar [!DNL AppMeasurement][!DNL Audience Manager] módulo con DIL 6.5 y configuraciones adicionales (AN -129411)

* Inclusión de la API de visitantes 1.8.0 (AN-129887)

## Versión 1.6.4 {#section_7C40FE01EA5B43E486098FCAC8FA5EC3}

Actualizado: **18/08/2016**

* Updated [!DNL AppMeasurement] to read and write AMCV cookies. (AN-127098)
* Inclusión de la API de visitante 1.7.0.

>[!NOTE]
>
>Also see the following release notes for [!DNL JavaScript] version 1.6.3, which includes updated requirements for Marketing Cloud ID service.

## Versión 1.6.3 {#section_34C75470A84B461A89FEF8CFF7B94090}

Actualizado: **04/08/2016**

* Fixed an issue where [!DNL AppMeasurement] prematurely terminated request connections. (AN-126448)

>[!IMPORTANT]
>
>Version 1.6.0 of the [!DNL Marketing Cloud] ID service *requires* [!DNL AppMeasurement] for [!DNL JavaScript] version 1.6.3 or higher. If you want to upgrade to version 1.6.0 of the Marketing Cloud ID service, please make sure you are using [!DNL AppMeasurement] code verison 1.6.3 or higher.

## Versión 1.6.2 {#section_419CBF264B5741DABB005AFDC6197C0D}

Fecha de publicación:**21 de julio de 2016**

* Inclusión de la API de visitante 1.6.0.
* Fixed an issue causing [!DNL AppMeasurement] to call the wrong obfuscated method in the Visitor API. (AN-126006)
* Fixed an issue causing the [!DNL JavaScript] error: "Attribute only valid on v:image". (AN-124009)

<!-- 

<note type="important">
  Adobe strongly recommends upgrading to version 1.6.2 or higher. This version requires Visitor API 1.6.0, and vice-versa. 
</note>

 -->

## Versión 1.6.1 {#section_E69F5883F84F4D2CAE25D385F56C6AF6}

Fecha de versión: **16 de junio de 2016**

Inclusión de la API de visitante 1.5.7.

## Versión 1.6.1 {#section_5927689A57164EC99BA501B4FDF0AE8F}

Fecha de versión: **19 de mayo de 2016**

[!DNL JavaScript] versión 1.5.6

* Inclusión de la API de visitante 1.5.6
* Se ha solucionado la administración del rastreo de clics de los vínculos en Firefox, que no activaba el evento completo.

## Versión 1.6 {#section_B132B272FC2E43E9A24198F459E29403}

Fecha de versión: **21 de abril de 2016**

* The [!DNL AppMeasurement] [!DNL Activity Map] module has been integrated in the [!DNL AppMeasurement] standard module, so that you only have to reference one [!DNL .js] file. Additionally, [!DNL Activity Map] tracking is activated by default. (AN-112689)

* Fixed a truncation issue occurring with the order of query-string variables in [!DNL AppMeasurement], so that *`pageURLRest`* is last. (AN-114647)

## Versión 1.5.4 {#section_A230E5F656734ABD9917388790A37B5D}

Fecha de versión: **17 de marzo de 2016**

* Inclusión de la API de visitante 1.5.4
* Compatibilidad con la anulación de la suscripción a la API de visitante 1.5.4+

## Versión 1.5.3 {#section_796927A1BBF74DF6A1A4B9477E0BD20E}

Fecha de versión: **21 de enero de 2016**

* Fixed handling of [!DNL Audience Manager] module when POSTs are used for tracking calls. (AN-115381)
* Se ha movido el resto de la URL de la página ("-g") al final de la cadena de solicitud de seguimiento. (AN-114647)

## Versión 1.5.2 {#section_17CFD0BBC8744447BDFCC833883BC93E}

Fecha de versión: **5 de noviembre de 2015**

* Inclusión de la API de visitante 1.5.3.
* Se ha solucionado la detección de IE11 para el truncado de la URL 2047 (AN-114914)

## Versión 1.5.1 {#section_432F3C69DDBB49C983D7CB0876C2152F}

Fecha de versión: **17 de septiembre de 2015**

* Inclusión de la API de visitante 1.5.2

## Versión 1.5.1 {#section_077DA135C1A5466EB00C44A3C3E472F8}

Fecha de versión: **29 de agosto de 2015**

* Inclusión de la API de visitante 1.5.1.

## Versión 1.5.1 {#section_3C9637EDB058479184731067897E857C}

Fecha de versión: **16 de julio de 2015**

* Updated [!DNL Audience Manager] module to use AAM DIL 6.2 - getCustomer IDs from VisitorAPI.js and pass them in /event call to AAM. (AN-104978)

## Versión 1.5 {#section_8809DBD822E440C6B5B7FF41E5DF3015}

Fecha de versión: **18 de junio de 2015**

* Compatibilidad con la API de visitante 1.5, que utiliza el método *`getCustomerIDs`* para recopilar ID de cliente y estados autenticados, y envía los ID con solicitudes de recopilación de datos.
* Fixed the creation of duplicate destinationing iframe in **[!UICONTROL AudienceManagement]** module (DIL 6.1)
* Se ha solucionado el error conocido descrito en la versión 1.4.5.

## Versión 1.4.5 {#section_FA2E94DF78614ACE9944660E14EF3A75}

Fecha de versión: **21 de mayo de 2015**

<table id="table_E0F3EF51FED44420AC97ACF0684554D0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Función </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="keyword"> Extensión de iOS</span> </p> </td> 
   <td colname="col2"> <p> Starting in <span class="keyword"> iOS </span> SDK version 4.5, a new <span class="keyword"> iOS </span> extension lets you collect usage data from your Apple Watch Apps, Today Widgets, Photo Editing widgets, and all the other <span class="keyword"> iOS </span> extension apps. </p> <p>Consulte <a href="https://marketing.adobe.com/resources/help/en_US/mobile/ios/?f=ios_ext" format="https" scope="external">Implementación de la extensión de iOS </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="keyword"> Extensión de Android Wearable</span> </p> </td> 
   <td colname="col2"> <p> Starting in <span class="keyword"> Android </span> SDK version 4.5, a new <span class="keyword"> Android </span> extension lets you collect data from your <span class="keyword"> Android </span> Wearable app. </p> <p>Consulte <a href="https://marketing.adobe.com/resources/help/en_US/mobile/android/?f=android_wearable" format="https" scope="external">Extensión de Android Wearable </a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

* Inclusión de la API de visitante 1.4.
* Se ha actualizado el módulo AudienceManagement para que utilice DIL versión 6.0.

**Problema conocido**

En las integraciones de API/ [!DNL AppMeasurement][!DNL Audience Manager] módulo de visitante, habrá dos solicitudes de iframe de publicación de destino realizadas en IE 6-9: `//fast.<subdomain>.demdex.net/dest5.html` y `//fast.<subdomain>.demdex.net/dest4.html`. El comportamiento correcto, tal como se ha observado en otros exploradores, es cargar únicamente `//fast.<subdomain>.demdex.net/dest5.html`.

## Versión 1.4.4 {#section_C069FA04496C4F7DAC165B04E836CF1F}

Fecha de versión: **16 de abril de 2015**

<table frame="all" colsep="1" rowsep="1" id="table_812CAB7DDC364DAABB7CDEDE55532E39"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> Función </th> 
   <th colname="2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p> Datos personalizados con métricas del ciclo vital </p> </td> 
   <td colname="2"> <p>Ahora puede incluir variables de datos de contexto personalizado con métricas del ciclo vital. </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Beacon tracking support in <span class="keyword"> PhoneGap </span> </p> </td> 
   <td colname="2"> <p>Las llamadas <code>trackBeacon</code> y <code>clearCurrentBeacon</code><span class="keyword"> ahora están disponibles en PhoneGap </span>. </p> </td> 
  </tr> 
 </tbody> 
</table>

Una pequeña corrección para borrar el ID del perfil de la llamada del servidor ligero después de la llamada `trackLight`.

## Versión 1.4.3 {#section_C307052BA42248ADB1969AE7A2593177}

Fecha de versión: **19 de febrero de 2015**

* Se ha sistematizado todo el tratamiento de las llamadas de seguimiento demoradas con lo cual se han corregido los problemas con las variables de copia de seguridad durante la demora, por ejemplo, el objeto en el que se ha hecho clic.
* Se ha cambiado la opción a no hacer seguimiento automático del referente tras la primera llamada de seguimiento, de modo que las llamadas segunda, tercera, etc. (por lo general seguimiento de vínculos) no contarán al referente doble si se ha configurado manualmente *`s.referrer`* se ha establecido manualmente antes de la primera llamada de seguimiento. 
* Se ha actualizado el zip de distribución para incluir la API de visitante 1.3.5.

## Versión 1.4.2 {#section_0A0BE40D32144A338231022F97B0E72B}

Fecha de versión: **15 de enero de 2015**

* Se ha solucionado la administración del procesamiento previo de WebKit para impedir que se haga un seguimiento de las páginas procesadas previamente que no se muestran.
* The distribution zip was updated to include Visitor API 1.3.4 and an updated **[!UICONTROL AudienceManagement]** module that includes DIL version 5.5.

## Versión 1.4.1 {#section_616FF936062F44E8B70032D18AAAFC5F}

Fecha de versión: **18 de septiembre de 2014**

* Se agregó una variable `tagContainerMarker` que permite la implementación para especificar hasta 4 caracteres que se anexan a la cadena de versión junto con un delimitador de guion adicional. Se usa mediante la administración dinámica de etiquetas.

   ```js
   // JavaScript 
   s.tagContainerMarker = "D1.0"; 
   
   // Data Collection request 
   //.../b/ss/myrsid/1/JS-1.4.1-D1.0/s43317392037311?...
   ```

   Los cuatro caracteres se limitan a caracteres permitidos en las rutas de archivo de URL, como caracteres alfanuméricos y punto.

* En las páginas con doble etiqueta con código H, se corrigió un bucle que se podía producir durante el seguimiento automático de vínculos (descarga y salida) cuando se habilita el seguimiento forzado de vínculos (exploradores de Webkit predeterminados). Además, se agregó una protección general en torno al seguimiento automático de vínculos para impedir bucles similares. Esta protección limita el seguimiento automático de vínculos de clics repetidos con el *mismo* objeto a una vez cada 10 segundos. Esta protección se aplica solo al seguimiento automático de vínculos, de modo que las llamadas al seguimiento manual de vínculos (s.tl) no están limitadas. Los clics a diferentes objetos tampoco se ven afectados por esta protección y se seguirán.
* Se corrigió el control del objeto en el que se hace clic cuando es necesario un retraso.
* Se corrigió un problema que provocaba un recuento doble de vista de página cuando se llamaba a s.t desde una función de onclick de vínculo, si la API del visitante no tiene aún los valores necesarios.
* Compatibilidad con HTTP POST.

   >[!IMPORTANT]
   >
   >For an [!DNL Analytics] call to use the POST method instead of the GET method in [!DNL AppMeasurement] (a method of solving [truncated URLs in IE](https://helpx.adobe.com/analytics/kb/shortening-image-request-urls.html)), you must be using the latest [Visitor ID Service](https://marketing.adobe.com/resources/help/en_US/mcvid/?f=mcvid_implement) implementation for Marketing Cloud.

## Versión 1.4 {#section_56ADFF9416B14ABCB3862B00F72B30A1}

Fecha de versión: **21 de agosto de 2014**

* Se ha eliminado el seguimiento de los plugins del explorador (parámetro de consulta `p`) porque los plugins ya no se incluyen en los informes en la versión 15.
* Addition of the **[!UICONTROL AudienceManagement]** Module in the download zip.

Se ha agregado compatibilidad con [eVars](https://marketing.adobe.com/resources/help/en_US/sc/implement/?f=evars_events) (76 - 250) y eventos (101-1000) adicionales.

>[!NOTE]
>
>El código H no admite las evars y los eventos adicionales.

[!DNL JavaScript]

## Versión 1.3.2 {#section_402A4142C4B846DE945FD59DAD9D9298}

Fecha de versión: **19 de junio de 2014**

* Fixed handling of done and waiting flags for Visitor API fields such as the legacy [!DNL Analytics] Visitor ID, that was causing errors.
* Compatibilidad para nuevas funciones en el servicio de ID de visitante 1.3.

## Versión 1.3.1 {#section_5E65422B9C1E4437A2473B119A14163E}

Fecha de versión: **22 de mayo de 2014**

* [!DNL AppMeasurement] para [!DNL JavaScript]`s_gi` la función no estaba buscando correctamente instancias creadas usando el código `s_gi`H. Note that this issue only impacted some dual tagging implementations where [!DNL AppMeasurement] for [!DNL JavaScript] and H code were on the same page with separate instances, and `s_gi` was being used to find instances by report suite.

## Versión 1.3 {#section_56B2C625368E4A5BA1E8770A8C78117D}

Fecha de versión: **17 de abril de 2014**

* Soporte para el [servicio de ID de visitante de Marketing Cloud](https://marketing.adobe.com/resources/help/en_US/mcvid/).

## Versión 1.2.4 {#section_94D9521FDBAB4224994B1671A9BD036B}

Fecha de versión: **13 de marzo de 2014**

* Correcciones de errores para vídeo de Heartbeat.

## Versión 1.2.3 {#section_7ED201192D05463DA9B1990EC281B142}

Fecha de versión: **20 de febrero de 2014**

* Correcciones de errores para vídeo de Heartbeat.

## Versión 1.2.2 {#section_E6CDDDB8EE214ADCBF3047EC42711F13}

Fecha de versión: **6 de febrero de 2014**

* Fixed a compatibility issue with the [!DNL Audience Manager] DIL module. [!DNL Audience Manager]Los clientes de también deben actualizar a la versión 4.8 del módulo DIL.

## Versión 1.2.1 {#section_6DA9384BC2C84698952D51FFB3732019}

Fecha de versión: **15 de noviembre de 2013**

* Se han solucionado eventos de página utilizados para la [medición de vídeo de Heartbeat](https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/hbvideo/).

## Versión 1.2 {#section_BDBE0C3D15F04856ABC6F111DDE6C8DB}

Fecha de versión: **14 de noviembre de 2013**

* Se ha agregado compatibilidad con la [medición de vídeos de Heartbeat](https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/hbvideo/).
* [!DNL VisitorAPI.js] se agregó para admitir [el servicio de ID de visitante](https://marketing.adobe.com/resources/help/en_US/sc/implement/?f=visid_service#).

## Versión 1.1.1 {#section_31F06384039648BB99F4BD630B685794}

* Se ha impedido que se enviara una llamada de seguimiento de vínculos desde los exploradores Opera en vínculos que empiezan con "opera:" ("opera:" se parece a "about:" y "chrome:" en otros exploradores).
* Added `alt=""` to all Image objects to comply with Accessible Video and Communications Act.

## Versión 1.1 {#section_4508FF0A14AE46DF96A08B5C6703E123}

Fecha de versión: **18 de septiembre de 2013**

* Se ha corregido la posibilidad de colocar el código de página y la biblioteca en la etiqueta `head`.
* Added missing module `onLoad` support.

## Versión 1.0.3 {#section_A74A78C30067480AB36C54A06706DF89}

Fecha de versión: **15 de agosto de 2013**

* Se ha añadido la compatibilidad para la implementación a través del administración de etiquetas de Adobe.
* Fixed an issue that prevented hierarchy variables from being set on the [!DNL AppMeasurement] object.

## Versión 1.0.2 {#section_C3BDD9A19EF84467A8FDC283AEAE2DB5}

Fecha de versión: **18 de julio de 2013**

* Ahora el seguimiento automático de vínculos ignora el hash/fragmento. Anteriormente, se seguía automáticamente la siguiente URL porque la `href` entera terminaba en `.pdf`:

   ```js
   <a href="index.htm#anchor.pdf">Test Link</a>
   ```

   Ahora se ignora el hash/fragmento de modo que el vínculo solo se sigue cuando el nombre del archivo termina en una extensión que coincide.

## Versión 1.0.1 {#section_3758B0C47171436ABB4B29F5924BE893}

Fecha de versión: **23 de mayo de 2013**

A new [!DNL JavaScript] [!DNL AppMeasurement] library is now available in Code Manager. Esta biblioteca proporciona la misma funcionalidad básica de [!DNL s_code.js], pero es más rápida y más ligera tanto en sitos móviles como del escritorio.

* De 3 a 7 veces más rápido que el código H.25
* Solo 21 k sin comprimir y 8 k comprimidos con gzip (el código H.25 tiene 33 k sin comprimir y 13 k comprimidos con gzip).
* Compatibilidad nativa para obtener parámetros de consulta, leer y escribir cookies y realizar un seguimiento de vínculos avanzado.
* Pequeño y lo suficientemente rápido para su uso en sitios móviles, así como lo bastante sólido para su uso en el escritorio web completo, lo que le permitirá aprovechar una sola biblioteca en todos los entornos web.

Consulte [AppMeasurement para Javascript](https://marketing.adobe.com/resources/help/en_US/sc/implement/index.html?f=appmeasure_mjs) en la Guía de implementación de [!DNL Analytics]

>[!NOTE]
>
>Algunos complementos no son compatibles con esta nueva versión. Consulte la [Compatibilidad de complementos](https://marketing.adobe.com/resources/help/en_US/sc/implement/index.html?f=plugins_support) para obtener más información.

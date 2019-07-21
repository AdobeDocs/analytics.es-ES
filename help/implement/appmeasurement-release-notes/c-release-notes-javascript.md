---
description: Recopilación de notas de versiones sobre el código H de JavaScript heredado.
seo-description: Recopilación de notas de versiones sobre el código H de JavaScript heredado.
seo-title: Código H de JavaScript - Heredado
solution: Analytics
subtopic: Notas de la versión
title: Código H de JavaScript - Heredado
topic: Desarrollador e implementación
uuid: 4586 b 250-0 f 1 b -45 b 8-829 c -18 dc 1201956 f f
translation-type: tm+mt
source-git-commit: 01a6fc7e44dc71b868bd38a4f6a5a4089eae6349

---


# Código H de JavaScript - Heredado{#javascript-h-code-legacy}

Recopilación de notas de versiones sobre el código H de JavaScript heredado.

>[!NOTE]
>
>To find the current library version, use [DigitalPulse Debugger](https://marketing.adobe.com/resources/help/en_US/sc/implement/index.html?f=debugger_about).

<!-- 

https://wiki.corp.adobe.com/pages/viewpage.action?spaceKey=omtrcache&title=AppMeasurement+Change+Log

 -->

## H.27.5 - Update {#section_DB9535C7EC4A4DDE9BA56B6C02BE8327}

Fecha de la versión: **16 de junio de 2016**

Inclusión de la API de visitante 1.5.7.

## H.25.5 - Update {#section_B10151D7718F4568AE523BE1553FCCB7}

Fecha de versión: **19 de mayo de 2016**

Inclusión de la API de visitante 1.5.5.

## H.27.5 - Update {#section_AD73ECD5CDAB4E158B509BA7B4B8CC1F}

Fecha de versión: **5 de noviembre de 2015**

* Inclusión de la API de visitante 1.5.3.

## H.27.5 - Update {#section_8A94D8A74A39486AAE248A22D661A261}

Fecha de versión: **17 de septiembre de 2015**

* Inclusión de la API de visitante 1.5.2.

## H.27.5 - Update {#section_62D1787F90FB4730B5F0C79EC1EF84B1}

Fecha de versión: **20 de agosto de 2015**

* Inclusión de la API de visitante 1.5.1.

## H.27.5 - Update {#section_F58AF8B7FAE9470ABCBF2AAD9E7AF881}

Fecha de versión: **18 de junio de 2015**

* Inclusión de la API de visitante 1.5.

## H.27.5 - Update {#section_B3E310AFF909480BAD59A7F87D298348}

Fecha de versión: **21 de mayo de 2015**

* Inclusión de la API de visitante 1.4

## H.27.5 - Update {#section_E7006FC903064376A85D3EC2AC1D2544}

Fecha de versión: **16 de abril de 2015**

* Added Integrate module to s_code.js in legacy [!DNL AppMeasurement] for [!DNL JavaScript] H.X ZIP file. (AN-101001)

## H.27.5 {#section_22DCF43169614B28BC17F46426C5D5B6}

Fecha de versión: **19 de febrero de 2015**

* Inclusión de la API de visitante 1.3.5.
* Se ha cambiado la opción a no hacer seguimiento automático del referente tras la primera llamada de seguimiento, de modo que las llamadas segunda, tercera, etc. (por lo general seguimiento de vínculos) no contarán al referente doble si *`s.referrer`* se ha establecido manualmente antes de la primera llamada de seguimiento. (AN-92647)

## H.27.4 - Update {#section_ED38D59E83B4417180877F7C10BE4582}

Fecha de versión: **15 de enero de 2015**

* Se ha actualizado el zip de distribución para incluir la API de visitante 1.3.4.

Fecha de versión: **18 de septiembre de 2014**

* Se agregó una variable `tagContainerMarker` que permite la implementación para especificar hasta 4 caracteres que se anexan a la cadena de versión junto con un delimitador de guion adicional. Se usa mediante la administración dinámica de etiquetas.

```js
  //  
<keyword>
  JavaScript 
</keyword> 
  s.tagContainerMarker = "D1.0"; 
    
  // Data Collection request 
  //.../b/ss/myrsid/1/JS-1.4.1-D1.0/s43317392037311?...
```

## H.27.3 {#section_B38C61EE3BEA49CAA7A664395C85E4CF}

Fecha de versión: **21 de agosto de 2014**

* Cambios internos para admitir las próximas funciones.

## H.27.2 {#section_402A4142C4B846DE945FD59DAD9D9298}

Fecha de versión: **19 de junio de 2014**

* Fixed handling of done and waiting flags for Visitor API fields such as the legacy [!DNL Analytics] Visitor ID, that was causing errors.
* Compatibilidad para nuevas funciones en el servicio de ID de visitante 1.3.

## H.27.1 {#section_CC2556C734EE4BAAB71D6A93095DB38F}

Fecha de versión: **11 de junio de 2014**

* Fixed an issue in the [!DNL Analytics] for [!DNL Target] integration that caused some hits to incorrectly be merged.

## H.27 {#section_023B6267C0DB424F99A23EBB732B8C69}

Fecha de versión: **22 de mayo de 2014**

* Soporte para el [servicio de ID de visitante de Marketing Cloud](https://marketing.adobe.com/resources/help/en_US/mcvid/).
* Soporte para la [integración de Analytics para Target](https://marketing.adobe.com/resources/help/en_US/target/a4t/).

## H.26.2 {#section_DE82C8BC7645400785E5B136565616F1}

Fecha de versión: **17 de octubre de 2013**

* Added `alt=""` to all Image objects to comply with Accessible Video and Communications Act.

## H.26.1 {#section_C3BDD9A19EF84467A8FDC283AEAE2DB5}

Fecha de versión: **18 de julio de 2013**

* Ahora el seguimiento automático de vínculos ignora el hash/fragmento. Anteriormente, se seguía automáticamente la siguiente URL porque la `href` entera terminaba en `.pdf`:

```js
  <a href="index.htm#anchor.pdf">Test Link</a>
```

Ahora se ignora el hash/fragmento de modo que el vínculo solo se sigue cuando el nombre del archivo termina en una extensión que coincide.

## H.26 {#section_E25814ACC21E41718EE1741A85AE567B}

Fecha de versión: **29 de abril de 2013**

* La opción `useForcedLinkTracking` que se describe en la sección sobre [seguimiento manual de vínculos con el código de vínculo personalizado](https://marketing.adobe.com/resources/help/en_US/sc/implement/index.html?f=c_manuallinktrackcustomlink) ahora se aplica a Firefox 20+ (anteriormente solo se aplicaba a usuarios de exploradores WebKit).

* La generación de ID de objeto de imagen ahora es única entre instancias. Esto evita las colisiones cuando hay más de una instancia en la misma página.

## H.25.5 {#section_A528D1D5E84146F9A56680E4427B2750}

Fecha de versión: **19 de abril de 2013**

* Fixed an issue in forced link tr [!DNL Windows]acking that caused a [!DNL JavaScript] error on some [!DNL Android] 2.2 Devices.

* En el seguimiento automático de vídeo en Media Player, se ha solucionado un problema que hacía que el tiempo reproducido no se rastreara correctamente al cancelar.

## H.25.4 {#section_009AF895C8DD47CABC9A3776D27E8300}

Fecha de versión: **febrero de 2013**

* Changed automatic exit link tracking to always ignore links with `HREF` attributes that start with `#`, `about:`, or `javascript:`.

* Alcance refinado de los eventos de clic afectados por `useForcedLinkTracking`. El seguimiento de vínculo forzado automático solo se aplica a:

   * `<A>` y `<AREA>` etiquetas

   * La etiqueta debe tener un atributo `HREF`
   * The `HREF` can't start with `#`, `about:`, or `javascript:`

   * The `TARGET` attribute must not be set, or the `TARGET` needs to refer to the current window ( `_self`, `_top`, or the value of `window.name`)

## H.25.3 {#section_FA6A6F9F5D64455DA5A54C007081341A}

Fecha de versión: **enero de 2013**

* Se ha agregado compatibilidad para enviar direcciones URL superiores a 255 bytes para admitir la expansión del campo de URL de la página en los servidores de recopilación de datos de Adobe. Page URLs longer than 255 bytes are split, with the first 255 bytes appearing in the `g=` parameter, with the remaining bytes appearing later in the query sting in the `-g=` query parameter. Esto ayuda a impedir que las direcciones URL largas prevalgan sobre otros datos en caso de truncamiento del navegador, pero sigue permitiendo capturar las direcciones URL largas. 

* Corrección en el control de descodificación de dirección URL para cadenas codificadas con un uso mixto de `escape` y `encodeURIComponent`.

* Se ha solucionado un problema en los navegadores WebKit en los que el seguimiento de enlace fallaba si el primer servidor llama al tiempo de espera de la página.
* Se ha agregado un nuevo método de identificación de visitantes alternativos. Consulte [Identificación de visitantes únicos](https://marketing.adobe.com/resources/help/en_US/sc/implement/index.html?f=c_identifying_unique_visitors).
* Added a new `abort` flag that can be set inside `doPlugins`. Configurar este indicador a verdadero impide que la biblioteca [!DNL AppMeasurement] siga con la llamada de seguimiento. El indicador de anulación se restablece con cada llamada de seguimiento, así que si también se tiene que cancelar una llamada de seguimiento posterior, de nuevo se tendrá que configurar el indicador dentro de `doPlugins`.

```js
  s.doPlugins = function(s) { 
       s.campaign = s.getQueryParam("cid"); 
       if ((!s.campaign) && (!s.events)) { 
            s.abort = true; 
       } 
  };
```

Esto permite centralizar la lógica utilizada para identificar la actividad que no se quiere seguir, por ejemplo algunos vínculos personalizados o vínculos externos para mostrar anuncios.

## H25.2 {#section_647D7638D0C04019B8C9986CD124914E}

Fecha de versión: **octubre de 2012**

* Added support for reporting an additional version number in the [!DNL JavaScript] version report. Anteriormente, esta versión estaba limitada a 2 caracteres (por ejemplo, 1.8). Se agregó compatibilidad para un número de versión de 3 caracteres (por ejemplo, 1.8.5).
* Fixed an issue with [!DNL Tag Manager] that prevented repeated values in Dependant Code blocks from being sent.

## H.25.1 {#section_680CE31CFA9945978F42612B684DB831}

Fecha de versión: **septiembre de 2012**

* Codificación de la dirección URL forzada para los siguientes caracteres:

```
  ~ 
  ! 
  * 
  ( 
  ) 
  '
```

This resolves issues with un-escaped characters being stored in the [!DNL ClickMap] `s_sq` cookie.

* Se ha solucionado un problema donde puede que el evento completo del vídeo no se envíe al utilizar un método `media.monitor` personalizado que rastrea el evento de cierre multimedia:

```
  If(media.event==”CLOSE”) { 
  … 
  } 
  
```

## H.25 {#section_BE76FEDFE03B44658808B0BDF779DE97}

Fecha de versión: **julio de 2012**

Se ha realizado una actualización para garantizar que el seguimiento de vínculos se complete de forma satisfactoria en exploradores WebKit (Safari y Chrome). Tras esta actualización, se realizará un seguimiento correcto de los vínculos de descarga y salida cuyo seguimiento es automático (determinado por `s.trackDownloadLinks` y `s.trackExternalLinks`). If you are tracking custom links using manual [!DNL JavaScript] calls, you need to modify how these calls are made.

Por ejemplo, el seguimiento de los vínculos de salida y de descarga se realiza a menudo utilizando código similar al siguiente:

```js
  <a href="http://anothersite.com" onclick="s.tl(this,'o','link name',null)">
```

Firefox e Internet Explorer ejecutan la llamada de seguimiento de vínculos y abren la nueva página. Sin embargo, los exploradores WebKit podrían cancelar la ejecución de la llamada de seguimiento de vínculos al abrirse la nueva página. Esto evita a menudo que las llamadas de seguimiento de vínculos se completen al utilizar exploradores WebKit.

Para solucionar este comportamiento, H.25 incluye un método de sobrecarga de seguimiento de vínculos (`s.tl`) que obliga los exploradores a esperar a que se complete la llamada de seguimiento de vínculos. Este nuevo método ejecuta la llamada de seguimiento de vínculos y, a continuación, se ocupa del de la navegación en lugar de utilizar la acción predeterminada del explorador. Este método de sobrecarga requiere un parámetro adicional, llamado `doneAction`, para especificar la acción que debe realizarse cuando se completa la llamada de seguimiento de vínculos.

Para utilizar este nuevo método, actualice las llamadas a `s.tl` con un parámetro adicional `doneAction`, similar al siguiente:

```js
  <a href="http://anothersite.com" onclick="s.tl(this,'o','link name',null 
  <codeph outputclass="syntax"> ,'navigate');return false"> 
  </codeph outputclass="syntax">
```

Al hacer pasar 'navegar' como `doneAction` se refleja el comportamiento predeterminado del explorador y abre la dirección URL especificada por el atributo `href` cuando se completa la llamada de seguimiento de vínculos.

La siguiente tabla resume las variables de configuración y las actualizaciones hechas a H.25 para admitir esta funcionalidad.

<table id="table_E67157D710874146B26EFB7D84762542"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Variable </p> </th> 
   <th colname="col2" class="entry"> <p>Descripción </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>useForcedLinkTracking </p> </td> 
   <td colname="col2"> <p>Esta marca se usa para deshabilitar el seguimiento de vínculos forzado para exploradores WebKit. El seguimiento de vínculos forzado se habilita de forma predeterminada para exploradores WebKit, mientras que el resto de exploradores lo ignoran. </p> <p> <b>Valor predeterminado</b> </p> <p> <code> true </code> </p> <p> <b>Ejemplo</b> </p> 
    <code class="syntax javascript">s. useforcedlinktracking &amp; amp; nbsp; = &amp; amp; nbsp; false </code>
  </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>forcedLinkTrackingTimeout </p> </td> 
   <td colname="col2"> <p>El número máximo de milisegundos que hay que esperar para que finalice el seguimiento antes de ejecutar el parámetro <code>doneAction</code> que se pasó a <code>s.tl</code>. Este valor especifica el tiempo de espera máximo. Si la llamada de seguimiento de vínculos se completa antes de este tiempo de espera, el parámetro <code>doneAction</code> se ejecuta inmediatamente. Si nota que las llamadas de seguimiento de vínculos no se completan, es posible que tenga que aumentar este tiempo de espera. </p> <p> <b>Valor predeterminado</b> </p> <p>250 </p> <p> <b>Ejemplo</b> </p> 
    <code class="syntax javascript">s. forcedlinktrackingtimeout &amp; amp; nbsp; = &amp; amp; nbsp; 500 </code>
  </td> 
  </tr> 
  <tr> 
   <td colname="col1"> trackLink (<code>s.tl </code>) </td> 
   <td colname="col2"> <p>Rastrea los vínculos de salida, descarga y los vínculos personalizados. Proporciona un parámetro opcional para especificar una acción de navegación que se ejecutará después de que se complete la llamada de seguimiento de vínculos en exploradores WebKit. </p> <p> <b>Sintaxis</b> </p> 
    <code class="syntax javascript">s. tl (linkobject, linktype, linkname, variableoverrides, doneaction) </code>
  <p> <b>doneAction</b>: (opcional) especifica la acción que se efectuará cuando la llamada de seguimiento de vínculos se haya enviado o cuando se haya acabado su tiempo de espera (conforme al valor especificado por <code>s.forcedLinkTrackingTimeout </code>). <code>doneAction</code> puede ser la cadena "navegar", lo que hace que el método establezca <code>document.location</code> en el atributo <code>href</code> de <code>linkObject </code>. <code>doneAction</code> también puede ser una función que permita una mayor personalización. </p> <p>If providing a value for <code> onclick </code> in an anchor <code> false </code> event, you must return <code> s.tl </code> after the <code> href </code> call to prevent the default browser navigation. </p> <p> To mirror the default behavior and follow the URL specified by the <code> doneAction </code> attribute, provide a string of 'navigate' as the <code> doneAction </code>. </p> <p>Optionally, you can provide your own function to handle the navigation event by passing this function as the <code>$1</code>. </p> <p> <b>Ejemplos</b> </p> 
    <code class="syntax javascript">&lt; a &amp; amp; nbsp; href = "…" &amp; amp; nbsp; onclick = "s. tl (this,' o ',' mylink ', null,' navigate '); return &amp; amp; nbsp; false " &gt; Click &amp; amp; nbsp; Aquí &lt;/a &gt; </code><code class="syntax javascript">
 
 
 &lt; a &amp; amp; nbsp; href = " #" &amp; amp; nbsp; onclick = "s. tl (this,' o ',' mylink ', null, function () {if (confirm (' Continue? '))document.location=...});return&amp;nbsp;false"&gt;Click&amp;nbsp;Here&lt;/a&gt; 
    </code> </td> 
  </tr> 
 </tbody> 
</table>

## H.24.4 {#section_1989179F10A34E88968CA5A5290CF17C}

Fecha de versión: **abril de 2012**

Se recomienda esta actualización a todos los clientes.

* Se ha realizado una mejora para detectar cuando una página se preprocesa usando Google Chrome Prerender ([https://developers.google.com/chrome/whitepapers/prerender](https://developers.google.com/chrome/whitepapers/prerender)). Since Prerender loads and executes [!DNL JavaScript] and other code, this could result in page views being sent before a user clicks to visit your site. [!DNL JavaScript] La biblioteca ahora espera hasta que el usuario visite el sitio antes de enviar llamadas al servidor para estas páginas preprocesadas.
* Se ha agregado la variable `timestamp`[!DNL JavaScript] a la biblioteca de para clientes que quieren personalizar la marca de fecha y hora de igual forma que se hace para otras bibliotecas de [!DNL AppMeasurement]

```js
  s.timestamp=Math.round((new Date()).getTime()/1000); 
  s.timestamp="2012-04-20T12:49:31-0700";
```

## H.24.3 {#section_F3D471B201F54C089320D3CE6D441DC0}

Fecha de versión: **febrero de 2012**

* Se ha solucionado un problema que causaba que los datos extra se incluyesen en la solicitud de imagen para los clientes que usan la anulación de Javascript `Object.prototype`. Todo el uso de `Object.prototype` se omite ahora al tratar las variables de datos contextuales.
* Se ha solucionado un problema que causaba que el parámetro de la consulta `pe` se pasase dos veces con el mismo valor en algunas circunstancias.
* Solucionar para que el seguimiento [!DNL ClickMap][!DNL JavaScript] en ignore los clics en la etiqueta de cuerpo, incluso cuando la etiqueta tiene un controlador de eventos `onClick`.
* Agregada una marca de hora a las variables que se usan con las llamadas de seguimiento light ( `trackLight`).

## H.24.2 {#section_91CF07C2BC9B4C8BA0235DFDFB95A4D9}

Fecha de versión: **enero de 2012**

* Seguimiento de vídeo actualizado con un nuevo método para realizar el seguimiento de visualizaciones completas de vídeo.
* Fixed an issue that caused an "Attribute only valid on v:image" [!DNL JavaScript] error for `OnClick` events on VML elements in IE.
* Se ha solucionado un error en el que las variables de datos de contexto no se incluían en las llamadas de servidor de vínculo a pesar de contener referencia en `linkTrackVars`. Las variables de datos de contexto se utilizan con reglas de procesamiento.

## H.24.1 {#section_967356D219FE4E9CAA110D03EDF4C8B1}

Fecha de versión: **noviembre de 2011**

* Se ha actualizado el seguimiento de vídeo para combinar las visitas de segmentos y los hitos que ocurren al mismo tiempo.

## H.24 {#section_78FF9B245643406BB7E9967E784A90AE}

Fecha de versión: **noviembre de 2011**

* Internal updates to support [!DNL Adobe Tag Manager].

## H.23.9 {#section_3834625A639A47428683E08A472359C7}

Fecha de versión: **noviembre de 2011**

* Internal updates to support [!DNL Adobe Tag Manager].

## H.23.8 {#section_FF3CEEAB6C6744D6B5EE314A0B5841CA}

Fecha de versión: **octubre de 2011**

* Fixed an issue that caused the `linkTrackVars=none` and `linkTrackEvents=none` settings to not apply when using automatic exit link tracking. Estas configuraciones no se aplican para los vínculos de salida automática, de forma que las props, los eVars y los eventos no se envían con la solicitud de imagen del vínculo de salida.

## H.23.7 {#section_D9D0CF343EBF49D9844C6BDA0C3C7A2E}

Fecha de versión: **septiembre de 2011**

* Se han eliminado los atributos del borde de las etiquetas de imagen en dispositivos móviles para cumplir las normas Wireless Markup Language (WML). Esto soluciona problemas de presentación en algunos dispositivos móviles.

## H.23.6 {#section_461A208BE1B64EDDA87A8D7C4FD5456C}

Fecha de versión: **agosto de 2011**

Se ha arreglado la precisión de las mediciones porcentuales en el seguimiento de vídeo.

## H.23.5 {#section_FCE48EE33C9A42F08386FA30037BF4E0}

Fecha de versión: **julio de 2011**

* Se ha agregado compatibilidad con [!DNL Adobe Tag Manager].

## H.23.4 {#section_E9152B4437C24107A68D264F70361930}

Fecha de versión: **junio de 2011**

* Fixed an issue that caused [!DNL JavaScript] errors when accessing certain properties of Vector Markup Language (VML) shape elements.
* Las cadenas de referentes que tengan más de 255 caracteres ahora se truncan acortando la ruta en vez de la cadena de consultas. Esto resuelve los problemas en los que se truncaban y no se recopilaban parámetros de cadenas.

## H.23.3 {#section_EAB0602E07EE4A5CA6521351F461D22D}

Fecha de versión: **mayo de 2011**

* Se ha solucionado un problema que impedía que se enviase la variable de seguimiento de vídeo (pev3).
* Se ha solucionado un problema que impedía que la llamada `s_gi` habilitase código para ser compatible con el modo G y H. Cuando se pasa un 1 como segundo parámetro para esta llamada, el código se configura ahora para ser compatible con ambas versiones.

## H.23.2 {#section_274143E83A8D42F1AD40CAE4326E99CE}

Fecha de versión: **abril de 2011**

* Compatibilidad para contextData que transmite reglas de procesamiento de parte del servidor (solo versión 15).
* Compatibilidad para llamadas al servidor livianas (solo versión 15).
* Compatibilidad para asignar un valor distinto de 1 a un evento de contador en la lista de eventos.
* Compatibilidad para un nuevo método de seguimiento de vídeo usando eVars y eventos de conversión (actualmente en fase beta).
* Se ha eliminado la compatibilidad para establecer Media.trackWhilePlaying en falso. Siempre será verdadero.
* Se ha agregado el indicador debugTracking para habilitar el registro de las solicitudes enviadas a la consola Firebug al igual que en el resto de plataformas.
* Asegúrese de que "+" siempre tenga codificación URL independientemente del explorador.

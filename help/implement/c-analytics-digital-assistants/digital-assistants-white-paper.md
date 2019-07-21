---
description: 'null'
seo-description: 'null'
seo-title: Implementar Analytics para ayudante digital
title: Implementar Analytics para ayudante digital
uuid: c 61 e 6 a 1 a-ec 08-4936-9053-5 f 57223 f 57 ff
translation-type: tm+mt
source-git-commit: 4e7a8bab956503093633deff0a64e8c7af2d5497

---


# Implementar Analytics para ayudante digital

<!-- 

<p>https://wiki.corp.adobe.com/display/mobileanalytics/Analytics+for+Digital+Assistants+Whitepaper </p> 
<p>https://marketing.adobe.com/resources/help/en_US/sc/implement/digital-assistants-white-paper.html </p> 
<p>Ticket: https://jira.corp.adobe.com/browse/AN-157750 </p>

 -->

Con los recientes avances en la informática de la nube, el aprendizaje automático y el procesamiento del lenguaje natural, los asistentes digitales comienzan a salir de la edad oscura y cada vez más forman parte de la vida cotidiana. Los consumidores empiezan a hablar con los dispositivos y esperan que estos escuchen, entiendan y respondan de forma natural y humana a frases como “Alexa, enciende las luces del salón” o “Vale, Google, ¿qué tiempo hace fuera?”.

El establecimiento cada vez mayor de estas plataformas permite a las marcas presentar sus servicios a los consumidores de un modo realista y natural. Por ejemplo, un consumidor puede preguntar cosas como:

* “Alexa, pregunta al coche cuándo hay que cambiarle el aceite”.
* “Cortana, ¿qué saldo tengo en la cuenta corriente?”.
* “Siri, envía a John 20 dólares desde mi aplicación de banca por la cena de anoche”.

Este documento técnico describe de forma general el mejor modo de utilizar Adobe Analytics Cloud para medir y optimizar este tipo de experiencias.

## Descripción general de la arquitectura de la experiencia digital {#concept_26AC08D291724223A943C80B1C6F2333}

![](assets/Digital-Assitants.png)

La mayoría de los asistentes digitales de hoy en día siguen una arquitectura de alto nivel similar:

1. **Dispositivo:** hay un dispositivo (como un Amazon Echo o un teléfono) con un micrófono que permite al usuario hacer una pregunta.
1. **Asistente digital:** el dispositivo interactúa con el servicio que alimenta el asistente digital. En este servicio es donde sucede en su mayoría la magia. Es donde el habla se convierte en intenciones comprensibles para la máquina y donde se analizan los detalles de la solicitud. Una vez entendida la intención del usuario, el asistente digital la transmite junto con los detalles de la solicitud a la aplicación que se encarga de tramitar dicha solicitud.
1. **“Aplicación”:** puede tratarse de una aplicación que hay en el teléfono o de una aplicación de voz. La aplicación es la encargada de responder a la solicitud. Responde al asistente digital, que a su vez responde al usuario.

## Dónde se implementa Analytics {#concept_F53A0566589042658DEA5B86B22C10CB}

Uno de los mejores lugares para implementar Analytics es en la aplicación. La aplicación recibe del asistente digital la [intención](../../implement/c-analytics-digital-assistants/digital-assistants-white-paper.md#section_BB339BDB5C3D40C6B5C426B0E092B48A) y los detalles de esta, y decide cómo responder.

Hay dos momentos durante el ciclo vital de una solicitud en que puede ser útil realizar una llamada a Analytics Cloud.

1. Cuando se envía la solicitud a la “aplicación”. Si necesita contexto adicional acerca del usuario antes de responder a la solicitud, debería aprovechar la capacidad de Audience Manager para obtener los segmentos a los que pertenece.
1. Tras devolverse la respuesta desde la aplicación. Si simplemente está interesado en registrar lo sucedido con el cliente para una futura optimización, envíe una solicitud a Adobe Analytics una vez devuelta la respuesta. De este modo dispondrá del contexto completo y sabrá cuál era la solicitud y cómo respondió el sistema.

## Nuevas instalaciones {#section_FD63267479DB47C2A081244A3E65A0CC}

En el caso de algunos asistentes digitales, recibirá una notificación cuando alguien instale la capacidad. Es así especialmente cuando media una autenticación. En ese momento, debería enviar a Adobe un evento *`Install`* estableciendo los datos de contexto en `a.InstallEvent=1`. Tenga en cuenta que este procedimiento no está disponible en todas las plataformas, pero, cuando está presente, es útil para comprobar la retención. El siguiente ejemplo de código envía *`Install`*, *`Install Date`* y *`AppID`*.

**Ejemplo de código**

```
GET 
/b/ss/[rsid]/0?vid=[UserID]&c.a.InstallEvent=1&amp;c.a.InstallDate=2017-04-24&c.a.AppID=Spoofify1.0&c .OSType=Alexa&pageName=install 
HTTP/1.1 
Host:  
<xref href="https: sc.omtrdc.net="" " format="http"  scope="external">
  sc.omtrdc.net 
 Cache-Control: no-cache 
</xref href="https:>
```

## Múltiples asistentes o aplicaciones {#section_81740741752E4142BE42DA4C9DDEEDF5}

Es probable que desarrolle aplicaciones para varias plataformas. Es recomendable incluir un ID de aplicación con cada solicitud. Puede establecerlo en los datos de contexto `a.AppID`. Follow the format of `[AppName] [BundleVersion]`, for example, BigMac for Alexa 1.2

**Ejemplo de código**

```
GET /b/ss/[rsid]/0?vid=[UserID]&c.a.AppID=Spoofify1.0&c.a.Launches=1&c.Product=AmazonEcho&c.OSType=Alexa&pageName=install  HTTP/1.1 
Host: [prefix].sc.omtrdc.net 
Cache-Control: no-cache
```

```
 GET /b/ss/[rsid]/0?vid=[UserID]&c.a.AppID=Spoofify2.0&c.a.Launches=1&c.Product=GoogleHome&c.OSType=Android&pageName=install  HTTP/1.1 
Host: sc.omtrdc.net 
Cache-Control: no-cache
```

## Identificación de usuarios/visitantes {#section_7CE70FEB43C44B90954702CA30F87D58}

The Analytics Cloud uses the [Identity Service](https://marketing.adobe.com/resources/help/en_US/mcvid/) (ECID) service to tie interactions across time to the same person. Most of the digital assistants will return a *`userID`* that you can use to keep the activity for different users separate in the ECID service. En la mayoría de los casos, esto es lo que se debería pasar como servicio ECID. Algunas plataformas devuelven un *`userID`* que supera los 100 caracteres que Analytics tiene como límite. If that is the case, Adobe recommends that you hash the *`userId`* to a fixed-length value using a standard hashing algorithm, such as MD5 or Sha1.

Aunque para esto puede utilizar el servicio ECID, hacerlo así solo tiene sentido si quiere asignar los ECID entre dispositivos diferentes (p. ej., de web a asistente digital). Si la suya es una aplicación móvil (p. ej., un vínculo profundo), debería utilizar el SDK tal como está y enviar la información. El *`userID`* puede adjuntarse al servicio ECID con el método setCustomerID, que permite un mejor cosido de los dispositivos. However, if your app is a service, use the *`userID`* provided by the service as the ECID, as well as setting it in the setCustomerID. De este modo puede ver cómo utiliza la gente el asistente digital a lo largo del tiempo.

**Ejemplo de código**

```
GET /b/ss/[rsid]/0?vid=[UserID]&pageName=[intent]  HTTP/1.1 
Host: sc.omtrdc.net 
Cache-Control: no-cache
```

## Sesiones {#section_BA4F996F976043B8993F2F7D24FE27FB}

Como los asistentes digitales son conversacionales, a menudo incluyen el concepto de sesión. Por ejemplo:

**Consumidor:** “Vale, Google, llámame un taxi”.

**Google:** “Claro, ¿para cuándo lo quieres?”.

**Consumidor:** “Las 8:30 de la tarde”.

**Google:** “Muy bien, el conductor llegará a las 8:30 de la tarde”.

Estas sesiones son importantes para mantener un contexto. Ayudan a recabar más detalles y hacen más naturales a los asistentes digitales.

Cuando se implementa Analytics en una conversación, hay dos cosas que deben hacerse al comienzo de una nueva sesión:

1. **Póngase en contacto con Audience Manager:** obtenga los segmentos relevantes a los que pertenece un usuario para que pueda personalizar la respuesta. (Por ejemplo, esa persona es elegible en este momento para del descuento multicanal).
1. **Envíe un evento de nueva sesión o de inicio:** cuando envíe la primera respuesta a Analytics, incluya un evento de inicio. Normalmente puede hacerse estableciendo los datos de contexto `a.LaunchEvent=1`.

**Ejemplo de código para[!DNL Launch, by Adobe]**

```
GET /b/ss/[rsid]/0?vid=[UserID]&c.a.LaunchEvent=1&c.Intent=[intent]&pageName=[intent]  HTTP/1.1 
Host: sc.omtrdc.net 
Cache-Control: no-cache
```

## Intenciones {#section_BB339BDB5C3D40C6B5C426B0E092B48A}

Todos los asistentes digitales cuentan con algoritmos que detectan las intenciones para luego transmitirlas a la “Aplicación” de modo que esta sepa lo que debe hacer. Estas intenciones son una representación sucinta de la solicitud.

Por ejemplo, si un usuario dice: “Siri, envía a John 20 dólares desde mi aplicación de banca por la cena de anoche”, la intención podría ser algo como *`sendMoney`*.

Al enviar cada una de estas solicitudes como una eVar, podrá realizar informes de control de rutas de todas las intenciones de una aplicación conversacional. También conviene asegurarse de que la “Aplicación” sea capaz de gestionar solicitudes sin intenciones. Recomendamos pasar un valor *`No Intent Specified`* en vez de dejar el valor en blanco.

**Ejemplo de código**

```
GET /b/ss/[rsid]/0?vid=[UserID]&c.a.AppID=Penmo1.0&c.a.LaunchEvent=1&c.Intent=SendPayment&pageName=[intent]  HTTP/1.1 
Host: sc.omtrdc.net 
Cache-Control: no-cache
```

o

```
GET /b/ss/[rsid]/0?vid=[UserID]&c.a.AppID=Penmo1.0&c.a.LaunchEvent=1&c.Intent=No_Intent_Specified&pageName=[intent]  HTTP/1.1 
Host: sc.omtrdc.net 
Cache-Control: no-cache
```

## Parámetros/Espacios/Entidades {#section_041CD1730F9E4096BE75DFF2CC810852}

Además de la intención, los asistentes digitales cuentan a menudo con un conjunto de pares de clave-valor que proporcionan los detalles de la intención. Reciben el nombre de espacios, entidades o parámetros. Por ejemplo:

“Siri, envía a John 20 dólares desde mi aplicación de banca por la cena de anoche” tendría los siguientes parámetros:

* Quién = John
* Cantidad = 20
* Por qué = Cena

Normalmente, una aplicación cuenta con un número finito de estos parámetros. Para realizar un seguimiento de los mismos en Analytics, envíelos como datos de contexto y, a continuación, asigne cada uno de los parámetros a una eVar.

**Ejemplo de código**

```
GET /b/ss/[rsid]/0?vid=[UserID]&c.a.AppID=Penmo1.0=1&c.a.LaunchEvent=1&c.Intent=SendPayment&c.Amount=20.00&c.Reason=Dinner&c.ReceivingPerson=John&c.Intent=SendPayment&pageName=[intent]  HTTP/1.1 
Host: sc.omtrdc.net 
Cache-Control: no-cache
```

## Sesión {#section_17D69D6B298E46E88E175F62F1ACD831}

Aunque no todas las aplicaciones generan ingresos, es importante que piense en cómo se determina su éxito e incluir algunas mediciones al respecto. Además del comportamiento de los usuarios, Adobe Analytics puede medir ingresos, impresiones publicitarias y otras formas de éxito.

## Estados de error {#section_E8EFF8D610B24DC899C34E50B058864D}

En ocasiones, el asistente digital proporciona entradas que la aplicación no sabe cómo manejar. Por ejemplo.

“Siri, envía a John 20 bolsas de carbón desde mi aplicación de banca por la cena de anoche”.

Cuando sucede esto, la aplicación debería pedir una clarificación. Además, cuando la aplicación responda a una solicitud así, debería enviarse a Analytics un evento que indique que la aplicación está en estado de error, además de una eVar que especifique el tipo de error producido.

Asegúrese de que incluye los errores que se producen cuando las entradas no son correctas y aquellos en los que la “Aplicación” ha tenido un problema.

**Ejemplo de código**

```
GET /b/ss/[rsid]/0/?vid=[UserID]&c.a.AppID=Penmo1.0&c.Error=1&c.ErrorName=InvalidCurrency&pageName=[intent] HTTP/1.1 
Host: sc.omtrdc.net 
Cache-Control: no-cache
```

## Capacidades de los dispositivos {#section_6770D82A3B0E4AD5A2172A7E67B0DF20}

Aunque la mayoría de las plataformas no exponen el dispositivo al que ha hablado el usuario, sí muestran las capacidades del dispositivo en cuanto a las interfaces disponibles (p. ej., audio, pantalla, vídeo, etc.). Se trata de información útil porque define los tipos de contenido que se pueden utilizar cuando se interactúa con los usuarios. Cuando se miden las interfaces, es conveniente concatenarlas (en orden alfabético).

Ejemplo: `:Audio:Camera:Screen:Video:`

Fíjese en los dos puntos de inicio y de final. These help when creating segments (for example, give me all interactions with `:Audio:` capabilities).

Capacidades de Amazon: [https://developer.amazon.com/public/solutions/alexa/alexa-skills-kit/docs/alexa-skills-kit-interface-reference](https://developer.amazon.com/public/solutions/alexa/alexa-skills-kit/docs/alexa-skills-kit-interface-reference)

Capacidades de Google: [https://developers.google.com/actions/assistant/surface-capabilities](https://developers.google.com/actions/assistant/surface-capabilities)

## Informes de Analytics para asistentes digitales {#concept_265BC8E99C5545D0A9B9412C11EE58CC}

Una vez que la aplicación para asistentes digitales está implementada, puede aprovechar con ella toda la potencia de Adobe Analytics. Abajo se incluyen unos pocos ejemplos de las cosas que es posible hacer con Analytics.

## Supervisión de intenciones {#section_6632D9F2EF9045A7A1A4263D3561C78F}

La mayoría de las aplicaciones incluye varias intenciones y permite hacer distintas cosas. You could easily use [!UICONTROL Analysis Workspace] to keep track of the top intents by instances and by users

<!-- 

<p>--- Image of Intents --- </p>

 -->

De este modo puede ver qué funciones se utilizan más a menudo y determinar el grado de adopción de las nuevas características.

## Solicitudes con errores {#section_CF1A79003E784F88A03F4EEF6CDC7A7C}

Es posible supervisar los errores y comprobar si existen lugares comunes donde los usuarios encuentran problemas.

<!-- 

<p>--- Image of Errors --- </p>

 -->

## Flujo entre eventos {#section_08FA8EBD384D41ED8CA52EFE438C8CD2}

Una de las posibilidades más potentes es la de observar el flujo de las intenciones. Resulta útil de dos maneras. Primero, puede observar dentro de una sesión cómo fluyen las intenciones del usuario en una conversación. Segundo, puede observar cómo los usuarios fluyen entre intenciones a lo largo de periodos más prolongados y así comprobar cómo evoluciona su uso de la “Aplicación”.

## Ejemplo {#concept_2B13D5E7A8E042D1A4B7BB80BBAACD12}

**Aplicación preinstalada**

<table id="table_70BF4E41D0BE4482BD925FB3A1768CE0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Persona </th> 
   <th colname="col2" class="entry"> Respuesta del dispositivo </th> 
   <th colname="col3" class="entry"> Acción/Intención </th> 
   <th colname="col4" class="entry"> Obtener solicitud </th> 
   <th colname="col5" class="entry"> Datos de análisis </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> Reproduce Spoofify </p> </td> 
   <td colname="col2"> <p> “vale, reproduciendo Spoofify” </p> </td> 
   <td colname="col3"> <p> Play </p> </td> 
   <td colname="col4"> <p> 
     <code>GET /b/ss/ [rsid]/0? vid = [userid] &amp; c. a. appid = Spoofify 1.0 &amp; c. a. launchevent = 1 &amp; c. Intent = Play &amp; pagename = playapp HTTP/1.1 
 Host: sc. omtrdc. net 
 Cache-Control: no-cache </code>
  </p> </td> 
   <td colname="col5"> <p> 
     <ul id="ul_E80B0BBEBE764023BB9B49FE5F15B918"> 
      <li id="li_9BC2CCABB0ED4246A57C37633666CDE2">ID de visitante </li> 
      <li id="li_1E7F9E979A3D49CE90899CE82C70BCD0">Versión de la aplicación </li> 
      <li id="li_C4BD7653B0FA47F6A3E4F1FF18138F10">N.º de inicios </li> 
      <li id="li_B7FA47CBD75747E8A8A25E228C90E524">Intención </li> 
      <li id="li_48274BA200704730A22C85FD682AE3B0">Respuesta </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Cambia canción </p> </td> 
   <td colname="col2"> <p> “vale, ¿qué canción quieres?” </p> </td> 
   <td colname="col3"> <p> ChangeSong </p> </td> 
   <td colname="col4"> <p> 
     <code>GET /b/ss/ [rsid]/0? vid = [userid] &amp; c. a. appid = Spoofify 1.0 &amp; c. Intent = changesong &amp; pagename = askforsong HTTP/1.1 
 Host: sc. omtrdc. net 
 Cache-Control: no-cache </code>
  </p> </td> 
   <td colname="col5"> <p> 
     <ul id="ul_AE8CF669F06547FDA68801F20BD8CBCE"> 
      <li id="li_5A03E41891AF4F37A3BE05BC11F197BC">ID de visitante </li> 
      <li id="li_435FF7DEB169466E8C3F9258C91315D1">Versión de la aplicación </li> 
      <li id="li_AB2B602D9DC74B3D951A0942B6CF8B39">Intención </li> 
      <li id="li_C9F87F3BB7104C9C978BB046C5DB9092">*lista de reproducción en blanco </li> 
      <li id="li_FB762962468A44A18DF93488EC2CB848">Respuesta </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Reproduce “My Heart Will Go On” de Celine Dion </p> </td> 
   <td colname="col2"> <p> “vale, reproduciendo 'My Heart Will Go On' de Celine Dion” </p> </td> 
   <td colname="col3"> <p> ChangeSong </p> </td> 
   <td colname="col4"> <p> 
     <code>GET /b/ss/ [rsid]/0? vid = [userid] &amp; c. a. appid = Spoofify 1.0 &amp; c. Intent = changeplaylist &amp; pagename = actionplaysong &amp; c. songid = [012345] HTTP/1.1 
 Host: sc. omtrdc. net 
 Cache-Control: no-cache </code>
  </p> </td> 
   <td colname="col5"> <p> 
     <ul id="ul_2AFEE1E928A8499E96B1BC6C5CC21F81"> 
      <li id="li_4BDF8093373A4DA1BB24A608FAC5B7CF">ID de visitante </li> 
      <li id="li_79B4FACCD333472EB9FC1F94B904AFB4">Versión de la aplicación </li> 
      <li id="li_3EDAB6208CB24213A934167BD08BD1AE">Intención </li> 
      <li id="li_C8E6609F9E0A45A8AED15F73374F40B2">ID de canción </li> 
      <li id="li_C4D99387C4D748189E15476F5E03BB76">Respuesta </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Cambia lista de reproducción </p> </td> 
   <td colname="col2"> <p> “vale, ¿qué lista de reproducción quieres?” </p> </td> 
   <td colname="col3"> <p> ChangePlaylist </p> </td> 
   <td colname="col4"> <p> 
     <code>GET /b/ss/ [rsid]/0? vid = [userid] &amp; c. a. appid = Spoofify 1.0 &amp; c. Intent = changeplaylist &amp; pagename = askforplaylist HTTP/1.1 
 Host: sc. omtrdc. net 
 Cache-Control: no-cache </code>
  </p> </td> 
   <td colname="col5"> <p> 
     <ul id="ul_913CF31C3EB34BDB819AD54D28F9DE5D"> 
      <li id="li_93036A142FB34A73A95B8AB114EA99C3">ID de visitante </li> 
      <li id="li_F699CDD7866C4EB4BECFF0FAA4689736">Versión de la aplicación </li> 
      <li id="li_6AB1FF7ED6A247FAA8922390410F2F5F">Intención </li> 
      <li id="li_9DF30E2E1958468783FF753D014F1A5F">*lista de reproducción en blanco </li> 
      <li id="li_B1106A51B8CD49DD8B566B946176F854">Respuesta </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Reproduce Usher </p> </td> 
   <td colname="col2"> <p> “vale, reproduciendo Usher” </p> </td> 
   <td colname="col3"> <p> ChangePlaylist </p> </td> 
   <td colname="col4"> <p> 
     <code>GET /b/ss/ [rsid]/0? vid = [userid] &amp; c. a. appid = Spoofify 1.0 &amp; c. Intent = changeplaylist &amp; pagename = actionplayplaylist &amp; c. Playlist = Usher HTTP/1.1 
 Host: sc. omtrdc. net 
 Cache-Control: no-cache </code>
  </p> </td> 
   <td colname="col5"> <p> 
     <ul id="ul_B70E7C9BEFA54C2FA8B7485F9BC7CEE7"> 
      <li id="li_2B0319D20189497D8C9981F871D4FBC4">ID de visitante </li> 
      <li id="li_78C28F34FC7C41589EB111ADCC5A0D66">Versión de la aplicación </li> 
      <li id="li_8ACF819CF80E4E8F942E0903DF75AE33">Intención </li> 
      <li id="li_49F407E43F474356A5F131F82B6C4EB9">Lista de reproducción </li> 
      <li id="li_7380EC51B0DE420EB5DD48BCE21B0567">Respuesta </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Apaga la música </p> </td> 
   <td colname="col2"> <p> *sin respuesta, la música se apaga </p> </td> 
   <td colname="col3"> <p> Off </p> </td> 
   <td colname="col4"> <p> 
     <code>GET /b/ss/ [rsid]/0? vid = [userid] &amp; c. a. appid = Spoofify 1.0 &amp; c. Intent = Off &amp; pagename = turnsoffmusic HTTP/1.1 
 Host: sc. omtrdc. net 
 Cache-Control: no-cache </code>
  </p> </td> 
   <td colname="col5"> <p> 
     <ul id="ul_BCA19F2A98CC42788A23E668B260F553"> 
      <li id="li_12A9DA8684B2479D90F3C357AE4F1D15">ID de visitante </li> 
      <li id="li_9E543F7F12D247D0900E5B1BE8EB0F61">Versión de la aplicación </li> 
      <li id="li_9627816FE3594C418EC52DAD42501BCA">Intención </li> 
      <li id="li_5D59C5D8D0F34F5193F592A867AE5639">Respuesta </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

**Requiere que el usuario instale una aplicación**

<table id="table_C178E3A2C87043A0A2B8C365869102A3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Persona </th> 
   <th colname="col2" class="entry"> Respuesta del dispositivo </th> 
   <th colname="col3" class="entry"> Acción/Intención </th> 
   <th colname="col4" class="entry"> Obtener solicitud </th> 
   <th colname="col5" class="entry"> Datos de análisis </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> Instala Spoofify </p> </td> 
   <td colname="col2"> <p> *sin respuesta </p> </td> 
   <td colname="col3"> <p> Install </p> </td> 
   <td colname="col4"> <p> 
     <code>GET /b/ss/ [rsid]/0? vid = [userid] &amp; amp; amp; c. a. installevent = 1 &amp; c. a. installdate = 2017-04-24 &amp; c. a. appid = Spoofify 1.0 &amp; c. ostype = Alexa &amp; c. Intent = Instalar &amp; pagename = Instalar HTTP/1.1 
 Host: sc. omtrdc. net 
 Cache-Control: no-cache </code>
  </p> </td> 
   <td colname="col5"> <p> 
     <ul id="ul_83A7731E5EA84477906AF4BFB3B50F48"> 
      <li id="li_A23A342B0D5745B3854B90ADFDD15EB2">ID de visitante </li> 
      <li id="li_E2F89B771B5F445B995E30C7E76BF2D2">Fecha </li> 
      <li id="li_03378BC9365F4020B7E28461AFDCB160">Intención </li> 
      <li id="li_6E1ECC9AF55141D1857688DA6A33DEEA">Versión de SO </li> 
      <li id="li_A4D06A0DFBC247499D9586F6B76571C4">Respuesta </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Reproduce Spoofify </p> </td> 
   <td colname="col2"> <p> “vale, reproduciendo Spoofify” </p> </td> 
   <td colname="col3"> <p> Play </p> </td> 
   <td colname="col4"> <p> 
     <code>GET /b/ss/ [rsid]/0? vid = [userid] &amp; c. a. appid = Spoofify 1.0 &amp; c. a. launchevent = 1 &amp; c. Intent = Play &amp; pagename = playapp HTTP/1.1 
 Host: sc. omtrdc. net 
 Cache-Control: no-cache </code>
  </p> </td> 
   <td colname="col5"> <p> 
     <ul id="ul_8FCA2B1357A8496DAF563775F019404F"> 
      <li id="li_78E84586A5284164B5B577B68A113394">ID de visitante </li> 
      <li id="li_977915DC425A43BDA69D9F76ADFBAB0C">Versión de la aplicación </li> 
      <li id="li_12725E1D4540485B8A3DB2EC82C6AD4C">N.º de inicios </li> 
      <li id="li_5B7F4487682241C38071A7037157F473">Intención </li> 
      <li id="li_A6AC81D56BF44E07B2FC0F2740CAB237">Respuesta </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Cambia canción </p> </td> 
   <td colname="col2"> <p> “vale, ¿qué canción quieres?” </p> </td> 
   <td colname="col3"> <p>ChangeSong </p> </td> 
   <td colname="col4"> 
    <code>GET /b/ss/ [rsid]/0? vid = [userid] &amp; c. a. appid = Spoofify 1.0 &amp; c. Intent = changesong &amp; pagename = askforsong HTTP/1.1 
 Host: sc. omtrdc. net 
 Cache-Control: no-cache </code>
  </td> 
   <td colname="col5"> <p> 
     <ul id="ul_C0FCB407A1344527A532A1EAEF0387E4"> 
      <li id="li_8905BCF15F0F493D90B5F1135AEC149C">ID de visitante </li> 
      <li id="li_2D1FAAF35CE24CE49D1AE3F24E4A5A86">Versión de la aplicación </li> 
      <li id="li_A7D11680A9554414878E6CBD03B66DC4">Intención </li> 
      <li id="li_64308721D00441FBB7E6EA6EDF93C100">*lista de reproducción en blanco </li> 
      <li id="li_A1B2C4E27F9E4B61AAA6373DA8CEB8F2">Respuesta </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Reproduce “My Heart Will Go On” de Celine Dion </p> </td> 
   <td colname="col2"> <p> “vale, reproduciendo 'My Heart Will Go On' de Celine Dion” </p> </td> 
   <td colname="col3"> <p> ChangeSong </p> </td> 
   <td colname="col4"> 
    <code>GET /b/ss/ [rsid]/0? vid = [userid] &amp; c. a. appid = Spoofify 1.0 &amp; c. Intent = changeplaylist &amp; pagename = actionplaysong &amp; c. songid = [012345] HTTP/1.1 
 Host: sc. omtrdc. net 
 Cache-Control: no-cache </code>
  </td> 
   <td colname="col5"> <p> 
     <ul id="ul_5D782E44875144BF96877897E1180D18"> 
      <li id="li_CB5009ED407A4D4ABF3AAFE73133CC66">ID de visitante </li> 
      <li id="li_D15D65E315964E0CBF75A87CF3FCF9B5">Versión de la aplicación </li> 
      <li id="li_055D7621BE1D44BA8B8C50E2E45DA6DF">Intención </li> 
      <li id="li_1D52C0AB9C12483E9CD7DC216D809E44">ID de canción </li> 
      <li id="li_5CFB748D02E84050AE216FDC55C680E2">Respuesta </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Cambia lista de reproducción </p> </td> 
   <td colname="col2"> <p> “vale, ¿qué lista de reproducción quieres?” </p> </td> 
   <td colname="col3"> <p> ChangePlaylist </p> </td> 
   <td colname="col4"> 
    <code>GET /b/ss/ [rsid]/0? vid = [userid] &amp; c. a. appid = Spoofify 1.0 &amp; c. Intent = changeplaylist &amp; pagename = askforplaylist HTTP/1.1 
 Host: sc. omtrdc. net 
 Cache-Control: no-cache </code>
  </td> 
   <td colname="col5"> <p> 
     <ul id="ul_7167AE13BBC64CC99E4A81B1FF6C9208"> 
      <li id="li_15554F7C8AC3487797A2FB65C8C1E636">ID de visitante </li> 
      <li id="li_11254FBCFA60436FB705D5FE4C313CC5">Versión de la aplicación </li> 
      <li id="li_4F3AE5B191DB4E73A2C08065A3D75188">Intención </li> 
      <li id="li_7F03D76A26254E65AAEB8E7D647895CA">*lista de reproducción en blanco </li> 
      <li id="li_DFB50E6BCEAF440D942B30A56CDD1503">Respuesta </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Reproduce Usher </p> </td> 
   <td colname="col2"> <p> “vale, reproduciendo Usher” </p> </td> 
   <td colname="col3"> <p> ChangePlaylist </p> </td> 
   <td colname="col4"> 
    <code>GET /b/ss/ [rsid]/0? vid = [userid] &amp; c. a. appid = Spoofify 1.0 &amp; c. Intent = changeplaylist &amp; pagename = actionplayplaylist &amp; c. Playlist = Usher HTTP/1.1 
 Host: sc. omtrdc. net 
 Cache-Control: no-cache </code>
  </td> 
   <td colname="col5"> <p> 
     <ul id="ul_BE5815D13CFA48408B4612D220356518"> 
      <li id="li_716EA824A56241A282FD1774A51CF52C">ID de visitante </li> 
      <li id="li_02CC3C2A66E44BB4BA865893F3206A6C">Versión de la aplicación </li> 
      <li id="li_558B15EC8605495B8DC01E644602FC4F">Intención </li> 
      <li id="li_21599097A3B14E368693C77CC7BA8ADD">Lista de reproducción </li> 
      <li id="li_70F4254A33704DA18D4D22028A1656E4">Respuesta </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Apaga la música </p> </td> 
   <td colname="col2"> <p> *sin respuesta, la música se apaga </p> </td> 
   <td colname="col3"> <p> Off </p> </td> 
   <td colname="col4"> 
    <code>GET /b/ss/ [rsid]/0? vid = [userid] &amp; c. a. appid = Spoofify 1.0 &amp; c. Intent = Off &amp; pagename = turnsoffmusic HTTP/1.1 
 Host: sc. omtrdc. net 
 Cache-Control: no-cache </code>
  </td> 
   <td colname="col5"> <p> 
     <ul id="ul_C623E19496DD466DA299AD610CE5ED1D"> 
      <li id="li_6A7AEF89A74C431C84D107E4F23AE223">ID de visitante </li> 
      <li id="li_B8CFF6AAB2E2476786026A98337589AF">Versión de la aplicación </li> 
      <li id="li_534596CB56B24B729AAA801A7B4D9D31">Intención </li> 
      <li id="li_CA3328E5FFF442BAA0F11C51DF2ED53F">Respuesta </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>


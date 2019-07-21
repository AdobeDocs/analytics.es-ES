---
description: Recopilación de notas de versiones para iOS.
seo-description: Recopilación de notas de versiones para iOS.
seo-title: iOS
solution: Analytics, Marketing Cloud
subtopic: Notas de la versión
title: iOS
topic: Desarrollador e implementación
uuid: cc 98 f 8 f 2-f 619-4 b 31-abf 9-e 43 f 4 deac 64 f
translation-type: tm+mt
source-git-commit: 01a6fc7e44dc71b868bd38a4f6a5a4089eae6349

---


# iOS{#ios}

Recopilación de notas de versiones para iOS.

>[!NOTE]
>
>Para encontrar la versión actual de la biblioteca, active la depuración de registro.

Las descargas de las bibliotecas móviles están disponibles en [GitHub](https://github.com/Adobe-Marketing-Cloud/mobile-services) y en [Developer Connection](https://marketing.adobe.com/developer/gallery/app-measurement-for-ios).

[Documentación de 4.x](https://marketing.adobe.com/resources/help/en_US/mobile/ios/)

[Documentación de 3.x](https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/ios/)

## Versión 4.13.4 {#section_BF05D33CEF6E42358C8089441449449B}

The [!DNL iOS] SDK version 4.13.4 (Feb 16, 2017) includes the following changes:

<table frame="all" colsep="1" rowsep="1" id="table_657D643E874D47C099F2F43519C9C1C7"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> Función </th> 
   <th colname="2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Mensajería en la aplicación </p> </td> 
   <td colname="2"> <p> Se ha corregido un error que impedía utilizar la versión adecuada de la aplicación al determinar una audiencia. Este problema se producía cuando un usuario actualizaba la versión de la aplicación sin haber lanzado un ciclo de vida nuevo. </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p> Adquisición </p> </td> 
   <td colname="2"> <p> Se ha agregado un retraso de tres segundos antes de realizar llamadas de API para datos de Search Ads de Apple en las instalaciones de las aplicaciones (según la recomendación de la documentación). </p> </td> 
  </tr> 
 </tbody> 
</table>

## Versión 4.13.3 {#section_39618D2B29F942FCBF37E4F5507AA131}

The [!DNL iOS] SDK version 4.13.3 (Jan 19, 2017) includes the following changes:

<table frame="all" colsep="1" rowsep="1" id="table_341D35BF18714139A95CA5491899185D"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> Función </th> 
   <th colname="2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Mensajería en la aplicación </p> </td> 
   <td colname="2"> <p> Ahora puede desactivar los mensajes a pantalla completa cuando VoiceOver se está ejecutando. </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p><span class="keyword">Analytics</span> </p> </td> 
   <td colname="2"> <p> Se ha mejorado el manejo de acceso de solo lectura a las bases de datos. </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p>General </p> </td> 
   <td colname="2"> <p> Se ha corregido un problema que a veces podía ocasionar un bloqueo al llamar a un método de seguimiento desde el fondo mientras se usaban grupos de aplicaciones. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Versión 4.13.2 {#section_CB0DFFDB38FE4D14A84423DF40BF8FD3}

The [!DNL iOS] SDK version 4.13.2 (Nov 10, 2016) includes the following changes:

<table frame="all" colsep="1" rowsep="1" id="table_AA26B14D271948FFBA44D4D06E3B71AA"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> Función </th> 
   <th colname="2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p> Servicio de ID de visitante </p> </td> 
   <td colname="2"> <p> Se ha añadido la marca de fecha y hora y el ID de organización de Marketing Cloud al parámetro <code>adobe_mc</code>. </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p> Configuración </p> </td> 
   <td colname="2"> <p> Los IDFA no válidos (00000000-0000-0000-0000-000000000000) que se pasen al SDK a través de <code>setAdvertisingIdentifier:</code> se ignorarán. </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p> Enlaces profundos </p> </td> 
   <td colname="2"> <p>Ahora, al llamar a <code>trackAdobeDeepLink</code>, las variables con los prefijos “<code>adb</code>” y “<code>ctx</code>” se gestionan correctamente. </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p> Adquisición </p> </td> 
   <td colname="2"> <p>Ahora, los datos de los anuncios de Apple Search se envían junto con los datos de adquisición. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Versión 4.13.1 {#section_18C8A7166EFD4E67AC0F7C06DFBBFE6A}

The [!DNL iOS] SDK version 4.13.1 (Oct 20, 2016) includes the following changes:

<table frame="all" colsep="1" rowsep="1" id="table_5B67A6B8B79D4783BA8DCDA7C2ACA765"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> Función </th> 
   <th colname="2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p> Adquisición </p> </td> 
   <td colname="2"> <p> El SDK ahora admite que datos de adquisición personalizados se devuelvan adecuadamente por invocaciones de <code>AdobeDataCallback</code>. </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Target </p> </td> 
   <td colname="2"> <p> Los parámetros del <span class="keyword">servicio de ID de visitante</span> ahora se pasan en solicitudes de <span class="keyword">Target</span> a través de <code>mboxParams</code>. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Correcciones de errores**

* Se ha corregido un problema que podía provocar un bloqueo al intentar sincronizar nuevos ID al servicio de ID de visitante al mismo tiempo que se enviaban visitas de seguimiento a [!DNL Adobe Analytics].
* Fixed an issue that was causing build warnings when targeting [!DNL iOS] versions older than 8.

## Versión 4.13.0 {#section_F72A3357994E4887A9F3967F0FBFFCDD}

The [!DNL iOS] SDK version 4.13.0 (Sep 15, 2016) includes the following changes:

<table frame="all" colsep="1" rowsep="1" id="table_FD6156E58FF54BA2BEED7398BC780C46"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> Función </th> 
   <th colname="2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Mensajería en la aplicación </p> </td> 
   <td colname="2"> <p>Nueva función: se ha añadido un tipo de mensaje nuevo que abre un URI de enlace profundo. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Versión 4.12.0 {#section_2AD26AABBB434833AE961C8D71C9AFE8}

The [!DNL iOS] SDK version 4.12.0 (Aug 18, 2016) includes the following changes:

<table frame="all" colsep="1" rowsep="1" id="table_CC3CD01203ED4BDA9BC26427E925C70D"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> Función </th> 
   <th colname="2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Servicio de ID de visitante </p> </td> 
   <td colname="2"> <p> Se ha añadido un nuevo método para asignar la identidad de los visitantes a una URL determinada a fin de transferir dicha identidad a una implementación basada en web. </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Mensajería en la aplicación </p> </td> 
   <td colname="2"> <p>Se ha corregido un problema que podía provocar un bloqueo al configurar el atributo "target" como "_blank" en una etiqueta HTML de un mensaje personalizado en pantalla completa. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Versión 4.11.0 {#section_3ABABE0F0B964EB48BD482CCE260A13D}

The [!DNL iOS] SDK version 4.11.0 (June 22, 2016) includes the following changes:

<table frame="all" colsep="1" rowsep="1" id="table_14B23402BA3B41238F419CA57341B8F5"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> Función </th> 
   <th colname="2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Métodos de Target </p> </td> 
   <td colname="2"> <p>Ahora puede utilizar el nuevo método <span class="keyword">Target</span> siguiente: </p> <p> 
     <ul id="ul_93CDE46E39C9431DA9104664F175708B"> 
      <li id="li_903FAC68526B4B7CB6555DC577CE493A"><code> targetLoadRequestWithName:defaultContent:profileParameters:orderParameters:mboxParameters:requestLocationParameters:callback:</code> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Versión 4.10.0 {#section_F0D6D7FD89DE4DF5A121B05FA093CC5B}

The [!DNL iOS] SDK version 4.10.0 (May 20, 2016) includes the following changes:

<table frame="all" colsep="1" rowsep="1" id="table_AC447B6E4D55489F803923BF5D1D6653"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> Función </th> 
   <th colname="2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Métodos de Target </p> </td> 
   <td colname="2"> <p>Ahora puede utilizar los nuevos métodos <span class="keyword">Target</span> siguientes: </p> <p> 
     <ul id="ul_D0594A9ABFD8448186DED87599A0E50E"> 
      <li id="li_A4B0ECDF200C438BB1AB24D613453A68"><code> targetLoadRequestWithName:defaultContent:profileParameters:orderParameters:mboxParameters:callback:</code> </li> 
      <li id="li_C0FADBB3CEE141AE951CBD49F3A52642"><code> targetThirdPartyID</code> </li> 
      <li id="li_3E1B3725D9EE4ECE9DB0EB1A9E7682A4"><code> targetSetThirdPartyID:</code> </li> 
      <li id="li_659E295610F541819DD7486FC5177012"><code> targetPcID</code> </li> 
      <li id="li_B00ADCF98B6D4694BB7664DB42CDFF99"><code> targetSessionID</code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Métodos de TVJS </p> </td> 
   <td colname="2"> <p>Ahora puede utilizar los nuevos métodos TVJS de <span class="keyword">Target</span> siguientes: </p> <p> 
     <ul id="ul_AED76A2B99534CF3A472AC0381B2618C"> 
      <li id="li_AA731652996C4A19A8E02D5D6B8BDC93"><code> targetThirdPartyID</code> </li> 
      <li id="li_744A63A62A8045E49C75F9D7AED5D75E"><code> targetSetThirdPartyID</code> </li> 
      <li id="li_72BC8D96FE0549A695D90B924FA80A02"> <code> targetPcID</code> </li> 
      <li id="li_FB7A9435B9994DB89FA80C2B2218C047"> <code> targetSessionID</code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Adobe Target para TVML/TVJS </p> </td> 
   <td colname="2"> <p>Ahora puede usar los nombres de propiedad siguientes al configurar su elemento <code>ADBTarget</code>: </p> <p> 
     <ul id="ul_A0CEE891AE644B47ABD6F7425ACD464D"> 
      <li id="li_2EB0C3CA52014F45BA1EC07703E821B8"><code> id</code> </li> 
      <li id="li_069D996CED534EE88A1EC82684E470D5"><code> total</code> </li> 
      <li id="li_97F290C03FFD46B8A1E78B7BF2021F55"> <code>purchasedProductIds</code> </li> 
      <li id="li_FAAC4BB12DF9491DA21F161711A7707D"> <code> mboxParameters</code> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Versión 4.9.0 {#section_DA97D7294B214067A4904B9738450759}

The [!DNL iOS] SDK version 4.9.0 (May 5, 2016) includes the following changes:

<table frame="all" colsep="1" rowsep="1" id="table_0B3A0F44549C4DA48C7639048C030065"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> Función </th> 
   <th colname="2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Enlaces profundos </p> </td> 
   <td colname="2"> <p>Puede implementar enlaces profundos en sus aplicaciones para llevar a los usuarios a destinos de aplicación o de vínculo web. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Versión 4.8.6 {#section_0150641B44CF4F6CBE2B21002F8EAB30}

The [!DNL iOS] SDK version 4.8.6 (March 9, 2016) includes the following changes:

<table frame="all" colsep="1" rowsep="1" id="table_5175CFFCA30B4DDBACFB23532111CB8A"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> Función </th> 
   <th colname="2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Seguimiento de errores de aplicaciones </p> </td> 
   <td colname="2"> <p>The <span class="keyword"> iOS</span> SDK version 4.8.6 contains critical changes that prevent false crashes from being reported. Le recomendamos encarecidamente que actualice a la versión 4.8.6. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Versión 4.8.5 {#section_F42EB64F91024748893E89575F2E4487}

The [!DNL iOS] SDK version 4.8.5 (February 18, 2016) includes the following changes:

<table frame="all" colsep="1" rowsep="1" id="table_AB225AF04A374421BDD8A972506ACD06"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> Función </th> 
   <th colname="2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Cancelación y configuración de privacidad </p> </td> 
   <td colname="2"> <p>Starting with <span class="keyword"> iOS</span> SDK 4.8.5, privacy settings set via the <code> setPrivacyStatus</code> method affect activity from <span class="keyword"> Analytics</span>, <span class="keyword"> Target</span>, and <span class="keyword"> Audience Manager</span>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Versión 4.8.0 {#section_2CF142C8C2D24B529559DAF76F851BBF}

The [!DNL iOS] SDK version 4.8.0 (November 2, 2015) includes the following changes:

<table frame="all" colsep="1" rowsep="1" id="table_9DB41F070D66498FACF1A9C135603C7A"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> Función </th> 
   <th colname="2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> Nuevos métodos del servicio de ID de visitante de Marketing Cloud </td> 
   <td colname="2"> <p>Se agregaron los siguientes métodos nuevos: </p> 
    <ul id="ul_55D8F29ADE3746C484FEC7893FA9EF23"> 
     <li id="li_19F8AF546EEB45EBB5849EA6EB3CE6A3"><code> visitorSyncIdentifiers:authenticationState:</code> </li> 
     <li id="li_1AF1CF62B3ED442D81B438ECBF981583"><code> visitorSyncIdentifierWithType:identifier:authenticationState: </code> </li> 
     <li id="li_C116F0DA8E2A449A8B76637961C2100C"><code> visitorGetIDs</code> </li> 
    </ul> <p>El método <code>visitorSyncIdentifiers:identifiers</code> se cambió <code>visitorSyncIdentifiers:</code> </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> Nuevos métodos de TVJS </td> 
   <td colname="2"> <p>Se agregaron los siguientes métodos nuevos: </p> 
    <ul id="ul_4C7F4BB1CF744444ABAA9F13BA98749E"> 
     <li id="li_5DAB089D115843CCA0A53873D6D676F0"><code> visitorSyncIdentifiersAuthenticationState</code> </li> 
     <li id="li_EDE2D1301E8648DB88A18D8C9F6A22C5"><code> visitorSyncIdentifierWithTypeIdentifierAuthenticationState</code> </li> 
     <li id="li_2CCED3C707774597934A2F08BC690B15"><code> visitorGetIDsJs</code> </li> 
    </ul> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> Nueva variable de configuración ADBMobile JSON </td> 
   <td colname="2"> <p>Se agregó la variable siguiente: </p> 
    <ul id="ul_95065BC06FD540D2937D11111799F77F"> 
     <li id="li_7C8C68A41FBA4D098D6803E71D4CCF7A"><code> analyticsForwardingEnabled</code> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## Versión 4.7.0 {#section_B37B1CAF065346E9A2073A06AB7AFEC2}

The [!DNL iOS] SDK version 4.7.0 (October 15, 2015) includes the following changes:

<table frame="all" colsep="1" rowsep="1" id="table_3CCA327B859B498D828B2E056A075BEC"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> Función </th> 
   <th colname="2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> Compatibilidad de tvOS </td> 
   <td colname="2"> <p>tvOS es compatible con Apple TV. </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> Compatibilidad de App Transport Security </td> 
   <td colname="2"> <p>Starting with <span class="keyword"> iOS</span> 9, Apple introduced App Transport Security, a set of requirements that conforms to best practices for secure connections. </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p><span class="keyword"> Métodos del plugin PhoneGap</span> </p> </td> 
   <td colname="2"> <p>Se agregaron los siguientes métodos nuevos: </p> <p><b>Métodos de configuración</b> </p> <p> 
     <ul id="ul_98C5E7B5C79446EEA00F0E7CBC213301"> 
      <li id="li_B403C06E57A0450CBB4ABAD45170C681">setPushIdentifier </li> 
      <li id="li_6D76C40601544D4FA13FD44F390C83CE">setAdvertisingIndentifier </li> 
      <li id="li_7D03005DBD9E4AC7BB78BA162CDC8153">keepLifecycleSessionAlive </li> 
      <li id="li_3DDE07508B764E679AF2ACECC4D935CB">trackingSendQueuedHits </li> 
     </ul> </p> <p><b>Métodos de seguimiento</b> </p> <p> 
     <ul id="ul_9B6002F5642B4D888FBD0A8D44EF32DB"> 
      <li id="li_5C1C9EA770E048E48723528F346712B4">trackPushMessageClickthrough </li> 
     </ul> </p> <p>Nuevo método de Target: </p> <p> 
     <ul id="ul_E6A481FCD49D4CF48A4B0636312FCD19"> 
      <li id="li_6604FBB05C4E4988A04CB376D6667C79">targetClearCookies </li> 
     </ul> </p> <p><b>Métodos de adquisición</b> </p> <p> 
     <ul id="ul_2015BFF019E64D5685A25E20D4B4A79B"> 
      <li id="li_D450F60189904C43BDAC5D658324AEAA">acquisitionCampaignStartForApp </li> 
     </ul> </p> <p><b>Métodos de Audience Manager</b> </p> <p> 
     <ul id="ul_7D5F339A1A004593AE1D5C26A5A495C5"> 
      <li id="li_2F44037A508D49308F42961FDFB6486C">audienceGetVisitorProfile </li> 
      <li id="li_4F8F43C875384A74ADD48D4197C2ACFD">audienceGetDpuuid </li> 
      <li id="li_B38B6700AF2F4B9FA80CC6774B5B14E7">audienceGetDpid </li> 
      <li id="li_12579B472B404ABAA12DFBDBB22A0C30">audienceSetDpidAndDpuuid </li> 
      <li id="li_2CA997AF9FE241FD961BB0A9B50E14D9">audienceSignalWithData </li> 
      <li id="li_3545CB51B6B7409D8CE2B97E291267E6">audienceReset </li> 
     </ul> </p> <p><b>Métodos del servicio de ID de visitante</b> </p> <p> 
     <ul id="ul_746B8A36715D4075B11C42F9FE82F538"> 
      <li id="li_A15AFA632E8C4C8D931CAB48B9A29ADB">visitorGetMarketingCloudId </li> 
      <li id="li_D80DD8DDE6AB4CB6BEE37DAA9BB28A98">visitorSyncIdentifiers </li> 
     </ul> </p> <p><b>Extensiones de la aplicación y métodos de Apple Watch</b> </p> <p> 
     <ul id="ul_66B1E1AC4A6D4970B0C77A46EA14ABA7"> 
      <li id="li_1EA7A063FED04E0585D463837A7555CE">setAppGroup </li> 
      <li id="li_5869EAB018C94EE4AC28B3EE62D9F0EF">syncSettings </li> 
      <li id="li_983A98CAEBAD404EBCE1D70CB0B52BA3">initializeWatch </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Versión 4.6 {#section_D091872501DA49C1A18CDC33C84B8256}

The [!DNL iOS] SDK version 4.6 (September 17, 2015) includes the following changes:

<table frame="all" colsep="1" rowsep="1" id="table_084C27B1A75A4A2EB84822242E37ED35"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> Función </th> 
   <th colname="2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Push Messaging to <span class="keyword"> Analytics</span> Segments </p> </td> 
   <td colname="2"> <p> El SDK de <span class="keyword">Adobe Mobile Services</span> y <span class="keyword">Adobe Mobile</span> permite enviar mensajes push a segmentos de <span class="keyword">Analytics</span>. También permite conocer fácilmente qué usuarios han abierto la aplicación como resultado de la lectura del mensaje push. </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Métodos de adquisición </p> </td> 
   <td colname="2"> <p>Permite a los desarrolladores iniciar una campaña de adquisición de aplicación como si el usuario hubiera hecho clic en un vínculo. Esto resulta útil para crear vínculos de adquisición manuales y controlar personalmente el redireccionamiento a la tienda de aplicaciones. </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Postback </p> </td> 
   <td colname="2"> <p>Los postback permiten enviar datos recopilados por el SDK a un servidor independiente de terceros. Con los mismos desencadenadores y las mismas características que se emplean para mostrar un mensaje en la aplicación, es posible configurar el SDK para que envíe datos personalizados a un destino de terceros. </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Identificadores </p> </td> 
   <td colname="2"> <p>Se han agregado los siguientes identificadores nuevos: </p> <p> 
     <ul id="ul_22EF89556F6B481ABE0D1B9C5EE70B55"> 
      <li id="li_C41F6FAC0B334B89B8B5D1A517CA2301"> <code> setPushIdentifier</code> </li> 
      <li id="li_B7893FB0453340EDB4290BC0B47BF096"><code> setAdvertisingIdentifier</code> </li> 
      <li id="li_85EF5F2B8837497B90F782946283622E"><code>trackPushMessageClickThrough</code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Compatibilidad de WatchKit para WatchOS 2 </p> </td> 
   <td colname="2"> <p>Se ha agregado la compatibilidad de WatchKit para WatchOS 2. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Versión 4.5 {#section_53DFAF8CFD614F69B3168014EF84DE9F}

The [!DNL iOS] SDK version 4.5 includes the following changes:

<table frame="all" colsep="1" rowsep="1" id="table_A69D0B8DA45348B8A5D6A014126F97C2"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> Función </th> 
   <th colname="2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p><span class="keyword"> Extensión de iOS</span> </p> </td> 
   <td colname="2"> <p>Starting in <span class="keyword"> iOS</span> SDK version 4.5, a new <span class="keyword"> iOS</span> extension lets you collect usage data from your Apple Watch Apps, Today Widgets, Photo Editing widgets, and all the other <span class="keyword"> iOS</span> extension apps. </p> <p>We strongly recommend that you use the <span class="keyword"> iOS</span> SDK rather than using your own wrapper. </p> <p>Apple proporciona un conjunto de API que permite a la aplicación Watch comunicarse con la aplicación contenedora (enviar solicitudes a la aplicación contenedora y, a continuación, recibir respuestas). </p> <p>Aunque se pueden enviar datos de seguimiento como un diccionario desde la aplicación Watch hasta la aplicación contenedora y, a continuación, llamar cualquier método de seguimiento de la aplicación contenedora para enviar los datos, esta solución tiene algunas limitaciones. </p> <p>En la mayoría de los casos, cuando un usuario utiliza la aplicación Watch, la aplicación contenedora se ejecuta en segundo plano y solo es seguro llamar a <code>TrackActionInBackground</code>, <code>TrackLocation</code> y <code>TrackBeacon</code>. El hecho de llamar a otros métodos de seguimiento interfiere con los datos del ciclo vital, por lo que solo debería utilizar estos tres métodos para enviar datos desde la aplicación Watch. </p> <p>Even if these three tracking methods meet your requirements, we recommend using the <span class="keyword"> iOS</span> SDK because the SDK for watch app includes all <span class="keyword"> Mobile</span> features except in-app messaging. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Versión 4.4 {#section_0B7A98761BF0400986C368E154A3B00B}

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
   <td colname="1"> <p>Beacon tracking support in <span class="keyword"> PhoneGap</span> </p> </td> 
   <td colname="2"> <p>Las llamadas <code>trackBeacon</code> y <code>clearCurrentBeacon</code><span class="keyword"> ahora están disponibles en PhoneGap</span>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Versión 4.3 {#section_0FD2B2C4F54E4A9E8C6D0CD2F103BB9A}

Fecha de versión: **24 de noviembre de 2014**

* Nuevo - Integración de Adobe Marketing Cloud ID
* Registros de depuración mejorados para una mayor claridad

## Versión 4.2 {#section_806710F7720C410DAB46376C0A7A283E}

Fecha de versión: **16 de octubre de 2014**

* Nuevo - Capacidades de mensajería en la aplicación.
* Nuevo - Ahora se puede especificar el archivo de configuración durante el inicio de la aplicación.
* Nuevo - Ahora, los puntos de interés se pueden actualizar automáticamente sin necesidad de un nuevo archivo de configuración.
* New - [!DNL Analytics] calls are now sent as HTTP POST requests.
* Se han eliminado los mensajes de registro y se han agregado más detalles a los registros cuando debugLogging está habilitado.
* Múltiples mejoras en rendimiento y estabilidad.

## Versión 4.1.3 {#section_8D679B676F604E0B9A64748569185368}

Fecha de versión: **18 de septiembre de 2014**

* Resolved potential crash that could occur if Audience Manager Submit Signal call or [!DNL Target] Load Request call failed due to an unknown network error.

## Versión 4.1.2 {#section_6128902E5AE142C4A95D2FB3053188F8}

Fecha de versión: **5 de agosto de 2014**

* Se ha resuelto un error de interbloqueo que se podía producir con una configuración específica de privacyStatus:optunknown y offlineEnabled:false

Fecha de versión: **4 de agosto de 2014**

* Se ha resuelto un error que podía causar que las visitas del ciclo de vida no se enviaran cuando el tiempo de espera del referente era &gt;= 5 segundos y el seguimiento sin conexión estaba deshabilitado.

Fecha de versión: **17 de abril de 2014**

* Seguimiento de las señalizaciones por Bluetooth.
* Análisis de adquisiciones de aplicaciones.
* Aplicaciones con la marca de hora habilitada, las visitas de bloqueo retrasan su fecha con respecto a la sesión correcta.
* Aplicaciones con la marca de hora habilitada, la sesión anterior se envía en una visita que retrasa su fecha con respecto a la sesión correcta. (deja de ser la sesión anterior)
* Lotes de visitas.

## Versión 4.0.2 {#section_B78AE82CDFAD44DCAC6D61E0B80BF4C8}

Fecha de versión: **20 de febrero de 2014**

* Se ha resuelto el problema que causaba un comportamiento incorrecto cuando se abría el mismo elemento multimedia en secuencia sin cerrar el elemento anterior.

## Versión 4.0.1 {#section_A6D017015BC742F69B6EE4A461D00FD7}

Fecha de publicación: **30 de enero de 2014**

* Se ha resuelto un problema que hacía que se enviaran varias visitas cuando la base de datos resultaba dañada.
* Se ha resuelto un problema que producía promedios de larga duración de sesión si un dispositivo tenía una configuración de tiempo incorrecta.

## Versión 3.3.2 {#section_6D12768F20C44BA4A0D1EA607D367147}

Fecha de publicación: **30 de enero de 2014**

* Se ha resuelto un problema que producía promedios de larga duración de sesión si un dispositivo tenía una configuración de tiempo incorrecta.

## Versión 4.0.0 {#section_79DCFAAF1DCB404898E3BE389AC835A6}

Fecha de versión: **27 de septiembre de 2013**

[!DNL iOS] SDK 4.x para Soluciones de Marketing Cloud ya está disponible con las siguientes nuevas funciones:

* Mejoras significativas en rendimiento. Todo el procesamiento se realiza en subprocesos en segundo plano, el SDK tiene protección completa frente a los subprocesos.
* Localización geográfica y puntos de interés
* Valor de duración
* Eventos temporizados
* Administración de inclusiones y exclusiones
* Compatibilidad con Audience Manager
* Lifecycle metrics passed to [!DNL Target] as mbox parameters
* Estandarización en datos de contexto y reglas de procesamiento

## Versión 3.3.0 {#section_28FB7CD64D6C49BF93E321587F1E8950}

Fecha de versión: **23 de septiembre de 2013**

* Se ha agregado compatibilidad con arquitecturas de simulador ARM64 y X64 (iPhone 5s)

## Versión 3.2.1 {#section_3E73A76401664C54B32C7F3BE8BE36E3}

Fecha de versión: **16 de agosto de 2013**

* Optimizado mediante la eliminación de código no utilizado.
* Se ha solucionado un posible bloqueo que se podía producir cuando clearVars se utilizaba en un escenario de subprocesos.

## Versión 3.2 {#section_A51E0EB26EF246DABE27234C77598D99}

Fecha de versión: **6 de agosto de 2013**

* Se ha agregado compatibilidad con Adobe Audience Manager.
* Lifecycle data is now sent with [!DNL Target] Mbox requests when lifecycle tracking is enabled.

## Versión 3.1.8 {#section_849BCD1D4379433D874B8A0E0099E2B1}

Fecha de versión: **20 de junio de 2013**

* Fixed a bug introduced in 3.1.7 that was causing issues with lifecycle on devices below [!DNL iOS] 5.0.

## Versión 3.1.7 {#section_EC59B76EE3A343D5921E906EB0A8DB49}

Fecha de versión: **23 mayo de 2013**

* Se ha agregado código para evitar que se envíen demasiadas visitas de ciclo de vida a través de notificaciones de ubicación y de Newsstand que inician una aplicación.

## Versión 3.1.6 {#section_4617D7A41D0841BEBD5829001DC74854}

Fecha de versión: **18 de abril de 2013**

* Se ha solucionado un problema que, en ocasiones, producía un cálculo incorrecto de la duración de la sesión anterior.

## Versión 3.1.5 {#section_620AA594868F47619A514AF3C1EAC93B}

Fecha de versión: **21 de marzo de 2013**

* `ADMS_Measurement.visitorID` ahora se rellena previamente con el valor predeterminado.

## Versión 3.1.4 {#section_B04D1A4858A84A19AA65A57609C9F53F}

Fecha de versión: **21 de febrero de 2013**

* Ya no es necesario configurar un `offlineThrottleDelay` obsoleto gracias a la optimización de los procesos. La configuración aún existe para preservar la compatibilidad con versiones anteriores, pero ya no tiene ningún efecto.

## Versión 3.1.3 {#section_CCFAE5A29FB14DAD9A9F14FE8EE09B75}

Fecha de versión: **noviembre de 2012**

* Se ha solucionado un posible problema de EXEC_BAD_Access cuando se establece manualmente la variable de los productos.
* Se ha solucionado un posible bloqueo del selector no válido cuando se acaba el tiempo de espera de mbox.
* Se ha agregado compatibilidad con el seguimiento de publicidades a la medición multimedia.

## Versión 3.1.2 {#section_25C8A6B67AB9487BA5DEB4DB196AE4BC}

Fecha de versión: **octubre de 2012**

* Se ha agregado una variable de configuración de `lifecycleSessionTimeout` que le permite especificar el tiempo, en segundos, que debe pasar entre inicios de la aplicación antes de que el inicio se considere una nueva sesión.
* Se ha solucionado un problema en el módulo multimedia que hacía que los eventos establecidos en el objeto de medición sobrescribieran eventos establecidos por el módulo multimedia.
* Fixed an issue that caused an exception when allocating an mbox through the [!DNL Target] integration.

## Versión 3.1.0 {#section_0F3E939885DE4DF1B7430DF5F5749AD2}

Fecha de versión: **septiembre de 2012**

* Se ha agregado compatibilidad para la arquitectura armv7s
* Se ha eliminado la compatibilidad para la arquitectura armv6
* Minimum supported [!DNL iOS] SDK is now 4.3

## Versión 3.0.2 {#section_1224693620524D6C8CCAB7707483536E}

Fecha de versión: **agosto de 2012**

* Los clientes que usen un delegado para el control multimedia ya no verán dos eventos de cierre.
* Se ha resuelto un problema en el que dos visitas de cierre a veces causaban una condición de bucle en el control multimedia.

## Versión 3.0 {#section_D28F56359EC04EDC8521BE93750AE90D}

Fecha de versión: **julio de 2012**

Versión inicial.

**Mejoras**

* Se ha agregado la funcionalidad "Auto-Tracking" (seguimiento automático)
* Se ha reducido el tamaño de la biblioteca a aprox. 90k en la composición final.
* Se han agregado los métodos "trackEvents" y "trackAppState"
* Se ha mejorado la compatibilidad y funcionalidad de datos de contexto. (Se recomienda usar datos de contexto para toda la información enviada)
* Se ha simplificado el seguimiento de modo que se puede efectuar una implementación de seguimiento básica en 5 minutos.

**Cambios**

* [!DNL AppMeasurement] Class es ahora ADMS_Measurement
* ADMS_Measurement actúa ahora como un verdadero Singleton
* Se han cambiado los captadores y definidores por eVars, props, listas, hiers y pevs
* Todas las variables pasadas a llamadas de "seguimiento" solo permanecerán para esa llamada.

**Se han modificado las siguientes variables**

| Versión anterior (2.x) | Versión actual (3.x) |
|---|---|
| account | reportSuiteIDs |
| dc | dataCenter |
| pageName | appState |
| contextData | persistentContextData |
| state | geoState |
| zip | geoZip |
| server | appSection |
| debugTracking | debugLogging |
| trackOffline | offlineTrackingEnabled |
| offlineLimit | offlineHitLimit |
| OfflineThrottleDelay | offlineThrottleDelay |

**Se ha modificado el objetivo de las siguientes variables:**

* linkURL (enviada con trackLinkURL:)
* linkName (enviada con trackLinkURL:)
* linkType (enviada con trackLinkURL:)
* lightProfileID (enviada con trackLight:)
* lightStoreForSeconds (enviada con trackLight:)
* lightIncrementBy (enviada con trackLight:)
* trackingServerSecure (trackingServer se usa cuando ssl está activado)

**Se han eliminado las siguientes variables:**

* timestamp
* userAgent
* dynamicVariablePrefix
* visitorNamespace
* pageURL
* pageType
* referrer
* linkLeaveQueryString
* usePlugins
* useBestPractices (gestionada por AutoTracking)
* delegate
* retrieveLightData
* deleteLightProfiles
* retrieveLightProfiles

## Versión iOS anterior (2.x) {#section_5F76C3DA854D4BAEA636A68B3811142B}

The following release notes apply to the 2.x version of [!DNL AppMeasurement] for [!DNL iOS]. Recomendamos a los clientes que actualicen a la versión 3.x lo antes posible.

## Versión 2.1.12 {#section_85C073B86B684D52A14E8038379F56DD}

Fecha de versión: **abril de 2012**

* Se ha agregado compatibilidad para la medición de vídeos de 
* Se han resuelto problemas relacionados con linktrackvars y datos de contexto.
* Se han hecho varias mejoras adicionales al rendimiento.

## Versión 2.1.11 {#section_F0AF2D4E5F504D798EEB95BE8FE61B4C}

Fecha de versión: **marzo de 2012**

* Se ha solucionado un problema que causaba que el seguimiento sin conexión detuviera el envío de datos en determinadas circunstancias.

## Versión 2.1.10 {#section_07C24EC83AA94A6AA6AB3DE7E8D6227F}

Fecha de versión: **febrero de 2012**

* Se ha solucionado un problema que causaba una excepción EXC_BAD_ACCESS en algunas circunstancias cuando varios procesos intentaban hacer simultáneamente una llamada de seguimiento.
* Se ha agregado una marca de hora a las variables que se usan con las llamadas de seguimiento light (trackLight).

## Versión 2.1.8 {#section_ACC6974CE3F741E58786CA8048F04521}

Fecha de versión: **enero de 2012**

* Ha aumentado significativamente el rendimiento del proceso de seguimiento.
* Se ha trasladado el almacenamiento de visitas sin conexión a otra ubicación que no se sincroniza con iCloud para ajustarse a las prácticas recomendadas de iCloud.
* Se ha actualizado la biblioteca para incluir el formato "fat binary" de Apple y que no sea necesario incluir la biblioteca específica para la arquitectura de su compilación.

## Versión 2.1.6 {#section_63B4967C537847C28D33EBB92CC15695}

Fecha de versión: **noviembre de 2011**

* Added support for [!DNL iOS] 5.
* [!DNL AppMeasurement]Se ha actualizado para para que el valor UDID obsoleto no se siga usando como valor predeterminado para visitorID. [!DNL iOS] Si establece un visitorID personalizado en su aplicación (por ejemplo, `s.visitorID = @12345`), no le afectará este cambio. Si no establece un visitorID personalizado, en lugar de usar el UDID como valor para visitorID, se genera un visitorID al azar en la ejecución inicial y, a continuación, se almacena en una clave predeterminada de usuario. [!DNL AppMeasurement] A partir de ese momento, esta clave se utiliza. Esta clave también se guarda y se restaura durante el proceso de copia de seguridad de la aplicación estándar.

* Updated calls from the [!DNL iOS] Best Practices plug-in that are not associated with a page view to send hits using trackLink. Esto ayuda a evitar que dichas visitas graben las vistas de página con el nombre predeterminado "nombre de aplicación/versión".

## Versión 2.1.3 {#section_E39666D780554B7398900C39C285CDB8}

Fecha de versión: **octubre de 2011**

* Tratamiento delegado mejorado. This fixes an issue that caused the [!DNL iOS] Best Practices Plug-in to crash when bringing the application out of the background.

## Versión 2.1.2 {#section_21014073AF804EFC8231047D8847485C}

Fecha de versión: **septiembre de 2011**

* Se ha actualizado el encabezamiento para habilitar el uso de prop y eVar 51-75.

## Versión 2.1.1 {#section_8FB3D7C77C884E2AB982103BF7E3312A}

Fecha de versión: **agosto de 2011**

* Capacidad de buscar grupos de informes y métricas al ejecutar un informe.
* Compatibilidad para datos de contexto que transmite reglas de procesamiento de parte del servidor (solo versión 15).
* Compatibilidad para llamadas al servidor livianas (actualmente en modo beta).


---
description: Recopilación de notas de versiones para la biblioteca móvil de Android.
seo-description: Recopilación de notas de versiones para la biblioteca móvil de Android.
seo-title: Android
solution: Analytics,Experience Cloud
subtopic: Notas de la versión
title: Android
topic: Desarrollador e implementación
uuid: 32232d28-3459-4f78-bb00-ca3163c63461
translation-type: tm+mt
source-git-commit: 0dbc8ac9b416ce50f197a884bb71c6cd389cd0bb

---


# Android{#android}

Recopilación de notas de versiones para la biblioteca móvil de Android.

>[!NOTE]
>
>Para encontrar la versión actual de la biblioteca, active el registro de depuración.

Las descargas de las bibliotecas móviles están disponibles en [GitHub](https://github.com/Adobe-Marketing-Cloud/mobile-services) y en [Developer Connection](https://marketing.adobe.com/developer/gallery/app-measurement-for-android-1).

## Versión 4.13.4 {#section_E4743079D8E64B9C890180A025C94B44}

The [!DNL Android] SDK version 4.13.4 (Feb 16, 2017) includes the following changes:

<table frame="all" colsep="1" rowsep="1" id="table_C0197701CB9B45E596818AF0BE5AC4F2"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> Función </th> 
   <th colname="2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p> Mensajería en la aplicación </p> </td> 
   <td colname="2"> <p> Se ha corregido un error que impedía utilizar la versión adecuada de la aplicación al determinar una audiencia. Este problema se producía cuando un usuario actualizaba la versión de la aplicación sin haber lanzado un ciclo de vida nuevo. </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Ciclo de vida </p> </td> 
   <td colname="2"> <p> Se ha corregido un error que podía impedir que se informara correctamente de la actualización de la versión de la aplicación. </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Adquisición </p> </td> 
   <td colname="2"> <p> Se ha corregido un error que causaba que los vínculos profundos diferidos no se activaran en el primer lanzamiento. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Versión 4.13.3 {#section_1C235192E9FB46E2A651017C1CF24A7F}

The [!DNL Android] SDK version 4.13.3 (Jan 19, 2017) includes the following changes:

<table frame="all" colsep="1" rowsep="1" id="table_5E744C8C9D064E999EB5055A8E3A99C5"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> Función </th> 
   <th colname="2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p> Mensajería en la aplicación </p> </td> 
   <td colname="2"> <p> Se ha corregido un problema que impedía la visualización de mensajes de alerta sin botón de pulsación. </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p><span class="keyword"> Analytics</span> </p> </td> 
   <td colname="2"> <p> Se ha mejorado el manejo de acceso de solo lectura a las bases de datos. </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Vínculos universales </p> </td> 
   <td colname="2"> <p> Se ha corregido un error que ocasionaba la activación de vínculos profundos diferidos adjuntados a datos de adquisición en ejecuciones sucesivas. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Versión 4.13.2 {#section_CEA2FF01EA414A32A8D164D981FBE71F}

The [!DNL Android] SDK version 4.13.2 (Nov 10, 2016) includes the following changes:

<table frame="all" colsep="1" rowsep="1" id="table_812CAB7DDC364DAABB7CDEDE55532E39"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> Función </th> 
   <th colname="2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p> Servicio de ID de visitante </p> </td> 
   <td colname="2"> <p>Added timestamp and Experience Cloud Organization ID to <code> adobe_mc</code> parameter. </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p> Enlaces profundos </p> </td> 
   <td colname="2"> <p>Ahora, al llamar a <code>trackAdobeDeepLink</code>, las variables con los prefijos “<code>adb</code>” y “<code>ctx</code>” se gestionan correctamente. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Versión 4.13.1 {#section_647C43BA95A3485381AC2E8DEAA6D2E4}

The [!DNL Android] SDK version 4.13.1 (Oct 20, 2016) includes the following changes:

<table frame="all" colsep="1" rowsep="1" id="table_1D1AFD90F8BB4F59869FD417ED9C45AB"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> Función </th> 
   <th colname="2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Adquisición </p> </td> 
   <td colname="2"> El SDK ahora admite que datos de adquisición personalizados se devuelvan adecuadamente por invocaciones de <code>AdobeDataCallback</code>. </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Adquisición </p> </td> 
   <td colname="2"> El SDK ahora almacena variables de Google Play Referrer y variables personalizadas, y las devuelve adecuadamente en invocaciones de <code>AdobeDataCallback</code>. </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Target </p> </td> 
   <td colname="2"> Los parámetros del servicio de ID de visitante ahora se pasan en solicitudes de <span class="keyword">Target</span> a través de <code>mboxParams</code>. </td> 
  </tr> 
 </tbody> 
</table>

**Correcciones de errores**

* Se ha corregido un problema en el que, en ocasiones, las solicitudes de datos al teléfono se agotaban.

## Versión 4.13.0 {#section_03370D8F93AE4B7A81C4B03910086556}

The [!DNL Android] SDK version 4.13.0 (Sept 15, 2016) includes the following changes:

<table frame="all" colsep="1" rowsep="1" id="table_AACF8B9BE89A4057B0396F487F82CF99"> 
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
  <tr rowsep="1"> 
   <td colname="1"> <p>Seguimiento de enlaces profundos </p> </td> 
   <td colname="2"> <p>Nueva función: se ha añadido la opción de habilitar el seguimiento de enlaces profundos diferidos de terceros. </p> <p> 
     <ul id="ul_DA54F09098A546B6A320E6B9F2937DAD"> 
      <li id="li_B483AEBE02F34E21B2CC731FC77448E8"><code> processAdobeDeepLink</code> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Versión 4.12.0 {#section_3FBC1C24267141C08A60E288662160D8}

The [!DNL Android] SDK version 4.12.0 (Aug 18, 2016) includes the following changes:

<table frame="all" colsep="1" rowsep="1" id="table_3BDD15254859475CBE5E27870619FF3A"> 
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
 </tbody> 
</table>

## Versión 4.11.0 {#section_34B295F3697F4AD6B6A6B8DD70AD1ECA}

The [!DNL Android] SDK version 4.11.0 (June 22, 2016) includes the following changes:

<table frame="all" colsep="1" rowsep="1" id="table_C3DC3890E81744828DE8946AE8067E1A"> 
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
     <ul id="ul_D0594A9ABFD8448186DED87599A0E50E"> 
      <li id="li_A4B0ECDF200C438BB1AB24D613453A68"><code> loadRequest</code> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Versión 4.10.0 {#section_262928ABA971490EA6B8E277E17BDD89}

The [!DNL Android] SDK version 4.10.0 (May 20, 2016) includes the following changes:

<table frame="all" colsep="1" rowsep="1" id="table_E6B19BD9903A41D9AAF0035CD66756B5"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> Función </th> 
   <th colname="2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> Métodos de Target </td> 
   <td colname="2"> <p>Se agregaron sintaxis y ejemplo nuevos para el método <code>loadRequest</code>. </p> <p>Se agregaron los siguientes métodos de <span class="keyword">Target</span> nuevos: </p> <p> 
     <ul id="ul_B32C3B3931764F21948E36384B775642"> 
      <li id="li_3421E7F78F3A4DDA8FF004903FC8C75E">setThirdPartyID </li> 
      <li id="li_0836075699C5480EB3D6B742FCF6D508">getThirdPartyID </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Versión 4.9.0 {#section_7393D3A5EA61431D9E7C07ECE176D17C}

The [!DNL Android] SDK version 4.9.0 (May 5, 2016) includes the following changes:

<table frame="all" colsep="1" rowsep="1" id="table_7D893A6E12554E9CA9AF2B03DA4C1A4B"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> Función </th> 
   <th colname="2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> Cancelación y configuración de privacidad </td> 
   <td colname="2"> <p>Puede implementar enlaces profundos en sus aplicaciones para llevar a los usuarios a destinos de aplicación o de vínculo web. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Versión 4.8.3 {#section_9BB3DFBECC434AC6B3D7C18AA9BC895C}

The [!DNL Android] SDK version 4.8.3 (February 18, 2016) includes the following changes:

<table frame="all" colsep="1" rowsep="1" id="table_6DE145BC30154B9FADCE584A9737018D"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> Función </th> 
   <th colname="2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> Cancelación y configuración de privacidad </td> 
   <td colname="2"> <p>Starting with <span class="keyword"> Android</span> SDK 4.8.3, privacy settings set via the <code> setPrivacyStatus</code> method affect activity from <span class="keyword"> Analytics</span>, <span class="keyword"> Target</span> , and <span class="keyword"> Audience Manager</span>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Versión 4.8.0 {#section_18FA091344644B43AA0E226241FF90DC}

The [!DNL Android] SDK version 4.8.0 (November 2, 2015) includes the following changes:

<table frame="all" colsep="1" rowsep="1" id="table_C47B9AEB2BB649CFA1D5CF04093B497B"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> Función </th> 
   <th colname="2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> Nuevos métodos del servicio de ID de visitante de Experience Cloud </td> 
   <td colname="2"> <p>Se agregaron los siguientes métodos: </p> 
    <ul id="ul_6B85F8A4826642BEB373225CA760D799"> 
     <li id="li_72B94B8CECB94229827BFCB06671DFC9"><code> syncIdentifer</code> </li> 
     <li id="li_CD0C6B6CEA064FDD8B109E01AEC63F5C"><code> syncIdentifiers</code> </li> 
     <li id="li_620A2D94F97A4451919F0867CA82B25D"><code> getIdentifiers</code> </li> 
    </ul> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> Nueva variable de configuración ADBMobile JSON </td> 
   <td colname="2"> <p>Se agregó la variable siguiente: </p> 
    <ul id="ul_7FF76521C59343A4ABC9573C3CD5DC38"> 
     <li id="li_1381E3EF082B4D7DBD131D8EC62F94D2"><code> analyticsForwardingEnabled</code> </li> 
    </ul> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"><span class="keyword"> Métodos del plugin PhoneGap</span> </td> 
   <td colname="2"> <p>Se agregaron los siguientes métodos nuevos </p> <p><b>Métodos de configuración</b> </p> <p> 
     <ul id="ul_98C5E7B5C79446EEA00F0E7CBC213301"> 
      <li id="li_B403C06E57A0450CBB4ABAD45170C681">setPushIdentifier </li> 
      <li id="li_6D76C40601544D4FA13FD44F390C83CE">setAdvertisingIndentifier </li> 
      <li id="li_7D03005DBD9E4AC7BB78BA162CDC8153">keepLifecycleSessionAlive </li> 
      <li id="li_3DDE07508B764E679AF2ACECC4D935CB">trackingSendQueuedHits </li> 
     </ul> </p> <p><b>Métodos de Target</b> </p> <p> 
     <ul id="ul_9B6002F5642B4D888FBD0A8D44EF32DB"> 
      <li id="li_5C1C9EA770E048E48723528F346712B4">targetClearCookies </li> 
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
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Versión 4.6.1 {#section_98CC97CF0F0C48F7855130044386845A}

The [!DNL Android] SDK version 4.6.1 (September 24, 2015) includes the following changes:

<table frame="all" colsep="1" rowsep="1" id="table_80693083398F472F8A4E7861606E602D"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> Función </th> 
   <th colname="2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p><span class="keyword"> Android SDK versión 4.6.1</span> </p> </td> 
   <td colname="2"> <p>SDK 4.6.0 or earlier supports <span class="keyword"> Android</span> 2.2(API 8) - <span class="keyword"> Android</span> 5.1.1 (API 22) </p> <p>SDK 4.6.1 or later supports <span class="keyword"> Android</span> 2.3(API 9) or later </p> </td> 
  </tr> 
 </tbody> 
</table>

## Versión 4.6 {#section_ADF6F871CF3C4E2381464D62DA6E1EB1}

The [!DNL Android] SDK version 4.6 (September 17, 2015) includes the following changes:

<table frame="all" colsep="1" rowsep="1" id="table_35D0692698EF49AE8204F2AEB57CABD7"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> Función </th> 
   <th colname="2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Push Messaging to <span class="keyword"> Analytics</span> Segments </p> </td> 
   <td colname="2"> <p>El SDK de <span class="keyword">Adobe Mobile Services</span> y <span class="keyword">Adobe Mobile</span> permite enviar mensajes push a segmentos de <span class="keyword">Analytics</span>. También permite conocer fácilmente qué usuarios han abierto la aplicación como resultado de la lectura del mensaje push. </p> </td> 
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
     <ul id="ul_84AD959FC65C445BB119F69657AB4AF8"> 
      <li id="li_418FD9EE570F491F9704F72AC70EEE8D"><code> setPushIdentifier</code> </li> 
      <li id="li_B350606A504449E5AAE208B1E590E2CA"> <code> submitAdvertisingIdentifierTask</code> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Versión 4.5 {#section_6E7614D4AEA24B7E81C4FC094882F062}

The [!DNL Android] SDK version 4.5 includes the following changes:

<table frame="all" colsep="1" rowsep="1" id="table_BF98A1E904EB4314828AC58A2A6E7016"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> Función </th> 
   <th colname="2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p><span class="keyword"> Extensión de Android Wearable</span> </p> </td> 
   <td colname="2"> <p>Starting in <span class="keyword"> Android</span> SDK version 4.5, a new <span class="keyword"> Android</span> extension lets you collect data from your <span class="keyword"> Android</span> Wearable app. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Versión 4.4 {#section_8D7FC183081E4BCFA8ADC33FB55E057C}

The [!DNL Android] SDK version 4.4 includes the following changes:

<table frame="all" colsep="1" rowsep="1" id="table_E8628F3806E24A0FB7157847D97C7B7A"> 
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

## Versión 4.3 {#section_789F3DA3DD3146CAA126B303F62D1A1A}

Fecha de versión: **24 de noviembre de 2014**

* Nuevo: integración con Adobe Experience Cloud ID
* Registros de depuración mejorados para una mayor claridad
* Se ha resuelto un posible bloqueo cuando se buscaban mensajes en la aplicación

## Versión 4.2 {#section_EDF95BA0301C4B54AAE839768917D439}

Fecha de versión: **16 de octubre de 2014**

* Nuevo - Capacidades de mensajería en la aplicación.
* Nuevo - Ahora se puede especificar el archivo de configuración durante el inicio de la aplicación.
* Nuevo - Ahora, los puntos de interés se pueden actualizar automáticamente sin necesidad de un nuevo archivo de configuración.
* New - [!DNL Analytics] calls are now sent as HTTP POST requests.
* Se ha resuelto un problema que podía hacer que no se realizara un seguimiento del bloqueo de la aplicación en determinadas situaciones.
* Se han eliminado los mensajes de registro y se han agregado más detalles a los registros cuando debugLogging está habilitado.
* Múltiples mejoras en rendimiento y estabilidad.

## Versión 4.1.7 {#section_DD98F9A4F00A457AA79D223CB1113A06}

Fecha de versión: **4 de agosto de 2014**

* Se ha resuelto un error que podía causar que las visitas del ciclo de vida no se enviaran cuando el tiempo de espera del referente era &gt;= 5 segundos y el seguimiento sin conexión estaba deshabilitado.

## Versión 4.1.6 {#section_B665DF1A4FB249539D73569B52FA8786}

Fecha de versión: **17 de julio de 2014**

* Se han agregado protecciones a excepciones que se producían si la base de datos resultaba dañada o no se podía crear.
* Se han agregado protecciones a problemas que se podían producir cuando la configuración no se podía cargar (generalmente debido a un contexto nulo).
* Se han agregado protecciones a excepciones que se podían producir cuando se actualizaban los datos de contexto de una acción temporizada.

## Versión 4.1.1 {#section_E5EFA05CEE9D486BA6B5C12B1102C117}

Fecha de versión: **23 de abril de 2014**

* Se ha solucionado un posible problema que se podía producir si se habilitaba el seguimiento del referente y se realizaba una llamada de seguimiento anterior al ciclo de vida.

## Versión 4.1.0 {#section_266B62F5B6A44F5F8E6AB8ED1870C4A3}

Fecha de versión: **17 de abril de 2014**

* Nuevo - Seguimiento de las señalizaciones por Bluetooth.
* Nuevo - Aplicaciones con la marca de hora habilitada, las visitas de bloqueo retrasan su fecha con respecto a la sesión correcta.
* Nuevo - Aplicaciones con la marca de hora habilitada, la sesión anterior se envía en una visita en la que se retrasa la fecha con respecto a la sesión correcta. (deja de ser la sesión anterior).
* Nuevo - Lotes de visitas.
* Se ha corregido el seguimiento del referente de Google Play con un tiempo de espera configurable para permitir datos del referente de Google con retraso.
* Se han resuelto advertencias de StrictMode que podían producirse en distintas situaciones.
* Se ha resuelto un problema muy infrecuente que podía bloquear la biblioteca si se realizaba una llamada a determinados métodos con un orden concreto.

## Versión 4.0.4 {#section_DCFAC758872D42F0BF0CCFCDDEA05E41}

Fecha de versión: **24 de febrero de 2014**

* Se ha resuelto un problema que podía hacer que se reprodujera contenido multimedia de forma ampliada si se llamaba a la detención y cierre posterior sin llamadas intermedias.
* Se ha resuelto un problema en el que se enviaba una visita de cierre multimedia si este contenido no se reproducía en ningún momento.

## Versión 4.0.3 {#section_FCC3D7D22EBF4A2FA949A4E88AD89F5C}

Fecha de versión: **20 de febrero de 2014**

* Added safety to network code to prevent crash caused by [!DNL Android] bug: https://code.google.com/p/android/issues/detail?id=54072

## Versión 4.0.2 {#section_5A7F4D5D9CBD4B79B3B590A2C3F4D0F9}

Fecha de publicación: **30 de enero de 2014**

* Se ha resuelto un problema que hacía que se enviaran varias visitas cuando la base de datos resultaba dañada.
* Se ha resuelto un problema que producía promedios de larga duración de sesión si un dispositivo tenía una configuración de tiempo incorrecta.

## Versión 3.2.5 {#section_A6E60DB42241481DA62F660344128F53}

Fecha de versión: **30 de enero de 2014**

* Se han agregado protecciones contra bases de datos dañadas que hacían que las visitas se repitieran.
* Se ha agregado un límite de duración máxima de la sesión para evitar sesiones demasiado largas cuando las horas del dispositivo son incorrectas.

## Versión 4.0.1 {#section_5F58DBABDAA049FE9070E46989B2E9A9}

Fecha de versión: **14 de noviembre de 2013**

* Se ha resuelto el formato incorrecto de los datos de trackLocation en determinadas configuraciones regionales.

## Versión 4.0.0 {#section_79DCFAAF1DCB404898E3BE389AC835A6}

Fecha de versión: **27 de septiembre de 2013**

[!DNL Android] SDK 4.x para soluciones de Experience Cloud ya está disponible con las siguientes nuevas funciones:

* Mejoras significativas en rendimiento. Todo el procesamiento se realiza en subprocesos en segundo plano, el SDK tiene protección completa frente a los subprocesos.
* Localización geográfica y puntos de interés
* Valor de duración
* Eventos temporizados
* Administración de inclusiones y exclusiones
* Compatibilidad con Audience Manager
* Lifecycle metrics passed to [!DNL Target] as mbox parameters
* Estandarización en datos de contexto y reglas de procesamiento

## Versión 3.2.3 {#section_E3464DDC3B4844CF9CC5FC3E35C5C785}

Fecha de versión: **23 de septiembre de 2013**

* Se ha corregido un error en Audience Manager que no permitía valores ni claves nulos en el parámetro.

## Versión 3.2.2 {#section_7D631AA2474F4DBAA043703629E3ECC6}

Fecha de versión: **12 de septiembre de 2013**

* Se ha corregido un error donde los eventos multimedia de linkTrackEvents no se agregaban a la solicitud.
* Se ha solucionado una posible excepción relacionada con la modificación de ContextData después de su traslado a una llamada de seguimiento.

## Versión 3.2.1 {#section_D269F9145B2844B6855423A30B125D5C}

Fecha de versión: **16 de agosto de 2013**

* Las conexiones SSL ahora utilizan una validación de host estricta
* Se ha corregido un error en el que las visitas realizaban reintentos rápidamente durante unos pocos segundos cuando la conexión de red se había perdido y offlineTracking se había deshabilitado.

## Versión 3.2 {#section_ABD4D192E3FF4240B1451262EAEE4F17}

Fecha de versión: **6 de agosto de 2013**

* Se ha agregado compatibilidad con Adobe Audience Manager.
* Los datos del ciclo de vida se envían ahora con solicitudes mbox de Target cuando el seguimiento del ciclo de vida está habilitado.
* Se ha resuelto un problema que podía hacer que SQLite forzara el cierre de cursores, lo que producía entradas de registro innecesarias.

## Versión 3.1.0 {#section_836B4F580B1C436FABD524A91857F882}

Fecha de versión: **13 de junio de 2013**

* Se ha actualizado el almacenamiento sin conexión para utilizar SQLite.
* Se ha corregido un error en el que el límite de desconexión podía restablecerse en el valor predeterminado (1000).
* Se ha actualizado startActivity para que acepte un contexto de actividad o aplicación.
* Se ha corregido un error donde, al establecer lifecycleSessionTimeout en 0, se producían eventos de inicio múltiples en la aplicación.

## Versión 3.0.8 {#section_51F50CD81C6A40C8BCF62F6F332A0800}

Fecha de versión: **18 de abril de 2013**

* Se ha solucionado un problema de codificación con algunos caracteres de UTF8.

## Versión 3.0.7 {#section_0F3FEE2886EB4AB7BA288891FF6B6BCD}

Fecha de versión: **18 de abril de 2013**

* Se ha solucionado un problema que, en ocasiones, producía un cálculo incorrecto de la duración de la sesión anterior.
* Los ID de nuevo visitante han dejado de basarse en deviceID o subscriberID.
* Se ha solucionado un posible bloqueo que se producía cuando se codificaban caracteres especiales en variables.

## Versión 3.0.6 {#section_72F3F9CB95BF4076AD882B3270F77B87}

Fecha de versión: **21 de marzo de 2013**

* Se ha solucionado un problema en el que visitorID no se podía leer sin establecerlo antes.
* Se han cambiado las convenciones de la nomenclatura en algunos mensajes para mayor claridad.
* Se ha cambiado la accesibilidad de varias clases de base para evitar confusión.
* Múltiples mejoras de rendimiento

## Versión 3.0.5 {#section_0540FF6477D74D1F8274E9340EDE7E16}

Fecha de versión: **21 de febrero de 2013**

* Ya no es necesario configurar un `offlineThrottleDelay` obsoleto gracias a la optimización de los procesos. La configuración aún existe para preservar la compatibilidad con versiones anteriores, pero ya no tiene ningún efecto.
* Solucionado un posible problema de sincronización en la caché de visitas sin conexión.
* Aclarado un mensaje de advertencia al establecer vars jerárquicos por encima de 5.
* Fixed issue that could cause OSVersion to be misreported on versions of [!DNL Android] &gt; 4.0.
* Múltiples mejoras del rendimiento
* Corregida una posible excepción que podría ser causada por una URL mal formada.

## Versión 3.0.4 {#section_69ADA2ACD9DE436692152C3836B14EEF}

Fecha de versión: **noviembre de 2012**

* Se ha agregado una variable de configuración de `lifecycleSessionTimeout` que le permite especificar el tiempo, en segundos, que debe pasar entre inicios de la aplicación antes de que el inicio se considere una nueva sesión.
* Se ha agregado la capacidad de establecer el valor de tiempo de espera para el cálculo de la duración de la sesión, usando la opción de configuración `lifecycleSessionTimeout`.
* Se han solucionado problemas de seguridad.

## Versión 3.0.3 {#section_F16E1A36AE3F4CBC92E4925D6DCCFADE}

Fecha de versión: **octubre de 2012**

* Se ha agregado compatibilidad con el [seguimiento de campaña de Google Play](https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/android/referrer.html).

## Versión 3.0.2 {#section_CB24859B34804F9391BA1BF8DF29CC86}

Fecha de versión: **septiembre de 2012**

* Se ha resuelto un problema en el que las visitas de cierre a veces causaban una condición de bucle en el control multimedia.

## Versión 3.0.1 {#section_541CE15B340E414AA018A0EFAEE459F0}

Fecha de versión: **agosto de 2012**

* Los parámetros de anulación de contexto ahora se envían como `Hashmap<String, Object>` (anteriormente `Hashmap<String, String>`).

## Versión 3.0 {#section_2955C0AF3A23476B8CF06C469DE3284C}

Fecha de versión: **julio de 2012**

Versión inicial.

## Versión anterior de Android (1.x) {#section_F2CC015616184D55AC6D6529DFC9A18B}

The following release notes apply to the 1.x version of [!DNL AppMeasurement] for [!DNL Android]. Recomendamos a los clientes que actualicen a la versión 3.x lo antes posible.

## Versión 1.2.3 {#section_5189CCE11EEF4350844B1490D0A9F534}

Fecha de versión: **marzo de 2012**

* Solucionado un problema que causaba una excepción en determinadas circunstancias al pasar datos mediante datos de contexto.

## Versión 1.2.2 {#section_C42925D94F3A429EB1299B96A6EEF6DF}

Fecha de versión: **febrero de 2012**

Solucionado un problema que causaba que las llamadas de seguimiento de vínculo codificasen con URL doble los valores pev1 - pev3.

Se ha agregado una marca de hora a las variables que se usan con las llamadas de seguimiento light (trackLight).

## Versión 1.2.1 {#section_21845E8A7D0C48B38CB90F0D4C5696AF}

Fecha de versión: **enero de 2012**

* Added [!DNL Android] 3.x and 4.x compatibility.
* Implemented a UUID for visitor ID on [!DNL Android] devices that do not have SIM cards (For example, Kindle Fire).

## Versión 1.2 {#section_EC83BE1F00BF481EA1C74A63E4B90F65}

Fecha de versión: **junio de 2011**

* Se ha actualizado la biblioteca para usar la ID del dispositivo para el valor ID del visitante de cuando no haya ninguna tarjeta SIM en el dispositivo. De forma predeterminada, la biblioteca usa la ID del suscriptor como ID del visitante que no está presente si no hay insertada ninguna tarjeta SIM.

## Versión 1.1.4 {#section_C602EC5C11594669A8797B736D240D2C}

Fecha de versión: **abril de 2011**

* Compatibilidad para todas las tabletas, incluida la Xoom.
* Capacidad de buscar grupos de informes y métricas al ejecutar un informe.
* Compatibilidad para contextData que transmite reglas de procesamiento de parte del servidor (solo versión 15).
* Compatibilidad para llamadas al servidor livianas (actualmente en modo beta).

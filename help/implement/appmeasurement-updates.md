---
title: Notas de la versión de AppMeasurement para JavaScript
description: Recopilación de notas de versiones de AppMeasurement para JavaScript.
subtopic: Release notes
translation-type: tm+mt
source-git-commit: 763c1b7405c1a1b3d6dbd685ce796911dd4ce78b
workflow-type: tm+mt
source-wordcount: '2123'
ht-degree: 100%

---


# Notas de la versión de AppMeasurement para JavaScript

Recopilación de notas de versiones de [!DNL AppMeasurement] para JavaScript.

<!-- https://wiki.corp.adobe.com/display/omtrcache/AppMeasurement+Change+Log -->

Puede descargar la versión más reciente de AppMeasurement en el [Administrador de códigos](/help/admin/admin/code-manager-admin.md).

## Versión 2.21.0

Fecha de versión: **24 de junio de 2020**

* Se corrigió un problema en el cual el filtro linkExclusions de Activity Map no siempre se aplicaba a Firefox.

## Versión 2.20.0

Fecha de versión: **5 de marzo de 2020**

* Se ha corregido un problema relacionado con la seguridad al actualizar la detección de Internet Explorer para suprimir la advertencia JSLint.

## Versión 2.19.0

Fecha de versión: **21 de febrero de 2020**

* Módulo de Gestión de público actualizado a DIL 9.4 (AN-209341)

## Versión 2.18.0

Fecha de versión: **13 de febrero de 2020**

* AppMeasurement ahora puede obligar a las cookies a incluir el atributo Secure configurando la variable [`writeSecureCookies`](vars/config-vars/writesecurecookies.md). El requisito de esta variable es que todo el sitio web del cliente se ofrezca de forma segura (HTTPS). (AN-204604)

## Versión 2.17.0

Fecha de lanzamiento: **23 de agosto de 2019**

* Se ha agregado compatibilidad con la reordenación de las cadenas de consulta Baidu. (AN-182483)
* Se ha corregido un problema que indicaba valores de visitantes antiguos en las visitas que se ponían en cola mientras se esperaba la inclusión. (AN-184391)

## Versión 2.16.0

Fecha de versión: **15 de agosto de 2019**

* Se ha implementado compatibilidad con `sendBeacon` en [!UICONTROL AppMeasurement] para vínculos de salida. Aunque la página no se cargue, si una visita utiliza `sendBeacon`, la solicitud se terminará de completar. Esto resulta muy útil para los vínculos de salida porque es más probable que la visita llegue a los servidores de recopilación de datos. (AN-175142)
* Los valores ECID/fid ahora se almacenan en la caché en la primera visita, aunque cambie la configuración de OptIn. (AN-175142)
* Módulo de Gestión de público actualizado a DIL 9.3. (AN-182704)
* Conmutador expuesto en `s.ActivityMap.trackScrollReach` para activar o desactivar el seguimiento de alcance de desplazamiento. (AN-182754)
* AppMeasurement actualizado para utilizar el servicio de ID de visitante 4.4.0. (AN-182912)

## Versión 2.15.0

Fecha de publicación:**15 de julio de 2019**

* Se ha agregado el seguimiento de alcance de desplazamiento de ActivityMap a la extensión Activity Map (AN -172949)
* Se agregó DIL 9.2 a AppMeasurement (AN-182472)

## Versión 2.14.0

Fecha de versión: **21 de mayo de 2019**

* Se han corregido los errores relacionados con la administración del estado de los parámetros del rastreador cuando hay varias visitas pendientes. (AN-176931, AN-176629, DTM-12758)
* AppMeasurement actualizado para incluir Visitor.js 4.3.0 (AN-180049)

## Versión 2.13.0

Fecha de versión: **10 de abril de 2019**

* Corrección de varios problemas detectados con clearVars. El problema se produce cuando las visitas se envían antes de que el rastreador esté listo. Cuando el rastreador está listo, la biblioteca puede establecer variables que ya se han borrado o cambiado. (AN-176931, AN-176629, DTM-12758).

## Versión 2.12.0

Fecha de versión: **22 de febrero de 2019**

* Módulo de Gestión de público actualizado a DIL 9.1 (AN-175255)
* Política de seguridad GTM que no permite el módulo de Activity Map. (AN-174679)
* Mejora de AppMeasurement para aceptar la exclusión cuando el servicio de Experience Cloud ID no se aprueba en el proceso de inclusión. (AN-175259)

## Versión 2.11.0

Fecha de versión: **11 de febrero de 2019**

* Se ha agregado compatibilidad con la nueva funcionalidad Servicios de inclusión de Adobe en AppMeasurement. (AN-163546)
* Se ha agregado compatibilidad con el almacenamiento de datos de seguimiento de vínculos en el almacenamiento de sesión. (AN-162272)
* Se ha agregado compatibilidad con el tipo de flujo de medios para Audio Analytics. (AN-173265)

## Versión 2.10.0

Fecha de versión: **20 de septiembre de 2018**

Esta versión garantiza el envío correcto de las cookies de la biblioteca de [!DNL AppMeasurement] para todos los tipos de conexión.

* [!DNL AppMeasurement] bloquea las transmisiones de cookies durante POST. (AN-165538)
* Se ha cancelado la compatibilidad con XDomainRequest. (AN-165733)
* Se ha reducido la duración de las cookies predeterminadas de [!DNL AppMeasurement] de cinco a dos años. (AN-158572)
* Eliminación del Módulo multimedia del Administrador de códigos ([!DNL AppMeasurement]) (AN-166590)

## Versión 2.9.0

Fecha de versión: **24 de mayo de 2018**

>[!NOTE]
>
>En el caso de los clientes que utilicen el servicio de [!DNL Experience Cloud] ID, se necesita la API de visitantes 3.0 o una versión posterior. Adobe recomienda actualizar a la última versión de la API de visitantes cada vez que se actualicen las bibliotecas de código asociadas ([!DNL at.js], etc.).[!DNL AppMeasurement.js]

* Se ha actualizado [!DNL AppMeasurement] para utilizar la interfaz de Visitante actualizada para solicitar los ID. (AN-151483)
* Se ha solucionado un problema que causaba que la cookie de seguimiento seguía escribiéndose tras desactivar el seguimiento de enlaces. (AN-156332)
* Se ha solucionado un problema que provocaba los desgloses `registerPreTrackCallback` y `registerPostTrackCallback` de firma de función callback cuando al llamarla varias veces. (AN-158566)

## Versión 2.8.2

Fecha de versión: **12 de abril de 2018**

* Se ha actualizado [!DNL AppMeasurement] para utilizar la interfaz de visitante actualizada para solicitar los ID. (AN-151483)
* La cookie de seguimiento de enlace sigue escribiéndose tras desactivar el seguimiento de enlaces. (AN-156332)
* Se ha reducido la duración de las cookies predeterminadas de [!DNL AppMeasurement] de cinco a dos años. (AN-158572)

## Versión 2.8.1

Fecha de versión: **29 de marzo de 2018**

Nuevo paquete de la API de Visitante 3.1.0 (AN-159524), que incluye las correcciones: (CORE-11390, CORE-10634)

## Versión 2.8.0

Fecha de versión: **15 de marzo de 2018**

Nuevo paquete de la API de Visitante 3.1.0 (AN-159524), que incluye las correcciones: (CORE-11390, CORE-10634)

* Paquete VAPI 3.1 con [!DNL AppMeasurement] 2.8. (AN-158353)
* Refactorización mediante la compilación del punto final de recopilación de datos para facilitar el uso compartido. (AN-156647)
* Adición de métricas de temporización de viajes de ida y vuelta de solicitud a [!DNL AppMeasurement]. (AN-158343)

## Versión 2.7.0

Fecha de la versión: **18 de enero de 2018**

* Abandono del soporte para las versiones 6 a 9 de Internet Explorer
* Inclusión de la API de visitantes 3.0.0
* Inclusión de DIL 7.00 

## Versión 2.6.0

Fecha de la versión: **9 de noviembre de 2017**

Se ha solucionado un problema en el que la biblioteca de [!DNL AppMeasurement] no siempre configuraba la combinación de cuentas correcta cuando se llamaba a s_gl. (AN-152153)

## Versión 2.5.0

Fecha de versión: **21 de septiembre de 2017**

* Inclusión de [!DNL dil.js 6.12] (módulo de [!DNL Audience Manager])
* Inclusión de la API de Visitante 2.5.0.

## Versión 2.4.0

Fecha de lanzamiento: **17 de agosto de 2017**

* Se ha incluido dil.js v6.11
* Se ha incluido la API 2.4.0 de visitante

## Versión 2.3.0

Fecha de la versión: **20 de julio de 2017**

* Se ha solucionado el error en el que `s.Util.getQueryParam` capturaba `#`
* Se ha añadido la versión 6.10 de `dil.js` (AN-145701)

## Versión 2.2.0

Fecha de versión: **8 de junio de 2017**

* Se ha añadido compatibilidad con varios órdenes de instanciación de [!DNL AppMeasurement]. (AN-138237)
* Inclusión de la API de visitante 2.2.0. (AN-144042)

## Versión 2.1.0

Fecha del lanzamiento de la versión: **20 de abril de 2017**

* Se ha incluido la última versión de `dil.js` (AN-140396)
* Se ha agregado compatibilidad para el parámetro `adobe_mc_ref`, que anula al referente de la página. (AN-131920)
* Se ha vuelto a incluir la API 2.1.0 de visitante. (AN-140873)
* Se ha agregado el parámetro `mcorgid`. (AN-139586)
* Se ha agregado el parámetro (customerPerspective). (AN-140897)

## Versión 2.0.0

Fecha de la versión: **9 de marzo de 2017**

* Se ha movido a un nuevo proceso de creación que exige actualizar al número de versión 2.0.0. (AN-137878)
* Se ha movido el tratamiento de mboxMCSDID a la ubicación de la sección correcta, donde se efectúa la llamada de seguimiento. (AN-138483)

## Versión 1.8.0

Fecha de publicación: **19 de enero de 2017**

* Inclusión de la API de visitante 2.0.0
* La función resecuenciada llama y comprueba de modo que SDID se consuma una vez completada la comprobación de anulación. (AN-134364)
* Se agregaron los ganchos `s.registerPreTrackCallback` y `s.registerPostTrackCallback`. (AN-134567)

## Versión 1.7.0

Actualizado: **11 de noviembre de 2016**

* Se ha incluido la API 1.10.1 de visitante.
* Actualización del módulo de [!DNL Audience Manager] con la biblioteca de integración de Demdex (DIL) 6.6. (AN-132065)
* Inclusión de la API de Visitante 1.9.0. (AN-132072)
* Actualización del módulo [!DNL Audience Manager] de [!DNL AppMeasurement] con DIL 6.5 y configuraciones adicionales (AN-129411)
* Inclusión de la API de visitantes 1.8.0 (AN-129887)

## Versión 1.6.4

Actualizado: **18 de agosto de 2016**

* [!DNL AppMeasurement] actualizado que permite leer y escribir cookies AMCV. (AN-127098)
* Inclusión de la API de Visitante 1.7.0.

>[!NOTE]
>
>También puede consultar las notas siguientes de la versión 1.6.3 de [!DNL JavaScript], que incluyen requisitos actualizados para el servicio de Experience Cloud ID.

## Versión 1.6.3

Actualizado: **4 de agosto de 2016**

* Se ha corregido un problema en el que [!DNL AppMeasurement] finalizaba de forma prematura las conexiones de solicitud. (AN-126448)

>[!IMPORTANT]
>
>La versión 1.6.0 del servicio de [!DNL Experience Cloud] ID *requiere* [!DNL AppMeasurement] compatible con la versión 1.6.3 o superiores de [!DNL JavaScript]. Si desea actualizar el servicio de Experience Cloud ID a la versión 1.6.0, compruebe que está utilizando la versión de código 1.6.3 o superior de [!DNL AppMeasurement].

## Versión 1.6.2

Fecha de versión: **21 de julio de 2016**

* Inclusión de la API de visitante 1.6.0.
* Se ha corregido un problema que hacía que [!DNL AppMeasurement] llamara al método ofuscado incorrecto en la API de visitante. (AN-126006)
* Se ha corregido un problema que daba lugar al error de [!DNL JavaScript]: “Attribute only valid on v:image”. (AN-124009)

## Versión 1.6.1

Fecha de versión: **16 de junio de 2016**

* Inclusión de la API de Visitante 1.5.7.
* Se ha solucionado la administración del rastreo de clics de los vínculos en Firefox, que no activaba el evento completo.

## Versión 1.6

Fecha de versión: **21 de abril de 2016**

* El módulo [!DNL AppMeasurement] de Activity Map de se ha integrado en el módulo estándar de [!DNL AppMeasurement], por lo que solo deberá hacer referencia a un archivo [!DNL .js]. Además, el seguimiento de Activity Map está habilitado de forma predeterminada. (AN-112689)
* Se ha solucionado un problema de truncamiento que sucedía al enviar la orden de variables de cadena de consulta en [!DNL AppMeasurement], por lo que *`pageURLRest`* se coloca al final. (AN-114647)

## Versión 1.5.4

Fecha de versión: **17 de marzo de 2016**

* Inclusión de la API de Visitante 1.5.4
* Compatibilidad con la anulación de la suscripción a la API de visitante 1.5.4+

## Versión 1.5.3

Fecha de versión: **21 de enero de 2016**

* Se ha solucionado la administración del módulo [!DNL Audience Manager] cuando se usan POST para las llamadas de seguimiento. (AN-115381)
* Se ha movido el resto de la URL de la página (&quot;-g&quot;) al final de la cadena de solicitud de seguimiento. (AN-114647)

## Versión 1.5.2

Fecha de versión: **5 de noviembre de 2015**

* Inclusión de la API de visitante 1.5.3.
* Se ha solucionado la detección de IE11 para el truncado de la URL 2047 (AN-114914)

## Versión 1.5.1

Fecha de versión: **17 de septiembre de 2015**

* Inclusión de la API de visitante 1.5.2
* Se ha actualizado el módulo [!DNL Audience Manager] para que utilice AAM DIL 6.2 y los ID getCustomer desde VisitorAPI.js y los traslade en AAM o realice la llamada de evento a AAM. (AN-104978)

## Versión 1.5

Fecha de versión: **18 de junio de 2015**

* Compatibilidad con la API de visitante 1.5, que utiliza el método *`getCustomerIDs`* para recopilar ID de cliente y estados autenticados, y envía los ID con solicitudes de recopilación de datos.
* Se ha corregido la creación de iframes de destino duplicados en el módulo **[!UICONTROL AudienceManagement]** (DIL 6.1)
* Se ha solucionado el error conocido descrito en la versión 1.4.5.

## Versión 1.4.5

Fecha de versión: **21 de mayo de 2015**

* A partir de iOS SDK versión 4.5, una nueva extensión de iOS le permite recopilar el uso de los datos de sus aplicaciones de Apple Watch, utilidades de Today, utilidades de edición fotográfica y todas las demás aplicaciones de extensión de iOS. Consulte [Implementación de la extensión de iOS](https://docs.adobe.com/content/help/es-ES/mobile-services/ios/ios-ext/ios-ext.html) en la guía del usuario de Mobile Services.
* A partir de la versión 4.5 del SDK para Android, una nueva extensión de Android le permitirá recopilar datos de su aplicación Android Wearable. Consulte [Android Wearables](https://docs.adobe.com/content/help/es-ES/mobile-services/android/wearables-android/android-wearable.html) en la guía del usuario de Mobile Services.
* Inclusión de la API de visitante 1.4.
* Se ha actualizado el módulo AudienceManagement para que utilice DIL versión 6.0.

>[!NOTE]
>
>**Problema conocido**: En las integraciones del módulo API de visitante/[!DNL AppMeasurement] de [!DNL Audience Manager], hay dos solicitudes de iFrame de publicación de destino realizadas en IE6-9: `//fast.<subdomain>.demdex.net/dest5.html` y `//fast.<subdomain>.demdex.net/dest4.html`. El comportamiento correcto, tal como se ha observado en otros exploradores, es cargar únicamente `//fast.<subdomain>.demdex.net/dest5.html`.

## Versión 1.4.4

Fecha de versión: **16 de abril de 2015**

* Ahora puede incluir variables de datos de contexto personalizado con métricas del ciclo vital.
* Las llamadas `trackBeacon` y `clearCurrentBeacon` ahora están disponibles en PhoneGap.
* Una pequeña corrección para borrar el ID del perfil de la llamada del servidor ligero después de la llamada `trackLight`.

## Versión 1.4.3

Fecha de versión: **19 de febrero de 2015**

* Se ha sistematizado todo el tratamiento de las llamadas de seguimiento demoradas con lo cual se han corregido los problemas con las variables de copia de seguridad durante la demora, por ejemplo, el objeto en el que se ha hecho clic.
* Se ha cambiado la opción a no hacer seguimiento automático del referente tras la primera llamada de seguimiento, de modo que las llamadas segunda, tercera, etc. (por lo general seguimiento de vínculos) no contarán al referente doble si se ha configurado manualmente  *`s.referrer`* se ha establecido manualmente antes de la primera llamada de seguimiento.
* Se ha actualizado el zip de distribución para incluir la API de visitante 1.3.5.

## Versión 1.4.2

Fecha de versión: **15 de enero de 2015**

* Se ha solucionado la administración del procesamiento previo de WebKit para impedir que se haga un seguimiento de las páginas procesadas previamente que no se muestran.
* El zip de distribución se ha actualizado para incluir la API 1.3.4 de visitantes y un módulo **[!UICONTROL AudienceManagement]** actualizado que incluye la versión 5.5 de DIL.

## Versión 1.4.1

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
   >Para que una llamada de [!DNL Analytics] utilice el método POST en lugar del método GET en [!DNL AppMeasurement] (para resolver [URL truncadas en IE](https://helpx.adobe.com/es/analytics/kb/shortening-image-request-urls.html)), debe utilizar la implementación más reciente del servicio de ID de visitante para Experience Cloud.

## Versión 1.4

Fecha de versión: **21 de agosto de 2014**

* Se ha eliminado el seguimiento de los plugins del explorador (parámetro de consulta `p`) porque los plugins ya no se incluyen en los informes en la versión 15.
* Adición del módulo **[!UICONTROL AudienceManagement]** en el zip de descarga.
* Se ha agregado compatibilidad con eVars (76 - 250) y eventos (101-1000) adicionales.

>[!NOTE]
>
>El código H no admite los eventos y eVars adicionales.

## Versión 1.3.2

Fecha de versión: **19 de junio de 2014**

* Tratamiento fijado de marcas listas y de espera para campos de API de visitante como el ID de visitante de [!DNL Analytics] heredado que estaba causando errores.
* Compatibilidad para nuevas funciones en el servicio de ID de visitante 1.3.

## Versión 1.3.1

Fecha de versión: **22 de mayo de 2014**

* La función [!DNL AppMeasurement] para `s_gi` de [!DNL JavaScript] no estaba encontrando correctamente instancias creadas con el código H `s_gi`. Tenga en cuenta que este problema impactó únicamente en algunas implementaciones duales donde [!DNL AppMeasurement] para [!DNL JavaScript] y código H estaban en la misma página con instancias separadas y el grupo de informes estaba usando `s_gi` para encontrar instancias.

## Versión 1.3

Fecha de versión: **17 de abril de 2014**

* Soporte para el [servicio de ID de visitante de Experience Cloud](https://docs.adobe.com/content/help/es-ES/id-service/using/home.html).

## Versión 1.2.4

Fecha de versión: **13 de marzo de 2014**

* Correcciones de errores para vídeo de Heartbeat.

## Versión 1.2.3

Fecha de versión: **20 de febrero de 2014**

* Correcciones de errores para vídeo de Heartbeat.

## Versión 1.2.2

Fecha de versión: **6 de febrero de 2014**

* Se ha solucionado un error de compatibilidad con el módulo DIL de [!DNL Audience Manager]. [!DNL Audience Manager]Los clientes de también deben actualizar a la versión 4.8 del módulo DIL.

## Versión 1.2.1

Fecha de versión: **15 de noviembre de 2013**

* Se han solucionado eventos de página utilizados para la medición de vídeo de Heartbeat.

## Versión 1.2

Fecha de versión: **14 de noviembre de 2013**

* Se ha agregado compatibilidad con la [medición de vídeos de Heartbeat](https://docs.adobe.com/content/help/es-ES/media-analytics/using/media-overview.html).
* `VisitorAPI.js` se ha incluido para admitir el [servicio de ID de visitante](https://docs.adobe.com/content/help/es-ES/id-service/using/home.html).

## Versión 1.1.1

* Se ha impedido que se enviara una llamada de seguimiento de vínculos desde los exploradores Opera en vínculos que empiezan con &quot;opera:&quot; (&quot;opera:&quot; se parece a &quot;about:&quot; y &quot;chrome:&quot; en otros exploradores).
* Se ha agregado `alt=""` en todos los objetos de imagen para cumplir con la Accessible Video and Communications Act (ley estadounidense de accesibilidad para comunicaciones y vídeo).

## Versión 1.1

Fecha de versión: **18 de septiembre de 2013**

* Se ha corregido la posibilidad de colocar el código de página y la biblioteca en la etiqueta `head`.
* Se ha agregado la compatibilidad con el módulo `onLoad` que faltaba.

## Versión 1.0.3

Fecha de versión: **15 de agosto de 2013**

* Se ha añadido la compatibilidad para la implementación a través del administración de etiquetas de Adobe.
* Se ha solucionado el problema que evitaba que las variables de jerarquía se fijaran en el objeto [!DNL AppMeasurement].

## Versión 1.0.2

Fecha de versión: **18 de julio de 2013**

* Ahora el seguimiento automático de vínculos ignora el hash/fragmento. Anteriormente, se seguía automáticamente la siguiente URL porque la `href` entera terminaba en `.pdf`:

   ```js
   <a href="index.htm#anchor.pdf">Test Link</a>
   ```

   Ahora se ignora el hash/fragmento de modo que el vínculo solo se sigue cuando el nombre del archivo termina en una extensión que coincide.

## Versión 1.0.1

Fecha de versión: **23 de mayo de 2013**

Ya tiene disponible en el Administrador de códigos una nueva biblioteca [!DNL AppMeasurement] para [!DNL JavaScript]. Esta biblioteca proporciona la misma funcionalidad básica de [!DNL s_code.js], pero es más rápida y más ligera tanto en sitos móviles como del escritorio.

* De 3 a 7 veces más rápido que el código H.25
* Solo 21 k sin comprimir y 8 k comprimidos con gzip (el código H.25 tiene 33 k sin comprimir y 13 k comprimidos con gzip).
* Compatibilidad nativa para obtener parámetros de consulta, leer y escribir cookies y realizar un seguimiento de vínculos avanzado.
* Pequeño y lo suficientemente rápido para su uso en sitios móviles, así como lo bastante sólido para su uso en el escritorio web completo, lo que le permitirá aprovechar una sola biblioteca en todos los entornos web.

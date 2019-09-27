---
description: 'null'
seo-description: 'null'
seo-title: Windows Silverlight, NET, IIS, XBOX
solution: Analytics
subtopic: Notas de la versión
title: Windows Silverlight, NET, IIS, XBOX
topic: Desarrollador e implementación
uuid: 15c20bca-4886-4d57-9957-fe99743851ea
translation-type: tm+mt
source-git-commit: 0dbc8ac9b416ce50f197a884bb71c6cd389cd0bb

---


# Windows Silverlight, NET, IIS, XBOX{#windows-silverlight-net-iis-xbox}

>[!IMPORTANT]
>
>Estos SDK se han cerrado y Adobe ya no los admite ni distribuye.

>[!NOTE]
>
>Para encontrar la versión actual de la biblioteca, active el registro de depuración.

## Versión 1.4.2 {#section_2B70F52C4D214A43844CCEC6B45037F0}

Fecha de versión: **agosto de 2014**

* Se ha eliminado la compatibilidad con el [!DNL Microsoft Silverlight Analytics Framework]. Adobe is no longer supporting or distributing the [!DNL Microsoft Silverlight Analytics Framework] integration for [!DNL AppMeasurement].

* Cambios internos para admitir próximas funciones.

## Versión 1.4.1 {#section_9134F77804BF472291DA7243FAC89C2B}

Fecha de versión: **marzo de 2013**

* Fixed exception with getting default referrer in [!DNL Silverlight] outside of a browser context and properly exposed SSL property in the [!DNL Microsoft Silverlight Analytics Framework] component.

## Versión 1.4 {#section_2F4ADA4628EC43B480177C3DDB3D1CFA}

Fecha de versión: **febrero de 2013**

* Se ha agregado compatibilidad para enviar direcciones URL superiores a 255 bytes para admitir la expansión del campo de URL de la página en los servidores de recopilación de datos de Adobe. Page URLs longer than 255 bytes are split, with the first 255 bytes appearing in the `g=` parameter, with the remaining bytes appearing later in the query sting in the `-g=` query parameter. Esto ayuda a impedir que las direcciones URL largas prevalgan sobre otros datos en caso de truncamiento del navegador, pero sigue permitiendo capturar las direcciones URL largas. 

* Se ha agregado un nuevo método de identificación de visitantes alternativos. Consulte [Identificación de visitantes únicos](https://marketing.adobe.com/resources/help/en_US/sc/implement/c_identifying_unique_visitors.html).
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

## Versión 1.3.8 {#section_03089199E2DE4199B32F6821DDAED7BD}

Fecha de versión: **septiembre de 2012**

* Se ha solucionado un problema donde puede que el evento completo del vídeo no se envíe al utilizar un método `media.monitor` personalizado que rastrea el evento de cierre multimedia:

   ```
   If(media.event==”CLOSE”) { 
   … 
   } 
   ```

## Versión 1.3.7 {#section_32AA8AE0CED4495496D25BF9246AE8AB}

Fecha de versión: **abril de 2012**

* Se ha agregado compatibilidad con [!DNL XBOX].

## Versión 1.3.6 {#section_9F2738FA31CD48C4877AB92281EC67A9}

Fecha de versión: **febrero de 2012**

* [!DNL iOS] Phone 7: solucionado un problema que causaba que offlineThrottleDelay no se aplicase correctamente.
* Se ha agregado una marca de hora a las variables que se usan con las llamadas de seguimiento light (trackLight).

## Versión 1.3.5 {#section_28BBDE7D187547A4AACCA60E5154DCD2}

Fecha de versión: **enero de 2012**

* Seguimiento de vídeo actualizado con un nuevo método para realizar el seguimiento de visualizaciones completas de vídeo. Consulte [Medición de vídeo en Adobe Analytics](https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/video/index.html).

## Versión 1.3.4 {#section_43788EE6B57E4B2DBEED68BE6954D9CA}

* New support and build for [!DNL iOS] Phone platform including offline tracking.
* Compatibilidad para que el delegado doRequest omita el modo en que se envían las solicitudes para los datos de seguimiento.
* Compatibilidad para contextData que transmite reglas de procesamiento de parte del servidor (solo versión 15).
* Compatibilidad para llamadas al servidor livianas (actualmente en modo beta).
* Compatibilidad para asignar un valor distinto de 1 a un evento de contador en la lista de eventos.
* Compatibilidad para un nuevo método de seguimiento de vídeo usando eVars y eventos de conversión (actualmente en fase beta).


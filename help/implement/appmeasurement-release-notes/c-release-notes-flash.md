---
description: Recopilación de notas de versiones para Flash. Las aplicaciones Flash con ActionScript pueden medirse en el escritorio y en la web.
subtopic: Release notes
title: Flash-Flex
topic: Developer and implementation
uuid: 2ee7fb92-9b62-44d4-bd93-6dff26764b7f
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Flash-Flex{#flash-flex}

Recopilación de notas de versiones para Flash. Las aplicaciones Flash con ActionScript pueden medirse en el escritorio y en la web.

> [!NOTE] Para saber la versión de la biblioteca actual, active los registros de depuración.

<!-- 

https://wiki.corp.adobe.com/pages/viewpage.action?spaceKey=omtrcache&title=AppMeasurement+Change+Log

 -->

## 20 de abril de 2017 {#section_8521EC2B68E24203A0F1B14A9D2652D2}

**Versión 4.0.3**

* Inclusión de la API de Visitante 1.6.1.

## 18 de agosto de 2016 {#section_D72EF20672174249B864997905D7552A}

**Actualización 4.0.2**

Inclusión de la API de visitante 1.6.0.

## 19 de mayo de 2016 {#section_061305CFC1E040E69E3CDF4078C17AE4}

**Actualización 4.0.1**

Inclusión de la API de visitante 1.5.6

## 21 de abril de 2016 {#section_6EFC6DBEB9E1460DB344A8278F9FC696}

Adobe ha lanzado una [actualización de seguridad APSB16-13](https://helpx.adobe.com/security/products/analytics/apsb16-13.html) para [!DNL AppMeasurement] para Flash. Esta actualización resuelve una importante vulnerabilidad de la biblioteca, que solo es relevante cuando `debugTracking` está habilitado y podría forzar que ocurrieran [ataques XSS basados en DOM](https://www.owasp.org/index.php/DOM_Based_XSS).

>[!IMPORTANT]
>
>Este problema afecta a [!DNL AppMeasurement] para Flash únicamente cuando `debugTracking` está habilitado (`debugTracking` se encuentra deshabilitado en la configuración predeterminada). **Si se ve afectado, le recomendamos encarecidamente que deshabilite`debugTracking`inmediatamente.** Esta es una muestra de código:

```
public var s:AppMeasurement; 
s = new AppMeasurement(); 
s.debugTracking = false; // set to false or remove line 
                         // for default "disabled" behavior 
```

Las versiones afectadas son [!DNL AppMeasurement] Para la versión 4.0 y anteriores de Flash en todas las plataformas.

> [!NOTE] Por razones de seguridad, no volveremos a distribuir la versión AS2 de [!DNL AppMeasurement] para Flash. La recopilación de datos de proyectos basados en AS2 seguirá siendo compatible. Sin embargo, es muy recomendable que los clientes actualicen sus implementaciones a AS3 e incorporen las últimas funciones de seguridad de [!DNL AppMeasurement] para Flash.

[!DNL AppMeasurement] para los clientes de Flash afectados por este problema, los proyectos deben volver a crearse con la biblioteca actualizada disponible para su descarga desde la [!DNL Analytics] consola [Más...](https://help.adobe.com/en_US/Flex/4.0/UsingFlashBuilder/WS6f97d7caa66ef6eb1e63e3d11b6c4d0d21-7feb.html#WS6f97d7caa66ef6eb1e63e3d11b6c4d0d21-7f88) (AN-121780)

## 5 de noviembre de 2015 {#section_18C1A1C82EA844E78A1D563E66DE3FCF}

Actualización de la versión 4.0:

* Inclusión de la API de visitante 1.5.3.

## 17 de septiembre de 2015 {#section_319911C0F080452981F8C8BEA2880463}

Actualización de la versión 4.0:

* Inclusión de la API de visitante 1.5.2.

## 20 de agosto de 2015 {#section_1BEA10285E9F4863B89B4B713DBB20DB}

Actualización de la versión 4.0:

* Inclusión de la API de visitante 1.5.1.

## 18 de junio de 2015 {#section_2ACB18A1693244D6A49B53F4E17F0C30}

Actualización de la versión 4.0:

* Inclusión de la API de Visitante 1.5.
* Utilice el método Visitor API 1.5+ getCustomerIDs para recopilar ID de visitante y estado autenticado y enviarlos con las solicitudes de recopilación de datos (AN-102131)

## 21 de mayo de 2015 {#section_F5EFCC451F13499F9AA53326AE5926F1}

Actualización de la versión 3.9.2:

* Inclusión de la API de visitante 1.4

## 19 de febrero de 2015 {#section_95ADF1725CE7415D956944A28182E69B}

Versión 3.9.2:

* Inclusión de la API de Visitante 1.3.5.
* Se ha cambiado la opción a no hacer seguimiento automático del referente tras la primera llamada de seguimiento, de modo que las llamadas segunda, tercera, etc. (por lo general seguimiento de vínculos) no contarán al referente doble si *`s.referrer`* se ha establecido manualmente antes de la primera llamada de seguimiento. (AN-92647)
* Eliminación del seguimiento de vídeo de [!UICONTROL Heartbeat] obsoleto incrustado en el módulo multimedia. El seguimiento de vídeo de [!UICONTROL Hearbeat] admitido se ha trasladado a una biblioteca de vídeos de [!DNL Analytics].

## 18 de septiembre de 2014 {#section_80939868A2284961BF620851B000294F}

Versión 3.9.1:

* Se ha agregado prueba de compatibilidad de cookies a Flash (k = S/N variable consulta-cadena) y pf=1 a consulta-cadena cuando la prueba de compatibilidad de cookies es posible (explorador con acceso a [!DNL JavaScript]).
* Compatibilidad para nuevas funciones en el servicio de ID de visitante 1.3.2.

## 21 de agosto de 2014 {#section_F7CA56E42B6548D3BE5A0D020BCEE97A}

Versión 3.9:

* Se han agregado variables de latitud y longitud.
* Compatibilidad para nuevas funciones en el servicio de ID de visitante 1.3.1.

## Versión 3.8.1 {#section_29A2A0A20D9B43A1B57E5ED299C6EAF3}

Fecha de versión: **19 de junio de 2014**

* Tratamiento fijado de marcas listas y de espera para campos de API de visitante como el ID de visitante de [!DNL Analytics] heredado que estaba causando errores.
* Compatibilidad para nuevas funciones en el servicio de ID de visitante 1.3.

## Versión 3.8 {#section_3F75C4D0C9BE470B95838DDB2CDCA79F}

Fecha de versión: **17 de abril de 2014**

* Support for the [Experience Cloud Visitor ID service](https://marketing.adobe.com/resources/help/en_US/mcvid/).

## Versión 3.7.3 {#section_1159B2AB56F54903A6FBFB7047AEC1C5}

Fecha de versión: **13 de marzo de 2014**

* Varias correcciones de errores del seguimiento de vídeo de [!UICONTROL Heartbeat].

## Versión 3.7.2 {#section_D6DCE5FE846A45F1A2CED237E8AAEFE9}

Fecha de versión: **6 de febrero de 2014**

* Varias correcciones de errores del seguimiento de vídeo de [!UICONTROL Heartbeat].

## Versión 3.7.1 {#section_DC79F108AB5E42189A8EC7D87697AE0B}

Fecha de versión: **14 de noviembre de 2013**

* Varias correcciones de errores del seguimiento de vídeo de [!UICONTROL Heartbeat].

## Versión 3.7 {#section_7239878DCD724FD0B9BC900821A4DA96}

Fecha de versión: **17 de octubre de 2013**

* Compatibilidad con el [seguimiento de vídeo de Heartbeat](https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/hbvideo/).
* VisitorAPI.swc se ha incluido para admitir el [servicio de ID de visitante](https://marketing.adobe.com/resources/help/en_US/sc/implement/visid_service#.html).
* Se ha eliminado la compatibilidad de Flash Player 9 con ActionScript 3. La versión mínima de Flash Player para ActionScript 3 es 10.

## Versión 3.6.2 {#section_57FB21568BDD48F7882F00AD630E6CE8}

Fecha de versión: **18 de septiembre de 2013**

* Cambios internos para admitir una próxima versión beta.

## Versión 3.5.5 {#section_149CAF8AF39741C2B9F6A015F7FB8C61}

Fecha de versión: **15 de agosto de 2013**

* Se ha deshabilitado la creación de nuevas colas de solicitudes fallidas cuando el seguimiento sin conexión está deshabilitado.

## Versión 3.5.4 {#section_3429BD7DE2B64110BEE3A3850E58A0F7}

Fecha de versión: **21 de febrero de 2013**

* Se ha solucionado un problema de codificación/descodificación de URL en ActionScript 2.

## Versión 3.5.3 {#section_5192BC1C8BF547D1A5A92863686601DD}

Fecha de versión: **31 de enero de 2013**

* Se ha agregado compatibilidad para enviar direcciones URL superiores a 255 bytes para admitir la expansión del campo de URL de la página en los servidores de recopilación de datos de Adobe. Las direcciones URL de la página superiores a 255 bytes se han partido. Los primeros 255 bytes aparecen en el parámetro `g=` y los bytes restantes aparecen luego en la cadena de consulta en el parámetro de consulta `-g=`. Esto ayuda a impedir que las direcciones URL largas prevalgan sobre otros datos en caso de truncamiento del navegador, pero sigue permitiendo capturar las direcciones URL largas.

* Se ha agregado un nuevo método de identificación de visitantes alternativos. Consulte [Identificación de visitantes únicos](https://marketing.adobe.com/resources/help/en_US/sc/implement/c_identifying_unique_visitors.html).
* Se ha añadido un nuevo indicador `abort` que se puede configurar dentro de `doPlugins`. Configurar este indicador a verdadero impide que la biblioteca [!DNL AppMeasurement] siga con la llamada de seguimiento. El indicador de anulación se restablece con cada llamada de seguimiento, así que si también se tiene que cancelar una llamada de seguimiento posterior, de nuevo se tendrá que configurar el indicador dentro de `doPlugins`.

   ```js
   s.doPlugins = function(s) { 
        s.campaign = s.getQueryParam("cid"); 
        if ((!s.campaign) && (!s.events)) { 
             s.abort = true; 
        } 
   };
   ```

   Esto permite centralizar la lógica utilizada para identificar la actividad que no se quiere seguir, por ejemplo algunos vínculos personalizados o vínculos externos para mostrar anuncios.

## Versión 3.5.2 {#section_77727E343EC14B869020358183DAB2DB}

Fecha de versión: **8 de noviembre de 2012**

* Actualizaciones internas para la integración de [!DNL Audience Manager].

## Versión 3.5.1 {#section_F6345AC9F4994D6F97BBCF399B02BB21}

Fecha de versión: **22 de octubre de 2012**

* Se han cambiado las compilaciones de ActionScript 3 para que ignoren cualquier configuración de `s.charSet` porque siempre se usa UTF-8

## Versión 3.5 {#section_7DC183DD46CF42FE85F42E7AB8915D99}

Fecha de lanzamiento: **13 de septiembre de 2012**
**Cambio importante en los enlaces de variables**: En la versión 3.5, se agregó una opción para deshabilitar los enlaces de variables para clientes que necesiten iniciar y finalizar valores de cadenas literales con llaves. Los enlaces de variables con llaves se usan principalmente al configurar reproductores de vídeo OSMF con etiquetas XML:

```
<autoTrackMediaName>{media.player.metadata(https://www.corp1.com/,episodeID)}</autoTrackMediaName>
```

Hay disponible un nuevo atributo llamado `autoBind` para anular el comportamiento predeterminado en las etiquetas XML:

```
<autoTrackMediaName autoBind=false>{123}</autoTrackMediaName>
```

Establecer `autoBind` en `false` hace que el valor se considere una cadena literal y no se usan enlaces de variables. Si este atributo no se establece en `false`, el comportamiento de las etiquetas XML permanece igual.

**Impacto en ActionScript Code**

Aunque no se usa a menudo, esta sintaxis también está disponible para enlazar variables de [!DNL AppMeasurement] en su código de ActionScript. Si no sabe si está usando o no enlaces de variables, busque en su código valores de variables [!DNL AppMeasurement] que empiecen y terminen con llaves. Por ejemplo:

```
s.eVar1 = "{source}";
```

Si está usando enlaces de variables, debería cambiar este código para que use el nuevo método `bindVariable`:

```
s.bindVariable("eVar1","source");
```

De forma opcional, en vez de cambiar cada ubicación, puede volver al comportamiento de la versión previa 3.5 estableciendo `autoBindVariablesByValue` en verdadero:

```
s.autoBindVariablesByValue = true;
```

**Correcciones adicionales:**

* Se ha solucionado un problema donde puede que el evento completo del vídeo no se envíe al utilizar un método `media.monitor` personalizado que rastrea el evento de cierre multimedia:

   ```
   If(media.event=="CLOSE") { 
   … 
   } 
   ```

## Versión 3.4.9 {#section_5F2566CF954242D0A7205DA0B257DABA}

Fecha de versión: **19 de julio de 2012**

* Added a master-only meta policy, see [https://www.adobe.com/devnet/flashplayer/articles/fplayer9_security.html](https://www.adobe.com/devnet/flashplayer/articles/fplayer9_security.html).

## Versión 3.4.8 {#section_7501E04F6A854D50BFF0F287607A796F}

Fecha de versión: **21 de junio de 2012**

* Se ha cambiado para usar siempre UTF-8 en composiciones AS3. Esto evita problemas con cadenas para algunos idiomas multibyte.

## Versión 3.4.7 {#section_B26A014D13B14878816472E394FBAAA6}

Fecha de versión: **26 de abril de 2012**

Medición de vídeo: se ha añadido un control de desplazamiento a la finalización incoherente registrada por la API del reproductor Brightcove. Ahora, si el desplazamiento se registra como cero, en la finalización se usa la duración como desplazamiento. De este modo se solucionan los problemas relacionados con el nuevo método de seguimiento de finalizaciones mediante un valor de desplazamiento.

## Versión 3.4.6 {#section_273B76A58745486E9715D9F5C2AEC433}

Fecha de versión: **19 de enero de 2012**

* Seguimiento de vídeo actualizado con un nuevo método para realizar el seguimiento de visualizaciones completas de vídeo.

## Versión 3.4.5 {#section_DEDF0BEF6BF4458CA00896799E5BA67C}

Fecha de versión: **8 de septiembre de 2011**

* Se han habilitado props que contienen un valor cero literal "0". Antiguamente no se enviaban props con valor cero literal.

## Versión 3.4.3 {#section_6C930AA0E95045BCA9AD4096B63657C9}

Fecha de versión: **mayo de 2011**

* En OSMF, se han solucionado problemas al usar complementos proxy para rastrear reproductores de vídeo OSMF. Este arreglo permite rastrear OSMF ProxyElements cuando el elemento sobre el que hacen la función proxy no se está rastreando.
* Se ha solucionado un problema que causaba un error al medir el vídeo en Flash Player 9.0.16.


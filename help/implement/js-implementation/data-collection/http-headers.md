---
description: Los encabezados de solicitud y respuesta HTTP se usan para recopilar datos adicionales a los que recopila AppMeasurement. En esta sección se describen los encabezados utilizados durante la recopilación de datos.
keywords: Implementación de Analytics
seo-description: Los encabezados de solicitud y respuesta HTTP se usan para recopilar datos adicionales a los que recopila AppMeasurement. En esta sección se describen los encabezados utilizados durante la recopilación de datos.
seo-title: Encabezados HTTP de recopilación de datos
solution: Analytics
title: Encabezados HTTP de recopilación de datos
topic: Desarrollador e implementación
uuid: 3325 e 13 c-b 300-46 e 4-a 592-3 a 83 ed 59718 b
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Encabezados HTTP de recopilación de datos

Los encabezados de solicitud y respuesta HTTP se usan para recopilar datos adicionales a los que recopila AppMeasurement. En esta sección se describen los encabezados utilizados durante la recopilación de datos.

## Encabezados de solicitud HTTP {#section_C1DE3416CCC241A898155C915A01A0FC}

<table id="table_84D1F4B54ABE4423A2EBE840C49D3876"> 
 <tbody> 
  <tr> 
   <td> <b>Encabezado</b> </td> 
   <td> <b>Uso</b> </td> 
  </tr> 
  <tr> 
   <td> Cookie </td> 
   <td> <p>Leer cookies anteriormente creadas por nuestros servidores de recopilación de datos. </p> <p> A fecha de 2014, los servidores de Adobe descartarán cualquier cookie que acompañe a una llamada de servidor, excepto aquellas establecidas por Adobe. Consulte <a href="https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/" format="https" scope="external">Cookies utilizadas en Experience Cloud</a> para obtener una lista completa de las cookies de Adobe. </p> </td> 
  </tr> 
  <tr> 
   <td> User-Agent </td> 
   <td> Se usa para detectar el explorador, el sistema operativo y el dispositivo móvil. </td> 
  </tr> 
  <tr> 
   <td> X-Device-User-Agent </td> 
   <td> Se utiliza como alternativa a User-Agent para detectar correctamente el explorador, el sistema operativo y el dispositivo móvil en algunos exploradores como OperaMini. </td> 
  </tr> 
  <tr> 
   <td> X-Original-User-Agent </td> 
   <td> Se utiliza como alternativa a User-Agent para detectar correctamente el explorador, el sistema operativo y el dispositivo móvil en algunos exploradores como OperaMini. </td> 
  </tr> 
  <tr> 
   <td> X-OperaMini-Phone-UA </td> 
   <td> Se utiliza como alternativa a User-Agent para detectar correctamente el explorador, el sistema operativo y el dispositivo móvil en algunos exploradores como OperaMini. </td> 
  </tr> 
  <tr> 
   <td> X-Skyfire-Phone </td> 
   <td> Se utiliza como alternativa a User-Agent para detectar correctamente el explorador, el sistema operativo y el dispositivo móvil en algunos exploradores como OperaMini. </td> 
  </tr> 
  <tr> 
   <td> X-Bolt-Phone-UA </td> 
   <td> Se utiliza como alternativa a User-Agent para detectar correctamente el explorador, el sistema operativo y el dispositivo móvil en algunos exploradores como OperaMini. </td> 
  </tr> 
  <tr> 
   <td> UA-OS </td> 
   <td> Se usa como alternativa para identificar el sistema operativo. </td> 
  </tr> 
  <tr> 
   <td> UA-Pixels </td> 
   <td> Se usa como fuente alternativa de la resolución de la pantalla cliente. </td> 
  </tr> 
  <tr> 
   <td> UA-Color </td> 
   <td> Se usa como fuente alternativa de la profundidad de color de la pantalla cliente. </td> 
  </tr> 
  <tr> 
   <td> X-moz </td> 
   <td> Detecta que la solicitud de recopilación de datos se realizó como parte de una captura previa de una página web. </td> 
  </tr> 
  <tr> 
   <td> X-Purpose </td> 
   <td> Detecta que la solicitud de recopilación de datos se realizó cuando el explorador mostraba una vista previa de una página web. </td> 
  </tr> 
  <tr> 
   <td> Accept </td> 
   <td> Se usa para identificar los formatos de imagen admitidos por el explorador con el fin de saber si es necesario devolver una imagen GIF o WBMP. </td> 
  </tr> 
  <tr> 
   <td> Referrer </td> 
   <td> Se usa como reserva para obtener información sobre la dirección URL desde la que se realizó la solicitud de recopilación de datos si no se pasó en la cadena de consulta o si es diferente del valor en la cadena de consulta. </td> 
  </tr> 
  <tr> 
   <td> X-Forwarded-For </td> 
   <td> Se usa para encontrar la dirección IP correcta del cliente que realizó la solicitud de recopilación de datos. La dirección IP se usa para generar informes de región geográfica o de operador de telefonía móvil, entre otros. </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Las implementaciones que utilizan variables dinámicas tienen la opción de leer en otros encabezados de solicitud HTTP no enumerados anteriormente.

## Encabezados de respuesta HTTP {#section_A9C7035198C84037A21A8033CC408F0E}

| **Encabezado** | **Uso** |
|---|---|
| Access-Control-Allow-Origin | Se usa para permitir solicitudes de recopilación de datos sobre estilos de uso compartido de recursos entre orígenes a nuestros servidores. |
| Expires | Control de caché del explorador. |
| Last-Modified | Control de caché del explorador. |
| Cache-Control | Control de caché del explorador. |
| Pragma | Control de caché del explorador. |
| ETag | Control de caché del explorador. |
| Vary | Control de caché del explorador. |
| P3P | Proporciona la directiva P3P predeterminada o personalizada para la solicitud de recopilación de datos. |
| Status | Contiene el estado "SUCCESS" o "FAILURE" para una solicitud que no es de contenido. Se usa únicamente cuando la solicitud especifica que no se debe devolver ningún contenido. |
| Reason | Contiene el motivo del estado de error de una solicitud que no es de contenido. Se usa únicamente cuando la solicitud especifica que no se debe devolver ningún contenido. |
| Location | Se usa para redirigir al cliente que realiza la recopilación de datos a una dirección URL diferente. Un ejemplo es nuestra negociación de cookies para detectar la posibilidad de configurar la cookie de ID de visitante. |
| Content-Type | Especifica el tipo de contenido que se devuelve al cliente (GIF, texto, Javascript, etc.). |
| Content-Length | Especifica el tamaño del contenido que se devuelve al cliente. |

>[!NOTE]
>
>Otros encabezados HTTP se pueden configurar en la respuesta para supervisar el estado interno. Algunos de estos encabezados podrían devolverse al explorador, pero no es necesario que los reciban.

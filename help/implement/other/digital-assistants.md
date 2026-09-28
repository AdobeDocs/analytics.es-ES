---
title: Implementar Analytics para asistentes digitales
description: Implemente Adobe Analytics en asistentes digitales, como Amazon Alexa o Google Home.
feature: Implementation Basics
exl-id: ebe29bc7-db34-4526-a3a5-43ed8704cfe9
role: Developer
TQID: 'https://experienceleague.adobe.com/QKlchx0r3ZDourRQaQAJaMn9Fh3bXiEWHprCkLVALsk'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
  - id: a421fb65-2c82-457a-921c-28c46b697a39
    internal-label: Analytics basics
subfeature_v2:
  - id: e992d880-33bc-4949-a648-aa7d410276cd
    internal-label: Validation
  - id: c24fe15a-643a-47bd-8278-5e027df49785
    internal-label: Implementation basics
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
    internal-label: Optimization
  - id: eb30f47f-d87a-400f-8f78-63ce7979ff56
    internal-label: Machine learning
source-git-commit: 9a50beeb0aa51cf9f4baf212566947c14029ce8e
workflow-type: tm+mt
source-wordcount: '1252'
ht-degree: 11%
---
# Implementar Analytics para asistentes digitales

Con los avances en computación en la nube, aprendizaje automático y procesamiento de lenguajes naturales, los asistentes digitales son parte de la vida cotidiana. Los consumidores hablan con sus dispositivos y esperan respuestas similares a las humanas, y las marcas pueden presentar sus servicios a través de estas mismas experiencias. Por ejemplo, los consumidores pueden preguntar:

* “Alexa, pregunta al coche cuándo hay que cambiarle el aceite”.
* &quot;Oye Google, ¿cuál es el saldo de mi cuenta corriente?&quot;
* “Siri, envía a John 20 dólares desde mi aplicación de banca por la cena de anoche”.

Esta página proporciona información general sobre cómo utilizar Adobe Analytics para medir y optimizar este tipo de experiencias.

## Información general de la arquitectura de la experiencia digital

![Flujo de trabajo del asistente digital](assets/Digital-Assitants.png)

La mayoría de los asistentes digitales siguen una arquitectura de alto nivel similar:

1. **Dispositivo**: Un dispositivo (como un altavoz inteligente o un teléfono) con un micrófono que permite al usuario hacer una pregunta.
1. **Asistente digital**: El servicio que alimenta el asistente. Convierte el habla en intenciones comprensibles para el equipo y analiza los detalles de la solicitud. Una vez entendida la intención, el asistente la transmite junto con los detalles a la aplicación que se encarga de la solicitud.
1. **&quot;Aplicación&quot;**: Una aplicación en el teléfono o una aplicación de voz que responde a la solicitud. Responde al asistente digital, que luego responde al usuario.

## Envío de datos a Adobe Analytics

Una aplicación de asistente digital se suele ejecutar en un servidor o plataforma que no tiene ninguna biblioteca del lado del cliente de Adobe (AppMeasurement o Web SDK). Envíe visitas del lado del servidor **mediante la API de inserción de datos [2}**. ](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/)Cada interacción que desea medir se convierte en una solicitud de API de inserción de datos cuya cadena de consulta (o cuerpo XML) lleva las variables descritas en esta página (generalmente [variables de datos de contexto](/help/implement/vars/page-vars/contextdata.md)) que se asignan a eVars, props y eventos con [reglas de procesamiento](/help/admin/tools/manage-rs/edit-settings/general/processing-rules/pr-overview.md).

Esta página se centra en *qué* medir y cómo modelarlo en Analytics. Para el extremo, las codificaciones de cadena de consulta y XML, los componentes necesarios y los tipos de respuesta, consulte la [documentación de API de inserción de datos](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/). Cada variable nombrada a continuación se asigna a un parámetro de cadena de consulta y etiqueta XML en la [referencia de variable](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference).

## Dónde se implementa Analytics

Uno de los mejores lugares para implementar Analytics es en la aplicación, que recibe la intención y los detalles del asistente digital y determina cómo responder. Hay dos momentos durante una solicitud que son útiles para enviar datos a Adobe Analytics:

1. Cuando se envía la solicitud a la aplicación.
1. Tras devolverse la respuesta desde la aplicación.

Si le interesa registrar lo sucedido para una futura optimización, envíe la visita una vez devuelta la respuesta; a continuación, tendrá el contexto completo de la solicitud y la forma en que respondió el sistema.

## Qué medir

### Nuevas instalaciones

Para los asistentes que le avisan cuando alguien instala la aptitud (especialmente cuando se trata de autenticación), envíe un evento de instalación configurando la variable de datos de contexto `a.InstallEvent=1`, junto con `a.InstallDate` y el ID de la aplicación (`a.AppID`). Esto no está disponible en todas las plataformas, pero resulta útil para el análisis de retención cuando está presente.

### Múltiples asistentes o aplicaciones

Las organizaciones suelen crear aplicaciones para varias plataformas. Incluya un id. de aplicación en cada solicitud en la variable de datos de contexto `a.AppID`, con el formato `[AppName] [BundleVersion]` (por ejemplo, `Spoofify 1.0`). Agregue una plataforma o variable de datos de contexto del sistema operativo (como `OSType`) para poder distinguir Alexa, el Ayudante de Google y otras plataformas en los informes.

### Identificación de visitantes

Adobe Analytics usa el [servicio de ID de visitante de Adobe](https://experienceleague.adobe.com/es/docs/id-service/using/home) para enlazar las interacciones a lo largo del tiempo con la misma persona. La mayoría de los asistentes digitales devuelven un(a) `userID` que puede usar como identificador único (páselo como anulación de ID de visitante (`vid`). Algunas plataformas devuelven un identificador que supera los 100 caracteres permitidos; en estos casos, se hace un hash con un valor de longitud fija con un algoritmo estándar como MD5 o SHA-1.

El uso del servicio de ID de visitante proporciona el mayor valor al asignar un ECID a varios dispositivos (por ejemplo, web a asistente digital). Si la aplicación es móvil, utilice Experience Platform Mobile SDK y envíe el ID de usuario con el método `setCustomerID`. Si su aplicación es un servicio, utilice el ID de usuario proporcionado por el servicio como ID de visitante y configúrelo también con `setCustomerID`. Para obtener información sobre cómo establecer identificadores en una solicitud del lado del servidor, consulte [Identificación de visitantes mediante la API de inserción de datos](../id/data-insertion.md).

### Sesiones

Como los asistentes digitales son conversacionales, a menudo incluyen el concepto de sesión (intercambio de varias vueltas). Cuando se inicia una nueva sesión, Adobe recomienda dos cosas:

1. **Póngase en contacto con Audience Manager** para obtener los segmentos a los que pertenece el usuario y personalizar la respuesta.
1. **Envíe un evento de inicio** con la primera respuesta configurando la variable de datos de contexto `a.LaunchEvent=1`.

### Intenciones

Cada asistente detecta las intenciones y las pasa a la aplicación. Una intención es una representación sucinta de la solicitud; por ejemplo, &quot;Siri, envía a John 20 dólares desde mi aplicación de banca por la cena de anoche&quot; podría resolver la intención *sendMoney*. Envíe cada intención a una variable de datos de contexto que asigne a una eVar para poder ejecutar informes de rutas de acuerdo con las intenciones. Asegúrese de que la aplicación también administre las solicitudes sin intención; Adobe recomienda enviar `No Intent Specified` en lugar de omitir la variable.

### Parámetros, ranuras y entidades

Además de la intención, los asistentes a menudo proporcionan detalles clave/valor de la solicitud (denominados espacios, entidades o parámetros). Por &quot;Siri, envía a John 20 dólares por la cena de anoche&quot;, los parámetros podrían ser:

* Quién = John
* Cantidad = 20
* Por qué = Cena

Normalmente, hay un conjunto finito de ellos por aplicación. Enviarlos a variables de datos de contexto y asignarlos a una eVar.

### Estados de error

A veces, el asistente pasa entradas que tu aplicación no puede manejar (por ejemplo, &quot;Siri, envía a John 20 bolsas de carbón desde mi aplicación de banca&quot;). Cuando esto ocurra, haga que la aplicación pida aclaraciones y envíe datos que indiquen un estado de error: establezca `a.Error=1` junto con una eVar que especifique el tipo de error. Incluya tanto los errores en los que las entradas no son válidas como los errores en los que la propia aplicación tuvo un problema.

### Capacidades de los dispositivos

Aunque la mayoría de las plataformas no exponen el dispositivo exacto, sí exponen sus capacidades (como audio, pantalla o vídeo), que definen los tipos de contenido que puede utilizar. Cuando mida las capacidades del dispositivo, concatenarlas en orden alfabético con dos puntos al inicio y al final (por ejemplo, `":Audio:Camera:Screen:Video:"`) para que pueda generar segmentos como &quot;todas las visitas con capacidades de `:Audio:`&quot;.

* [Referencia de la interfaz Alexa de Amazon](https://developer.amazon.com/public/solutions/alexa/alexa-skills-kit/docs/alexa-skills-kit-interface-reference)
* [Funciones de superficie del Ayudante de Google](https://developers.google.com/actions/assistant/surface-capabilities)

## Solicitud de ejemplo

La siguiente solicitud GET de la API de inserción de datos registra una intención *SendPayment* para una aplicación bancaria, y establece el ID de la aplicación, un evento de inicio, la intención y los valores de la ranura como datos de contexto:

```text
GET /b/ss/examplersid1,examplersid2/1?vid=[UserID]&c.a.AppID=Penmo%201.0&c.a.LaunchEvent=1&c.Intent=SendPayment&c.Amount=20.00&c.Reason=Dinner&c.ReceivingPerson=John&pageName=SendPayment HTTP/1.1
Host: example.data.adobedc.net
```

Para obtener el formato de solicitud, los extremos y los tipos de respuesta completos, consulte la [documentación de la API de inserción de datos](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/request).

## Ejemplo de modelo de medición

La siguiente tabla muestra cómo se asignan las acciones comunes de una aplicación de música a variables de Analytics. Configúrelas como variables de datos de contexto en cada solicitud de API de inserción de datos y, a continuación, asígnelas a eVars y eventos con reglas de procesamiento.

| Acción de persona | Intención/evento | Datos de contexto para establecer |
| --- | --- | --- |
| Instalación de la aplicación | Se instala | `a.InstallEvent=1`, `a.InstallDate`, `a.AppID`, `OSType` |
| Inicie la aplicación | Launch | `a.LaunchEvent=1`, `a.AppID`, `Intent=Play` |
| Pide cambiar la canción | ChangeSong | `a.AppID`, `Intent=ChangeSong` |
| Reproducir una canción específica | ChangeSong | `a.AppID`, `Intent=ChangeSong`, `SongID` |
| Cambio de la lista de reproducción | ChangePlaylist | `a.AppID`, `Intent=ChangePlaylist`, `Playlist` |
| Encontrar una entrada no válida | (error) | `a.Error=1`, `ErrorName` |

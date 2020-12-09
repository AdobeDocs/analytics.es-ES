---
title: Implementar Analytics para asistentes digitales
description: Implemente Adobe Analytics en asistentes digitales, como Amazon Alexa o Google Home.
translation-type: tm+mt
source-git-commit: 09b453c1b4cd8555c5d1718759003945f5c230c5
workflow-type: tm+mt
source-wordcount: '1266'
ht-degree: 98%

---


# Implementar Analytics para asistentes digitales

Con los recientes avances en computación en la nube, aprendizaje automático y procesamiento de lenguajes naturales, los asistentes digitales se están convirtiendo en parte de la vida cotidiana. Los consumidores están empezando a hablar con sus dispositivos y a esperar que comprendan y respondan de formas parecidas a las humanas. El establecimiento cada vez mayor de estas plataformas permite a las marcas presentar sus servicios a los consumidores de un modo realista y natural. Por ejemplo, un consumidor puede preguntar cosas como:

* “Alexa, pregunta al coche cuándo hay que cambiarle el aceite”.
* “Cortana, ¿qué saldo tengo en la cuenta corriente?”.
* “Siri, envía a John 20 dólares desde mi aplicación de banca por la cena de anoche”.

Esta página describe de forma general el mejor modo de utilizar Adobe Analytics para medir y optimizar este tipo de experiencias.

## Información general de la arquitectura de la experiencia digital

![Flujo de trabajo de Digital Assistant](assets/Digital-Assitants.png)

La mayoría de los asistentes digitales de hoy en día siguen una arquitectura de alto nivel similar:

1. **Dispositivo:** hay un dispositivo (como un Amazon Echo o un teléfono) con un micrófono que permite al usuario hacer una pregunta.
1. **Asistente digital:** el dispositivo interactúa con el servicio que alimenta el asistente digital. Es donde el habla se convierte en intenciones comprensibles para la máquina y donde se analizan los detalles de la solicitud. Una vez entendida la intención del usuario, el asistente digital la transmite junto con los detalles de la solicitud a la aplicación que se encarga de tramitar dicha solicitud.
1. **“Aplicación”:** puede tratarse de una aplicación que hay en el teléfono o de una aplicación de voz. La aplicación es la encargada de responder a la solicitud. Responde al asistente digital, que a su vez responde al usuario.

## Dónde se implementa Analytics

Uno de los mejores lugares para implementar Analytics es en la aplicación. La aplicación recibe la intención y los detalles del asistente digital y, a continuación, la aplicación determina cómo responder.

Hay dos ocasiones durante una solicitud que pueden resultar útiles para enviar datos a Adobe Analytics.

1. Cuando se envía la solicitud a la aplicación.
1. Tras devolverse la respuesta desde la aplicación.

Si simplemente está interesado en registrar lo sucedido con el cliente para una futura optimización, envíe una solicitud a Adobe Analytics una vez devuelta la respuesta. Dispondrá del contexto completo y sabrá cuál era la solicitud y cómo respondió el sistema.

## Nuevas instalaciones

Con algunos asistentes digitales, recibe una notificación cuando alguien instala la habilidad, especialmente cuando se trata del proceso de autenticación. Adobe recomienda enviar un evento de instalación configurando la variable de datos de contexto `a.InstallEvent=1`. Tenga en cuenta que este procedimiento no está disponible en todos los asistentes digitales, pero, cuando está presente, es útil para comprobar la retención. El siguiente ejemplo de código envía los valores del evento de instalación, fecha de instalación y AppID a las variables de datos de contexto.

```text
GET
/b/ss/examplersid/1?vid=[UserID]&c.a.InstallEvent=1&c.a.InstallDate=2017-04-24&c.a.AppID=Spoofify1.0&c.OSType=Alexa&pageName=install
HTTP/1.1
Host:
<xref href="https://example.data.adobedc.net">
  example.data.adobedc.net
 Cache-Control: no-cache
</xref href="https:>
```

## Múltiples asistentes o aplicaciones

Es probable que su organización quiera aplicaciones para varias plataformas. Es recomendable incluir un ID de aplicación con cada solicitud. Esta variable se puede establecer en la variable de datos de contexto `a.AppID`. Siga el formato de `[AppName] [BundleVersion]`, por ejemplo, BigMac para Alexa 1.2:

```text
GET /b/ss/examplersid/1?vid=[UserID]&c.a.AppID=Spoofify1.0&c.a.Launches=1&c.Product=AmazonEcho&c.OSType=Alexa&pageName=install  HTTP/1.1
Host: example.data.adobedc.net
Cache-Control: no-cache
```

```text
GET /b/ss/examplersid/1?vid=[UserID]&c.a.AppID=Spoofify2.0&c.a.Launches=1&c.Product=GoogleHome&c.OSType=Android&pageName=install  HTTP/1.1
Host: example.data.adobedc.net
Cache-Control: no-cache
```

## Identificación de usuarios/visitantes

Adobe Analytics utiliza el [servicio de Adobe Experience Cloud ID](https://docs.adobe.com/content/help/es-ES/id-service/using/home.html) para enlazar las interacciones a lo largo del tiempo con la misma persona. La mayoría de los asistentes digitales devuelven un `userID` que puede utilizar para mantener la actividad de distintos usuarios. En la mayoría de los casos, este valor es lo que se puede pasar como identificador único. Algunas plataformas devuelven un identificador que supera los 100 caracteres permitidos. En estos casos, Adobe recomienda que se utilice la función hash con el identificador único y se cree un valor de longitud fija mediante un algoritmo hash estándar, como MD5 o Sha1.

El uso del servicio de ID proporciona el mayor valor al asignar un ECID a distintos dispositivos (por ejemplo, web a asistente digital). Si la aplicación es móvil, utilice los SDK de Experience Platform tal cual y envíe el ID de usuario con el método `setCustomerID`. Sin embargo, si su aplicación es un servicio, utilice el ID proporcionado por el servicio de ECID y configúrelo en `setCustomerID`.

```text
GET /b/ss/examplersid/1?vid=[UserID]&pageName=[intent]  HTTP/1.1
Host: example.data.adobedc.net
Cache-Control: no-cache
```

## Sesiones

Como los asistentes digitales son conversacionales, a menudo incluyen el concepto de sesión. Por ejemplo:

**Consumidor:** “Vale, Google, llámame un taxi”.

**Google:** “Claro, ¿para cuándo lo quieres?”.

**Consumidor:** “Las 8:30 de la tarde”.

**Google:** “Muy bien, el conductor llegará a las 8:30 de la tarde”.

Las sesiones son importantes para mantener el contexto y ayudar a recopilar más detalles para que el asistente digital sea más natural. Cuando se implementa Analytics en una conversación, hay dos cosas que deben hacerse al comienzo de una nueva sesión:

1. **Póngase en contacto con Audience Manager:** obtenga los segmentos relevantes a los que pertenece un usuario para que pueda personalizar la respuesta. (Por ejemplo, esa persona es elegible en este momento para del descuento multicanal).
2. **Envíe un evento de nueva sesión o de inicio:** cuando envíe la primera respuesta a Analytics, incluya un evento de inicio. Normalmente puede hacerse estableciendo los datos de contexto `a.LaunchEvent=1`.

```text
GET /b/ss/examplersid/1?vid=[UserID]&c.a.LaunchEvent=1&c.Intent=[intent]&pageName=[intent]  HTTP/1.1
Host: example.data.adobedc.net
Cache-Control: no-cache
```

## Intenciones

Todos los asistentes digitales cuentan con algoritmos que detectan las intenciones para luego transmitirlas a la “Aplicación” de modo que esta sepa lo que debe hacer. Estas intenciones son una representación sucinta de la solicitud.

Por ejemplo, si un usuario dice: “Siri, envía a John 20 dólares desde mi aplicación de banca por la cena de anoche”, la intención podría ser algo como *sendMoney*.

Al enviar cada una de estas solicitudes como una eVar, puede realizar informes de control de rutas de todas las intenciones de una aplicación conversacional. Asegúrese de que la aplicación también pueda gestionar solicitudes sin intención. Adobe recomienda pasar &#39;Sin intención especificada&#39; a la variable de datos de contexto por intención, en lugar de omitir la variable.

```text
GET /b/ss/examplersid/1?vid=[UserID]&c.a.AppID=Penmo1.0&c.a.LaunchEvent=1&c.Intent=SendPayment&pageName=[intent]  HTTP/1.1
Host: example.sc.adobedc.net
Cache-Control: no-cache
```

O bien

```text
GET /b/ss/examplersid/1?vid=[UserID]&c.a.AppID=Penmo1.0&c.a.LaunchEvent=1&c.Intent=No_Intent_Specified&pageName=[intent]  HTTP/1.1
Host: example.data.adobedc.net
Cache-Control: no-cache
```

## Parámetros/Espacios/Entidades

Además de la intención, los asistentes digitales cuentan a menudo con un conjunto de pares de clave-valor que proporcionan los detalles de la intención. Reciben el nombre de espacios, entidades o parámetros. Por ejemplo: “Siri, envía a John 20 dólares desde mi aplicación de banca por la cena de anoche” tendría los siguientes parámetros:

* Quién = John
* Cantidad = 20
* Por qué = Cena

Por lo general, una aplicación cuenta con un número finito de estos parámetros. Para realizar un seguimiento de los mismos en Analytics, envíelos como datos de contexto y, a continuación, asigne cada uno de los parámetros a una eVar.

```text
GET /b/ss/examplersid/1?vid=[UserID]&c.a.AppID=Penmo1.0=1&c.a.LaunchEvent=1&c.Intent=SendPayment&c.Amount=20.00&c.Reason=Dinner&c.ReceivingPerson=John&c.Intent=SendPayment&pageName=[intent]  HTTP/1.1
Host: example.data.adobedc.net
Cache-Control: no-cache
```

## Estados de error

En ocasiones, el asistente digital proporciona entradas que la aplicación no sabe cómo manejar. Por ejemplo: “Siri, envía a John 20 bolsas de carbón desde mi aplicación de banca por la cena de anoche”.

Cuando esto ocurra, haga que la aplicación pida una aclaración. Además, envíe datos a Adobe que indiquen que la aplicación tiene un estado de error junto con una eVar que especifique el tipo de error. Asegúrese de que incluye los errores que se producen cuando las entradas no son correctas y aquellos en los que la aplicación ha tenido un problema.

```text
GET /b/ss/examplersid/1?vid=[UserID]&c.a.AppID=Penmo1.0&c.Error=1&c.ErrorName=InvalidCurrency&pageName=[intent]  HTTP/1.1
Host: example.data.adobedc.net
Cache-Control: no-cache
```

## Capacidades de los dispositivos

Aunque la mayoría de las plataformas no exponen el dispositivo con el que habló el usuario, sí exponen las capacidades del dispositivo. Por ejemplo: audio, pantalla, vídeo, etc. Se trata de información útil porque define los tipos de contenido que se pueden utilizar cuando se interactúa con los usuarios. Cuando se miden las capacidades de los dispositivos, es conveniente concatenarlas (en orden alfabético).

Ejemplo: `":Audio:Camera:Screen:Video:"`

Los dos puntos al inicio y al final ayudan a crear segmentos. Por ejemplo, mostrar todas las visitas con capacidades de `:Audio:`.

* [Capacidades de Amazon](https://developer.amazon.com/public/solutions/alexa/alexa-skills-kit/docs/alexa-skills-kit-interface-reference) con Amazon Alexa
* [Capacidades de Google](https://developers.google.com/actions/assistant/surface-capabilities) mediante acciones en Google

## Ejemplos

| Persona | Respuesta del dispositivo | Acción/Intención | Obtener solicitud |
|---|---|---|---|
| Instala Spoofify | Sin respuesta | Se instala | `GET /b/ss/examplersid/1?vid=[UserID]&c.a.InstallEvent=1&c.a.InstallDate=[currentDate]&c.a.AppID=Spoofify1.0&c.OSType=Alexa&c.Intent=Install&pageName=Install  HTTP/1.1`<br>`Host: example.data.adobedc.net`<br>`Cache-Control: no-cache` |
| Reproduce Spoofify | “Vale, reproduciendo Spoofify” | Play | `GET /b/ss/examplersid/1?vid=[UserID]&c.a.AppID=Spoofify1.0&c.a.LaunchEvent=1&c.Intent=Play&pageName=PlayApp  HTTP/1.1`<br>`Host: example.data.adobedc.net`<br>`Cache-Control: no-cache` |
| Cambia canción | “Vale, ¿qué canción quieres?” | ChangeSong | `GET /b/ss/examplersid/1?vid=[UserID]&c.a.AppID=Spoofify1.0&c.Intent=ChangeSong&pageName= Ask%20For%20Song  HTTP/1.1`<br>`Host: example.data.adobedc.net`<br>`Cache-Control: no-cache` |
| Reproduce “Baby Shark” | “Vale, reproduciendo ‘Baby Shark’ de PinkFong” | ChangeSong | `GET /b/ss/examplersid/1?vid=[UserID]&c.a.AppID=Spoofify1.0&c.Intent=ChangeSong&pageName=Action%20Play%20Song&c.SongID=[012345]  HTTP/1.1`<br>`Host: example.data.adobedc.net`<br>`Cache-Control: no-cache` |
| Cambia lista de reproducción | “Vale, ¿qué lista de reproducción quieres?” | ChangePlaylist | `GET /b/ss/examplersid/1?vid=[UserID]&c.a.AppID=Spoofify1.0&c.Intent=ChangePlaylist&pageName=Ask%20For%20Playlist  HTTP/1.1`<br>`Host: example.data.adobedc.net`<br>`Cache-Control: no-cache` |
| Reproduce mi lista de reproducción de canciones favoritas | “Vale, reproduciendo tu lista de canciones favoritas” | ChangePlaylist | `GET /b/ss/examplersid/1?vid=[UserID]&c.a.AppID=Spoofify1.0&c.Intent=ChangePlaylist&pageName=Action%20Play%20Playlist&c.Playlist=My%20Favorite%20Songs  HTTP/1.1`<br>`Host: example.data.adobedc.net`<br>`Cache-Control: no-cache` |
| Apaga la música | Sin respuesta, la música se apaga | Off | `GET /b/ss/examplersid/1?vid=[UserID]&c.a.AppID=Spoofify1.0&c.Intent=Off&pageName=Music%20Off  HTTP/1.1`<br>`Host: example.data.adobedc.net`<br>`Cache-Control: no-cache` |

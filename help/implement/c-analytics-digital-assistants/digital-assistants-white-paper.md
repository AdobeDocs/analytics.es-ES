---
description: 'null'
title: Implementar Analytics para asistentes digitales
uuid: c61e6a1a-ec08-4936-9053-5f57223f57ff
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Implementación de Analytics para asistentes digitales

<!-- 
https://wiki.corp.adobe.com/display/mobileanalytics/Analytics+for+Digital+Assistants+Whitepaper
https://marketing.adobe.com/resources/help/en_US/sc/implement/digital-assistants-white-paper.html
Ticket: https://jira.corp.adobe.com/browse/AN-157750
-->

Con los recientes avances en computación en nube, aprendizaje automático y procesamiento de lenguajes naturales, los asistentes digitales se están convirtiendo en parte de la vida cotidiana. Los consumidores están empezando a hablar con sus dispositivos y a esperar que comprendan y respondan de formas parecidas a las humanas. El establecimiento cada vez mayor de estas plataformas permite a las marcas presentar sus servicios a los consumidores de un modo realista y natural. Por ejemplo, un consumidor puede preguntar cosas como:

* “Alexa, pregunta al coche cuándo hay que cambiarle el aceite”.
* “Cortana, ¿qué saldo tengo en la cuenta corriente?”.
* “Siri, envía a John 20 dólares desde mi aplicación de banca por la cena de anoche”.

Esta página proporciona información general sobre cómo utilizar Adobe Analytics para medir y optimizar estos tipos de experiencias.

## Descripción general de la arquitectura de la experiencia digital

![](assets/Digital-Assitants.png)

La mayoría de los asistentes digitales de hoy en día siguen una arquitectura de alto nivel similar:

1. **Dispositivo:** hay un dispositivo (como un Amazon Echo o un teléfono) con un micrófono que permite al usuario hacer una pregunta.
1. **Asistente digital:** el dispositivo interactúa con el servicio que alimenta el asistente digital. Es donde el habla se convierte en intenciones comprensibles para la máquina y donde se analizan los detalles de la solicitud. Una vez entendida la intención del usuario, el asistente digital la transmite junto con los detalles de la solicitud a la aplicación que se encarga de tramitar dicha solicitud.
1. **“Aplicación”:** puede tratarse de una aplicación que hay en el teléfono o de una aplicación de voz. La aplicación es la encargada de responder a la solicitud. Responde al asistente digital, que a su vez responde al usuario.

## Dónde se implementa Analytics

Uno de los mejores lugares para implementar Analytics es en la aplicación. La aplicación recibe la intención y los detalles del asistente digital y, a continuación, la aplicación determina cómo responder.

Hay dos veces durante una solicitud que pueden resultar útiles para enviar datos a Adobe Analytics.

1. Cuando se envía la solicitud a la aplicación.
1. Tras devolverse la respuesta desde la aplicación.

Si simplemente está interesado en registrar lo sucedido con el cliente para una futura optimización, envíe una solicitud a Adobe Analytics una vez devuelta la respuesta. Tendrá el contexto completo de lo que fue la solicitud y cómo respondió el sistema.

## Nuevas instalaciones

Para algunos asistentes digitales, recibe una notificación cuando alguien instala la habilidad, especialmente cuando se trata de autenticación. Adobe recomienda enviar un evento Install configurando la variable de datos de contexto `a.InstallEvent=1`. Esta función no está disponible en todos los asistentes digitales, pero es útil cuando está presente para consultar la retención. El siguiente ejemplo de código envía los valores de evento Install, Fecha de instalación y AppID a las variables de datos de contexto.

```text
GET
/b/ss/[rsid]/1?vid=[UserID]&c.a.InstallEvent=1&c.a.InstallDate=2017-04-24&c.a.AppID=Spoofify1.0&c.OSType=Alexa&pageName=install
HTTP/1.1
Host:
<xref href="https://sc.omtrdc.net">
  sc.omtrdc.net
 Cache-Control: no-cache
</xref href="https:>
```

## Varios asistentes o varias aplicaciones

Es probable que su organización quiera aplicaciones para varias plataformas. Es recomendable incluir un ID de aplicación con cada solicitud. This variable can be set in the `a.AppID` context data variable. Siga el formato `[AppName] [BundleVersion]`, por ejemplo, BigMac para Alexa 1.2:

```text
GET /b/ss/[rsid]/1?vid=[UserID]&c.a.AppID=Spoofify1.0&c.a.Launches=1&c.Product=AmazonEcho&c.OSType=Alexa&pageName=install  HTTP/1.1
Host: example.sc.omtrdc.net
Cache-Control: no-cache
```

```text
GET /b/ss/[rsid]/1?vid=[UserID]&c.a.AppID=Spoofify2.0&c.a.Launches=1&c.Product=GoogleHome&c.OSType=Android&pageName=install  HTTP/1.1
Host: example.sc.omtrdc.net
Cache-Control: no-cache
```

## Identificación de usuario/visitante

Adobe Analytics utiliza el servicio [de identidad de](https://docs.adobe.com/content/help/en/id-service/using/home.html) Adobe Experience Cloud para enlazar las interacciones a lo largo del tiempo con la misma persona. La mayoría de los asistentes digitales devuelven una `userID` que puede utilizar para mantener la actividad para distintos usuarios. En la mayoría de los casos, este valor es lo que se puede pasar como identificador único. Algunas plataformas devuelven un identificador que supera los 100 caracteres permitidos. En estos casos, Adobe recomienda que se hash el identificador único en un valor de longitud fija mediante un algoritmo hash estándar, como MD5 o Sha1.

El uso del servicio de ID proporciona el mayor valor al asignar ECID a distintos dispositivos (por ejemplo, Web a asistente digital). Si la aplicación es móvil, utilice los SDK de la plataforma de experiencia tal cual y envíe el ID de usuario con el `setCustomerID` método . However, if your app is a service, use the user ID provided by the service as the ECID, as well as setting it in `setCustomerID`.

```text
GET /b/ss/[rsid]/1?vid=[UserID]&pageName=[intent]  HTTP/1.1
Host: example.sc.omtrdc.net
Cache-Control: no-cache
```

## Sesiones

Como los asistentes digitales son conversacionales, a menudo incluyen el concepto de sesión. Por ejemplo:

**Consumidor:** “Vale, Google, llámame un taxi”.

**Google:** “Claro, ¿para cuándo lo quieres?”.

**Consumidor:** “Las 8:30 de la tarde”.

**Google:** “Muy bien, el conductor llegará a las 8:30 de la tarde”.

Las sesiones son importantes para mantener el contexto y ayudar a recopilar más detalles para que el asistente digital sea más natural. Al implementar Analytics en una conversación, hay dos cosas que hacer cuando se inicia una nueva sesión:

1. **Póngase en contacto con Audience Manager:** obtenga los segmentos relevantes a los que pertenece un usuario para que pueda personalizar la respuesta. (Por ejemplo, esa persona es elegible en este momento para del descuento multicanal).
2. **Envíe un evento de nueva sesión o de inicio:** cuando envíe la primera respuesta a Analytics, incluya un evento de inicio. Normalmente puede hacerse estableciendo los datos de contexto `a.LaunchEvent=1`.

```text
GET /b/ss/[rsid]/1?vid=[UserID]&c.a.LaunchEvent=1&c.Intent=[intent]&pageName=[intent]  HTTP/1.1
Host: sc.omtrdc.net
Cache-Control: no-cache
```

## Intenciones

Todos los asistentes digitales cuentan con algoritmos que detectan las intenciones para luego transmitirlas a la “Aplicación” de modo que esta sepa lo que debe hacer. Estas intenciones son una representación sucinta de la solicitud.

Por ejemplo, si un usuario dice: “Siri, envía a John 20 dólares desde mi aplicación de banca por la cena de anoche”, la intención podría ser algo como *sendMoney*.

Al enviar cada una de estas solicitudes como una eVar, puede ejecutar informes de rutas en cada una de las intenciones de las aplicaciones de conversación. Asegúrese de que la aplicación también puede gestionar solicitudes sin intención. Adobe recomienda pasar 'Sin intención especificada' a la variable de datos de contexto por intención, en lugar de omitir la variable.

```text
GET /b/ss/[rsid]/1?vid=[UserID]&c.a.AppID=Penmo1.0&c.a.LaunchEvent=1&c.Intent=SendPayment&pageName=[intent]  HTTP/1.1
Host: example.sc.omtrdc.net
Cache-Control: no-cache
```

O bien

```text
GET /b/ss/[rsid]/1?vid=[UserID]&c.a.AppID=Penmo1.0&c.a.LaunchEvent=1&c.Intent=No_Intent_Specified&pageName=[intent]  HTTP/1.1
Host: sc.omtrdc.net
Cache-Control: no-cache
```

## Parámetros/Espacios/Entidades

Además de la intención, los asistentes digitales suelen tener un conjunto de pares clave/valor que dan detalles de la intención. Se pueden llamar ranuras, entidades o parámetros. Por ejemplo, "Siri, envía a John $20 para cenar anoche desde mi aplicación bancaria" tendría los siguientes parámetros:

* Quién = John
* Cantidad = 20
* Por qué = Cena

Normalmente, con la aplicación hay un número finito de estos valores. Para rastrear estos valores en Analytics, envíelos a variables de datos de contexto y, a continuación, asigne cada uno de los parámetros a una eVar.

```text
GET /b/ss/[rsid]/1?vid=[UserID]&c.a.AppID=Penmo1.0=1&c.a.LaunchEvent=1&c.Intent=SendPayment&c.Amount=20.00&c.Reason=Dinner&c.ReceivingPerson=John&c.Intent=SendPayment&pageName=[intent]  HTTP/1.1
Host: example.sc.omtrdc.net
Cache-Control: no-cache
```

## Estados de error

A veces, el asistente digital proporciona a la aplicación entradas que no sabe gestionar. Por ejemplo, "Siri, envía a John 20 bolsas de carbón para cenar anoche desde mi aplicación bancaria"

Cuando esto ocurra, pida a la aplicación que aclare esta situación. Además, envíe datos a Adobe que indiquen que la aplicación tiene un estado de error junto con una eVar que especifique el tipo de error. Asegúrese de incluir errores en los casos en los que las entradas no son correctas y errores en los que la aplicación ha tenido un problema.

```text
GET /b/ss/[rsid]/1?vid=[UserID]&c.a.AppID=Penmo1.0&c.Error=1&c.ErrorName=InvalidCurrency&pageName=[intent]  HTTP/1.1
Host: example.sc.omtrdc.net
Cache-Control: no-cache
```

## Funciones del dispositivo

Aunque la mayoría de las plataformas no exponen el dispositivo con el que habló el usuario, sí exponen las capacidades del dispositivo. Por ejemplo, audio, pantalla, vídeo, etc. Esta información es útil porque define los tipos de contenido que se pueden utilizar al interactuar con los usuarios. Al medir las capacidades del dispositivo, es mejor concatenarlas (en orden alfabético).

Ejemplo: `":Audio:Camera:Screen:Video:"`

Los dos puntos al inicio y al final ayudan a crear segmentos. Por ejemplo, mostrar todas las visitas con `:Audio:` capacidades.

* [Capacidades](https://developer.amazon.com/public/solutions/alexa/alexa-skills-kit/docs/alexa-skills-kit-interface-reference) de Amazon con Amazon Alexa
* [Capacidades](https://developers.google.com/actions/assistant/surface-capabilities) de Google mediante acciones en Google

## Ejemplos

| Persona | Respuesta del dispositivo | Acción/Intención | Solicitud GET |
| --- | --- | --- | --- | ---|
| Instala Spoofify | Sin respuesta | Install | `GET /b/ss/[rsid]/1?vid=[UserID]&c.a.InstallEvent=1&c.a.InstallDate=[currentDate]&c.a.AppID=Spoofify1.0&c.OSType=Alexa&c.Intent=Install&pageName=Install  HTTP/1.1`<br>`Host: example.sc.omtrdc.net`<br>`Cache-Control: no-cache` |
| Reproduce Spoofify | "Bien, jugando a Spoofify" | Play | `GET /b/ss/[rsid]/1?vid=[UserID]&c.a.AppID=Spoofify1.0&c.a.LaunchEvent=1&c.Intent=Play&pageName=PlayApp  HTTP/1.1`<br>`Host: example.sc.omtrdc.net`<br>`Cache-Control: no-cache` |
| Cambia canción | "Bien, ¿qué canción quieres?" | ChangeSong | `GET /b/ss/[rsid]/1?vid=[UserID]&c.a.AppID=Spoofify1.0&c.Intent=ChangeSong&pageName= Ask%20For%20Song  HTTP/1.1`<br>`Host: example.sc.omtrdc.net`<br>`Cache-Control: no-cache` |
| Jugar "Baby Shark" | "Bien, jugando al "Baby Shark" por PinkFong" | ChangeSong | `GET /b/ss/[rsid]/1?vid=[UserID]&c.a.AppID=Spoofify1.0&c.Intent=ChangeSong&pageName=Action%20Play%20Song&c.SongID=[012345]  HTTP/1.1`<br>`Host: example.sc.omtrdc.net`<br>`Cache-Control: no-cache` |
| Cambia lista de reproducción | "Bien, ¿qué lista de reproducción quieres?" | ChangePlaylist | `GET /b/ss/[rsid]/1?vid=[UserID]&c.a.AppID=Spoofify1.0&c.Intent=ChangePlaylist&pageName=Ask%20For%20Playlist  HTTP/1.1`<br>`Host: example.sc.omtrdc.net`<br>`Cache-Control: no-cache` |
| Reproducir mi lista de reproducción de canciones favoritas | "Bien, tocando tu lista de canciones favoritas" | ChangePlaylist | `GET /b/ss/[rsid]/1?vid=[UserID]&c.a.AppID=Spoofify1.0&c.Intent=ChangePlaylist&pageName=Action%20Play%20Playlist&c.Playlist=My%20Favorite%20Songs  HTTP/1.1`<br>`Host: example.sc.omtrdc.net`<br>`Cache-Control: no-cache` |
| Apaga la música | Sin respuesta, la música se apaga | Off | `GET /b/ss/[rsid]/1?vid=[UserID]&c.a.AppID=Spoofify1.0&c.Intent=Off&pageName=Music%20Off  HTTP/1.1`<br>`Host: example.sc.omtrdc.net`<br>`Cache-Control: no-cache` |

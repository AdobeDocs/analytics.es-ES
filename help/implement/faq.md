---
title: Preguntas frecuentes acerca de la implementación de Analytics
description: Preguntas más frecuentes sobre implementación y vínculos a más información.
keywords: Analytics Implementation;faq;frequently asked questions;evar expiration;custom event visibility;timestamp;visitor id grace period;visitor id;Experience Cloud visitor id;analytics visitor id;dtm;heartbeat;cookies;tracking server;performance;javascript;data collection;s_code version;s_code debug;track link types;track video;track mobile app;first party cookie;ssl certificate;certification expiration;certificate expiration;plugins;data insertion api;500 error;500;Manage user;manage group;users;groups
translation-type: ht
source-git-commit: d1db8da65faac1bf09fa2a290a2645092b542a35
workflow-type: ht
source-wordcount: '412'
ht-degree: 100%

---


# Preguntas frecuentes acerca de la implementación de Analytics

Preguntas más frecuentes sobre implementación y vínculos a más información.

**¿Cuál es la diferencia entre la asignación de variables y la caducidad?**

La asignación y la caducidad son opciones que se pueden aplicar a las variables personalizadas. *La asignación* entra en juego cuando se tiene un valor de variable persistente y un nuevo valor de variable. Determina si se conserva el valor antiguo o el nuevo. *La caducidad* entra en juego cuando no desea que un valor de variable se siga utilizando.

**¿Cuál es la diferencia entre el ID del visitante de Experience Cloud y el ID del visitante de Analytics?**

El servicio de identidad asigna un identificador único y persistente que se puede compartir con otras soluciones de Experience Cloud. El ID de visitante de Analytics solo lo utiliza Analytics. Adobe recomienda utilizar el servicio de ID de visitante de Experience Cloud en la implementación.

**¿Cómo se establece un ID de visitante si se bloquean las cookies?**

Si la cookie estándar `s_vi` no está disponible, se crea una cookie de reserva en el dominio del sitio web con un ID único generada aleatoriamente. Esta cookie, denominada `s_fid`, se configura con una caducidad de 2 años y se usa como método de identificación de reserva a partir de ahora.

**¿Cómo implemento Seguimiento de vídeos de Heartbeat?**

Consulte [Medición de audio y vídeo en Adobe Analytics](https://docs.adobe.com/content/help/es-ES/media-analytics/using/media-overview.html).

**¿Puede una interrupción del servicio en Adobe afectar al rendimiento?**

No. El archivo de JavaScript no se aloja en servidores de Adobe, por lo que una interrupción en Adobe no afectará a su biblioteca de AppMeasurement. Si utiliza Adobe Experience Platform Launch, el archivo JavaScript se aloja en Akamai o en una ubicación de servidor determinada por su organización.

**¿Puede reducir el rendimiento el envío de datos desde el explorador a los servicios de Adobe?**

AppMeasurement crea un objeto de imagen en la página HTML y, a continuación, el explorador solicita el objeto de imagen de los servidores de recopilación de datos de Adobe. Si los servidores de recopilación de datos van lentos o no responden, el proceso que administra esa solicitud se retrasará hasta que se devuelva la imagen o se agote el tiempo de espera. Como los exploradores administran las imágenes con varios procesos, una interrupción de Adobe tendría un impacto mínimo en el tiempo de carga de la página y bloquearía un proceso mientras los otros continúan funcionando.

**¿Cómo realizo el seguimiento de una aplicación móvil?**

Puede utilizar el SDK de Adobe Experience Platform. Consulte [Información general del SDK de Adobe Experience Platform](https://aep-sdks.gitbook.io/docs/) para obtener más información.

**¿Qué son los complementos?**

Los complementos son fragmentos de código que realizan funciones avanzadas. Amplían las capacidades de AppMeasurement para proporcionar más funcionalidad en la implementación.

---
title: Preguntas frecuentes acerca de la implementación de Analytics
description: Preguntas más frecuentes sobre implementación y vínculos a más información.
keywords: Analytics Implementation;faq;frequently asked questions;evar expiration;custom event visibility;timestamp;visitor id grace period;visitor id;Experience Cloud visitor id;analytics visitor id;dtm;heartbeat;cookies;tracking server;performance;javascript;data collection;s_code version;s_code debug;track link types;track video;track mobile app;first party cookie;ssl certificate;certification expiration;certificate expiration;plugins;data insertion api;500 error;500;Manage user;manage group;users;groups
translation-type: tm+mt
source-git-commit: d1db8da65faac1bf09fa2a290a2645092b542a35

---


# Preguntas frecuentes acerca de la implementación de Analytics

Preguntas más frecuentes sobre implementación y vínculos a más información.

**¿Cuál es la diferencia entre la asignación de variables y la caducidad?**

La asignación y la caducidad son opciones que se pueden aplicar a las variables personalizadas. *La asignación* entra en juego cuando se tiene un valor de variable persistente y un nuevo valor de variable. Determina si se conserva el valor antiguo o el nuevo. *La caducidad* entra en juego cuando no desea que un valor de variable continúe persistiendo.

**¿Cuál es la diferencia entre el ID de visitante de Experience Cloud y el ID de visitante de Analytics?**

El servicio de identidad asigna un identificador único y persistente que se puede compartir entre otras soluciones de Experience Cloud. El ID de visitante de Analytics solo lo utiliza Analytics. Adobe recomienda utilizar el servicio de ID de visitante de Experience Cloud en la implementación.

**¿Cómo se establece una ID de visitante si se bloquean las cookies?**

If the standard `s_vi` cookie is unavailable, a fallback cookie is created on the domain of the website with a randomly generated unique ID. This cookie, named `s_fid`, is set with a 2-year expiration and is used as the fallback identification method going forward.

**¿Cómo implemento el seguimiento de vídeo de Heartbeat?**

Consulte [Medición de audio y vídeo en Adobe Analytics](https://docs.adobe.com/content/help/en/media-analytics/using/media-overview.html).

**¿Puede una interrupción del servicio en Adobe afectar al rendimiento?**

No. El archivo JavaScript no está alojado en los servidores de Adobe, por lo que una interrupción de Adobe no afecta a la biblioteca de AppMeasurement. Si utiliza Adobe Experience Platform Launch, el archivo JavaScript se aloja en Akamai o en una ubicación de servidor determinada por su organización.

**¿Puede reducir el rendimiento el envío de datos desde el navegador a los servicios de Adobe?**

AppMeasurement crea un objeto de imagen dentro de la página HTML y, a continuación, el explorador solicita el objeto de imagen desde los servidores de recopilación de datos de Adobe. Si los servidores de recopilación de datos fueran lentos o no respondieran, el subproceso que gestiona esa solicitud se retrasaría hasta que se devuelva la imagen o se agote el tiempo de espera. Como los exploradores administran las imágenes con varios procesos, una interrupción de Adobe tendría un impacto mínimo en el tiempo de carga de la página y bloquearía un proceso mientras los otros continúan funcionando.

**¿Cómo rastreo una aplicación móvil?**

Puede utilizar el SDK de la plataforma Adobe Experience. Consulte [Descripción general](https://aep-sdks.gitbook.io/docs/) del SDK de Adobe Experience Platform para obtener más información.

**¿Qué son los complementos?**

Los complementos son fragmentos de código que realizan funciones avanzadas. Amplían las capacidades de AppMeasurement para proporcionar más funcionalidad en la implementación.

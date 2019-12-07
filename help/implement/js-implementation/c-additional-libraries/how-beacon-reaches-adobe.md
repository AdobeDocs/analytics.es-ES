---
description: Cuando un dispositivo móvil solicita una página de un servidor web, la solicitud se envía a través de una puerta de enlace que convierte la solicitud móvil (normalmente en el protocolo WAP o I-Mode) en una solicitud HTTP que se envía a un servidor web.
keywords: Analytics Implementation;gateway;wap;i-mode;wbmp
title: Puerta de enlace de red con protocolo móvil
topic: Developer and implementation
uuid: a2c92ce2-53a9-4b5b-be1a-89d9f1bf776f
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Puerta de enlace de red con protocolo móvil

Cuando un dispositivo móvil solicita una página de un servidor web, la solicitud se envía a través de una puerta de enlace que convierte la solicitud móvil (normalmente en el protocolo WAP o I-Mode) en una solicitud HTTP que se envía a un servidor web.

Cuando un dispositivo móvil solicita una página de un servidor web, la solicitud se envía a través de una puerta de enlace que convierte la solicitud móvil (normalmente en el protocolo WAP o I-Mode) en una solicitud HTTP que se envía a un servidor web. El servidor web responde a la puerta de enlace, que reenvía la solicitud al teléfono. Esta puerta de enlace actúa en gran medida como un servidor proxy estándar. Sin embargo, la puerta de enlace pasa la cadena del agente de usuario del dispositivo móvil al servidor web. Esto permite al servidor web responder con una página creada específicamente para el dispositivo que la solicita.

Como el tamaño de pantalla de los dispositivos móviles WAP es limitado, las páginas móviles suelen ser muy ligeras y solo contienen texto y una imagen en caché. Cuando se agrega la etiqueta de imagen a las páginas, se envía una solicitud de imagen en cada página a los servidores de Adobe. Cuando se devuelve la imagen, un archivo WBMP, los servidores de Adobe indican al explorador que no la almacenen en caché. Por lo tanto, la imagen se vuelve a solicitar en las páginas posteriores. El número aleatorio descrito anteriormente debe usarse para protegerse de los exploradores que no siguen las directivas de no almacenamiento en caché de Adobe.

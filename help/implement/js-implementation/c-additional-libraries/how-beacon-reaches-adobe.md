---
description: Cuando un dispositivo móvil solicita una página de un servidor web, la solicitud se envía a través de una puerta de enlace que convierte la solicitud móvil (normalmente en el protocolo WAP o I-Mode) en una solicitud HTTP que se envía a un servidor web.
keywords: Implementación de Analytics; gateway; wap; i-mode; wbmp
seo-description: Cuando un dispositivo móvil solicita una página de un servidor web, la solicitud se envía a través de una puerta de enlace que convierte la solicitud móvil (normalmente en el protocolo WAP o I-Mode) en una solicitud HTTP que se envía a un servidor web.
seo-title: Puerta de enlace de red de protocolo móvil
solution: Analytics
title: Puerta de enlace de red de protocolo móvil
topic: Desarrollador e implementación
uuid: a 2 c 92 ce 2-53 a 9-4 b 5 b-be 1 a -89 d 9 f 1 bf 776 f f
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Puerta de enlace de red de protocolo móvil

Cuando un dispositivo móvil solicita una página de un servidor web, la solicitud se envía a través de una puerta de enlace que convierte la solicitud móvil (normalmente en el protocolo WAP o I-Mode) en una solicitud HTTP que se envía a un servidor web.

Cuando un dispositivo móvil solicita una página de un servidor web, la solicitud se envía a través de una puerta de enlace que convierte la solicitud móvil (normalmente en el protocolo WAP o I-Mode) en una solicitud HTTP que se envía a un servidor web. El servidor web responde a la puerta de enlace, que reenvía la solicitud al teléfono. Esta puerta de enlace actúa en gran medida como un servidor proxy estándar. Sin embargo, la puerta de enlace pasa la cadena del agente de usuario del dispositivo móvil al servidor web. Esto permite al servidor web responder con una página creada específicamente para el dispositivo que la solicita.

Como el tamaño de pantalla de los dispositivos móviles WAP es limitado, las páginas móviles suelen ser muy ligeras y solo contienen texto y una imagen en caché. Cuando se agrega la etiqueta de imagen a las páginas, se envía una solicitud de imagen en cada página a los servidores de Adobe. Cuando se devuelve la imagen, un archivo WBMP, los servidores de Adobe indican al explorador que no la almacenen en caché. Por lo tanto, la imagen se vuelve a solicitar en las páginas posteriores. El número aleatorio descrito anteriormente debe usarse para protegerse de los exploradores que no siguen las directivas de no almacenamiento en caché de Adobe.

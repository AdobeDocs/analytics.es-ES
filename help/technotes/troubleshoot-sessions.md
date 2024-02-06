---
title: Solución de problemas de sesión de Adobe Analytics
description: Obtenga información sobre cómo resolver problemas relacionados con la desconexión de Adobe Analytics.
feature: Analytics Basics
exl-id: 191250ef-8313-47be-9717-046cce870998
source-git-commit: d3d5b01fe17f88d07a748fac814d2161682837c2
workflow-type: tm+mt
source-wordcount: '339'
ht-degree: 99%

---

# Solución de problemas de sesión de Adobe Analytics

En esta página se dan orientaciones para la resolución de problemas con las sesiones, es decir, casos en los que es posible iniciar sesión pero en los que existen problemas de desconexión. Si tiene problemas para iniciar sesión en Adobe Analytics, consulte [Solución de problemas para iniciar sesión en Adobe Analytics](troubleshoot-login.md).

Casi todos los problemas relativos a las sesiones se originan en la red corporativa personalizada de una organización. Si puede iniciar sesión en Adobe Analytics pero tiene problemas de desconexión, este artículo le ayudará a determinar la causa.

## Determine si el problema se debe a la red de su organización {#network}

Muchas organizaciones implementan funciones de red adicionales para mejorar la seguridad, como servidores proxy o firewalls. Estos ajustes pueden interferir en ocasiones con la capacidad de mantener una sesión activa en Adobe Analytics.

Para determinar si la red corporativa a la que se ha conectado interfiere con el uso de Adobe Analytics, utilice sus credenciales de inicio de sesión de Experience Cloud en un dispositivo ajeno a la red corporativa. Puede iniciar sesión en dispositivos que estén conectados, por ejemplo, a su red doméstica o a los datos de su móvil. Si puede moverse correctamente de una página a otra sin cerrar la sesión, es probable que la red de su organización sea el motivo por el que experimenta problemas de desconexión en Adobe Analytics.

## Problemas debidos a proxies {#proxy}

Adobe utiliza un encabezado de autorización cuando realiza solicitudes a Adobe. Algunos proxies, como Edge Secure Web Gateway (anteriormente, Bluecoat), eliminan la información crítica del encabezado de autorización utilizado por Adobe Analytics. Si Adobe no ve el encabezado de autorización, la sesión caduca.

Para resolver este problema, Adobe recomienda pedir ayuda al equipo informático de su organización para evitar que un proxy interfiera con el encabezado de autorización.

>[!NOTE]
>
>Aunque los miembros de la comunidad de Analytics han encontrado útiles los siguientes vínculos, no son propiedad de Adobe. Tenga en cuenta esta nota cuando visualice su contenido.

Encontrará información sobre los proxies de y sobre los encabezados de autenticación aquí:

* [Configure la autenticación de proxy ascendente en una implementación de cadena de proxy en un dispositivo ProxySG o ASG](https://techdocs.broadcom.com/us/en/symantec-security-software/web-and-network-security/edge-swg/7-3/authentication_co.html)
* [Cómo reenviar las credenciales de usuario a un servidor detrás del dispositivo ProxySG ](https://knowledge.broadcom.com/external/article/165859/how-to-forward-user-credentials-to-a-ser.html)

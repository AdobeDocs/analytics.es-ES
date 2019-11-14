---
title: Resolución de problemas de sesiones en Adobe Analytics
description: Obtenga información sobre cómo resolver problemas relacionados con la desconexión de Adobe Analytics.
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Resolución de problemas de sesiones en Adobe Analytics

Esta página trata sobre la resolución de problemas de las sesiones, lo que significa que puede iniciar sesión correctamente pero tiene problemas para seguir iniciando sesión. Si tiene problemas para iniciar sesión en Adobe Analytics, consulte [Solución de problemas para iniciar sesión en Adobe Analytics](troubleshoot-login.md).

Casi todos los problemas basados en sesiones se originan en la red corporativa personalizada de una organización. Si puede iniciar sesión en Adobe Analytics pero tiene problemas para seguir iniciándola, utilice este artículo para determinar la causa.

## Determinar si el problema se debe a la red de su organización

Muchas organizaciones implementan funciones de red adicionales para mejorar la seguridad, como servidores proxy o servidores de seguridad. Estas personalizaciones a veces pueden interferir con la capacidad de mantener una sesión activa en Adobe Analytics.

Para determinar si la red corporativa a la que está conectado está causando problemas con el uso de Adobe Analytics, utilice sus credenciales de inicio de sesión de Experience Cloud en un dispositivo fuera de la red corporativa. Algunos ejemplos de dispositivos pueden ser la red doméstica o el plan de datos de un dispositivo móvil. Si puede moverse correctamente de una página a otra sin cerrar la sesión, es probable que la red de su organización sea el motivo por el que cierre la sesión de Adobe Analytics.

## Problemas debidos al proxy

Adobe utiliza un encabezado de autorización cuando realiza solicitudes a Adobe. Algunos proxies, como Bluecoat (ahora propiedad de Symantec), eliminan la información crítica del encabezado de autorización utilizada por Adobe Analytics. Cuando Adobe no ve el encabezado de autorización, la sesión caduca.

Para resolver este problema, Adobe recomienda trabajar con el equipo de TI de su organización para permitir el encabezado de autorización a través del proxy de su organización.

> [!NOTE] Aunque los miembros de la comunidad de Analytics han encontrado útiles los siguientes vínculos, no son propiedad de Adobe. Tenga en cuenta esta nota cuando visualice su contenido.

Encontrará información sobre los proxies de Symantec y los encabezados de autenticación aquí:

* [Configuración de la autenticación de proxy ascendente en una implementación de cadena de proxy en un dispositivo ProxySG o ASG](https://support.symantec.com/en_US/article.TECH246122.html)
* [Permitir que ProxySG siempre reenvíe la autorización del servidor hacia arriba](https://support.symantec.com/en_US/article.TECH244708.html)

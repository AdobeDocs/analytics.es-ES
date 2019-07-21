---
title: Solución de problemas de sesiones en Adobe Analytics
description: Descubra cómo resolver problemas en torno a la cierre de sesión de Adobe Analytics.
seo-title: Solución de problemas de sesiones en Adobe Analytics
seo-description: Descubra cómo resolver problemas en torno a la cierre de sesión de Adobe Analytics.
translation-type: tm+mt
source-git-commit: b5e3801454dafbcc47b93e65f8b5e7c59c3a8081

---


# Solución de problemas de sesiones en Adobe Analytics

Esta página trata acerca de las sesiones de solución de problemas, lo que significa que puede iniciar sesión correctamente pero tener problemas al iniciar sesión. If you are having issues logging in to Adobe Analytics, see [Troubleshoot logging in to Adobe Analytics](troubleshoot-login.md).

Casi todos los problemas basados en sesiones se originan en la red corporativa personalizada de una organización. Si puede iniciar sesión en Adobe Analytics pero tiene problemas para permanecer conectado, utilice este artículo para determinar la causa.

## Determinar si el problema se debe a la red de su organización

Muchas organizaciones implementan funciones de red adicionales para mejorar la seguridad, como servidores proxy o servidores de seguridad. A veces, estas personalizaciones pueden interferir con la capacidad de conservar una sesión activa en Adobe Analytics.

Para determinar si la red corporativa a la que está conectado provoca problemas con el uso de Adobe Analytics, use sus credenciales de inicio de sesión de Experience Cloud en un dispositivo fuera de la red corporativa. Algunos ejemplos de dispositivos pueden ser a través de su red doméstica o del plan de datos de un dispositivo móvil. Si puede pasar de una página a otra sin cerrarse, la red de su organización es probablemente la razón por la que se cierra la sesión de Adobe Analytics.

## Problemas debido a la agrupación de direcciones IP

Algunas redes utilizan una práctica llamada agrupación de direcciones IP, donde la dirección IP de un dispositivo puede cambiar con frecuencia dentro de un intervalo utilizado por la organización. Como parte de las prácticas de seguridad de Adobe, si una dirección IP cambia a mitad de la sesión, dicha sesión ha caducado.

Si su organización utiliza agrupamiento de direcciones IP, utilice las instrucciones siguientes para que los intervalos de IP se agreguen a la lista de direcciones permitidas de Adobe:

1. Trabaje con el equipo de TI de su organización para obtener una lista de intervalos de IP utilizados en su organización
2. Póngase en contacto con el servicio de atención al cliente de Adobe y proporcione a Adobe los intervalos de IP
3. El agente introduce los intervalos IP en una lista blanca para evitar que las sesiones caduquen si ambas direcciones están dentro de los intervalos proporcionados.

## Problemas debido al proxy

Adobe utiliza un encabezado de autorización cuando realiza solicitudes a Adobe. Algunos proxies, como Bluecoat (ahora propiedad de Symantec), eliminan la información esencial de encabezados de autorización utilizada por Adobe Analytics. Cuando Adobe no ve el encabezado de autorización, la sesión ha caducado.

Para resolver este problema, Adobe recomienda trabajar con el equipo de TI de su organización para permitir el encabezado de autorización a través del proxy de la organización.

> [!NOTE] Nota
>
> Aunque los miembros de la comunidad de Analytics han encontrado los vínculos siguientes, no son propiedad de Adobe. Tenga en cuenta esta nota al ver su contenido.

Aquí puede encontrar información sobre los encabezados de autenticación y proxies Symantec:

* [Configurar autenticación proxy de flujo ascendente en una implementación de cadena proxy en un dispositivo ASG de PROG](https://support.symantec.com/en_US/article.TECH246122.html)
* [Permitir que proxysg siempre reenvíe el flujo ascendente de autorización del servidor](https://support.symantec.com/en_US/article.TECH244708.html)

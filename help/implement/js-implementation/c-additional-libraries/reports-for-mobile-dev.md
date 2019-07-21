---
description: El seguimiento de los dispositivos móviles se realiza mediante una señalización, al igual que ocurre con otros visitantes, por lo que la mayoría de los informes se encuentran disponibles y son correctos.
keywords: Implementación de Analytics; informes; protocolos móviles; motores de búsqueda; palabras clave de búsqueda; dominios de referencia; referrers; segmentación geográfica; dominios; tipo de conexión; huso horario; cookies; java; javascript; colores de monitor; resolución del monitor; ancho del explorador; height; complemento netscape
seo-description: El seguimiento de los dispositivos móviles se realiza mediante una señalización, al igual que ocurre con otros visitantes, por lo que la mayoría de los informes se encuentran disponibles y son correctos.
seo-title: Informes para dispositivos con protocolos móviles
solution: Analytics
title: Informes para dispositivos con protocolos móviles
topic: Desarrollador e implementación
uuid: 4 aab 125 d-c 131-4402-9 bc 8-1 c 7 fd 1 bb 2 bee
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Informes para dispositivos con protocolos móviles

El seguimiento de los dispositivos móviles se realiza mediante una señalización, al igual que ocurre con otros visitantes, por lo que la mayoría de los informes se encuentran disponibles y son correctos.

[!DNL VISTA] se puede utilizar para modificar los datos recopilados tanto por métodos móviles como estándar. Se admiten todos los informes de [!UICONTROL Perspectiva] [!UICONTROL personalizada] ([!UICONTROL prop] y [!UICONTROL eVar]), [!UICONTROL Evento], [!UICONTROL Tráfico del sitio] y [!UICONTROL Rutas].

## Motores de búsqueda, Palabras clave de búsqueda, Dominios de referencia y Referentes {#section_184D2EF9D906443FBDED04A09CDC50E9}

Estos informes solo tienen datos si el referente se rellena en la solicitud de imagen enviada desde la página móvil. El referente se rellena mediante el parámetro de cadena de consulta "r", como se indica en el documento técnico Implementación sin JavaScript. También debe pasar manualmente la información del referente en la solicitud de imagen.

El parámetro de cadena de consulta "r" debe incluir el protocolo del referente. De no hacerlo así, no se rellenará el informe del referente. For example, use `r=https://msn.com` not `r=msn.com`.

## Segmentación geográfica y dominios {#section_2B4E9443AAFE4ECA961F9E993592E628}

Los informes de segmentación geográfica se basan en la dirección IP del dispositivo que envía la solicitud. Debido a que los dispositivos móviles utilizan una puerta de enlace para solicitar imágenes de los servidores de Adobe, se utiliza la dirección IP de la puerta de enlace para determinar la ubicación geográfica del usuario. Debido a que las puertas de enlace y sus direcciones IP se registran para grandes redes, la ubicación geográfica asociada suele ser menos precisa.

Los dominios también se basan en la dirección IP de la puerta de enlace, lo que significa que los informes de dominios suelen contener el nombre del operador de telefonía propietario de la puerta de enlace. Debido a los operadores de redes virtuales móviles (MVNO), es posible que esto no sea preciso.

## Tipos de conexión {#section_0E7FA18178B848AEBB839B1694B4D691}

Adobe mantiene una gama conocida de direcciones IP que pertenecen a operadores de telefonía móvil. Cuando se recibe una visita desde un rango de direcciones IP que pertenece a un operador de telefonía móvil conocido, la visita aparece como "Operador de telefonía móvil" en el informe Tipo de conexión. De lo contrario, el tráfico móvil aparece bajo "LAN/Wifi".

## Zonas horarias, cookies, Java, JavaScript, intensidad del color y resolución del monitor, ancho y alto del explorador y complementos de Netscape {#section_158C848273AE4691B4413767E849E846}

Todos estos informes se recopilan usando JavaScript para detectar configuraciones específicas del explorador Como no se usa JavaScript para crear la señalización de imagen en dispositivos móviles, estos informes no incluyen los datos recopilados de usuarios móviles.

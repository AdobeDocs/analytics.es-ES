---
description: Si los demás métodos de ID de visitante fallan, Adobe configura una cookie de reserva o utiliza una combinación de dirección IP y agente de usuario para identificar al visitante.
keywords: Implementación de Analytics
seo-description: Si los demás métodos de ID de visitante fallan, Adobe configura una cookie de reserva o utiliza una combinación de dirección IP y agente de usuario para identificar al visitante.
seo-title: Métodos de ID de reserva
solution: Analytics
title: Métodos de ID de reserva
topic: Desarrollador e implementación
uuid: f 242 d 481-81 f 0-4287-be 4 f -52 fd 03 eb 01 fc
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Métodos de ID de reserva

Si los demás métodos de ID de visitante fallan, Adobe configura una cookie de reserva o utiliza una combinación de dirección IP y agente de usuario para identificar al visitante.

## Método de identificación de visitantes de reserva {#section_2BA15E4FA6034C3EBF43859406343EB6}

AppMeasurement para JavaScript 1.x y JavaScript H.25.3 (comercializado en enero de 2013) contienen un nuevo método de identificación de visitantes de reserva para aquellos visitantes cuyo explorador bloquea la cookie configurada por los servidores de recopilación de datos de Adobe (denominada `s_vi`). Anteriormente, si no se podía configurar una cookie, los visitantes se identificaban con una combinación de la dirección IP y la cadena del agente de usuario durante la recopilación de datos.

Con esta actualización, si la cookie `s_vi` estándar no está disponible, se crea una cookie de reserva en el dominio del sitio web con una ID única generada aleatoriamente. Esta cookie, denominada `s_fid`, se configura con una caducidad de 2 años y se usa como método de identificación de reserva a partir de ahora. This change should result in increased accuracy in visit and visitor counts in situations where the primary cookie ( `AMCV_` or `s_vi`) cannot be set.

El total de visitas incluye todos los visitantes identificados por la cookie `s_vi` o mediante un método de reserva.

## Dirección IP, agente de usuario y dirección IP de puerta de enlace {#section_104819D74C594ECE879144FCC5DEF4BF}

. If the `AMCV_` or `s_vi` and the `s_fid` cookies cannot be set, visitors are identified using a combination of IP address and User Agent.

---
title: Firmas comunes de bots
description: Reconocer los identificadores comunes de los bots.
translation-type: tm+mt
source-git-commit: 8edfd278fdb4316c304301e5178dc07949127758
workflow-type: tm+mt
source-wordcount: '519'
ht-degree: 0%

---


# Firmas comunes de bots

Aunque la identificación de bots en un conjunto de datos es diferente según el entorno, existen algunas formas comunes de identificar bots.

## Gran número de vistas de página por visita

Puede extraer un informe de Data Warehouse con direcciones IP, vistas de página y visitantes únicos. A continuación, cree un &#x200B; de cálculo &#x200B; en Excel para las vistas de página por visita y ordene de más alto a más bajo. Los bots suelen tener un número muy alto de vistas de página por visita (de varios cientos a miles). Verá una fuerte caída a medida que se mueve al tráfico real real.

## Sin remitente del reenvío

Los bots no suelen tener una dirección URL de referencia. En la segmentación esto se puede filtrar como `Referring Domain equals Typed/Bookmarked`.

## Agentes de usuarios extraños

Los bots suelen utilizar agentes de usuario personalizados que no están clasificados en la dimensión Exploradores ni se muestran como una `unknown` versión de un navegador estándar. Safari desconocido y ópera desconocida tienen una probabilidad extremadamente alta de ser bots.

## Sistemas operativos Linux o &quot;no especificados&quot;

No pretendemos desacreditar el bueno sistema operativo Linux de código abierto, pero aparentemente a los bots les gusta definirlo como su sistema operativo. Sin embargo, tenga cuidado de excluir el tráfico legítimo de los usuarios de Linux. A los bots también les gusta no configurar un sistema operativo, que se puede segmentar como `Operating System &#x200B;equals Not Specified`.

## Vistas de página = Visitas = Visitantes únicos

Esto se aplica especialmente al informe del agente de usuario. Como puede ver en la captura de pantalla de abajo, la &quot;versión desconocida&quot; de estos exploradores tiene casi el mismo número de visitantes que visitantes únicos (y casi el mismo número de vistas de página). Esto se puede aislar en la segmentación mediante la creación de un contenedor [!UICONTROL Incluir] para `Single Page Visits equals Enabled` o `Hit Depth is less than 2`.

![](assets/bots-browsers-unknown.png)

## Número de visita de 1

Los bots generalmente obtienen una nueva ID de visitante cada vez que se ejecutan, lo que implica una sola visita y todo su tráfico consistirá en un número de visita de 1.

## Menor resolución del monitor

Los usuarios modernos tienen monitores de resolución mucho más altos que en años anteriores. Las visitas con las siguientes resoluciones parecen ser muy populares para los bots:

* 1024 x 768&#x200B;&#x200B;
* 1366 x 768
* 1600 x 864
* 800 x 600
* 1600 x 1200
* No especificado
* 1024 x 667

## Distinción entre país y zona horaria

Habrá una discordancia entre el país de origen y el huso horario. Por ejemplo, una ubicación de Estados Unidos pero con una zona horaria GMT.

![](assets/bots-country-time-zone.png)

## No ha iniciado sesión

El usuario no inicia sesión en ningún momento de la visita y las eVars de identificación del usuario no persisten en las visitas anteriores. Aunque algunos bots pueden configurarse para autenticarse, la mayoría no son tan inteligentes.

## No hay KPI en la visita

Los bots normalmente no agregan productos a un carro de compras o a su salida. La mayoría de las veces no envían formularios de posibles clientes u otros eventos de éxito, pero algunos bots envían formularios HTML simples. &#x200B;

## Cadena de consulta específica presente

A veces, los bots intentan cortar la caché o de otro modo romper sitios al visitar direcciones URL o direcciones URL mal formadas que no existen (como las páginas de administración típicas de LAMP o Wordpress) o al anexar cadenas de consulta específicas.

## Direcciones IP que se originan en plataformas informáticas distribuidas

Los servicios de hospedaje web como los servicios web de Amazon o Google Cloud pueden utilizarse como granjas de bots. Estas direcciones IP corren un alto riesgo de convertirse en bots:
&#x200B;
* [Google Cloud](https://cloud.google.com/compute/): INICIOS de direcciones IP con `&#x200B;35.199` o `35.194&#x200B;`

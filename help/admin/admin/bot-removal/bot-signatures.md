---
title: Firmas comunes de bots
description: Reconoce los identificadores comunes de bots.
exl-id: 57622af6-c1d3-4ef1-b3e6-10c14f04a55c
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '521'
ht-degree: 100%

---

# Firmas comunes de bots

Aunque la identificación de bots en un conjunto de datos es diferente en función del entorno, hay algunas formas comunes de identificar bots.

## Número elevado de vistas de página por visita

Puede extraer un informe de Data Warehouse con direcciones IP, vistas de página y visitantes únicos. A continuación, cree un cálculo en Excel para vistas de página por visita y ordene de mayor a menor. Los bots suelen tener un número muy alto de vistas de página por visita (de varios cientos a miles). Verá una gran caída a medida que avanza hacia el tráfico real.

## Sin referente

Los bots no suelen tener una dirección URL de referencia. En la segmentación esto puede filtrarse como `Referring Domain equals Typed/Bookmarked`.

## Agentes de usuario extraños

Los bots suelen utilizar agentes de usuario personalizados que no están clasificados en la dimensión Exploradores ni aparecen como una versión `unknown` de un navegador estándar. Safari desconocido y Opera desconocido tienen una alta probabilidad de ser bots.

## Sistemas operativos Linux o “No especificado”

No pretendemos desacreditar el genial sistema operativo Linux, de código abierto, pero aparentemente a los bots les gusta configurarlo como su sistema operativo. Sin embargo, tenga cuidado de excluir el tráfico legítimo de los usuarios de Linux. A los bots también les gusta no configurar un sistema operativo, que se puede segmentar como `Operating System &#x200B;equals Not Specified`.

## Vistas de página = Visitas = Visitantes únicos

Esto se aplica especialmente al informe de agente de usuario. Como puede ver en la captura de pantalla siguiente, la “versión desconocida” de estos navegadores tiene casi el mismo número de visitantes que visitantes únicos (y casi el mismo número de vistas de página). Esto se puede aislar en la segmentación mediante la creación de un contenedor [!UICONTROL Incluir] para `Single Page Visits equals Enabled` o `Hit Depth is less than 2`.

![](assets/bots-browsers-unknown.png)

## Número de visita de 1

Los bots generalmente obtienen un nuevo ID de visitante cada vez que se ejecutan, por lo que solo realizan una visita cada vez y todo su tráfico consistirá en una visita número 1.

## Resoluciones de monitores más bajas

Los usuarios modernos tienen monitores de resolución mucho más alta que los de años anteriores. Las visitas con las siguientes resoluciones parecen ser muy populares entre los bots:

* 1024 x 768&#x200B;&#x200B;
* 1366 x 768
* 1600 x 864
* 800 x 600
* 1600 x 1200
* Sin especificar
* 1024 x 667

## Desajuste de país y zona horaria

Observaría un desajuste entre el país de origen y la zona horaria. Por ejemplo, la ubicación puede ser Estados Unidos, pero la zona horaria podría ser GMT.

![](assets/bots-country-time-zone.png)

## Sesión no iniciada

El usuario no inicia sesión en ningún momento de su visita y las eVars de identificación del usuario no persisten en las visitas anteriores. Aunque algunos bots se pueden configurar para autenticarse, la mayoría no son tan inteligentes.

## No hay KPI en la visita

Los bots normalmente no añaden productos al carro de compras ni se registran. La mayoría de las veces no envían formularios de posibles clientes u otros eventos de éxito, pero algunos bots envían formularios HTML simples.

## Cadena de consulta específica presente

A veces, los bots intentan cortar la caché o, de otro modo, romper sitios visitando direcciones URL o URL con formato incorrecto que no existen (como las páginas de administración típicas de LAMP o Wordpress) o añadiendo cadenas de consulta específicas.

## Direcciones IP que se originan en plataformas informáticas distribuidas

Se puede abusar de servicios de hosting web como Amazon Web Services o Google Cloud usándolas como granjas de bots. Estas direcciones IP tienen un alto riesgo de ser bots:
&#x200B;
* [Google Cloud](https://cloud.google.com/compute/): La dirección IP empieza por `&#x200B;35.199` o `35.194&#x200B;`

---
description: Ejemplo que contiene una muestra de llamadas al servidor enviadas en una interacción de cliente habitual.
keywords: Analytics Implementation
solution: Analytics
subtopic: Visitors
title: Ejemplo de identificación de visitantes entre dispositivos
topic: Developer and implementation
uuid: bc5f8f56-52e3-42d8-af1a-7f5c7b9496c0
translation-type: tm+mt
source-git-commit: 3e2f0bccbe7183ea75b12b1ef2b5afdd87837629

---


# Ejemplo de identificación de visitantes entre dispositivos

> [!IMPORTANT] Ya no se recomienda este método de identificación de visitantes entre dispositivos. Consulte Análisis [entre dispositivos](/help/components/cda/cda-home.md) en la guía del usuario Componentes.

El siguiente ejemplo ilustra el funcionamiento de la identificación de visitantes entre dispositivos mediante una muestra de llamadas al servidor enviadas en una interacción común de clientes.

| Llamada al servidor | Acción | Cookie de ID de visitante | Variable de ID de visitante | ID de visitante efectiva | Número de página de visita | Número de visita |
|--- |--- |--- |--- |--- |--- |--- |
| 1 | Un visitante hace clic en un vínculo de un correo electrónico de marketing y visita su sitio desde el equipo de casa. Este visitante ha visitado su sitio 7 veces más en el pasado. | 1 | - | 1 | 1 | 8 |
| 2-8 | Visita otras 7 páginas del sitio. | 1 | - | 1 | 2-8 | 8 |
| 9 | Se autentica en el equipo de casa. | 1 | CID1 | CID1 | 9 <br>(This is CID1's first hit ever, so it takes over and continues on the visitor profile from Visitor ID 1.) | 8 |
| 10 | Visita 1 página adicional. | 1 | CID1 | CID1 | 10 | 8 |
| 11 | Abre el sitio desde el ordenador portátil de la oficina. El visitante no ha visitado el sitio antes de utilizar este servicio. | 2 | - | 2 | 1 | 1 |
| 12 | Se autentica en el ordenador portátil. | 2 | CID1 | CID1 | 1 | 9 |
| 13 | Ve 1 página adicional. | 2 | CID1 | CID1 | 2 | 9 |

## Recuento de visitas

Analytics cuenta una visita cada vez que ve una visita individual con un número de página de visita igual a 1.

Con la tabla anterior, se contabilizó una nueva visita 4 veces: en las visitas individuales 1, 9, 11 y 12.

## Recuento de visitantes

Analytics contabiliza cada ID de visitante efectiva única como un visitante único.

Con la tabla anterior, se contabilizó un visitante nuevo tres veces: en las visitas individuales 1, 9 y 10.

Cuando utiliza la identificación de visitantes entre dispositivos, puede aumentar el número de visitantes únicos que ve. El visitante se puede contar dos veces en la misma visita: una vez para la visita inicial y otra vez después de autenticar al usuario.

![](assets/visitors.png)

Después de la asociación inicial, los recuentos de visitas vuelven a la normalidad porque el visitante está asociado a través de la cookie del explorador. Si más adelante el visitante ve el sitio y después se autentica, el recuento de visitantes no aumenta porque la ID de visitante efectiva no cambia después de la autenticación.

![](assets/visitors_2.png)

Asegúrese de que es lo más coherente posible al identificar visitantes únicos. Por ejemplo, utilice siempre la `visitorID` variable cuando el usuario esté autenticado.

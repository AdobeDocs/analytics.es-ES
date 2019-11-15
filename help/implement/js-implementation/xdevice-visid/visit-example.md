---
description: Ejemplo que contiene una muestra de llamadas al servidor enviadas en una interacción de cliente habitual.
keywords: Analytics Implementation
solution: Analytics
subtopic: Visitors
title: Visita de ejemplo
topic: Developer and implementation
uuid: bc5f8f56-52e3-42d8-af1a-7f5c7b9496c0
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Visita de ejemplo

>[!IMPORTANT]
>
>Ya no se recomienda este método de identificación de visitantes entre dispositivos. Consulte la documentación [de cooperación entre dispositivos de](https://marketing.adobe.com/resources/help/en_US/mcdc/)Adobe Experience Cloud.

Ejemplo que contiene una muestra de llamadas al servidor enviadas en una interacción de cliente habitual.

| Llamada al servidor | Acción | Cookie de ID de visitante | Variable de ID de visitante | ID de visitante efectiva | Número de página de visita | Número de visita |
|--- |--- |--- |--- |--- |--- |--- |
| 1 | Un visitante hace clic en un vínculo de un correo electrónico de marketing y visita su sitio desde el equipo de casa. Este visitante ha visitado su sitio 7 veces más en el pasado. | 1 | - | 1 | 1 | 8 |
| 2-8 | Visita otras 7 páginas del sitio. | 1 | - | 1 | 2-8 | 8 |
| 9 | Se autentica en el equipo de casa. | 1 | CID1 | CID1 | 9 <br>Esta es la primera visita de CID1, de modo que se continúa en el perfil del visitante desde el ID de visitante 1.</br> | 8 |
| 10 | Visita 1 página adicional. | 1 | CID1 | CID1 | 10 | 8 |
| 11 | Abre el sitio desde el ordenador portátil de la oficina. El visitante no ha visitado el sitio antes de utilizar este servicio. | 2 | - | 2 | 1 | 1 |
| 12 | Se autentica en el ordenador portátil. | 2 | CID1 | CID1 | 1 | 9 |
| 13 | Ve 1 página adicional. | 2 | CID1 | CID1 | 2 | 9 |

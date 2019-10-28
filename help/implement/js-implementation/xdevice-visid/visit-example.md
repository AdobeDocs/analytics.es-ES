---
description: Ejemplo que contiene una muestra de llamadas al servidor enviadas en una interacción de cliente habitual.
keywords: Implementación de Analytics
seo-description: Ejemplo que contiene una muestra de llamadas al servidor enviadas en una interacción de cliente habitual.
seo-title: Visita de ejemplo
solution: Analytics
subtopic: Visitantes
title: Visita de ejemplo
topic: Desarrollador e implementación
uuid: bc5f8f56-52e3-42d8-af1a-7f5c7b9496c0
translation-type: ht
source-git-commit: 67cc404c4502b1b7be3f089538d8a28d5cf7f659

---


# Visita de ejemplo

>[!IMPORTANT]
>
>Ya no se recomienda este método de identificación de visitantes entre dispositivos. Consulte [Documentación de Adobe Experience Cloud Device Co-op](https://marketing.adobe.com/resources/help/es_ES/mcdc/).

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
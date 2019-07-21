---
description: Los servicios de envío de contenido o las redes de distribución de contenido (CDN), como Akamai y Speedera, llevan el contenido más cerca del límite de la red y mantienen los documentos que se solicitan con más frecuencia cerca del lugar desde el que se accede a ellos.
keywords: Implementación de Analytics
seo-description: Los servicios de envío de contenido o las redes de distribución de contenido (CDN), como Akamai y Speedera, llevan el contenido más cerca del límite de la red y mantienen los documentos que se solicitan con más frecuencia cerca del lugar desde el que se accede a ellos.
seo-title: Redes y servicios de envío de contenido
solution: Analytics
subtopic: Resolución de problemas
title: Redes y servicios de envío de contenido
topic: Desarrollador e implementación
uuid: 6 cb 57 c 59-d 0 f 9-4 ca 5-9 f 15-0 e 74 e 585 a 4 a 1
translation-type: tm+mt
source-git-commit: 6250335d05c8e7799802fce26192896a7a6598fe

---


# Redes y servicios de envío de contenido

Los servicios de envío de contenido o las redes de distribución de contenido (CDN), como Akamai y Speedera, llevan el contenido más cerca del límite de la red y mantienen los documentos que se solicitan con más frecuencia cerca del lugar desde el que se accede a ellos.

Generalmente, esto reduce la latencia del acceso, el uso del ancho de banda y el coste de la infraestructura.

El archivo de biblioteca de AppMeasurement para JavaScript se puede enviar mediante una CDN para mejorar el rendimiento y el envío del archivo al visitante del sitio. Los clientes de Adobe deben asegurarse de que sus servicios de CDN están correctamente configurados. Las CDN suelen ser un motivo habitual de fluctuaciones en los tiempos de descarga y se deben considerar la causa más probable de los cambios en los tiempos de descarga.

El administrador de etiquetas almacena todo el JavaScript en una CDN.

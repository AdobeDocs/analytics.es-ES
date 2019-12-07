---
description: Colocar la llamada al archivo de biblioteca JavaScript en la parte superior de la página garantiza que la imagen estará entre los primeros elementos que se descarguen.
keywords: Analytics Implementation
subtopic: Troubleshooting
title: Ubicación y simultaneidad del archivo JavaScript
topic: Developer and implementation
uuid: ed5118a8-b142-4fab-8aa1-92d931cc1439
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Ubicación y simultaneidad del archivo JavaScript

Colocar la llamada al archivo de biblioteca JavaScript en la parte superior de la página garantiza que la imagen estará entre los primeros elementos que se descarguen.

La mayoría de los exploradores web descargan las imágenes de forma simultánea. Normalmente se pueden descargar de tres a cuatro imágenes simultáneamente.

Debido a que la mayoría de los exploradores web descargan los elementos de forma simultánea, la barra de estado de muchos exploradores (incluido Internet Explorer) no refleja exactamente qué elemento está intentando cargar el explorador. Por ejemplo, la barra de estado puede notificar que el explorador está esperando para descargar la imagen 1. Las pruebas de paquetes de red muestran que el explorador ya ha recibido la imagen 1 y que está esperando la imagen 2.

> [!NOTE] Debido a que los proveedores de auditoría de rendimiento de Internet de terceros (como Keynote Systems) descargan los elementos de imagen de página secuencialmente, no imitan la experiencia del usuario típica.


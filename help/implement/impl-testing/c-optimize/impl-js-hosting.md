---
description: Colocar la llamada al archivo de biblioteca JavaScript en la parte superior de la página garantiza que la imagen estará entre los primeros elementos que se descarguen.
keywords: Implementación de Analytics
seo-description: Colocar la llamada al archivo de biblioteca JavaScript en la parte superior de la página garantiza que la imagen estará entre los primeros elementos que se descarguen.
seo-title: Ubicación y simultaneidad del archivo JavaScript
solution: Analytics
subtopic: Resolución de problemas
title: Ubicación y simultaneidad del archivo JavaScript
topic: Desarrollador e implementación
uuid: ed5118a8-b142-4fab-8aa1-92d931cc1439
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Ubicación y simultaneidad del archivo JavaScript

Colocar la llamada al archivo de biblioteca JavaScript en la parte superior de la página garantiza que la imagen estará entre los primeros elementos que se descarguen.

La mayoría de los exploradores web descargan las imágenes de forma simultánea. Normalmente se pueden descargar de tres a cuatro imágenes simultáneamente.

Debido a que la mayoría de los exploradores web descargan los elementos de forma simultánea, la barra de estado de muchos exploradores (incluido Internet Explorer) no refleja exactamente qué elemento está intentando cargar el explorador. Por ejemplo, la barra de estado puede notificar que el explorador está esperando para descargar la imagen 1. Las pruebas de paquetes de red muestran que el explorador ya ha recibido la imagen 1 y que está esperando la imagen 2.

> [!NOTE] Debido a que los proveedores de auditoría de rendimiento de Internet de terceros (como Keynote Systems) descargan los elementos de imagen de página secuencialmente, no imitan la experiencia del usuario típica.

